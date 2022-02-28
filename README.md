# MIUI bug上报 在MIUI下运行高德Flutter 3D地图插件返回时闪退

闪退时会抛出以下错误信息，从描述上来看和内存扩展有关，但尝试关闭内存扩展重启后再试仍然存在此问题。  
且使用Android Studio的Profiler并没有观察到内存异常现象
![image](https://user-images.githubusercontent.com/34338289/155953059-842e7dd2-ab96-417b-9cf1-c823e8c95aac.png)

# bug触发条件
1. 下载[此处的apk](https://github.com/DubheBroken/FlutterAMapCrashInMIUI/releases/tag/bugreport)  
2. 安装在MIUI 12以上的小米手机上  
3. 打开运行，授予定位权限。  
4. 点击右下角的加号图标，会弹出3D地图界面  
5. 等待地图加载完成后，点击返回键  
6. 点击返回键后会回到第一个界面，随后会在3秒内发生崩溃（必现）

# 已知bug触发信息
触发概率：必现

已知的会产生此问题的设备和系统：
| 设备名	| 代号 | MIUI版本 | 安卓版本 |
|  ----  | ----  | ---- | ---- | 
| 红米K40 Pro+ |	haydn |	MIUI 13.0.3 |	Android 12 |
| 小米mix4 |	odin |	MIUI 13 开发版 V13.0.4.1.7.DEV |	Android 12 |
| 小米9 |	cepheus |	MIUI 12.5 |	Android 11 |
| 小米10 Ultra |	cas |	MIUI 12.5 |	Android 11 |

已知的不会产生此问题的设备和系统：
| 设备名	| 代号 |	系统版本 |	安卓版本 |
|  ----  | ----  | ---- | ---- | 
| Pixel 3 XL |	crosshatch |	SP1A.210812.016.C1 |	Android 12 |
| 荣耀9X |	HLK-AL00 |	鸿蒙2.0.0 |	Android 10 |

# 代码调试引导
如果你想查看代码并在复现此问题时实时调试。请`clone`本项目，使用Android Studio打开运行。  
请配置Flutter SDK、Dart SDK、为Android Studio安装Flutter和Dart插件，之后再打开项目。  
版本参考：  
Android Studio 2020.3.1  
Flutter 2.10.0 Stable  
Dart 2.16.0

# 参考资料
[高德地图Flutter插件集成文档](https://lbs.amap.com/api/flutter/guide/map-flutter-plug-in/map-flutter-info)  
[Flutter环境配置指南-Flutter中文网](https://flutterchina.club/get-started/install/)
[logcat中的参考url](https://source.android.com/devices/tech/debug/tagged-pointers)
