# cmake

## 
### 更新
* 1.卸载旧版cmake`sudo apt remove cmake`
* 2.安装依赖`sudo apt install build-essential libssl-dev`
* 3.下载并编译源码`https://cmake.org/download/`
* 3.1 解压源码`sudo tar xf cmake-3.17.0.tar.gz`
* 3.2 编译安装
> sudo ./configure
> sudo make
> sudo make install 
* 4.创建软连接`sudo ln -sf /usr/local/bin/*  /usr/bin/`
* 5.查看版本`cmake -version `

## 附录
* [更新cmake](https://blog.csdn.net/u013925378/article/details/106945800)