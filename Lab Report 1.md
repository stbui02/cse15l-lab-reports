# Lab Report 1

**Examples for each of the commands `cd`, `ls`, and `cat`**

**For `cd`**
---
1. When using the command with no argument when in the ~/home directory does nothing, but if in "lecture1" cd brings us back to ~/home.
```
[user@sahara ~]$ cd
[user@sahara ~]$
```
```
[user@sahara ~/lecture1]$ cd
[user@sahara ~]$
```
2. `cd lecture1` brings us into the lecture1 folder.
```
[user@sahara ~]$ cd lecture1/
[user@sahara ~/lecture1]$
```
3. When using the command with a file as an argument, in this case a txt file, the command will return "Not a directory".
```
[user@sahara ~/lecture1]$ cd Hello.java 
bash: cd: Hello.java: Not a directory
[user@sahara ~/lecture1]$
```

**For `ls`**
---
1. Using the `ls` command in the ~/home directory lists the folders in the workspace.
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
3. `ls README` just prints "README", the name of the file, in the terminal.
```
[user@sahara ~/lecture1]$ ls README 
README
[user@sahara ~/lecture1]$
```

**For `cat`**
---
