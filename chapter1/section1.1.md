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
node cli.js install npm -g
可以用version检查安装是否正确
安装gitbook

npm install gitbook-cli -g
可以用version检查安装是否正确

作者：穆弋
链接：https://www.jianshu.com/p/f44aaf36a96d
來源：简书
简书著作权归作者所有，任何形式的转载都请联系作者获得授权并注明出处。
