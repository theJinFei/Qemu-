# qemu
## qemu相关介绍

qemu是什么，简单来说它是一个虚拟机的管理器，类似Virtualbox之类的。为了使虚机达到接近主机的性能，一般会结合kvm（或者Xen）对硬件虚拟化。kvm负责cpu+mem虚拟化，但kvm不能模拟其他设备；qemu负责模拟IO设备（网卡，usb等），两者结合能实现真正意义上的全系统仿真。kvm与qemu的结构如图所示：

具体可参考
> http://liushy.com/2017/04/29/libvirt-qemu/

## 安装环境说明

## Qemu安装
`
sudo yum install qemu 
`

## Qemu参数启动
```
sudo yum install qemu 
sudo yum install qemu 
sudo yum install qemu 
```


## Qemu网络配置

### 新建虚拟网桥

### 为各个guest分配静态ip

### 使用host网络 访问外网

- 这是列表1
- 这是列表2
- 这是列表3


* 这是列表1
* 这是列表2
* 这是列表3

1. 这是列表1
2. 这是列表2
3. 这是列表3

![blockchain](https://ss0.bdstatic.com/70cFvHSh_Q1YnxGkpoWK1HF6hhy/it/u=702257389,1274025419&fm=27&gp=0.jpg "区块链")
