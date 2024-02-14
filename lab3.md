# Lab Report 3
## Part 1
---

This is the failure-inducing JUnit test:
```
import org.junit.Rule;
import org.junit.Test;
import org.junit.rules.TemporaryFolder;
import java.io.File;
import java.io.IOException;
import java.util.List;
import static org.junit.Assert.assertEquals;

@Rule
    public TemporaryFolder tempFolder = new TemporaryFolder();

@Test
    public void testGetFilesWithDirectoryInput() throws IOException {
        // Creates temporary directory structure
        File directory = tempFolder.newFolder("some-files");
        File moreFiles = tempFolder.newFolder("some-files", "more-files");
        File evenMoreFiles = tempFolder.newFolder("some-files", "even-more-files");

        File aTxt = tempFolder.newFile("some-files/a.txt");
        File bTxt = tempFolder.newFile("some-files/more-files/b.txt");
        File cJava = tempFolder.newFile("some-files/more-files/c.java");
        File dJava = tempFolder.newFile("some-files/even-more-files/d.java");

        List<File> result = FileExample.getFiles(directory);
        assertEquals(7, result.size()); // Expects all files in the directory and its subdirectories
    }
```

This is the JUnit test that passes:
```
import org.junit.Rule;
import org.junit.Test;
import org.junit.rules.TemporaryFolder;
import java.io.File;
import java.io.IOException;
import java.util.List;
import static org.junit.Assert.assertEquals;

@Rule
    public TemporaryFolder tempFolder = new TemporaryFolder();

@Test
    public void testGetFilesWithFileInput() throws IOException {
        // Creates temporary directory structure
        File directory = tempFolder.newFolder("some-files");

        File aTxt = tempFolder.newFile("some-files/a.txt");

        List<File> result = FileExample.getFiles(aTxt); // Passes aTxt as input
        assertEquals(1, result.size()); // Expects only the input file
    }
```

Screenshots of the outputs from running the tests:

Failed-![Image](Lab 3 Failed Test Output.PNG)


Passed-![Image](Lab 3 Sucess Output.PNG)

The bug I chose from week 4's lab is from FileExample.java which is below

---
```
import java.io.File;
import java.io.IOException;
import java.util.ArrayList;
import java.util.List;

public class FileExample {

	static List<File> getFiles(File start) throws IOException {
	  File f = start;
	  List<File> result = new ArrayList<>();
	  result.add(start);
	  if(f.isDirectory()) {
	    File[] paths = f.listFiles();
	    for(File subFile: paths) {
	      result.add(subFile);
	    }
	  }
	  return result;
	}
}
```
The issue here is that it only adds the starting directory to the list and then adds all the files. This results in duplicate entries and an incorrect count when running tests.

This is the after code below
```
import java.io.File;
import java.io.IOException;
import java.util.ArrayList;
import java.util.List;

public class FileExample {

    static List<File> getFiles(File start) throws IOException {
        List<File> result = new ArrayList<>();
        collectFiles(start, result);
        return result;
    }

    private static void collectFiles(File directory, List<File> fileList) {
        fileList.add(directory); // Adds the directory itself to the list
        File[] files = directory.listFiles();
        if (files != null) {
            for (File file : files) {
                if (file.isDirectory()) {
                    collectFiles(file, fileList);
                } else {
                    fileList.add(file);
                }
            }
        }
    }
}
```

