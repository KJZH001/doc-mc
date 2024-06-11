# CoreProtect
---

著名的保护插件

官方wiki（英文）：[wiki](https://docs.coreprotect.net/)

中文百科（部分过时）：[mc插件百科](https://mineplugin.org/index.php?title=CoreProtect)
- - -

您可以使用 来访问以下命令。`/co`

## 命令概述

| 命令                         | 描述           |
| ---------------------------- | -------------- |
| [/co help](#co-help)         | 显示命令列表   |
| [/co inspect](#co-inspect)   | 切换检查器     |
| [/co lookup](#co-lookup)     | 查找块数据     |
| [/co rollback](#co-rollback) | 回滚块数据     |
| [/co restore](#co-restore)   | 恢复块数据     |

### 别名命令

| 命令     | 描述                        |
| -------- | --------------------------- |
| /co near | 执行半径为 5 的查找         |
| /co undo | 通过相反的操作还原回滚/还原 |

- - -

## 命令详细信息

_下面列出了详细的命令信息。_

### /co help

显示游戏中的命令列表。

- - -

### /co inspect

启用检查器。再次键入该命令以禁用它。您也可以只使用“/co i”。

- - -

### /co lookup

执行查找。几乎所有参数都是可选的。

| 命令       | 参数                                                              |
| ---------- | ----------------------------------------------------------------- |
| /co lookup | `u:<user> t:<time> r:<radius> a:<action> i:<include> e:<exclude>` |
| /co l      | _`/co lookup <params>`_                                           |

#### 参数

| 参数                       | 描述                         |
| -------------------------- | ---------------------------- |
| [`u:<user>`](#uuser)       | 指定要查找的用户。           |
| [`t:<time>`](#ttime)       | 指定查找的时间量。           |
| [`r:<radius>`](#rradius)   | 指定要限制查找的半径区域。   |
| [`a:<action>`](#aaction)   | 将查找限制为特定操作。       |
| [`i:<include>`](#iinclude) | 在查找中包含特定的块/实体。  |
| [`e:<exclude>`](#eexclude) | 从查找中排除块/实体。        |
| [`#<hashtag>`](#hashtag)   | 添加井号标签以执行其他操作。 |

#### 分页

如果返回多个页面，请使用该命令切换页面。  
若要更改页面上显示的行数，请使用 。`/co lookup <page>``/co lookup <page>:<lines>`

> _例如，`/co l 1：10` 将返回 10 行数据，从第一页开始。_

- - -

### /co rollback

执行回滚。使用与 /co 查找相同的[参数](#parameters)。  
_回滚可用于还原玩家操作。_

| 命令         | 参数                                                              |
| ------------ | ----------------------------------------------------------------- |
| /co rollback | `u:<user> t:<time> r:<radius> a:<action> i:<include> e:<exclude>` |
| /CO RB       | _`/co rollback <params>`_                                         |

- - -

### /co restore

执行还原。使用与 /co 查找相同的[参数](#parameters)。  
_还原可用于撤消回滚或还原玩家操作。_

| 命令        | 参数                                                              |
| ----------- | ----------------------------------------------------------------- |
| /co restore | `u:<user> t:<time> r:<radius> a:<action> i:<include> e:<exclude>` |
| /co rs      | _`/co restore <params>`_                                          |

- - -


## 参数详细信息

### `u:<user>`

_您可以指定单个用户或多个用户。_

*   例：`u:Notch`
*   例：`u:Notch,Intelli`
*   例：`u:#fire,#tnt,#creeper,#explosion`

- - -

### `t:<time>`

_您可以指定周、日、小时、分钟和秒。_  
_时间量可以组合，并且可以使用小数。_

*   例：`t:2w,5d,7h,2m,10s`
*   例：`t:5d2h`
*   示例：_（一到两个小时之间）_`t:1h-2h`
*   示例：_（两个半小时）_`t:2.50h`

- - -

### `r:<radius>`

_数字半径的目标在玩家位置的多个方块内。_

*   示例：_（定位到距离您所在位置 10 个街区以内的定位条件）_`r:10`
*   示例：_（定位特定世界）_`r:#world_the_end`
*   示例：_（面向整个服务器）_`r:#global`
*   示例：或_（以 WorldEdit 选区为目标）_`r:#worldedit``r:#we`

- - -

### `a:<action>`

_将命令限制为特定操作_

*   示例：_（仅包括放置的块）_`a:+block`

#### 行动

| 行动           | 描述                                   |
| -------------- | -------------------------------------- |
| `a:block`      | 放置/损坏的块                          |
| `a:+block`     | 放置的块                               |
| `a:-block`     | 块被打破了                             |
| `a:chat`       | 在聊天中发送的消息                     |
| `a:click`      | 玩家互动                               |
| `a:command`    | 使用的命令                             |
| `a:container`  | 从箱子里拿走或放在箱子里的物品         |
| `a:+container` | 放入箱子的物品                         |
| `a:-container` | 从箱子里拿走的物品                     |
| `a:inventory`  | 在玩家物品栏中添加或删除的物品         |
| `a:+inventory` | 添加到玩家物品栏的物品                 |
| `a:-inventory` | 从玩家物品栏中移除的物品               |
| `a:item`       | 玩家掉落、投掷、捡起、存放或取出的物品 |
| `a:+item`      | 玩家捡到或取出的物品                   |
| `a:-item`      | 玩家掉落、投掷或存放的物品             |
| `a:kill`       | 被杀的生物/动物                        |
| `a:session`    | 玩家登录/注销                          |
| `a:+session`   | 玩家登录                               |
| `a:-session`   | 玩家注销                               |
| `a:sign`       | 写在标志上的信息                       |
| `a:username`   | 用户名更改                             |

- - -

### `i:<include>`

_可用于指定块/项目/实体。_

*   示例：_（仅包括石头）_`i:stone`
*   示例：_（指定多个块）_`i:stone,oak_wood,bedrock`

> You can find a list of block names at [https://coreprotect.net/wiki-blocks](https://coreprotect.net/wiki-blocks).  
> You can find a list of entity names at [https://coreprotect.net/wiki-entities](https://coreprotect.net/wiki-entities).

- - -

### `e:<exclude>`

_可用于排除块/项目/实体/用户。_

*   示例：_（不包括 TNT）_`e:tnt`

- - -

### `#<hashtag>`

在命令末尾添加井号标签以执行其他操作。

*   示例：_（执行回滚预览）_`#preview`

#### 主题标签

| 标签       | 影响                          |
| ---------- | ----------------------------- |
| `#preview` | 预览回滚/还原                 |
| `#count`   | 返回在查找查询中找到的行数    |
| `#verbose` | 在回滚/还原期间显示其他信息   |
| `#silent`  | 在回滚/还原期间显示最少的信息 |

- - -

## 示例命令

### 示例回滚命令

默认情况下，如果未指定半径，则将应用半径 10，将回滚限制在距离您 10 个街区以内。用于执行全局回滚。`r:#global`

*   `/co rollback Notch t:1h`  
    _（回滚缺口 1 小时（默认半径为 10））_
*   `/co rollback u:Notch,Intelli t:1h #preview`  
    _（预览：将 Notch 和 Intelli 回滚 1 小时（默认半径为 10））_
*   `/co rollback u:Notch t:23h17m`  
    _（回滚缺口 23 小时 17 分钟（默认半径为 10））_
*   `/co rollback u:Notch t:1h i:stone`  
    _（仅回滚 Notch 在过去一小时内放置/破坏的石头（默认半径为 10））_
*   `/co rollback u:Notch t:1h i:stone a:-block`  
    _（回滚 仅在过去一小时内被缺口打破的石头（默认半径为 10））_
*   `/co rollback u:Notch t:1h r:#global e:stone,dirt`  
    _（回滚 Notch 在过去一小时内所做的一切，除了放置/损坏的石头和污垢）_
*   `/co rollback u:Notch t:1h r:20`  
    _（回滚悲伤 Notch 在距离你 20 个街区以内的最后一个小时内所做的）_
*   `/co rollback u:Notch t:1h r:#nether`  
    _（回滚悲伤 Notch 在最后一个小时只在下界）_
*   `/co rollback u:Notch t:5m a:inventory`  
    _（Notch在过去5分钟内回滚库存交易记录）_
*   `/co rollback t:15m r:30`  
    _（回滚您 15 个街区内 30 分钟内完成的所有事情）_
*   `/co rollback t:15m r:#worldedit`  
    _（回滚过去 15 分钟内在 WorldEdit 选区中完成的所有操作）_

- - -

### 查找命令示例

查找命令通常与回滚命令相同。主要区别在于默认半径不应用于查找，这意味着默认情况下所有查找命令都执行全局搜索。

*   `/co lookup i:diamond_ore t:1h a:-block`  
    _（查找过去一小时内开采的所有钻石矿石）_
*   `/co lookup u:Notch t:30m a:chat`  
    _（Notch在过去30分钟内发送的查找聊天消息）_
*   `/co lookup u:Notch t:3d a:inventory`  
    _（按 Notch 查找过去 3 天内的库存交易记录）_
*   `/co lookup u:Notch a:login`  
    _（查找Notch曾经完成的所有登录）_
*   `/co lookup u:Notch a:login`  
    _（查找Notch曾经完成的所有登录）_
*   `/co lookup u:Notch a:username`  
    _（查找 Notch 以前使用的用户名）_

- - -