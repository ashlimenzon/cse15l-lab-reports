# Command: cd
**No argument**
```
shlim@Abi_HP_Laptop MINGW64
$ cd

```
**Path to directory as argument**
```
shlim@Abi_HP_Laptop MINGW64 ~
$ cd lecture1

shlim@Abi_HP_Laptop MINGW64 ~/lecture1 (main)
$
```
**Path to file as argument**
```
shlim@Abi_HP_Laptop MINGW64 ~/lecture1 (main)
$ cd Hello.java
bash: cd: Hello.java: Not a directory

```

# Command: ls
**No argument**
```
shlim@Abi_HP_Laptop MINGW64 ~/lecture1 (main)
$ ls
Hello.class  Hello.java  messages/  README

```
**Path to directory as argument**
```
shlim@Abi_HP_Laptop MINGW64 ~/lecture1 (main)
$ ls lecture1
ls: cannot access 'lecture1': No such file or directory

```
**Path to file as argument**
```
shlim@Abi_HP_Laptop MINGW64 ~/lecture1 (main)
$ ls Hello.java
Hello.java

```
# Command: cat
**No argument**
```
shlim@Abi_HP_Laptop MINGW64 ~/lecture1 (main)
$ cat

```
**Path to directory as argument**
```
shlim@Abi_HP_Laptop MINGW64 ~/lecture1 (main)
$ cat lecture1
cat: lecture1: No such file or directory

```
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


