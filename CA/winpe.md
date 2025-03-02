# 制作WinPE启动盘全新安装Windows11

其实使用微软官方教程和软件就可以搞定，不需要使用第三方工具。但不得不说微软教程实在过于冗长，不是给使用者看的，应该是为开发人员设计的。以下为参考链接：  
[制作WinPE启动U盘](https://learn.microsoft.com/zh-cn/windows-hardware/manufacture/desktop/winpe-create-usb-bootable-drive?view=windows-11&source=recommendations)  

 
以下为操作流程关键点：  
第一步：安装ADK和Windows PE工具箱，并加载Windows PE启动镜像文件  
![alt text](winpe/image.png ':size=600')  

第二步：创建工作文件  
![alt text](winpe/image-1.png ':size=600')  

第三步：自定义Windows PE，添加WinPE-WMI和WinPE-SecureStartup组件，如果不包含这些可选组件，可能会看到错误，它显示你的电脑不满足最低硬件要求。  
[添加组件方法](https://learn.microsoft.com/zh-cn/windows-hardware/manufacture/desktop/winpe-mount-and-customize?view=windows-11)  

第四步：创建启动U盘，大于32GB的U盘可以先建立fat32分区，用Disk Manager。另外刷新BIOS也是一样，因为都只能使用FAT32格式。  
![alt text](winpe/image-2.png ':size=600')  

第五步：下载Windows11镜像文件，解压后复制到U盘，大于32GB的U盘，可以将镜像文件可以放在另一个分区（和上一步呼应），这个分区是ntfs格式也没关系。

第六步：将U盘插入电脑，启动电脑，按F11后选择U盘启动，进入WinPE，在命令行进行Windows11的安装。命令行操作全过程可以问Deepseek，可以解决95%的问题，非常靠谱，剩下5%的问题，google搜索解决。  
![alt text](winpe/image-4.png ':size=600')  
![alt text](winpe/image-5.png ':size=600')  
![alt text](winpe/image-6.png ':size=600')  
  
上图步骤4中版本号索引具体是什么要结合实际Windows11镜像文件来确定。比如我下载的是multi-edition版本，里面包含了若干版本，而我想安装的是专业版，所以需要使用6作为索引号。关于如何查询索引号，可参考GitHub上网友分享（[Step 4](https://gist.github.com/pratyakshm/f19c106205f9327e9f1d538fb91fce65)）。整个过程只是在这一步deepseek有一点小错误。

