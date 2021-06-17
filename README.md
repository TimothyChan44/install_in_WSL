# install in WSL

## install nvm in WSL-Debian

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

