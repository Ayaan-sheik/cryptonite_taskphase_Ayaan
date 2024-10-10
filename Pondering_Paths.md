# Pondering Paths

## The root

root directory is the directory under which everything is present. an absolute path is the path which starts from the directory that is 

`/pwn`

which is used in this challenge to invoke pwn program to get the flag

## Program and absolute paths

In this challenge they want us to run the program run which is in challenge directory to get the flag.

- command used:
    - `/challenge

## Position Thy self

In this challenge they teach about cd command which basically refers to change directory it changes the directory to argument that is passed. 

- commands used:
    - `/challenge/run`
    - it gives us the path to cd into ie./usr/share/build-essential
    - `cd /usr/share/build-essential`
    - `/challenge/run`

## Position elsewhere

This challenge teaches us that before the $ sign is the directory address of which we are in currently

- commands used:
    - `/challenge/run`
    - it gives us the path to cd into ie./usr/share/doc
    - `cd /usr/share/doc`
    - `/challenge/run`

## position yet elsewhere

similar challenge to previous two ones

- commands used:
    - `/challenge/run`
    - it gives us the path to cd into ie./home
    - `cd /home`
    - `/challenge/run`

## implicit relative paths, from

relative paths this teaches us if we are in /tmp/a/b/c then the relative path to the file is ../myfile . in the challenge we need to find a relative path to /challenge/run while / be the working directory 

- commands used:
    - cd /
    - challenge/run
- flag : pwn.college{42SntdHlGT8QNz3JSclYET6twKP.dlDN1QDL4QDO1czW}

## explicit relative paths, from

- commands used:
    - cd /
    - ./challenge/run
- flag: pwn.college{cPuHntkBzYKnXQLsuRCgJ6rEHWZ.dBTN1QDL4QDO1czW}

## implicit relative path

in linux a naked path wont run the command in the directory as a safety measure so we need to use .

- commands used:
    - cd /challenge
    - ./run
- flag : pwn.college{Eixbx_QMl8wEGX70VqvYw-4Jpmx.dFTN1QDL4QDO1czW}

## Home Sweet Home

in this challenge we need to write a path as an argument in less than 3 characters to complete the challenge. we learn in this topic that ~ is the adress of the current working directory 

- commands used:
    - /challenge/run ~ / ~
- flag: pwn.college{Ygq6APd2YpzXkHCa4mBjc7l0Xph.dNzM4QDL4QDO1czW}
