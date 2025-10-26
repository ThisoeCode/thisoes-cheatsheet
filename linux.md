> ## Menu
>
> [for C](#linux-for-c-ubuntu)
>
> [for SSH](#web-dev-ssh)


# Linux for C (Ubuntu)

- <cite>This part is note written while watching [OJ Tube C Tuturial](https://www.youtube.com/playlist?list=PLz--ENLG_8TMdMJIwyqDIpcEOysvNoonf [C언어 강의]개발자의 로망 - 리눅스 기반 C언어).</cite>

### Basics

```bash
# login root
su -

sudo
cd ~
ls

# list out details
ls -l

mkdir acme
# force remove everything under the dir
rm -rf acme

# Ubuntu: install from app store
apt-get update
apt-get install vim
apt-get install gcc

# Vim: create/edit
vi helloworld.c

# show the ASCII hex code of a file
xxd helloworld.c

```

### Vim
Command mode: `ESC` -> `Shift`+`:`
`:w` Save
`:q` Quit
`:q!` Force quit (without saving)






*******



# Web Dev SSH

### Install Composer
```bash
wget https://getcomposer.org/installer
php installer

composer --version
```
(Composer commands see [#Composer](#composer))

### Install Node
  1. Download (Please change Nodejs version as your need)
  ```bash
  wget https://nodejs.org/dist/v20.11.1/node-v20.11.1-linux-x64.tar.gz
  tar xvzf node-v20.11.1-linux-x64.tar.gz
  mv node-v20.11.1-linux-x64 nodejs
  ```
  2. Move bin file
  ```bash
  mkdir ~/bin
  cp nodejs/bin/node ~/bin
  ```
  3. Link
  ```bash
  cd ~/bin
  ln -s ../nodejs/lib/node_modules/npm/bin/npm-cli.js npm
  ```
  4. Test command
  ```bash
  node --version
  ```
  5. Enable `npm`
  ```bash
  cd ~/bin
  ln -s ../nodejs/bin/npm npm
  
  npm --version
  ```

