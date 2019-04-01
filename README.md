# qemu安装
## qemu相关介绍

qemu是什么，简单来说它是一个虚拟机的管理器，类似Virtualbox之类的。为了使虚机达到接近主机的性能，一般会结合kvm（或者Xen）对硬件虚拟化。kvm负责cpu+mem虚拟化，但kvm不能模拟其他设备；qemu负责模拟IO设备（网卡，usb等），两者结合能实现真正意义上的全系统仿真。kvm与qemu的结构如图所示：

具体可参考
> http://liushy.com/2017/04/29/libvirt-qemu/

## QEMU模拟器基本原理
作为系统模拟器时，会模拟出一台能够独立运行操作系统的虚拟机。如下图所示，每个虚拟机对应主机(Host)中的一个QEMU进程，而虚拟机的vCPU对应QEMU进程的一个线程。
![Qemu与硬件的关系](https://static.oschina.net/uploads/img/201702/21145729_5FGx.png "区块链")

系统虚拟化最主要是虚拟出CPU、内存及I/O设备。虚拟出的CPU称之为vCPU，QEMU为了提升效率，借用KVM、XEN等虚拟化技术，直接利用硬件对虚拟化的支持，在主机上安全地运行虚拟机代码(需要硬件支持)。

QEMU发起ioctrl来调用KVM接口，KVM则利用硬件扩展直接将虚拟机代码运行于主机之上，一旦vCPU需要操作设备寄存器，vCPU将会停止并退回到QEMU，QEMU去模拟出操作结果。

虚拟机内存会被映射到QEMU的进程地址空间，在启动时分配。在虚拟机看来，QEMU所分配的主机上的虚拟地址空间为虚拟机的物理地址空间。

QEMU在主机用户态模拟虚拟机的硬件设备，vCPU对硬件的操作结果会在用户态进行模拟，如虚拟机需要将数据写入硬盘，实际结果是将数据写入到了主机中的一个镜像文件中。

具体可参考
> https://my.oschina.net/kelvinxupt/blog/265108

## 安装环境说明

- Qemu命令行安装
`
sudo yum install qemu 
`


- Qemu源码编译安装
```
wget http://download.qemu-project.org/qemu-2.70.tar.xz

tar xvJf qemu-2.7.0.tar.xz

cd qemu-2.70

./configure --enable-kvm --enable-debug --enable-vnc --enable-werror  --target-list="x86_64-softmmu" # 需要添加kvm硬件支持

make

sudo make install


configure脚本用于生成Makefile，其选项可以用./configure --help查看。这里使用到的选项含义如下：

--enable-kvm：编译KVM模块，使QEMU可以利用KVM来访问硬件提供的虚拟化服务。
--enable-vnc：启用VNC。
--enalbe-werror：编译时，将所有的警告当作错误处理。
--target-list：选择目标机器的架构。默认是将所有的架构都编译，但为了更快的完成编译，指定需要的架构即可。

```

## 使用Qemu创建启动镜像



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


