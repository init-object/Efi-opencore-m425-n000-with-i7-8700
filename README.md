# Efi-opencore-m425-n000-with-i7-8700
![image](https://user-images.githubusercontent.com/20026922/174951046-16a51076-3482-4919-8563-290fdb4f7d5c.png)
![image](https://user-images.githubusercontent.com/20026922/175474616-13b4bb39-6299-4892-9a4e-3694636b6dd1.png)

## 配置
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
  
--------[ 主板 ]----------------------------------------------------------------------------------

  主板型号               联想 313A
  芯片组                 B360 芯片组
  主板版本               NOK
  BIOS                   联想 M1YKT49A  /  BIOS程序发布日期: 06/17/2019
  BIOS的大小             8192 KB

  板载设备               视频设备 (启用)
  --------[ 处理器 ]----------------------------------------------------------------------------------

  处理器                 英特尔 Core i7-8700 @ 3.20GHz 六核
  速度                   3.20 GHz
  处理器数量             核心数：6 / 线程数：12
  核心代号               Ivy Bridge E
  生产工艺               14 nm
  插槽/插座              LGA1151
  一级数据缓存           6 x 32 KB, 8-Way, 64 byte lines
  一级代码缓存           6 x 32 KB, 8-Way, 64 byte lines
  二级缓存               6 x 256 KB, 4-Way, 64 byte lines
  三级缓存               12 MB, 16-Way, 64 byte lines
  特征                   MMX, SSE, SSE2, SSE3, SSSE3, SSE4.1, SSE4.2, HTT, EM64T, EIST, Turbo Boost
  
  ChannelA-DIMM1         三星 DDR4 2666MHz 8GB
  制造日期               2019 年 22 周
  型号                   M378A1K43CB2-CTD
  序列号                 325F222E
  厂商                   SAMSUNG
  模块位宽               64 Bits
  模块电压               SSTL 1.2V

  ChannelB-DIMM1         三星 DDR4 2666MHz 8GB
  制造日期               2019 年 22 周
  型号                   M378A1K43CB2-CTD
  序列号                 325F20A2
  厂商                   SAMSUNG
  模块位宽               64 Bits
  模块电压               SSTL 1.2V

--------[ 显卡 ]----------------------------------------------------------------------------------

  主显卡                 英特尔 UHD Graphics 630
  显存                   128 MB
  显卡制造商             联想
  芯片制造商             Intel
  
--------[ 其他设备 ]----------------------------------------------------------------------------------

  网卡                   Realtek PCIe GBE Family Controller

  声卡                   瑞昱 ALC662 @ 英特尔 High Definition Audio 控制器

  键盘                   HID 标准键盘
  鼠标                   HID-compliant 鼠标
--------[ 硬盘 ]----------------------------------------------------------------------------------

  产品                   HFM128GDHTNG-8310B (固态硬盘)
  大小                   128 GB
  固件                   80060C00
  接口                   NVM Express
  特性                   S.M.A.R.T
  硬盘已使用             共 26 次，累计 2 小时

  产品                   希捷 ST1000DM003-1SB102
  大小                   1 TB
  固件                   CC63
  缓存                   64 MB
  接口                   SATA III
  数据传输率             600.00 MB/秒
  特性                   S.M.A.R.T,  APM,  48-bit LBA,  NCQ
  硬盘已使用             共 23 次，累计 8 小时
  转速                   7200 转/分

--------[ 内存 ]----------------------------------------------------------------------------------

  ChannelA-DIMM1         三星 DDR4 2666MHz 8GB
  制造日期               2019 年 22 周
  型号                   M378A1K43CB2-CTD
  序列号                 325F222E
  厂商                   SAMSUNG
  模块位宽               64 Bits
  模块电压               SSTL 1.2V

  ChannelB-DIMM1         三星 DDR4 2666MHz 8GB
  制造日期               2019 年 22 周
  型号                   M378A1K43CB2-CTD
  序列号                 325F20A2
  厂商                   SAMSUNG
  模块位宽               64 Bits
  模块电压               SSTL 1.2V
  
### 制作流程 （黑苹果思路）
#### EFI结构图 （最终结果 opencore版本：0.8.1）
![image](https://user-images.githubusercontent.com/20026922/175478939-29957649-dfda-47ea-8eba-d8e3240221d7.png)

#### 定制流程 

1. 制作ACPI(SSDT)
2. 准备必要Kexts
   本机参考kexts [Efi-opencore-m425-n000-with-i7-8700-amd-rx6600xt](https://github.com/afly2020/Efi-opencore-m425-n000-with-i7-8700-amd-rx6600xt) 感谢@afly2020（去掉了A卡的驱动）
   
3. 配置config.plist 
   3.1 下载opencore-0.8.1 https://github.com/acidanthera/OpenCorePkg/releases/download/0.8.1/OpenCore-0.8.1-RELEASE.zip
   解压之后 取64位EFI文件夹
   https://dortania.github.io/OpenCore-Install-Guide/assets/img/ia32-x64.aa5dccd9.png![image](https://user-images.githubusercontent.com/20026922/175479582-e94393b1-22b4-41af-a7ae-047692c9078b.png)
   删除多余文件 最终结果参考[EFI结构图][EFI结构图 （最终结果 opencore版本：0.8.1）]

    https://dortania.github.io/OpenCore-Install-Guide/config.plist/coffee-lake.html
4. 由于此机主板只有HDMI和VGA口（VGA可以正常输出） 只接HDMI口后显示器黑屏
   
   
#### 参考文档
https://dortania.github.io/OpenCore-Install-Guide/prerequisites.html
