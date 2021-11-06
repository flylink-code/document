# SSH文档

## 一、VSCODE使用SSH
### 1.1 安装
* 在扩展工具里安装VsCode官方插件"Remote - SSH"、"Remote - SSH: Editing Configuration Files".  
![插件](./picture/2.png)
* 插件安装完成后，重启vscode会发现左侧提示栏新增图标  
![图标](./picture/1.png)
### 1.2 建立连接
* 想要建立新连接,我们点击侧边栏的图标，鼠标移至TAG栏,点击+，在弹出框里输入ssh连接  
![图标](./picture/3.png)
* 输入格式如下：ssh://name:pwd@ip:prot(例：ssh://root:pwd@192.168.1.1:22)  
* 输入完成后回车选择保存地址  
![图标](./picture/4.png)  
> 选项1是保存到当前用户下    
选项2是保存到所有用户下  
* 选择完成后添加成功  
![图标](./picture/5.png)
* 选中新增的ssh，点击右边加号框图标，弹出新窗口，开始新连接  
![图标](./picture/6.png)

## 附录
### 1.注意事项
* 每次连接远程都需要输入密码
