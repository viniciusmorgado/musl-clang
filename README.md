musl-clang for Fedora 29

Observation: This is a fork of esjeon/musl-clang tested and modify for Fedora 29 - Last update 11/12/2018.

Tested under Fedora linux with bash shell.

Installation on Fedora 29

Install Clang/LLVM on Fedora 29:

  sudo dnf install clang llvm

Install musl libc on Fedora:

  sudo dnf install git
  
  git clone git://git.musl-libc.org/musl
  
  ./configure
  
  sudo make install clean
  
Install musl-clang Wrapper:

  git clone https://github.com/viniciusmorgado/musl-clang
  cd /musl-clang
  sudo mv musl-clang /usr/local/musl/bin/
  
Creating a symbolic link that can be accessed from any system directory.

  sudo ln -s /usr/local/musl/bin/./musl-clang
  sudo ln -s /usr/local/musl/bin/./musl-gcc
 
Now you can use musl-clang and musl-gcc for compile C software with GCC and LLVM compiler on Fedora.

Sintaxe:

For compile with musl+LLVM/Clang

  musl-clang -o <binary-name> <source.c>

    example: musl-clang -o HelloWorld main.c
  
For compile with musl+gcc

  musl-gcc -o <binary-name> <source.c>

    example: musl-gcc -o HelloWorld main.c
  
License
-------
Distributed under MIT/X Consortium License. See the script for more details.
