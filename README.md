# -STM32-
通过制作一个stm32读卡器来锻炼自己的Embeded Level

可是由于stm32芯片的USB原因，读写的速度很慢，只能几百k！

由于要使用到SDIO外设，所以要使用到大容量的stm32芯片：STM32F103RCT6

# 笔记：

## 环境配置：

不同stm32f103芯片的的代码移植：

https://blog.csdn.net/ysgjiangsu/article/details/89930634

注意启动文件(.s文件)里面：https://blog.csdn.net/T_Peach_T/article/details/104238954

要注意的是：原子的例程里面，delay_ms()里面，传入的参数不能超过1000！！！



### 硬件：

+ 在用原子的移植的时候，原子的时候大的SD卡，可是要做成TF卡的大小，对应的引脚要注意对应：

![](./image/1.png)

+ 在看别人的原理图的时候，电阻上面标记20R意思就是20Ω。

+ 降压芯片的选取（5V-3.3V）：RT9193 

  需要注意的是，这个降压芯片使用适用于低功率的电路，要是很大功率的要使用AMS1117

  降压电路参考最小板的设计：

  <img src="image/image-20201204200118632.png" alt="image-20201204200118632"  />



## AD19画板子：

+ 在多part的原理图封装中，比如说有两个part。那么放置这个器件时候可以放两个，然后改好每个器件的part。注意两个器件的designer一定要一样！

<img src="image/image-20201206151518425.png" alt="image-20201206151518425" style="zoom:67%;" />



+ 在进行USB和type-c的原理图连接的时候，要注意对应！！

  参考资料：https://baijiahao.baidu.com/s?id=1599597028027686520&wfr=spider&for=pc

  <img src="image/image-20201206164446647.png" alt="image-20201206164446647" style="zoom:67%;" />

+ STM32F103RCT6的连接图：

  <img src="image/image-20201206224833851.png" alt="image-20201206224833851"  />

![image-20201206225005583](image/image-20201206225005583.png)

这个原理图就是STM32F103RCT6的。

























