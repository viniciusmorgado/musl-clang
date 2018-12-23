# musl-clang wrapper script for Fedora 29

A clang wrapper for musl C library.

This is a equivalent to musl-gcc wrapper script, Included in official musl package, however this unofficial version is for compile software using musl+LLVM/Clang, I considere this a best combination for compile C/C++ software especially for embedded devices.

Considerations:

º This is a fork of esjeon/musl-clang tested and modify for Fedora 29 - Last update 13/12/2018.

º Tested under Fedora linux 29 with bash shell (KDE Plasma Spin, Gnome3/Workstation and Fedora LXQt Spin).

° If you are a user of Solus OS, please check out this most complete tutorial in the official forum: https://getsol.us/forums/viewtopic.php?f=11&t=13121

## Installation on Fedora 29

### Install Clang/LLVM:

For use the musl-clang we need llvm/clang and make installed on Fedora, therefore:

```
sudo dnf install clang llvm make
```

### Install musl libc

Fedora does not have the musl package by default in its repositories, I've chosen to compile the musl from the source code and not use "alternate" repositories for security reasons.

```
sudo dnf install git
```
```
git clone git://git.musl-libc.org/musl
```
```
cd musl
```
```
./configure
```
```
sudo make install clean
```

And finally the wrapper clang script:

```
git clone https://github.com/viniciusmorgado/musl-clang
```
```
cd musl-clang
```
```
sudo mv musl-clang /usr/local/musl/bin/
```

### Creating a symbolic link that can be accessed from any system directory.
```
cd /usr/bin
```
```
sudo ln -s /usr/local/musl/bin/./musl-clang
```
```
sudo ln -s /usr/local/musl/bin/./musl-gcc
```
Now you can use musl-clang and musl-gcc for compile C software with GCC and LLVM compiler on Fedora.

## Using script:

### Syntax Clang/LLVM+musl:

Compiling software in C with Clang/LLVM+Musl:

```
musl-clang -o <binary-name> <source.c>

  example: musl-clang -o HelloWorld main.c
```

### Syntax GCC+musl

Compiling software in C with GCC+musl:

```
musl-gcc -o <binary-name> <source.c>

  example: musl-gcc -o HelloWorld main.c
```

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details.

The Installation tutorial is licensed under CC BY License - see the [LICENSE.md](LICENSE.md) file for details.

## Acknowledgments

* Eon S. Jeon - https://github.com/esjeon
