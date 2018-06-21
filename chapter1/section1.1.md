# Section1.1

安装Git

sudo apt-get install git

安装node npm

安装nvm

cd ~

mkdir .nvm

cd .nvm

git clone https://github.com/creationix/nvm

等待下载完毕后将source ~/.nvm/nvm/nvm.sh添加到~/.profile之类的文件中

vim ~/.profile 并在文件末尾添加source ~/.nvm/nvm/nvm.sh

source 一下.profile

nvm --version检查安装是否正确

安装node

nvm install node

node --version

安装npm

git clone --recursive git://github.com/isaacs/npm.git

cd npm

可以用version检查安装是否正确

这里需要做一下链接，执行

sudo ln -s /home/bitmain/.nvm/npm /usr/local/bin/npm

source 一下 .profile
最好重启一下电脑

安装gitbook

npm install gitbook-cli -g

可以用version检查安装是否正确


转载自 https://www.jianshu.com/p/f44aaf36a96d


