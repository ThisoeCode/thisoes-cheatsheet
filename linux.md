## Menu
- [for C](#ubuntu)
- [for SSH](#web-dev-ssh)

*******



# Ubuntu

- <cite>This part is note written while watching [OJ Tube C Tuturial](https://www.youtube.com/playlist?list=PLz--ENLG_8TMdMJIwyqDIpcEOysvNoonf [C언어 강의]개발자의 로망 - 리눅스 기반 C언어).</cite>

### Basics

```bash
# help
man ls

# return file content
cat file.txt

# list out details
ls -l

# create new dir
mkdir acme

# Ubuntu app store
apt-get update
apt-get install gcc

# show the ASCII hex code of a file
xxd helloworld.c

```

### Vim
Command mode: `ESC` -> `:`
`:w` Save
`:q` Quit
`:q!` Quit without saving
`:wq` Save then Quit






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

