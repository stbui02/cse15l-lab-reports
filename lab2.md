# Lab Report 2

**Part 1**
---
This is the screenshot of my code.
```
[user@sahara ~]$ cd
[user@sahara ~]$
```
```
[user@sahara ~/lecture1]$ cd
[user@sahara ~]$
```
2. `cd lecture1` while in the `/home directory changes the directory to the "lecture1" folder. This case is not an error.
```
[user@sahara ~]$ cd lecture1/
[user@sahara ~/lecture1]$
```
3. When using the command with a file as an argument, in this case a txt file, the command will return "Not a directory". Since the command expects a directory as an argument inputting a file results in an error. This command is used in the "lecture1" directory. This is an error.
```
[user@sahara ~/lecture1]$ cd Hello.java 
bash: cd: Hello.java: Not a directory
[user@sahara ~/lecture1]$
```
