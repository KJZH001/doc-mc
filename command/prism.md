# Prism
## 简介
> Prism (棱镜) 是一款强大的、高效的服务器防熊管理插件，有着回滚、还原等多个功能。 它速度惊人，用途广泛，易于使用。 让熊孩不再破坏游戏的乐趣！

本站提供了一部分文档。

你可以直接在服务器内使用 `/prism help` 获取帮助。

或者查询wiki。

* [汉化wiki](https://prism-cn.readthedocs.io/zh-cn/latest/index.html)
* [英文原版wiki](https://prism-bukkit.readthedocs.io/en/latest/Welcome.html)

---

## 命令

* 查询
  * `/prism lookup <参数> <标志>`
  * `/pr l <参数> <标志>`
  * `/pr 查询 <参数> <标志>`
  
  ![查询图像](https://prism-cn.readthedocs.io/zh-cn/latest/_images/prism_standard_display.png)

* 未完待续......

## 参数

> “参数”(Parameters) 指的是在 Prism 的 查询、预览、回滚、还原 等指令中使用的”参数”(arguments). 使用它们可以准确地定义 Prism 需要操作的数据.
> 
> 您可以定义每一个参数、一部分参数、或者不定义任何参数. (如果没有定义则为安全的默认值) 您可以无序地排列它们.
> 
> 对于大多数的参数类型, 您可以使用逗号来定义多个参数. 例如 a:break,place.
> 
> 玩家可能收到的常见错误可能是: 您遗漏了有效的行为. 使用 /prism ? 来获取帮助.
>

### 参数列表
+   `a:[行为]` - 例如 “block-break” (您可以在下面看到一个完整的列表). 默认值为所有行为.
    
+   `r:[半径]` - 查询您附近多少格方块半径内的事件记录, 例如 `r:20`. 默认值为配置文件中所设值.
    
+   `r:global` `r:全局` - 指示 Prism 不要限制记录的位置, 在全世界各个位置中查询. 使用此参数需要特别地在配置文件中配置, 或拥有针对于 查询/回滚/还原 操作使用的权限.
    
+   `r:we` - 使用 WorldEdit 选区来限制记录的位置. 可以配合 查询/回滚/还原 操作使用. 对任何支持\`\`r\`\`参数的记录都有效. 玩家必须拥有 WorldEdit 选区权限.
    
+   `r:玩家名:[半径]` 将半径中心定义到另一玩家处.
    
+   `r:x,y,z:[半径]` - 将半径中心定义到坐标 x,y,z 处.
    
+   `r:world` `r:世界` - 不限制半径, 但将世界限制为当前所处世界或者 w: 参数定义的世界.
    
+   `r:c` `r:区块` - 限制半径范围内目前所处的区块 (目前区块的 x/z, 基岩层到世界高度这个长方体范围内)
    
+   `b:[方块名/方块ID]` - 例如 b:grass 、b:2 和\`b:2:0\`. 没有默认值.
    
+   `e:[实体名]` - 例如 e:pig. 没有默认值.
    
+   `t:[时长]` - 从 x 时长后发生的事件. 例如1(seconds|秒), 20m(minutes|分), 1h(hour|时), 7d(days|天), 2w(weeks|周). 没有默认值. 您也可以配合多个单位使用, 例如 `1时20分`.
    
+   `before:[时长]` - 在 x 时长前发生的事件.
    
+   `since:[时长]` - 从 x 时长后发生的事件 (等同于 t:).
    
+   `p:[玩家名]` - 例如 `p:viveleroi`. 没有默认值.
    
+   `w:[世界名]` - 例如 `w:world_nether`. 默认值为所处的世界.
    
+   `k:[关键字]` - 基于文本的关键字搜索 (主要适用于 指令/聊天 事件).
    
+   `id:[ID]` - 单个的记录 id.


### 行为列表

| 行为              | 可回滚 | 可还原 | 简述                                                   | 权限状态 |
| ----------------- | ------ | ------ | ------------------------------------------------------ | -------- |
| block-break       | ✔️      | ✔️      | 任何被破坏的方块.                                      | ✔️        |
| block-burn        | ✔️      | ✔️      | 任何被烧掉的方块.                                      | ✔️        |
| block-dispense    | ❌      | ❌      | 一个方块中发射出去的物品.                              | ✔️        |
| block-fade        | ✔️      | ✔️      | 一个消亡的方块, 例如雪融化,树叶在断开与树的连接后消亡. | ✔️        |
| block-fall        | ✔️      | ✔️      | 例如沙子坠落.                                          | ✔️        |
| block-form        | ✔️      | ✔️      | 形成圆石或形成冰.                                      | ✔️        |
| block-place       | ✔️      | ✔️      | 任何被放置的方块.                                      | ✔️        |
| block-shift       | ❌      | ❌      | 被活塞推动的方块.                                      | ✔️        |
| block-spread      | ✔️      | ✔️      | 方块有机地蔓延, 如草方块.                              | ✔️        |
| block-use         | ❌      | ❌      | 使用方块, 如工作台.                                    | ✔️        |
| bucket-fill       | ❌      | ❌      | 填装一个桶.                                            | ✔️        |
| bonemeal-use      | ❌      | ❌      | 使用骨粉.                                              | ✔️        |
| container-access  | ❌      | ❌      | 使用一个容器.                                          | ✔️        |
| cake-eat          | ❌      | ❌      | 食用地上的蛋糕.                                        | ✔️        |
| craft-item        | ❌      | ❌      | 合成一个物品.                                          | ❌        |
| creeper-explode   | ✔️      | ✔️      | 苦力怕爆炸.                                            | ✔️        |
| crop-trample      | ✔️      | ✔️      | 损坏农作物.                                            | ✔️        |
| dragon-eat        | ✔️      | ✔️      | 末影龙吃掉方块.                                        | ✔️        |
| enchant-item      | ✔️      | ✔️      | 附魔一个物品.                                          | ❌        |
| enderman-pickup   | ✔️      | ✔️      | 末影人拿起方块.                                        | ✔️        |
| enderman-place    | ✔️      | ✔️      | 末影人放置方块.                                        | ✔️        |
| entity-break      | ✔️      | ✔️      | 实体破坏一个方块.                                      | ✔️        |
| entity-dye        | ❌      | ❌      | 染色一个物品.                                          | ❌        |
| entity-explode    | ✔️      | ✔️      | 实体爆炸.                                              | ✔️        |
| entity-follow     | ❌      | ❌      | 实体跟随一个玩家.                                      | ✔️        |
| entity-form       | ✔️      | ✔️      | 形成一个实体.                                          | ✔️        |
| entity-kill       | ✔️      | ✔️      | 实体被击杀.                                            | ✔️        |
| entity-leash      | ❌      | ❌      | 实体被栓绳拴住.                                        | ✔️        |
| entity-shear      | ❌      | ❌      | 实体被剪刀剪.                                          | ✔️        |
| entity-spawn      | ❌      | ❌      | 实体被生成.                                            | ✔️        |
| entity-unleash    | ❌      | ❌      | 实体被解拴.                                            | ✔️        |
| fireball          | ❌      | ❌      | 使用火球点火.                                          | ✔️        |
| fire-spread       | ✔️      | ✔️      | 火焰蔓延.                                              | ✔️        |
| firework-launch   | ✔️      | ✔️      | 发射烟花.                                              | ✔️        |
| hangingitem-break | ✔️      | ✔️      | 例如画被破坏.                                          | ✔️        |
| hangingitem-place | ✔️      | ✔️      | 例如画被放置.                                          | ✔️        |
| item-drop         | ✔️      | ✔️      | 丢弃一个物品到地上.                                    | ✔️        |
| item-insert       | ✔️      | ✔️      | 将物品放入容器.                                        | ✔️        |
| item-pickup       | ✔️      | ✔️      | 拾起地上的掉落物.                                      | ✔️        |
| item-remove       | ✔️      | ✔️      | 拿出容器内的物品.                                      | ✔️        |
| item-rotate       | ❌      | ❌      | 旋转物品展示框内的物品.                                | ✔️        |
| lava-break        | ❌      | ❌      | 熔岩破坏一个方块.                                      | ✔️        |
| lava-bucket       | ✔️      | ✔️      | 收集熔岩.                                              | ✔️        |
| lava-flow         | ✔️      | ✔️      | 熔岩流动.                                              | ✔️        |
| lava-ignite       | ❌      | ❌      | 熔岩点燃周围的环境.                                    | ✔️        |
| leaf-decay        | ✔️      | ✔️      | 树叶凋落.                                              | ✔️        |
| lighter           | ❌      | ❌      | 使用打火石.                                            | ✔️        |
| lightning         | ❌      | ❌      | 闪电劈下来.                                            | ✔️        |
| mushroom-grow     | ✔️      | ✔️      | 蘑菇树生长.                                            | ✔️        |
| player-chat       | ❌      | ❌      | 玩家聊天.                                              | ❌        |
| player-command    | ❌      | ❌      | 玩家执行指令.                                          | ❌        |
| player-death      | ❌      | ❌      | 玩家死亡.                                              | ✔️        |
| player-join       | ❌      | ❌      | 玩家进入服务器.                                        | ❌        |
| player-kill       | ✔️      | ❌      | 击杀玩家.                                              | ❌        |
| player-quit       | ❌      | ❌      | 玩家离开服务器.                                        | ❌        |
| player-teleport   | ❌      | ❌      | 玩家传送.                                              | ❌        |
| potion-splash     | ❌      | ❌      | 玩家掷出喷溅药水.                                      | ✔️        |
| sheep-eat         | ❌      | ❌      | 绵羊吃草.                                              | ✔️        |
| sign-change       | ❌      | ✔️      | 修改告示牌上的文本.                                    | ✔️        |
| spawnegg-use      | ❌      | ❌      | 使用刷怪蛋.                                            | ✔️        |
| tnt-explode       | ✔️      | ✔️      | TNT 爆炸.                                              | ✔️        |
| tnt-prime         | ❌      | ❌      | 点燃 TNT.                                              | ❌        |
| tree-grow         | ✔️      | ✔️      | 树生长.                                                | ✔️        |
| vehicle-break     | ✔️      | ❌      | 破坏载具.                                              | ✔️        |
| vehicle-enter     | ❌      | ❌      | 进入载具.                                              | ✔️        |
| vehicle-exit      | ❌      | ❌      | 离开载具.                                              | ✔️        |
| vehicle-place     | ❌      | ❌      | 放置载具.                                              | ✔️        |
| water-break       | ✔️      | ✔️      | 水破坏方块.                                            | ✔️        |
| water-bucket      | ✔️      | ✔️      | 收集水.                                                | ✔️        |
| water-flow        | ✔️      | ✔️      | 水流动.                                                | ❌        |
| world-edit        | ✔️      | ✔️      | 编辑世界.                                              | ❌        |
| xp-pickup         | ❌      | ❌      | 拾起经验球.                                            | ❌        |
| target-hit        | ❌      | ❌      | 标靶方块被箭击中.                                      | ❌        |
| player-trade      | ❌      | ❌      | 玩家与村民交易.                                        | ❌        |
| item-receive      | ✔️      | ✔️      | 与村民交易收到的物品.                                  | ❌        |

### 理解行为间的关系

Prism 会将类似的行为分成不同的子行为, 所以您可以更加高效地来查找、回滚、还原您需要的内容.

Prism 以下面两种方式来使用关系.

#### 科属

行为科属定义很简单, 指两种行为十分相似, 比如 creeper-explode 和 tnt-explode 都是因爆炸破坏方块, 但是是由两种不同的原因而导致的. 如果使用短行为名 explode, 插件会查询匹配这个短行为名的所有行为. 如果指定了一个具体的行为名称, 插件就只会查询这一个行为.

比较一下具体的行为名称和短行为名称, 您可以了解更多. block-break 和 water-break 这两个都是具体的行为名称且属于同一科属, 可以单独地追踪, 也可以通过短行为名 break 来追踪双方.

#### 因果

有一些事件是相关联的, 一个事件会导致另一个事件. 要想掌握正确回滚被熊区域的技术, 您真的需要了解它们.

下面举出一个简单的例子. 一个插着火把的木栅栏被烧掉了. 方块被烧掉的记录会以行为 block-burn 记录, 然后火把脱离了放置着它的方块, 火把也会被移除, 以行为 block-break 记录. Prism 会将事件都清晰准确地记录下来, 不会将这个火把被破坏的行为记录为 block-burn , 毕竟火把不可燃烧.

所有 附近/查询/检查 操作都会清晰地向你展示出事件行为记录.

如果要回滚整个栅栏, 应该使用 /prism rollback a:burn,break. 如果只要特别具体的话, 使用 /prism rollback a:block-burn,block-break.

Prism 会智能地先回滚木栅栏, 然后再插上火把.

只要知道了每一个行为代表什么, 您就可以理解行为间的关系了.

这里有两个参考例子: - /prism rollback a:water-flow,water-break - 水流动之后破坏了一个方块. - /prism rollback a:block-break,block-fade - 树被砍之后树叶消亡了.


## 标志

小技巧

`/pr flags`

`/pr 标志`

此指令会向执行者展示所有可用的标志. 这里面的一些指令标志可以控制将要运行的进程的特定细节, 让您获得 Prism 的全新控制能力.

### 排水/仅排水/仅排熔岩

`/prism (指令) (参数) -drain`

添加了排水标志会在回滚期间执行一个排水操作 (与 /prism drain 的效果完全相同). 使用 `-drain-lava` 或者 `-drain-water` 可以针对一种特定的液体来执行排水操作.

### 扩展

除非在配置文件中启用了显示扩展记录, 我们在默认情况下是不会向您显示扩展信息的, 可以减少杂乱的信息. 但是有的时候您可能会需要它. 使用 `-extended` 可以查询到扩展记录.

![显示扩展记录的 Prism 查询信息.](https://prism-cn.readthedocs.io/zh-cn/latest/_images/prism_extended_display.png)

### 不分组

不想获得自动分组后的查询信息? 这种情况可以使用 `-no-group`.

### 不灭火

`/prism (指令) (参数) -no-ext`

如果在配置文件中配置了, Prism 会在执行 行为为burn 的回滚操作时自动扑灭范围内的火焰. 如果想要为一次特殊的回滚操作关闭此功能, 可以在指令中使用该标志.

### 覆写

`/prism (指令) (参数) -overwrite`

覆盖所有在操作过程中可能冲突的方块. 如果没有此标志, 默认它们会被跳过.

### 每页结果

`/prism (指令) (参数) -per-page=#`

调整一次查询中每页显示的结果数量.

### 分享

`/prism (指令) (参数) -share=#`

分享当前查询的结果给列表中的在线玩家.

### 粘贴

`/prism (指令) (参数) -paste`

将结果粘贴在 “[paste.gg](https://paste.gg)” 中. 这是一个粘贴箱服务网站.