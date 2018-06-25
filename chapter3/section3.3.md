# section3.3scp远程服务器

需求： 1.远程到服务器10.30.50.207

使用ssh

ssh linaro@10.30.50.207

load_server目录下load_server脚本得到日志文件，这个脚本需要一直启动

读取日志文件

获取核心板ip,文件倒数6行

6块核心板的ip做成case， all.cmd

一个新的脚本，再次远程到核心板，执行测试脚本，获取脚本启动信息。

方法：使用expect可以远程到无服务器，同时在脚本中对服务器进行操作。

#!/usr/bin/expect

set timeout  10

spawn ssh linaro@10.30.50.211

expect "*password*"

send "linaro\r"

sleep 1

send "cd load_server;

echo hello test > /home/linaro/log/test.txt\r"


#!/usr/bin/expect

set timeout 10

spawn scp linaro@10.30.50.211:/home/linaro/load_server/ip_info.txt /home/bitmain/zl/shell/ssh

expect "*password*"

send "linaro\r"

sleep 1


#!/bin/bash

./expect.exp

./scp.exp

cd /home/bitmain/zl/shell/ssh

tail -n 5 *.txt > last5.ini

line1=`sed -n "1p" last5.ini`

line2=`sed -n "2p" last5.ini`

line3=`sed -n "3p" last5.ini`

line4=`sed -n "4p" last5.ini`

line5=`sed -n "5p" last5.ini`

IP_NUM1=${line1:21:13}

IP_NUM2=${line2:21:13}

IP_NUM3=${line3:21:13}

IP_NUM4=${line4:21:13}

IP_NUM5=${line5:21:13}

echo $IP_NUM1

echo $IP_NUM2

echo $IP_NUM3

echo $IP_NUM4

echo $IP_NUM5









