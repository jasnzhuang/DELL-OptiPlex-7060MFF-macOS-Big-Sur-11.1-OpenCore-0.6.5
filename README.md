# DELL-OptiPlex-7060MFF-macOS-Big-Sur-11.1-OpenCore-0.6.5
 

前言：
前段时间发现小黄鱼上出现戴尔 7060MFF (5060MFF&3060MFF) ，近期就Dell OptiPlex 7060MFF进行黑苹果的研究和安装，目前已经完成最新版系统Big Sur 11.1的安装，正在使用，目前未发现较大问题，该小主机日常使用还是比较安静的，简单办公还是靠谱的。

硬件规格：
Dell OptiPlex 7060 Micro Form Factor
处理器: Intel® Core™ i5-8600T
核显: Intel® UHD Graphics 630
内存: 16GB DDR4 2666 (枭鲸单条)
硬盘: WD SN550 NVMe SSD 500G
Wi-Fi & Bluetooth: BCM94360CS2 +NGFF 反向转接卡

已解决：
4K状态下的休眠唤醒问题
DP连接时的音频输出
已定制USB

问题：
目前已知问题：麦克风无法使用

要点：
BIOS设置
BIOS版本1.8.0
General → Advanced Boot Options: 不勾选
System Configuration → SATA Operation: AHCI
Secure Boot → Secure Boot Enable: 不勾选
Intel® Software Guard Extensions™ → Intel® SGX™ Enable: Disabled
Power Management → Block Sleep: 不勾选
Virtualization Support → VT for Direct I/O: 不勾选
GURB调整
预分配的DVMT调整： setup_var 0x8DC 0x02
禁用CFG锁定： setup_var 0x5BE 0x00
