## Ubuntu 16.04 Graphics Card Switching Between INTEL And NVIDIA
## this is from [source](https://www.jianshu.com/p/85cbb0258d32 "Ubuntu 16.04如何切换Intel集显与Nvidia独显")

一、安装NVIDIA显卡驱动(Install The Driver To Use NVIDIA Graphic Card)
  1. 先添加NVIDIA 的ppa 源：(First Add The PPA Source Of NVIDIA)
  ```
  sudo add-apt-repository ppa:graphics-drivers/ppa
  sudo apt-get update
  ```
  2. 打开软件和更新的附加驱动(Open The Software&Updates -> Additional Drivers)  
    
    里面会有很多选项(There Will Be Many Options)  
    默认会使用nouveau(Nouveau Is The Default Option)  
    运行如下命令查看显卡可用的驱动(Run The Following Command To View The Drivers Available For The Graphics Card)  
      sudo ubuntu-drivers devices
    对于我的设备，标记recommand的驱动是nvidia-430(For My Device, Nvidia-430 Has The Recommand Mark)
      sudo apt install nvidia-430  
二、切换集成显卡和独立显卡(Graphics Card Switching Between INTEL And NVIDIA)
    
  ```
  nvidia-settings
  ```
    里面的PRIME Profiles(Select The PRIME Profiles)
三、可能出现的问题(Probable Problems)
  1. 花屏或黑屏(The Screen May Not Work Properly)  
    
   * 关闭安全启动(Disable The Secure Boot)
   * 卸载Nvidia驱动(Uninstall The Nvidia Driver)
     ```
      sudo apt-get purge --remove nvidia-*
     ```
