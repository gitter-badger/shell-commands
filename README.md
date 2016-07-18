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


###Installing all fonts at once 
copy all fonts in the directory called `.fonts` if directory is not present create one directory   
```
cd;mkdir .fonts
```
or
```
cd ~
mkdir .fonts
```
copy all your fonts to `.fonts` folder and run the command `fc-cache -f -v` this command refresh the fonts now you can use the fonts

#### Right click to open terminal
`sudo apt-get install nautilus-open-terminal`this is for ubuntu and elementary os 

#### Making auto start application 
`.config/autostart` drop all the applicatin files inside this folder 

#### Conky setup and runnig multiple files
##### Installation
```bash
sudo apt-get install conky-all
sudo apt-get install conky
sudo apt-get install lm-sensors hddtemp
```
To set multiple Conky to run at startup, create a folder called `.conky` 
```
mkdir ~/.conky       //add all conky configuration files to this folder ex conkyrc_network,conkyrc_clock ..... 
```
Make a file called `conky_start` in the folder `~/bin` if the folder is not present create one with command `mkdir ~/bin`    
Add the following lines to the file 
```
 #!/bin/bash
conky -c ~/.conky/.conkyrc_network &
conky -c ~/.conky/.conkyrc_clock
```
add the startup command as `~/bin/conky_start`  

all lines must end with `&` except the last line in this way you can add the multiple files   

### Show the top ten running processes (sorted by memory usage):
` ps aux | sort -nrk 4 | head `
### Executing previous command as root 
`sudo !!`
### Recording the Desktop Video
` ffmpeg -f x11grab -s wxga -r 25 -i :0.0 -sameq /tmp/out.mpg `

#### Deleting all folders except some specific folders in a directory
```
find /directory where to remove/ -type d -not -name folder1 -not -name folder2 -exec rm -R {} \;
```
**OR**
                         
```bash
shopt -s extglob
rm !(file.txt)
```
### finding the file size or disk usage of the file
```
du -a
du -a -h
du -a -s
```
### enable wifi if it is blocked
```
rfkill unblock all
sudo /etc/init.d/networking restart
sudo rm /etc/udev/rules.d/70-persistent-net.rules
sudo reboot

```
### Adding Insults when you type wrong password for sudo

For this you need to edit the configuration of sudo you need to add the following line 

```
Defaults      insults
```
To edit the configuration type the following command  

```
sudo visudo
```          
It will open the `/etc/sudoers.tmp` configuration in nano editor after adding the line you need to press `Ctrl+X` then it will ask for save the changes press `y` for accepting the changes.        

Then get ready to being insulted :smile:       

### Enabling the autocd 
```bash
shopt -s autocd
```
After Enabling this command whenever you type if the command is not present then automatically it takes that input and apply for `cd`     
#####Example
Think you have the followinf directory structure `/home/user/bin/code` and your present directory is `/home/user` then if you want to change the directory to `bin` you no need to type `cd bin` just type `bin` it will changes automatically .

##### Upgrading the Node 
```bash
sudo npm cache clean -f
sudo npm install -g n
sudo n stable
```
**Note**              
Here You can use your own node version instead of the `stable` key word for example If you want install the node version `6.3.0` then the line should be like the following one              
```bash
sudo n 6.3.0
```
