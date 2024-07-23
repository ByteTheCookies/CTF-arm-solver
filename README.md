# CTF-arm-solver
This repository aim to give a solution for all the tools that are not naive supported for arm chipsets

## Step 1

### Linux

Skip to step 2

### Macos & Windows

Setup a linux VM

## Step 2

Install the dependencies

```
sudo apt install make
sudo apt install gcc
sudo apt install g++
sudo apt install libglib2.0-dev
sudo apt install libpixman-1-dev
sudo apt install libfdt-dev
sudo apt install python3.12
git clone https://github.com/ninja-build/ninja.git
cd ninja
./configure.py --bootstrap
sudo apt install gcc-x86-64-linux-gnu
```
## Step 3

Install qemu

```
git clone https://github.com/qemu/qemu.git
cd qemu
mkdir build
cd build
../configure --target-list=x86_64-softmmu,x86_64-linux-user
make
```

## Step 4

Install gdb & pwndbg & pwntools

```
sudo apt install gdb
sudo apt install gdb-multiarch
git clone https://github.com/pwndbg/pwndbg
cd pwndbg
./setup.sh
sudo pip3 install pwntools
```

## How to debug

### 1st terminal

`qemu-x86_64 -L /usr/x86_64-linux-gnu/ -g 12345 /path/to/executable`

### 2nd terminal

```
gdb-multiarch
set arch i386:x86-64
target remote 127.0.0.1:12345
```
