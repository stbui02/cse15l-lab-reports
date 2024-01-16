# Lab Report 1

**Examples for each of the commands `cd`, `ls`, and `cat`**

**For `cd`**
---
1. When using the command with no argument when in the ~/home directory does nothing as cd alone takes you to your ~/home directory, so when if in "lecture1" cd brings us back to ~/home.
```
[user@sahara ~]$ cd
[user@sahara ~]$
```
```
[user@sahara ~/lecture1]$ cd
[user@sahara ~]$
```
2. `cd lecture1` changes the directory to the "lecture1" folder.
```
[user@sahara ~]$ cd lecture1/
[user@sahara ~/lecture1]$
```
3. When using the command with a file as an argument, in this case a txt file, the command will return "Not a directory". Since the command expects a directory as an argument inputting a file results in an error.
```
[user@sahara ~/lecture1]$ cd Hello.java 
bash: cd: Hello.java: Not a directory
[user@sahara ~/lecture1]$
```

**For `ls`**
---
1. Using the `ls` command with no argument when in the ~/home directory lists the folders in the current workspace.
```
[user@sahara ~]$ ls
lecture1
[user@sahara ~]$
```
2. `ls lecture1/` lists the folders/files inside lecture1 without moving into the directory.
```
[user@sahara ~]$ ls lecture1/
Hello.class  Hello.java  messages  README
[user@sahara ~]$
```
3. `ls README` prints "README", the name of the file, in the terminal.
```
[user@sahara ~/lecture1]$ ls README 
README
[user@sahara ~/lecture1]$
```

**For `cat`**
---
1. Using the `cat` command with no argument when in the ~/home directory the prompt terminal moves to the next line and waits for user input. Any text typed here will be repeated and displayed.
```
[user@sahara ~]$ cat
[]  //waits for another input and repeats when an input is typed in
```
Example of the looping:
```
[user@sahara ~]$ cat
ls  //this line is the user input
ls  //this line is the repeated text
[]  //waits for another input and will repeat whatever is typed into the terminal
```
2. The `cat` command expects files as an argument and will result in an error if used with a directory.
```
[user@sahara ~]$ cat lecture1/
cat: lecture1/: Is a directory
[user@sahara ~]$
```
3. `cat en-us.txt` in the path /lecture1/messages/ prints the text within the file.
```
[user@sahara ~/lecture1/messages]$ cat en-us.txt 
Hello World!
[user@sahara ~/lecture1/messages]$
```




