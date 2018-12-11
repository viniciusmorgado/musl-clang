# musl-clang for Fedora 29

A clang wrapper for musl C library.

Observation: This is a fork of esjeon/musl-clang tested and modify for Fedora 29 - Last update 11/12/2018.

Tested under Fedora linux 29 with bash shell.

## Installation on Fedora 29

### Install Clang/LLVM:

For use the musl-clang we need llvm/clang install on Fedora, therefore:

```
sudo dnf install clang llvm
```

### Install musl libc

Fedora does not have the musl package by default in its repositories, I've chosen to compile the musl from the source code and not use "alternate" repositories for security reasons.

```
sudo dnf install git

git clone git://git.musl-libc.org/musl

./configure

sudo make install clean
```

And finally the wrapper clang script:

```
git clone https://github.com/viniciusmorgado/musl-clang

cd /musl-clang

sudo mv musl-clang /usr/local/musl/bin/
```

### Creating a symbolic link that can be accessed from any system directory.

```
sudo ln -s /usr/local/musl/bin/./musl-clang

sudo ln -s /usr/local/musl/bin/./musl-gcc

```
Now you can use musl-clang and musl-gcc for compile C software with GCC and LLVM compiler on Fedora.

## Using script:

### Sintaxe Clang/LLVM+musl:

Compiling software in C with Clang/LLVM+Musl:

```
musl-clang -o <binary-name> <source.c>

  example: musl-clang -o HelloWorld main.c
```

### Sintaxe gcc+musl

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
