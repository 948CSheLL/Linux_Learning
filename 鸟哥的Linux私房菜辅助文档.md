# 0、计算机概论
## 0.1、电脑：辅助人脑的好工具
### 0.1.2、一切设计的起点：CPU的架构
1. 关于32位CPU和64位CPU的说明
- 32位CPU的意思就是CPU每次解析数据是32bits，也就是4B，那么支持的地址就是4B长度的，也就是支持的最大内存是2^32(个地址)*1Byte=4GB。
- 同理64位CPU每次解析数据是64位，也就是8B，那么支持的地址长度就是8B长度，如果按照字节进行编址的话，支持的最大内存就是2^64（个地址）*1Byte。
2. Intel/AMD的x86架构中的重要指令（以下内容了解即可）
- MMX（Multi Media eXtension，多媒体扩展指令集）指令集是Intel公司于1996年推出的一项多媒体指令增强技术。MMX指令集中包括有57条多媒体指令，通过这些指令可以一次处理多个数据，在处理结果超过实际处理能力的时候也能进行正常处理，这样在软件的配合下，就可以得到更高的性能。
- SSE（Streaming SIMD Extensions，单指令多数据流扩展）指令集是Intel在Pentium III处理器中率先推出的。其实，早在PIII正式推出之前，Intel公司就曾经通过各种渠道公布过所谓的KNI（Katmai New Instruction）指令集，这个指令集也就是SSE指令集的前身，并一度被很多传媒称之为MMX指令集的下一个版本，即MMX2指令集。
- SSE2(Streaming SIMD Extensions 2，Intel官方称为单指令多数据流技术扩展 2或单指令多数据流扩展指令集 2)指令集是Intel公司在SSE指令集的基础上发展起来的。相比于SSE，SSE2使用了144个新增指令，扩展了MMX技术和SSE技术，这些指令提高了广大应用程序的运行性能。随MMX技术引进的单指令多数据流整数指令从64位扩展到了128 位，使SIMD整数类型操作的有效执行率成倍提高。双倍精度浮点（实数）单指令多数据流指令允许以 单指令多数据流格式同时执行两个浮点（实数）操作，提供双倍精度操作支持有助于加速内容创建、财务、工程和科学应用。除SSE2指令之外，最初的SSE指令也得到增强，通过支持多种数据类型（例如，双字和四字）的算术运算，支持灵活并且动态范围更广的计算功能。
## 0.2、个人电脑架构与相关设备组件
### 0.2.1、执行脑袋运算与判断的CPU
1. 什么是CPU架构？
- 个人理解：CPU架构就是CPU和其他的单元部件是如何摆放的。

### 0.2.3、显卡
1. 什么是GPU？
- 图形处理器（英语：Graphics Processing Unit，缩写：GPU），又称显示核心、视觉处理器、显示芯片，是一种专门在个人电脑、工作站、游戏机和一些移动设备（如平板电脑、智能手机等）上做图像和图形相关运算工作的微处理器。
- GPU使显卡减少了对CPU的依赖，并进行部分原本CPU的工作，尤其是在3D图形处理时GPU所采用的核心技术有硬件T&L（几何转换和光照处理）、立方环境材质贴图和顶点混合、纹理压缩和凹凸映射贴图、双重纹理四像素256位渲染引擎等，而硬件T&L技术可以说是GPU的标志。GPU的生产商主要有NVIDIA和ATI。
- GPU存在于显卡中。

### 0.2.8、选购须知
1. 关于速度瓶颈分析的例题
由于内存使用的是DDR3-1600型号，所以数据位宽是64位，频率是1600MHz，故带宽为频率*位宽=64bit*1600MHz=12.8GB/s。
由于磁盘列阵卡使用的是PCIe 2.0 x8型号，PCIe 2.0 x1的250MB/s，因为后面的x1表示一个通道，x8表示8个通道，故PCle 2.0 x8是PCIe 2.0 x1的8倍，所以带宽为4GB/s。
由于安装了8块3TB理论速度可以达到200MB/s的硬盘，而且是可叠加访问速度的RAID 0 配置，因此速度在200MB/s~1.6GB/s之间。
网络使用的是千兆网卡，即1000Mbit/s，也就是125MB/s，安装在PCIe 2.0 x1的接口上，PCIe 2.0 x1的带宽是500MB/s，但是千兆网络最多只能达到125MB/s，故网络接口的带宽是125MB/s。
故综上所述，速度最慢的是网络接口的125MB/s，所以要让整机性能提升，需要解决网络问题。

## 0.6、本章习题
- 第一题
截止到2020.6，最快的超级计算机：
名称：Supercomputer Fugaku - Supercomputer Fugaku, A64FX 48C 2.2GHz, Tofu interconnect D, Fujitsu RIKEN Center for Computational Science
所在位置：日本
使用的CPU型号与规格：富士通ARM处理器 A64FX 48C 2.2GHz
总共使用CPU数量：7,299,072
- 第三题：
CPU：Inter Pentium G620  2.6GHz
内存：4GBytes；DDR3
显卡：PCI Express 3.0；2GBytes
主板：ASUSTEK COMPUTER INC；Intel H61（南桥）；
```总结```：如果是Windows操作系统可以使用鲁大师软件或者CPUID CPU-Z软件查询电脑硬件配置。如果是Linux操作系统可以使用cat /proc/cpuinfo或者lspci等命令查看各项组件型号。
- 第四题：
（1）DMI2 5GT/S；（2）三级缓存 8MB；（3）16条PCIe 通道。
- 第五题：
（1）SATA3（6Gbps，即6Gbit/s）；（2）读：280MB/S(SATA2)，550MB/S（SATA3）；写：260MB/S（SATA2），520MB/S（SATA3）；（3）IOPS的值为：6187（读），17740（写）。

# 1、Linux是什么与如何学习
## 1.6、本章习题
- 第一题：
截止到2020年6月22日，Linux内核最新稳定版是	5.7.5
```总结```：要查询目前linux内核目前的最新版本可以直接登陆网站（https://www.kernel.org/）进行查询即可。如果要直接在Linux系统中查询内核版本，可以通过命令（uname -r）来查询。
- 第二题：
Linux·吉祥物名字叫做tuxedo
- 第三题：
1.5   Cupcake ---> 2.6.27
1.6   Donut ---> 2.6.29
2.0/1 Eclair ---> 2.6.29
2.2.x Froyo ---> 2.6.32
2.3.x Gingerbread ---> 2.6.35
3.x.x Honeycomb ---> 2.6.36
4.0.x Ice Cream San ---> 3.0.1
4.1.x Jelly Bean ---> 3.0.31
4.2.x Jelly Bean ---> 3.4.0
4.3   Jelly Bean ---> 3.4.39
4.4   Kit Kat ---> 3.10
5.x   Lollipop ---> 3.16.1
6.0   Marshmallow ---> 3.18.10
7.0   Nougat ---> 4.4.1
7.1   Nougat ---> 4.4.1 (To be updated)
```总结```：详细的Android与Linux内核的对应关系参考：https://blog.csdn.net/ly890700/java/article/details/75040704