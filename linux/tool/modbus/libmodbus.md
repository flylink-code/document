# LIBMODBUS

## <font color=#1D28F9>1.移植libmodbus</font>
### 1.1 下载源码
[libmodbus-3.0.6](http://libmodbus.org/releases/libmodbus-3.0.6.tar.gz)
### 1.2 准备交叉编译
* tar -zxvf libmodbus-3.0.6.tar.gz // 解压
* mkdir install                    // 创建安装目录
* cd libmodbus-3.0.6               // 进入解压目录
* /configure --host=arm-linux-gnueabi --enable-static --prefix=[安装路径]/install/                    // 配置选项
* make                             // 编译
* make install                     // 安装

### 1.3 测试与使用
* 测试代码
```cpp
#include<stdio.h>
#include<stdlib.h>
#include"modbus.h"
#include <memory.h>


int main(void)
{
    modbus_t *mb;
    uint16_t tab_reg[64]={0};

    //1-打开端口
    mb = modbus_new_rtu("/dev/ttymxc1",19200,'E',8,1);

    //2-设置从地址
    modbus_set_slave(mb,1);

    //3-建立连接
    modbus_connect(mb);

    //4-设置应答延时
    struct timeval t;
    t.tv_sec=0;
    t.tv_usec=1000000;//1000ms
    modbus_set_response_timeout(mb,&t);

    //5-循环读
    int num = 0;
    while(1)
    {   
        memset(tab_reg,0,64*2);

        //6-读寄存器设置：寄存器地址、数量、数据缓冲
        int regs=modbus_read_registers(mb, 0, 20, tab_reg);
       
        printf("-------------------------------------------\n");
        printf("[%4d][read num = %d]",num,regs);
        num++;
        
        int i;
        for(i=0; i<20; i++)
        {
            printf("<%#x>",tab_reg[i]);
        }
        printf("\n");
        printf("-------------------------------------------\n");
        sleep(1);
    }

    //7-关闭modbus端口
    modbus_close(mb);

    //8-释放modbus资源
    modbus_free(mb);
    return 0;
}
```
* 编译测试代码  
arm-linux-gnueabi-gcc -o modbus_rtu_test modbus_rtu_test.c -L../install/lib -lmodbus -I ../install/include/modbus
* 运行代码

## <font color=#1D28F9>附录</font>
[libmodbus官网](http://libmodbus.org/download/)
[原文](https://blog.csdn.net/u010168781/article/details/73924974)