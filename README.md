# Efi-opencore-m425-n000-with-i7-8700
![image](https://user-images.githubusercontent.com/20026922/174951046-16a51076-3482-4919-8563-290fdb4f7d5c.png)
![image](https://user-images.githubusercontent.com/20026922/175474616-13b4bb39-6299-4892-9a4e-3694636b6dd1.png)

## 机器配置
--------[ 概览 ]----------------------------------------------------------------------------------

  电脑型号               联想 启天M425-N000 台式电脑

  操作系统               Windows 10 Enterprise 64位（Version 1809 / DirectX 12）

  处理器                 英特尔 Core i7-8700 @ 3.20GHz 六核

  主板                   联想 313A（B360 芯片组）

  显卡                   英特尔 UHD Graphics 630 ( 128 MB / 联想 )

  内存                   16 GB ( 三星 DDR4 2666MHz )

  主硬盘                  HFM128GDHTNG-8310B ( 128 GB / 固态硬盘 )

  显示器                 宏碁 ACR0216 S242HL ( 24 英寸  )

  声卡                   瑞昱 ALC662 @ 英特尔 High Definition Audio 控制器

  网卡                   瑞昱 RTL8168/8111/8112 Gigabit Ethernet Controller / 联想

### 制作流程 （黑苹果思路）
#### EFI结构图
![image](https://user-images.githubusercontent.com/20026922/175478939-29957649-dfda-47ea-8eba-d8e3240221d7.png)

#### 定制流程 

1. 制作ACPI(SSDT)
   可参考 [司波图教程](https://www.youtube.com/watch?v=Lu6Kmz5aDhY) 11:45处开始

2. 准备必要Kexts
   本机参考kexts [Efi-opencore-m425-n000-with-i7-8700-amd-rx6600xt](https://github.com/afly2020/Efi-opencore-m425-n000-with-i7-8700-amd-rx6600xt)  去掉了A卡的驱动 感谢@[afly2020](https://github.com/afly2020)

3. 配置config.plist 
   3.1 下载[opencore-0.8.1](https://github.com/acidanthera/OpenCorePkg/releases/download/0.8.1/OpenCore-0.8.1-RELEASE.zip)

   解压之后 取64位EFI文件夹

   ![image](https://user-images.githubusercontent.com/20026922/175482373-c5d59425-a17f-47e9-8cc0-86dbcd3edf2d.png)

   3.1.1 将第一步生成的SSDT文件拷贝进ACPI文件夹

   3.1.2 将第二部获取到的驱动文件kext放入kexts文件夹

   3.1.3 删除多余文件 
   
   3.1.4 将opencore-0.8.1的doc/sample.plist拷贝进EFI/OC文件夹下 并改名为config.plist
   
   最终结果参考[EFI结构图](#EFI结构图)
   
   3.2 定制config.plist
   
    https://dortania.github.io/OpenCore-Install-Guide/config.plist/coffee-lake.html
   
   根据上面文档设置config.plist的每项配置
   
   3.3 修复HDMI输出
   
   由于此机主板只有HDMI和VGA口（VGA可以正常输出） 只接HDMI口后显示器黑屏
   
   修复连接器类型：
   
   文档参考 https://dortania.github.io/OpenCore-Post-Install/gpu-patching/intel-patching/connector.html
   
   参考文档：https://www.hurryyu.com/2022/05/28/黑苹果折腾记录/#2-2、DeviceProperties配置
   
   我重启了20多次才试成功 哈哈哈😂
   ![image](https://user-images.githubusercontent.com/20026922/175490306-d8503ade-dc0f-43a5-9752-33e324e5edc5.png)
   
   3.4 HDMI VGA同时输出
   ![image](https://user-images.githubusercontent.com/20026922/175490344-dcb59fbe-77c9-4279-be8a-27b4c74a2fbb.png)
   
   3.5 声卡
   
   根据声卡型号找layoutid ALC662填的是17
   
   https://blog.daliansky.net/AppleALC-Supported-codecs.html
   
   
#### 参考文档
https://dortania.github.io/OpenCore-Install-Guide/prerequisites.html

## 感谢

Youtuber [司波图](https://www.youtube.com/c/SpotoTsui)

[HurryYu(于子豪)](https://www.hurryyu.com/about/)

[afly2020](https://github.com/afly2020)
