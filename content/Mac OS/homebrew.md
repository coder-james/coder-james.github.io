---
title: "Homebrew"
date: 2016-05-26 12:42
---

#Homebrew

###OS X不可或缺的套件管理器
[官方网站]

[官方网站]: http://brew.sh/index_zh-cn.html

`# /usr/bin/ruby -e "$(curl -fsSL `

`https://raw.githubusercontent.com/Homebrew/install/master/install)"`

e.g. `brew install wget`

####Q&A
1. Cowardly refusing to 'sudo brew install'
   
   	`brew install` will not work with root privileges unless `brew` itself is owned by root
   
   	`chown root:staff /usr/local/bin/brew`