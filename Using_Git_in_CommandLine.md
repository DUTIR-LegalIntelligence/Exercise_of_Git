# Git使用

## Git安装与下载

- ### 安装

地址： https://git-scm.com/downloads

安装过程可以参考 ： https://www.cnblogs.com/xueweisuoyong/p/11914045.html

> - 注意： 在安装程序的配置PATH步骤中，选择第二个选项以便于在PowerShell、CommandLine和Anaconda Prompt中使用Git

- ### 配置

Git安装完成之后，要配置Git的个人信息，包括名称和email地址，以便对修改人进行区分：

示例：

```
$ git config --global user.name "John Doe" 
$ git config --global user.email johndoe@example.com
```

## Git的使用

- 1. 首先创建一个项目文件夹，其中包括所有你**本项目**中需要的代码
- 2. 运行`git init`来初始化Git版本追踪文件夹（在项目目录中会生成一个`.git`文件夹来进行版本保存）
- 3. 使用`git add <files>`来添加你想追踪的文件，当然`<files>`也可以使用通配符来进行匹配，例如`*.py`, `*.cpp`等等；当然也可以使用`git rm --cached <files>`来取消追踪你需要的文件，使用`--cached`参数不会使本地文件删除。
- 4. 配置`.gitignore`文件，在其中添加你不需要追踪的内容，示例：
  ```
  .vscode
  .pycharm
  *.txt
  *.log
  data
  ```
- 5. 如果没有文件需要修改的话，可以直接使用`git commit`操作来建立自己的第一个版本，运行命令后根据命令行提示输入注释等信息即可。
  
### **项目已经准备就绪，可以准备推送到Github仓库了**

- 6. 如果还未在Github创建项目，需要在Github新建一个Repository （略）
- 7. 在推送之前，我们需要为项目配置远程项目地址，语法如下
  
  ```git remote add <name> <address>```

  `<name>`为远程项目的自定义名称，对于只有一个远程地址的情况建议命名为`origin`,以便于与其他fork项目区分开。
  `<address>`为远程项目地址，Github会提供给你

- 8. 在配置好远程项目地址之后，我们就可以运行`git push -u origin master`推送到Github了。这里的`-u origin master`可以理解为设定了默认推送的地址，以后每次只需要运行`git push`即可


## 为远程仓库更新版本

- 1. 在修改之前请使用`git pull`拉取一次远程代码，来保证本地的代码是与远程同步的（最新的）
- 2. 修改完成后记得暂存更改,可以同样使用`git add <files>`此处`<files>`为修改后的文件
- 3. `git commit`来建立一个新的版本号
- 4. 这时可以直接运行`git push`将新版本代码推送到远程了