# Lab 1

## **`cd` Command**
**No arguments**
```
[user@sahara ~/lecture1]$ cd
[user@sahara ~]$ 
```

Working Directory: `/home/lecture1` 

Explanation: No argument was given and the working directory changed from `/home/lecture1` to `/home`. There was no error.

Another Example:
```
[user@sahara ~/lecture1/messages]$ cd
[user@sahara ~]$ 
```

Working Directory: `/home/lecture1/messages`

Explanation: No argument was given and the working directory changed from `/home/lecture1/messages` to `/home`. 

**Directory as argument**
```
[user@sahara ~]$ cd lecture1/
[user@sahara ~/lecture1]$ 
```

Working Directory: `/home`

Explanation: `lecture1/` was given as an argument so the working directory changed to `/home/lecture1` after the command was run. There was no error


**File as argument**
```
[user@sahara ~/lecture1]$ cd Hello.java
bash: cd: Hello.java: Not a directory
```

Working Directory: `/home/lecture1`

Explanation: The `cd` command requires a directory as an argument but since `Hello.java` is a file (not a directory) an error message was output.


## **`ls` Command**
**No arguments**
```
[user@sahara ~/lecture1]$ ls
Hello.class  Hello.java  messages  README
```

Working Directory: `/home/lecture1`

Explanation: The `ls` command outputs a list of the files/directories under the current directory when no arguments are given. There was no error message.


**Directory as argument**
```
[user@sahara ~/lecture1]$ ls messages/
en-us.txt  es-mx.txt  fr.txt  zh-cn.txt
```

Working Directory: `/home/lecture1`

Explanation: In this case, a directory was given as an argument to the `ls` command. This outputs the files/directories under the given directory. There was no error message.


**File as argument**
```
[user@sahara ~/lecture1]$ ls Hello.java
Hello.java
```

Working Directory: `/home/lecture1`

Explanation: This time, a file was given as the argument. The `ls` command printed the given file name. There was not error message.


## **`cat` Command**
**No arguments**
```
[user@sahara ~/lecture1]$ cat
pwd
pwd
ls
ls
^C
[user@sahara ~/lecture1]$ 
```

Working Directory: `/home/lecture1`

Explanation: When no argument is passed to the `cat` command, it doesn't run anything and the terminal keeps going on and on. Whenever I input any other commands, the command is just re-printed to the console. This is not an error because the `cat` command does what it is supposed to do when no arguments are given.


**Directory as argument**
```
[user@sahara ~/lecture1]$ cat messages/
cat: messages/: Is a directory
```

Working Directory: `/home/lecture1`

Explanation: When a directory is given a an argument, the `cat` command outputs an error message that clarifies that the argument given is a directory.


**File as argument**
```
[user@sahara ~/lecture1]$ cat Hello.java
import java.io.IOException;
import java.nio.charset.StandardCharsets;
import java.nio.file.Files;
import java.nio.file.Path;

public class Hello {
  public static void main(String[] args) throws IOException {
    String content = Files.readString(Path.of(args[0]), StandardCharsets.UTF_8);    
    System.out.println(content);
  }
```

Working Directory: `/home/lecture1`

Explanation: When there is a file given as an argument to the `cat` command, the contents of that file is printed. There was no error.
