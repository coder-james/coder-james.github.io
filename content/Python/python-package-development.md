---
title: "Python Package Development"
date: 2016-06-10 09:59
---


![alt text](../attach/python-logo.png)
###PyPI - the Python Package Index

PyPI是Python编程语言的软件源，其中有超过8万个包，本文将教会大家如何独立开发python软件，并上传至PyPI。

1. 账号准备

	需要在https://pypi.python.org/pypi和https://testpypi.python.org/pypi(测试站点)注册账号，通过邮箱验证后即可使用

2. Python项目布局

	使用cookiecutter模板来生成项目结构，首先安装：
	
	`pip install cookiecutter`
	
	`cookiecutter https://github.com/wdm0006/cookiecutter-pipproject.git` 按照提示，依次输入项目信息，如全名、email、项目名等，如下为小编生成的mcheck目录结构
	
	![alt text](../attach/python-project-structure.png)
	
	- LICENSE 许可证协议
		小编将项目上传到了github上，并使用GPL许可证
	- docs 项目文档
	- dist 之后打包的项目会在该目录下
	- mcheck 项目代码，文件目录和项目名相同
	- mcheck.egg-info 之后打包项目自动生成的文件
	- requirements.txt 项目依赖的软件包
	- setup.py 包含所有的项目信息，被distuils用来安装Python包

3. 上传测试

	项目开发完成后，通过以下命令上传至刚才的测试站点，在此之前，需要在~/目录下新建.pypirc文件内容如下：
		
		[distutils]
			index-servers =
        pypi
        pypitest

		[pypi]
		repository = https://pypi.python.org/pypi
		username = coder-james
		password = xxx

		[pypitest]
		repository = https://testpypi.python.org/pypi
		username = coder-james
		password = xxx
		
	pypi和pypitest分别为之前注册账号的站点，现在我们将项目上传至测试站点，首先在站点注册我们的项目：
	
	`python setup.py register -r pypitest`
	
	然后上传，其中sdist是以可pip安装的形式打包我们的python项目，可以看到打包后，会在dist项目下生成我们的python包mcheck-0.0.1.tar.gz：
	
	`python setup.py sdist upload -r pypitest`
	
	确认我们项目在服务器上后，我们就可以从测试站点安装我们的python包了：
	
	`pip install -i https://testpypi.python.org/pypi mcheck`
	
	注意每次上传时，不能提交相同版本号的项目。
4. 发布
	
	在测试成功后，我们还可以上传至pypi站点，以供大家下载使用，命令与上面相似：
	`python setup.py register -r pypi` 
	
	`python setup.py sdist upload -r pypi`
	
	`pip install mcheck`