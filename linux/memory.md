# 内存

## 修改板载内存大小
### IMX6UL - linux4.9
#### 1.uboot
```

```
#### 2.dts
```
memory [     
    device_type = "memory";
    reg = <0x80000000 0x8000000>; // 内存地址域内存大小
]
```
#### 3.