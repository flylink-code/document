# 设备树

## 在根文件系统查看设备树
**/sys/firmware/fdt**               
进入/sys/firmware目录后便可看到二个文件，一个是devicetree文件夹，另一个是fdt（原始dtb文件，可以用hexdump -C fdt 将其打印出来查看就会发现里面的数据和dtb文件是一致的）。

**/sys/firmware/devicetree**  
以目录结构呈现的dtb文件。 根节点对应base目录, 每一个节点对应一个目录, 每一个属性对应一个文件

**/sys/devices/platform**  
系统中所有的platform_device, 有来自设备树的, 也有来有.c文件中注册的
对于来自设备树的platform_device,可以进入 /sys/devices/platform/<设备名>/of_node 查看它的设备树属性（例如进入/sys/devices/platform/led/后若发现该目录下有of_node节点，就表明该platform_device来自设备树）

**/proc/device-tree**  
是链接文件, 指向 /sys/firmware/devicetree/base