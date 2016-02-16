# commands
##This is about basic commands collections that we encounter in daily basis
---
### unzip the files 
```bash
unzip file-name.zip -d destination-path
```
    if unzip is not present just install it 
    sudo apt-get install unzip 
    the installation depends on the linux-XX os 
### converting images to pdf in unite 
```bash
convert one.jpg two.jpg final.pdf
```
    this command is used to convert images to pdf 
    all pdf to single pdf file 
    
###ssh key generation 
```
    ssh-keygen
```

###changing the default editor 
```sudo update-alternatives --config editor```
### How to add aliases 
The files inclcuding the aliases are as follows
```(~/.bashrc or /etc/bash.bashrc).```
Now open those files in your favourite editor and keep adding the commands
```alias alias_name="command"``` the command should be quoted and alias name not
#####extra information
by default ```~/.bashrc``` file checks for the ```~/.bash_aliases``` so create one file with that filename and add all your aliases or else add following lines in the ```~/.bashrc``` file

```
if [ -f ~/.bash_aliases ]; then 
. ~/.bash_aliases 
fi
```
after that rebstart the system with ```reboot``` command
###Recomended commands
```
alias cd..='cd ..'     moves backword directory by one level
alias cp='cp -i'
alias d='ls'
alias df='df -h -x supermount'
alias du='du -h'
alias egrep='egrep --color'
alias fgrep='fgrep --color'
alias grep='grep --color'
alias l='ls'
alias la='ls -a'
alias ll='ls -l'
alias ls='ls -F --color=auto'
alias lsd='ls -d */'
alias md='mkdir'
alias mv='mv -i'
alias p='cd -'
alias rd='rmdir'
alias rm='rm -i
```
####How to escape alias
for example in above aliases ```alias rm = 'rm -i'``` this will interactively remove the files when ever you try to remove but if you want escape from that alias command try like this 

`\rm filename` this removes the file with out interactively
####Check the aliases 
check your aliases with command `alias`

###Adding the path permanently 
There are two ways you can do   
##### Editinng `~./profile or ~./bash_profile` 
```export PATH=$PATH:/path to be added/``` add this line either of the files

####Editing ```/etc/environment`` :file  

when you open the file you will find the following line just add the path to end of the line  
```PATH="/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games"``` add the `:` at the end add your path here


