# Command: cd
**No argument**
```
shlim@Abi_HP_Laptop MINGW64
$ cd

```
- Absolute path to working directory right before: `/c/Users/shlim`
- Reason for output: The command `cd` is used to switch the current working directory to the given path, but since there was no argument given it defaults to switching the current working directory back to the home directory. Since the working directory right before the command was given was already the home directory then it stays in the same directory. This is not an error.

**Path to directory as argument**
```
shlim@Abi_HP_Laptop MINGW64 ~
$ cd lecture1

shlim@Abi_HP_Laptop MINGW64 ~/lecture1 (main)
$
```

- Absolute path to working directory right before: `/c/Users/shlim`
- Reason for output: `cd lecture1` switches the current working directory (which is the home directory) to the given path (which is lecture1) so the working directory becomes `/c/Users/shlim/lecture1`. This is not an error.

**Path to file as argument**
```
shlim@Abi_HP_Laptop MINGW64 ~/lecture1 (main)
$ cd Hello.java
bash: cd: Hello.java: Not a directory

```
- Absolute path to working directory right before: `/c/Users/shlim/lecture1`
- Reason for output: An error message is displayed that states that `Hello.java` is not a directory. `Hello.java` is a file and not a directory and since `cd` can only take a directory as an argument (because `cd` is used to switch the current working directory to the given path) and a working directory can't be a file, it produces an error.

# Command: ls
**No argument**
```
shlim@Abi_HP_Laptop MINGW64 ~/lecture1 (main)
$ ls
Hello.class  Hello.java  messages/  README

```
- Absolute path to working directory right before: `/c/Users/shlim/lecture1`
- Reason for output: When no argument is given to `ls` it defaults to display the files and folders in the current working directory, which is `lecture1`. `Hello.class`, `Hello.java`, `messages/`, and `README` are all of the files and folders in `lecture1`, so this is not an error.

**Path to directory as argument**
```
shlim@Abi_HP_Laptop MINGW64 ~/lecture1 (main)
$ ls lecture1
ls: cannot access 'lecture1': No such file or directory

```
- Absolute path to working directory right before: `/c/Users/shlim/lecture1`
- Reason for output: `lecture1` is a relative path, and since `lecture1` doesn't exist in `/c/Users/shlim/lecture1` which is the working directory `ls lecture1` produces an error. This is an error caused by being in the wrong working directory. If I was in the home directory, where `lecture1` is located then the files and folders located in `lecture1` would have been displayed.

**Path to file as argument**
```
shlim@Abi_HP_Laptop MINGW64 ~/lecture1 (main)
$ ls Hello.java
Hello.java

```
- Absolute path to working directory right before: `/c/Users/shlim/lecture1`
- Reason for output: `Hello.java` exists in `/c/Users/shlim/lecture1` which is the current working directory so `ls Hello.java` displays the file name of the file given as an argument. This is not an error.

# Command: cat
**No argument**
```
shlim@Abi_HP_Laptop MINGW64 ~/lecture1 (main)
$ cat

```
- Absolute path to working directory right before: `/c/Users/shlim/lecture1`
- Reason for output: The command doesn't finish and runs an infinite loop. This is an error because `cat` is used to print the contents of a file and since no argument is given, the command doesn't complete.

**Path to directory as argument**
```
shlim@Abi_HP_Laptop MINGW64 ~
$ cat lecture1
cat: lecture1: Is a directory

```
- Absolute path to working directory right before: `/c/Users/shlim`
- Reason for output: `cat` is used to print the contents of a file and since the argument given, `lecture1`, is not a file but a directory, an error message is displayed stating that `lecture1` is a directory. This is an error produced by the fact that the given argument is not a file that the command can print the contents of.

**Path to file as argument**
```
shlim@Abi_HP_Laptop MINGW64 ~/lecture1 (main)
$ cat Hello.java
import java.io.IOException;
import java.nio.charset.StandardCharsets;
import java.nio.file.Files;
import java.nio.file.Path;

public class Hello {
  public static void main(String[] args) throws IOException {
    String content = Files.readString(Path.of(args[0]), StandardCharsets.UTF_8);
    System.out.println(content);
  }
}
```
- Absolute path to working directory right before: `/c/Users/shlim/lecture1`
- Reason for output: `cat` printed out the contents of `Hello.java`. This is not an error, because `cat` is supposed to print the contents of the file given by the path.


