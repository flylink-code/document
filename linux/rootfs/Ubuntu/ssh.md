# ubuntu-SSH配置

## Ubuntu 16.04
### 安装与配置SSH服务
* sudo apt-get update
* sudo apt-get install openssh-server

### 启动服务
* sudo service ssh start

### 查询状态
* sudo ps -e | grep ssh
* sudo service ssh status

### 配置开机启动
* sudo sysv-rc-conf
* ![ssh1]()

### 修改配置文件
* sudo vim /etc/ssh/sshd_config

```
# PermitRootLogin without-password
PermitRootLogin yes
```

### 重启服务
* sudo service ssh restart

### 创建root账户
* sudo passwd root
