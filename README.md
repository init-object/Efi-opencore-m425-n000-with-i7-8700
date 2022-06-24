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
#### EFI结构图 （最终结果 opencore版本：0.8.1）
![image](https://user-images.githubusercontent.com/20026922/175478939-29957649-dfda-47ea-8eba-d8e3240221d7.png)

#### 定制流程 

1. 制作ACPI(SSDT)

2. 准备必要Kexts
   本机参考kexts [Efi-opencore-m425-n000-with-i7-8700-amd-rx6600xt](https://github.com/afly2020/Efi-opencore-m425-n000-with-i7-8700-amd-rx6600xt)  去掉了A卡的驱动 感谢@afly2020

3. 配置config.plist 
   3.1 下载opencore-0.8.1 https://github.com/acidanthera/OpenCorePkg/releases/download/0.8.1/OpenCore-0.8.1-RELEASE.zip

   解压之后 取64位EFI文件夹

   ![image](https://user-images.githubusercontent.com/20026922/175482373-c5d59425-a17f-47e9-8cc0-86dbcd3edf2d.png)

   删除多余文件 最终结果参考[EFI结构图][EFI结构图 （最终结果 opencore版本：0.8.1)]

    https://dortania.github.io/OpenCore-Install-Guide/config.plist/coffee-lake.html

4. 由于此机主板只有HDMI和VGA口（VGA可以正常输出） 只接HDMI口后显示器黑屏

   
#### 参考文档
https://dortania.github.io/OpenCore-Install-Guide/prerequisites.html
