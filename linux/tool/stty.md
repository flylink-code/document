# stty的使用记录

## 设置串口参数
* stty -F /dev/ttyO3 ispeed 115200 ospeed 115200 cs8
  
## 查看串口配置
* stty -F /dev/ttyUSB0

## 去掉串口回显
* Stty -F /dev/ttyUSB0 -echo

