# Ways to Use "Alias"  
## All cited from [cyberciti.biz](https://www.cyberciti.biz/tips/bash-aliases-mac-centos-linux-unix.html)  
Alias is a way to make shortcut for your bash terminal. It significantly saves your time. Here are the ways to use it.  
### Alias  
If you type `alias` and press `enter` in your terminal, this would show up:  
```
$ alias 
alias ll='ls -l'
alias ls='ls -F --color=auto --show-control-chars'
```
These are the default alias that bash gives you, and if you add some new alias later, they will also show up here.  
### How to use alias  
Sometimes, you don't feel like typing "clear" to clear your terminal because it is too long. Here you can make an alias for it.  
To make your first alias, type `alias c='clear'`.  
To confirm you did it, type `alias` like we did. The following should show up:  
```
$ alias
alias c='clear'
alias ll='ls -l'
alias ls='ls -F --color=auto --show-control-chars'
```
Here, you can see that `alias c='clear'` is added to the list.  
To use it, you just type `c` and press `enter`.
Your terminal should be cleared now, just like the command `clear` would do.  
### Unalias  
If you do not want to save your time anymore by having the alias `c`, that's totally fine. Just type `unalias c`.  
To verify you have removed this alias, type `alias` again. `alias c='clear'` should not be there anymore.
### Permanent alias  
If you start a new terminal, your created alias will be gone, because they are not permanent.  
To make them permenant, we need to write it to the `.bashrc` file.  
Type `nano ~/.bashrc`, and in the nano, add your alias `alias c='clear'` to it; press `ctrl + s` to save, and press `ctrl + x` to exit.  
Reload your terminal, and then try to use `c` to clear your terminal. It works now!  
### Useful aliases  
1. `alias ..='cd ..'`  
2. `alias h='history`  
3. `alias ssh='<your school account>'`  
You can create many aliases to boost your efficiency! Have fun!  
