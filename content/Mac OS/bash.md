---
title: "Bash"
date: 2016-05-25 08:35
---

1.  授权目录及目录下所有文件

	chown -R [user]:[usergroup] [directory]
    
    e.g.  `chown -R James:staff mywiki`

2.	移动硬盘文件呈灰色，无法打开
	
	`xattr -l [filename]`
	
	`xattr -d com.apple.FinderInfo [filename]`

3.	Finder显示文件

	`cd /`
	
	`sudo chflags hidden *`