# matebook-13/14-2019-OpenCore 黑苹果 hackintosh 
  
如果你不会安装，需要安装服务，联系微信ske1996
可提供收费安装服务，帮你弄好一切可以弄好的驱动，并且保修1个月，收费200，非诚勿扰  

[中文🇨🇳](readme.md) | [日本語🇯🇵](readme-jp.md) | [English🇬🇧](readme-en.md)   

⚠️一定要先看下面的更新日志  

有问题只在github免费答疑，不在微信进行答疑，想白嫖请在github提交issue，微信答疑一问50，【想白嫖请在github提交issue】  

⚠️如果你访问这个网页显示发现图片挂了，那你一定要整个vpn再来看这个网站，因为有些教程里面图片很重要  
⚠️无法下载我这里的东西也可以通过连接vpn来解决

如果可用请在issues中提交你的机器信息（年份，cpu，matebook13还是14）  
用于构建更好的efi。 

我希望有问题的人都可以在issue里面提交，我会回答你，这个答案会一直保存下来，这样可以帮助很多小白的朋友，这些都是经验  

     


## 更新日志  
<details>  
<summary>点击以查看详细信息</summary>  
  
 
- 20200724:  
1.重新拆包分析了最新的1.28的bios，cfglock的偏移地址依旧是0x3E，因此教程依旧可用  
2.更新了关于HIDPI的注意事项  
3.更新oc至0.5.9  



- 20200715:  
耳机接口修复成功，已更新耳机接口修复教程，在下面就可以找到  

- 20200712:  
已知本efi可同时用于matebook 13/14 2019  
于2020版本测试情况如下：  
除了wifi不能驱动一切同2019版本，原因可能是2020版本采用了第二代9560

- 20200710:  
添加了配置好的clover的efi文件用于安装，虽然也可以用这个clover文件复制到esr分区用于引导   
但是强烈建议使用oc的efi引导你的hackintosh  

- 20200709:  
1.更改了三码  
2.添加了保险文件（WRCOVERY.BIN）  
用法：放入esr分区，与EFI文件夹并列即可

![image](https://github.com/ske1996/matebook-13-2019-oc-efi/blob/master/%E6%9D%82%E9%A1%B9/recovery.png?raw=true)
</details>
下一个版本可能更新bigsur的EFI

## 正常可用的部件：
  
  
1.蓝牙（无需热启动）[@zxystd](https://github.com/OpenIntelWireless/itlwm)  
【华为的蓝牙鼠标不可用！！！去买一个罗技的或是苹果的就行了】  


2.wifi可用 （⚠️需要用propertree([点击下载](https://github.com/ske1996/matebook-13-2019-oc-efi/raw/master/ProperTree.zip))注入你自己的ssid跟password➡️[教程链接](http://bbs.pcbeta.com/forum.php?mod=viewthread&tid=1848662)）[@zxystd](https://github.com/OpenIntelWireless/itlwm)

3.睡眠正常

4.hdmi正常（可音频输出）

5.触摸板正常

6.解锁cfg lock后可完美原生电源管理

7.已注入缓冲帧 核显正常

8.cpu变频正常（补充：此efi内涵cpufriend，设置为：1800mhz，最高性能）

9.usb已定制（通过ssdt定制）

10.键盘快捷键正常  

11.耳机接口正常（需要使用下面的【安装ComboJack实现耳机耳麦切换，改进电流声】）

  
  
## 无法正常工作的部件：  


1.摄像头（UVC Camera VendorID_1480 ProductID_975这个可用）

2.mx250独显（这个是废话）

  
## 个人使用版本信息等   
<details>  
<summary>点击以查看详细信息</summary>  
oc版本0.5.8

自用macos版本：10.15.5. 

matebook2019 i7-8565u mx250 sn720
</details>  

## 安装方法：  


先于此blog下载：10.15.5 19F101 双EFI分区版

这个文章很长，使劲往下翻，或使用网页搜索功能

下载链接
：https://blog.daliansky.net/macOS-Catalina-10.15.5-19F96-Release-version-with-Clover-5118-original-image-Double-EFI-Version-UEFI-and-MBR.html
  
    
      
## 安装视频教程：

https://www.bilibili.com/video/BV1jJ41127YT/?spm_id_from=333.788.videocard.0
  
如果你不会安装，需要安装服务，联系微信ske1996
可提供收费安装服务，并且保修1个月  

有问题只在github免费答疑，不在微信进行答疑，想白嫖请在github提交issue，微信勿扰  

## 安装注意点：  
<details>  
<summary>点击以查看详细信息</summary>  

1.安装使用的镜像推荐使用我给的链接下载的那个，不要用他给的，以内有点旧了

2.视频的【03:57】他说把配置好的clover文件解压到这个文件夹下时，将我的库中的【安装用clover的EFI】放进去  

3.视频的【14:37】开始他开始吧u盘的clover efi复制进ESR（EFI）分区，这一步复制我的oc的efi进去。注意：这一步的efi跟第二步不一样，这一步用oc的

4.视频的【16:44】开始是使用easyuefi创建efi引导，这一步前面都跟他视频一样，他怎么点你就怎么点，只不过，选择引导文件为：EFI/BOOT/BOOTx64.efi
  
</details>

## 安装ComboJack实现耳机耳麦切换，改进电流声。（修复耳机接口）
<details>  
<summary>点击以查看详细信息</summary>   
  
参考： 

![image](https://github.com/ske1996/matebook-13-2019-oc-efi/blob/master/%E6%9D%82%E9%A1%B9/audiojack.png?raw=true)



在这里下载由Heporis制作的ComboJack.

https://github.com/randomprofilename/ComboJack


终端运行下面路径的脚本
```bash
ComboJack_Installer/install.sh
```
  
</details>

## 开启HIDPI：
<details>  
<summary>点击以查看详细信息</summary>  
https://github.com/xzhih/one-key-hidpi
 

我说下我的选择：  
第一步选择 开启HiDPi  
第二步选择 保持原样  
第三步选择 手动输入分辨率  
分辨率输入的是 1600x1066 1343x895 2160x1440  

- 最后说一句，开启了hidpi之后，在设置→显示器里不要让分辨率超过1343x895，最大只能到这个，因为超过这个会引发一些唤醒后屏幕显示的问题（比如唤醒后屏幕只显示到四分之三），而且不要觉得这个分辨率小，因为这个是hipdi分辨率，跟你理解的分辨率不一样，1343×895实际上等于你理解的一般分辨率的2686×1790，是超过2k的，如下图所示  

*注意⚠️你的1343x895这个分辨率的设置位置不一定是在【更大空间】  

![image](https://github.com/ske1996/matebook-13-2019-oc-efi/blob/master/%E6%9D%82%E9%A1%B9/HIDPI.png?raw=true)  

*注意⚠️你的1343x895这个分辨率的设置位置不一定是在【更大空间】

</details> 

## 解锁CFG：
<details>  
<summary>点击以查看详细信息</summary>  

关于解锁cfg后能做到什么？  
完美的电源管理  
CPU完美变频  
完美睡眠（我个人经验：睡眠6H只掉了1%的电） 


以下教程来自：  
https://zhuanlan.zhihu.com/p/121655468

先去华为官网升级bios至1.28

然后找偏移地址就不用做了，我告诉你，就是0x3E  

【⚠️千万不要用oc去引导ru！！】懂得人自然懂，收起那个想法，老老实实按我下面写的来  

- U盘准备阶段：  
（大小无所谓）  

1.先准备一个u盘，格式化为fat32  
2.u盘里创建文件夹：EFI  
3.打开EFI文件夹，在里面创建文件夹BOOT  
4.复制[cfgunlock.zip(点击下载)](https://github.com/ske1996/matebook-13-2019-oc-efi/raw/master/cfgunlock.zip)里面的bootx64.efi进U盘的EFI/BOOT下  
5.关机后开机按F12使用这个U盘去引导，然后进入修改bios底层阶段  

- 以下为修改bios底层阶段：  
1. 进入后 ‘alt’ + ’=‘ 切换进 ACPI Variable  
2. 用pageup/pagedown/上下方向键找到 CPUSetup  
3. 回车进入然后用上下左右方向键找到对应的地址（也就是0x3e，那么就是纵坐标03，横坐标0e的位置）  
![image](https://github.com/ske1996/matebook-13-2019-oc-efi/blob/master/%E6%9D%82%E9%A1%B9/RU.jpg?raw=true)  
4. 一看，确实是0x01，那么回车，输入0 就可以看到它变成了0  
5. 使用'crtl' + 'w' 来保存 保存的时候屏幕上会直接显示update written 的，这说明已经写入了  
6. 使用'alt' + 'q' 来退出，然后即可回到引导进入系统了，CFG已经解锁  

</details> 

  
如果你不会安装，需要安装服务，联系微信ske1996，可提供收费安装服务，并且保修1个月
      
## 解决window与macos时间不同步/显示不正确
<details>  
<summary>点击以查看详细信息</summary>  
  
  
  
在windows下面WIN+x 选择管理员模式进入CMD  
  
  执行以下命令：  
  
```bash
Reg add HKLM\SYSTEM\CurrentControlSet\Control\TimeZoneInformation /v RealTimeIsUniversal /t REG_DWORD /d 1
```  
</details>   

## 如果你用了我的efi觉得好用，要是想打赏小的，请选择一个你喜欢的方式打赏五块钱，谢谢！


微信收款码链接：

![image](https://github.com/ske1996/matebook-13-2019-oc-efi/blob/master/%E6%9D%82%E9%A1%B9/%E5%BE%AE%E4%BF%A1.jpg?raw=true). 
  
  

支付宝收款码链接：

![image](https://github.com/ske1996/matebook-13-2019-oc-efi/blob/master/%E6%9D%82%E9%A1%B9/%E6%94%AF%E4%BB%98%E5%AE%9D.jpg?raw=true)

  
  
    
    
  
  
如果可用请在issues中提交你的机器信息（年份，cpu，matebook13还是14）  
用于构建更好的efi

## 感谢：

- @intel 感谢10年一管牙膏

- @apple 感谢创造出macos

- [@zxystd](https://github.com/OpenIntelWireless/itlwm) 感谢创造出wifi以及蓝牙的驱动

- [@MoZyo](https://github.com/MoZyo/RedmiBook-13-10th-Gen-Intel-Hackintosh) 教会了我很多东西

- [@Edoardo001](https://github.com/Edoardo001/Matebook-13-Hackintosh) 我做黑苹果的入门引路人 感谢他在matebook13的clover版efi上的杰出贡献

- [@Zero-zer0](https://github.com/Zero-zer0) 参考了他的热键修复方法 十分感谢

