---
layout: post
title: "Bash Aliases"
description: "What are they and  why use them?"
comments: true 
keywords: "bash, aliases"
---
This is my first blog and I will try to keep it simple and easy to understand. In this blog I am going to talk about what are aliases and what is the use of them.

### What is a Alias and Why use them 
Alias is  like shortened version of a command than can be used instead of typing out the whole command. These are quite helpful if you have some common commands that you use on a regualar basis. The alias concept is not something that is particular to bash but can used by different shells like zsh, fish but there is a little difference in syntax. Here I will be giving some examples that are written for bash shell.

### Get started
Creating an alias is simple. All you need to do is go to your home directory and you can get started by writing `alias [alias_name]="[command]"` in your `.bashrc` file or you can create an `.aliases` file and source it in from your `.bashrc` file. I prefer to do the latter as in that way I can keep a clean record of my aliases in a single file.

**Note:** You can source your `.aliases` file by typing 
```bash 
source ~/.aliases
```

### Some of my personal aliases

In my opionion learning by example is the best practice and with that here are few of my personal aliases which i use daily.

* Related to listing of files in a directory
```bash
alias ls = "lsd"
alias l = "ls -l"
alias la = "ls -a"   
alias lla = "ls -la"
alias lt = "ls --tree"
```
Here I use a program called [lsd](https://github.com/Peltoche/lsd) for giving colourized output for ls with icons make sure to use Hack-Nerd Font.
* Get your public ip 
```bash
alias myip = "curl ipinfo.io/ip"
```
* Playing music using mpv
```bash
alias mm = "mpv ~/Path_to_music_file"
```
* Get weather info 
```bash
alias weather = "clear && curl wttr.in"
```
This can used to pause bash history and then enable it.
```bash
alias ph = "set +o history"
alias sh = "set -o history"
```
#### Some macos specific aliases

* Used to find and clean all occurences of `.DS_Store` file in a directory and its subdirectories.
```bash
alias cleanup = "find . -type f -name '*.DS_Store' -ls -delete"
```
* This can used to hide and show your desktop.
```bash
alias hidedesktop = "defaults write com.apple.finder CreateDesktop -bool false && killall Finder"
alias showdesktop = "defaults write com.apple.finder CreateDesktop -bool true && killall Finder"
```

##### For Github
* I have added  
```bash 
alias g = "git" 
``` 
to my `.aliases` file and added the following command in `.gitconfig`

    ```bash
    [alias]
        s = status
        d = diff
        co = checkout
        br = branch
        last = log -1 HEAD
        cane = commit --amend --no-edit
        lo = log --oneline -n 10
        a = add .
        rh = reset --hard
        cm = commit -m
        p = pull --rebase
    ```

---
_With this small introduction to aliases I hope you are able to grasp something about aliases and will try to implement some of your own aliases._
