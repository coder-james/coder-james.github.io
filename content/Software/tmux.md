---
title: "Tmux"
date: 2016-05-27 08:45
---

####Tmux 安装

######Linux

准备软件：

`libevent-2.0.10-stable.tar.gz`

`tmux-2.0.tar.gz`

安装步骤

1. yum install gcc
2. yum install ncurses-devel
3. 安装libevent 

	./configure
	
	make
	
	make install
4. 安装tmux

	./configure
	
	make
	
	make install
	
###Q&A
`libevent-2.0.so.5: cannot open shared object file: No such file or directory`

libevent-2.0.so.5默认安装目录，无法找到，需要建立软链接

`ln -s /usr/local/lib/libevent-2.0.so.5 /usr/lib64/libevent-2.0.so.5`