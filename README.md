# install in WSL

## vscode 



```
vim /etc/wsl.conf

[automount]
enabled = true
root = /mnt/
options = "metadata,umask=22,fmask=11"
mountFsTab = false
```

vim ~/.bashrc

```
# git
function git_branch {
    branch="`git branch 2>/dev/null | grep "^\*" | sed -e "s/^\*\ //"`"
    if [ "${branch}" != "" ];then
        if [ "${branch}" = "(no branch)" ];then
            branch="(`git rev-parse --short HEAD`...)"
        fi
        echo " ($branch)"
    fi
}
export PS1='\u@\h \[\033[01;36m\]\W\[\033[01;32m\]$(git_branch)\[\033[00m\] \$ '

source /etc/bash_completion.d/git-prompt 
```


## install nvm in WSL-Debian (Failed)

Step 1. Download Bash shell script from https://github.com/nvm-sh/nvm#install--update-script
```
$ curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/${VERSION}/install.sh | bash

eg: $ curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.38.0/install.sh | bash
```

Step 2. Sure your C++ compiler is latest:

```
$ apt install -y build-essential libssl-dev
$ command -v nvm
-> nvm
$ nvm isntall node
```

## install nodejs v12 in WSL-Debian

Step 1. 
```
curl -sL https://deb.nodesource.com/setup_12.x -o nodesource_setup.sh
bash nodesource_setup.sh
```

Step 2 apt

```
apt install -y nodejs
```
