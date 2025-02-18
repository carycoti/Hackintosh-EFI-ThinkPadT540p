# Hackintosh-EFI-ThinkPadT540p
## 联想ThinkPad T540p，黑苹果，EFI

### 软件版本
| 软件 | 版本 |
| --- | :--: |
| 系统 | macOS Big Sur 11.7.1 (20G918) |
| 引导 | OpenCore v0.8.5 |

### 自选硬件
|   硬件    |   型号  |
| -------- | :----: |
| 主机 | 联想 ThinkPad T540p |
| CPU | Intel Core i5 4300MQ |
| 内存 | 三星 DDR3 1600 8G+4G |
| 硬盘 | Sata 60GB |
| 显卡 | Intel HD Graphics 4600 |
| 屏幕 | 720p屏 |
| 无线网卡 | Intel 7260AC |

### 完成度

+ 核显正常驱动，2048MB显存
+ 声卡正常驱动
+ Wi-Fi正常驱动，蓝牙不稳定(蓝牙连接音响正常，声音不卡顿；连接罗技AnyWhere3蓝牙鼠标失败)，隔空投送不能用
+ USB定制，所有USB接口正常
+ SD卡读卡器正常驱动
+ 双盘双系统，OC可引导Win10

### 缺陷

+ 引导界面不能图形化，不懂原因，估计是BIOS设置的问题
+ 睡眠花屏，禁用睡眠、休眠（转发CSDN教程原文地址：[黑苹果完全禁用睡眠](https://blog.csdn.net/fjh1997/article/details/112559539)）
```bash
# Before doing anything, save your current configuration using
pmset -g
# To disable sleep 彻底禁用
sudo pmset -a sleep 0; sudo pmset -a hibernatemode 0; sudo pmset -a disablesleep 1;
# And to go back to normal 还原
sudo pmset -a sleep 1; sudo pmset -a hibernatemode [original hibernatemode value]; sudo pmset -a disablesleep 0;
```
+ Intel网卡，蓝牙不稳定(蓝牙连接音响正常，声音不卡顿；连接罗技AnyWhere3蓝牙鼠标失败)，且隔空投送不能用

### 备注
1. PlatformInfo的机型选择，必须选“MacBookPro11,1”，否则引导卡进度条
2. DeviceProperties的核显缓冲帧补丁，PciRoot(0x0)/Pci(0x2,0x0)，AAPL,ig-platform-id为0300220D，device-id为12040000。虽然看起来与当前核显型号不符，但是更换成其它的，引导卡进度条

### 效果图
![关于本机.png](https://gitee.com/kangla/hackintosh-efi-think-pad-t540p/blob/main/OpenCore%20v0.8.5%20&%20macOS%20Big%20Sur%2011.7.1%20(20G918)/%E5%85%B3%E4%BA%8E%E6%9C%AC%E6%9C%BA.png "关于本机")
![PlatformInfo机型选择.png](https://github.com/demon3434/Hackintosh-EFI-ThinkPadT540p/blob/main/OpenCore%20v0.8.0%20%26%20macOS%20Big%20Sur%2011.6.5%20(20G527)/2.OCC%E6%9C%BA%E5%9E%8B%E9%80%89%E6%8B%A9.png "PlatformInfo机型选择")
![核显缓冲帧补丁.png](https://github.com/demon3434/Hackintosh-EFI-ThinkPadT540p/blob/main/OpenCore%20v0.8.0%20%26%20macOS%20Big%20Sur%2011.6.5%20(20G527)/3.%E6%A0%B8%E6%98%BE%E7%BC%93%E5%86%B2%E5%B8%A7%E8%A1%A5%E4%B8%81.png "核显缓冲帧补丁")
![Hackintool系统信息.png](https://github.com/demon3434/Hackintosh-EFI-ThinkPadT540p/blob/main/OpenCore%20v0.8.0%20%26%20macOS%20Big%20Sur%2011.6.5%20(20G527)/4.Hackintool%E7%B3%BB%E7%BB%9F%E4%BF%A1%E6%81%AF.png "Hackintool系统信息")
