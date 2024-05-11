# 术语
空梦世界术语参考手册 Version.1.0.0

您可以使用左侧的目录来查看术语的详细信息，也可以通过目录上方的搜索来查找您需要的术语

对于受支持的浏览器，您通常可以使用 `Ctrl + F` 来搜索页面上的内容，这可以减少您的查找时间

我们不会对任何更新预先发出声明，也不会对任何过时的术语进行保留，如果您有需要查阅旧版本的手册，请在github翻阅历史提交记录

此处的术语仅在我们认为有必要的限度内进行解释，不会完全按照严谨的角度进行说明，为了便于理解，可能有些概念会被简化甚至是错误的

如果您对术语有任何疑问，或者希望添加新的术语，请联系我们

## IPv4/IPv6
### IPv4
IPv4是互联网协议第四版（Internet Protocol version 4）的简称，是目前广泛使用的网络层协议，也是互联网的基础协议。IPv4是一个32位地址空间的协议，理论上最多可以支持约42亿个地址。IPv4地址通常用点分十进制表示

例如：`192.168.1.1`

### IPv6
IPv6是互联网协议第六版（Internet Protocol version 6）的简称，是IPv4的下一代协议。IPv6的地址长度为128位，理论上最多可以支持约3400亿亿亿亿个地址。IPv6地址通常用冒号分隔的八组十六进制数表示

例如：`2001:0db8:85a3:0000:0000:8a2e:0370:7334`

在有些地方使用ipv6地址，您可能需要在两侧添加中括号，例如：`[2001:0db8:85a3:0000:0000:8a2e:0370:7334]`，这是一个历史遗留问题，不是所有软件都需要这样做

---
通常，您不需要在乎IPv4和IPv6的区别，因为大多数情况下，您只需要知道您的服务器的地址即可，而不需要关心它是IPv4还是IPv6

ip地址中有内网和外网地址的差异，内网地址在局域网以外无法被访问，而外网地址可以被全球范围内的设备访问

如果您需要自己和好友单独开房间联机，那么您需要注意这一点，我们不会为此提供支持

我们给出的服务器地址一定是外网地址，所以您不需要担心这个问题，只需要将地址填入游戏中即可

## IP地址/域名/端口
以我们编写时的java服务器地址为例（可能后续会发生变化）

**优先推荐（需要ipv6）**
```plaintext
mcv6.moeworld.top
mc.v6.moeworld.top:35578
```

**备用地址**
```plaintext
mcpc.moeworld.top
mc.moeworld.top
mc.moeworld.top:35578
```

这里有两种格式的地址，一些为单纯的域名，一些为域名+端口，这里简单的解释一下这三个概念

### IP地址
详细的解释请参阅上面的`IPv4/IPv6`章节，这里只是简单的说明

他们通常长这样：`192.168.1.1`

### 域名
域名是互联网上的一个地址，用于标识一个网站或者服务器，域名通常由多个部分组成，每个部分之间用点号分隔

例如我们的官网地址：[`projectmoeworld.tech`](https://project.moeworld.tech)

以及上方的例子：`mc.moeworld.top:35578`中的`mc.moeworld.top`

多数情况下，我们给出的服务器地址是域名，而不是IP地址，因为域名更容易记忆，并且ip发生变化时，我们可以通过修改域名解析来实现无缝切换

这意味着玩家（也就是您）无需在客户端中修改服务器地址，可以使用原有的域名继续访问服务器

### 端口
端口是一个数字，用于标识一个网络服务，端口通常是一个0-65535的数字，其中0-1023是系统保留端口

例如：`25565`和`19132`

若以上方的例子：`mc.moeworld.top:35578`中的`35578`

这两个端口是Minecraft游戏的默认端口，分别用于Java版和基岩版（携带版）

对于玩家来说，您只需按照我们给出的端口填入即可，不需要关心端口的具体含义

## 对于Minecraft填写地址的注意事项
### Java版
java版只有一个输入框用于输入服务器地址，您只需要将我们给出的地址直接填入即可，不管是域名还是ip地址，有没有端口号，都可以直接填入

例如`mc.moeworld.top:35578`

### 基岩版
基岩版有两个输入框，一个用于输入服务器地址，一个用于输入端口号，您需要将我们给出的地址填入服务器地址框，将端口号填入端口号框

以 `mc.moeworld.top:35578`为例，端口和域名以冒号分隔

`mc.moeworld.top`是域名，`35578`是端口，分别填入两个输入框，而不能单独写入一个框内

任何一个输入框填写错误都会无法加入服务器，所以请务必填写正确