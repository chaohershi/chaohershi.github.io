---
permalink: /Change-Xiaomi-Mi-Notebook-Pro-Keyboard-Layout/
title: 小米笔记本Pro键帽及键位位置调整
---

因个人习惯想要调整一下键盘布局，将Home、End、PgUp、PgDn调整为Home、PgUp、PgDn、End。这篇文章将介绍如何操作。整个流程并不复杂。

## 调整键帽位置

将End、PgUp、PgDn三个按键的键帽扣下。

扣键帽时，先扣右上角：从键帽的右侧上方，慢慢施力，向左侧方向抬起，直至听到脆响。再扣左上角：从键帽左侧上方，向右向上抬起，直至听到脆响。上半部分扣下后，向下滑动，键帽即可脱落。

调整好布局后，将键帽摆正，向下按压至扣上。

![小米笔记本Pro键帽特写](https://chaohershi.github.io/images/Xiaomi_Mi_Notebook_Pro_Key_Cap.png "小米笔记本Pro键帽特写")

## 调整键位映射

向注册表中写入:
```
[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Keyboard Layout]
"Scancode Map"=hex:00,00,00,00,00,00,00,00,04,00,00,00,51,e0,49,e0,49,e0,4f,e0,4f,e0,51,e0,00,00,00,00
```

完成后重启电脑，即可将End、PgUp、PgDn映射为PgUp、PgDn、End。

[点我下载注册表文件](https://chaohershi.github.io/assets/Remap_Keys_from_End_PgUp_PgDn_to_PgUp_PgDn_End.zip)

## 完成效果

![小米笔记本Pro键帽及键位位置调整前后对比图](https://chaohershi.github.io/images/Xiaomi_Mi_Notebook_Pro_Keyboard_Layout_Change.png "小米笔记本Pro键帽及键位位置调整前后对比图")

---

参考资料：
- [【原创】巧克力键盘的键帽最安全省力拆卸方法 - ThinkPad 专区 - 专门网论坛 - 专业的笔记本电脑技术交流社区](https://forum.51nb.com/thread-1803503-1-1.html)
- [How to Disable Caps Lock Key in Windows 7, 8, 10, or Vista](https://www.howtogeek.com/howto/windows-vista/disable-caps-lock-key-in-windows-vista/)
- [Map Any Key to Any Key on Windows 10, 8, 7, or Vista](https://www.howtogeek.com/howto/windows-vista/map-any-key-to-any-key-on-windows-xp-vista/)
- [Remapping keys without external software](https://superuser.com/questions/514903/remapping-keys-without-external-software)
