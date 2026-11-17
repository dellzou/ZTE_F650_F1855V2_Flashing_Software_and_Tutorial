# 中兴 F650 / F1855V2（天翼网关 4.0）工具包

配套文章：[中兴 F650 / F1855V2 开 Telnet 与取超密](https://xiaozou123.cn/zte-f650-f1855v2-telnet-super-password/)

天翼网关 4.0 的两件事：把 Telnet 打开，把配置文件解出来看超密。仓库只放工具，`f650.bin` 在 Releases。

## 目录

- `TelnetONU1.2.1_cracked.exe`：老版开 T 工具，需要 `1.lic`
- `factorymode.exe` / `getinfo.exe` / `decrypt.exe`：工厂模式、信息读取、配置解密（一套）
- `ztecfg/`：配置解密工具，`命令.txt` 是原始用法记录
- `get_superpass/`：另一套取超密的组合（factorymode_crack + tftpd64 + ztecfg）
- `tftpd32.exe`：TFTP 服务端，配套 ini 已调好

## 已排除的文件

原包里这三类东西**没有**上传：

- `ztecfg/1.cfg`、`db_user_cfg.xml`：某台真实设备的解密配置，含超管密码、SN、MAC、SSID
- `userpass.txt`：工厂模式返回的会话级临时凭据
- `log/`：2019–2021 年的操作日志，含设备回显与登录名

自己备份配置时请放在本地，不要提交到公开仓库。

## 文件与 SHA256

| 文件 | 字节 |
|---|---|
| `1.lic` | 288 |
| `Cmd_Onu.txt` | 4,630 |
| `TFTPHost.ini` | 0 |
| `TelnetONU1.2.1_cracked.exe` | 77,824 |
| `date.dll` | 13 |
| `decrypt.exe` | 53,248 |
| `factorymode.exe` | 143,360 |
| `get_superpass/factorymode_crack.exe` | 872,448 |
| `get_superpass/tftpd64.exe` | 343,040 |
| `get_superpass/ztecfg.exe` | 7,037,223 |
| `get_superpass/说明.txt` | 179 |
| `getinfo.exe` | 229,376 |
| `tftpd32.exe` | 235,008 |
| `tftpd32.ini` | 616 |
| `ztecfg/ztecfg.exe` | 7,037,223 |
| `ztecfg/命令.txt` | 242 |

```
2801a741cfa7d5f4fc282462d024feb3064f6a52ca680804765ff84eca48e748  1.lic
e1c51e6d0b111833a4c9fcac5c303c5d79d53d3a727ccc16dc5f111bcb4874bc  Cmd_Onu.txt
e3b0c44298fc1c149afbf4c8996fb92427ae41e4649b934ca495991b7852b855  TFTPHost.ini
df26580326f9af4d4c8c874954e98bae7ea770060eaf7c530194f091b4a2dcb1  TelnetONU1.2.1_cracked.exe
04cf9377b7082835bd6c4fd26d268fa5fde7ac42f950db44f1ca4e39aa9b8c93  date.dll
d9e46a77a566b511fb154327637da91546086e34e02ba41c82b1f86c6746beb6  decrypt.exe
2efd80588d6ccb184e2d71d5c5e193f18609ddfc0be86a349698fe4f2f618a6c  factorymode.exe
e5fa3ca8a74a768c58abe7a0e552bbd66276353804604cbaa6c2479b95b9d702  get_superpass/factorymode_crack.exe
2f5de838cf3079723f1697e5fac2f75fad4b98cd81b165f87cdfa99ded22d801  get_superpass/tftpd64.exe
a14be5d00516fc8ca950e97347e4f6e3f535f354254542f746739407aa9e3f46  get_superpass/ztecfg.exe
aa38436d03b7b4529cf7f456ff484bb808c057c3f90c7fe2a80f95fe82bbfce3  get_superpass/说明.txt
e23a28d6e864287281fd7656f0e9cf63076b8c22a462b2c7f39c1321a176ff64  getinfo.exe
c34aa849239c81fcf97eb9e15c5f34f70a4d6cfcc0b0e88223186819832d2b7a  tftpd32.exe
0c00cbdae4e3f2f430ca803e2e08bb3cbba4e83cf9024dbb64da212b8034e60d  tftpd32.ini
a14be5d00516fc8ca950e97347e4f6e3f535f354254542f746739407aa9e3f46  ztecfg/ztecfg.exe
4f014b90d1e08051da1aabebc05903193a81e29bffde16d832635a49f9e177a3  ztecfg/命令.txt
```

## 相关仓库

同品牌其它机型，命令体系相近，排障时可以互相参照；每个仓库开头都对应一篇文章：

- [中兴 F673AV9 / F7015TV3 / F7610M 工具包](https://github.com/dellzou/ZTE_F673AV9_F7015TV3_F7610M_Flashing_Software_and_Tutorial)：中兴 F673AV9 / F7015TV3 / F7610M，一套命令通吃
- [中兴 F7607P 工具包](https://github.com/dellzou/ZTE_F7607P_Flashing_Software_and_Tutorial)：中兴 F7607P，改地区与电信版固件
- [中兴 G7610 工具包](https://github.com/dellzou/ZTE_G7610_Flashing_Software_and_Tutorial)：中兴 G7610，工厂模式、setmac 改码、配置解密
- [中兴 G7615 / G7611 工具包](https://github.com/dellzou/ZTE_G7615_G7611_Flashing_Software_and_Tutorial)：中兴 G7615 / G7611，改地区与分区刷写

## 免责声明

工具与固件均来自公开维修资料，仅供自有设备维修与学习使用。刷机有风险，操作前先备份，后果自负。
