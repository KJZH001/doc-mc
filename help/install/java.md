# 安装java
---

本文讲述的是如何在64位Windows上安装Microsoft JDK的安装版，我们不会教你如何使用绿色版JDK。

因为如果您具有使用绿色版jdk的能力，或者您是Linux/类Unix用户，以及为数不多的32位系统使用者，那么您也不存在阅读本教程的必要，我们相信您具有自己解决问题的能力。

**仅Minecraft Java版需要安装Java**，如果你选择基岩版进行游戏，不需要进行此步骤。

## 选择java版本

根据您的minecraft版本，选择适配的java版本。未列出的版本优先继承版本数字号较小的版本的要求。

| minecraft版本 | java最低版本 |
| ------------- | ------------ |
| 1.12.x        | 8            |
| 1.17.x        | 16           |
| 1.18.x        | 17           |
| 1.20.5        | 21（64位）   |

## 下载

以java17为例

打开 https://learn.microsoft.com/zh-cn/java/openjdk/download

![LG4xH.png](https://r2.img.cdn.loliloli.net/19d48d1c0382158a62dfb072681f2190/2024/05/11/LG4xH.png)

找到`OpenJDK 17/microsoft-jdk-17.0.11-windows-x64.msi`

点击下载，并打开安装。

请使用默认位置，一律点击下一步和我同意，不要进行其他更改。

其他版本可依葫芦画瓢

下列是其他可供选择的java

[Azul Zulu JDKs](https://www.azul.com/downloads/)

## 验证
打开cmd，输入`java -version`，如果类似出现以下内容，则安装成功。

```shell
openjdk version "17.0.11" 2024-04-16
OpenJDK Runtime Environment (build 17.0.11+9-0)
OpenJDK 64-Bit Server VM (build 17.0.11+9-0, mixed mode, sharing)
```
