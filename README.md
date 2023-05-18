# Family with fasta, Conda yaml file and Singularity image

## 1.Basic writing and formatting syntax in README file
https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax
## 2. How to install packages from yaml file in conda?
https://stacktuts.com/how-to-install-packages-from-yaml-file-in-conda
## 3. Install Anvaconda on Linux
Include the bash command regardless of whether or not you are using the Bash shell

https://docs.anaconda.com/free/anaconda/install/linux/
## 4. Why does "(base)" appear in front of my terminal prompt?
https://askubuntu.com/questions/1026383/why-does-base-appear-in-front-of-my-terminal-prompt

This can also be because auto_activate_base is set to True. You can check this using the following command
```
conda config --show | grep auto_activate_base
```
To set it false
```
conda config --set auto_activate_base False
source ~/.bashrc
```
To reactivate set it to True
```
conda config --set auto_activate_base True
source ~/.bashrc
```

## 5. Singularity tutorial video
https://www.youtube.com/watch?v=_KhbwXqk0Bk&t=521s
## 6. Singularity guide website
https://sylabs.io/

## 7. Install Singularity-ce & quick guide
Firstly: install C, Golang language
https://docs.sylabs.io/guides/latest/user-guide/quick_start.html#

## 8. Fix: Could not connect to archive.ubuntu.com:80 (185.125.190.39)
https://askubuntu.com/questions/1198621/apt-get-cannot-connect-to-ubuntu-archives

https://askubuntu.com/questions/249203/what-does-sudo-echo-nameserver-8-8-8-8-etc-resolv-conf-do

```
$ echo nameserver 8.8.8.8 > /etc/resolv.conf
```

## 9. Fix 
```+ apt-get -y install shovill
Reading package lists... Done
Building dependency tree       
Reading state information... Done
E: Unable to locate package shovill
FATAL:   While performing build: while running engine: exit status 100
```

-->  Should install shovill on latest ubuntu version

--> Change "From: ubuntu:20.04" to "From: ubuntu:23.04" problem solved

## 10. Common command using for working with singularity imgae
Build a Singulary image
```
$ sudo singularity pull library://lolcow
$ sudo singularity build lolcow.sif docker://sylabsio/lolcow
$ sudo singularity build lolcow.sif lolcow.def
$ sudo singularity build lolcow.sif lolcow
$ sudo singularity build --sandbox lolcow lolcow.def
$ sudo singularity build --sandbox lolcow lolcow.sif
```
Cache
```
$ singularity cache list
$ singularity cache clean
$ singularity cache clean --help
```
Interacting with images
```
$ sudo singularity shell lolcow.def
$ sudo singulariry shell lolcow
$ sudo singularity shell --writable lolcow.def
$ sudo singularity shell --writable lolcow
$ sudo singularity exec ubuntu echo "Hello world!"
$ sudo singularity exec ubuntu /bin/python3 main.py
$ sudo singularity exec --writable ubuntu /bin/bash
```
