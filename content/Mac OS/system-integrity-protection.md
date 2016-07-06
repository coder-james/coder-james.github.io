---
title: "System Integrity Protection"
date: 2016-05-26 14:58
---

###System Integrity Protection

####Mac OS X 10.11 EI Capitan

	    SIP是一个被设计用来预防潜在恶意软件修改Mac上受保护文件和文件夹的安全技术。
	
	    在OS X中，“root”用户没有权限限制，可以访问任何Mac上的系统文件夹或应用。在你安装软件输入管理账户和密码时，一旦软件获取了root级别的访问权限，便可以修改和重写任何系统文件或应用。这是非常危险的！
	    系统完整性保护机制限制了root账户的权限，使得root账户不能进行所有受保护文件的操作。例如：/System,/usr,/bin,/sbin


  重启Mac，按下`option[alt] + R`进入恢复模式
  
  选择`Utilities/Terminal`检查SIP状态：  
  
  `csrutil status`
  
  `csrutil disable` 停用SIP
  
  `csrutil enable` 开启SIP
  