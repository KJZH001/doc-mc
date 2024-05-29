# imageframe
将图片显示在地图上

## 介绍
ImageFrame是一个可以将图片显示在地图上的插件，可以用来制作地图、标记地图，或者也可以用来生成一些地图画来用于装饰

生成的地图画和普通的地图没有本质区别，你也可以将它放在物品展示架上用于展示或和其他地图放在一起拼接为更大的图片

## 使用方法
基础指令`/if create <名称> <图片地址> 1 1`

目前，**每个玩家只有两张地图画的配额**，请勿滥用

图片需要提前上传到指定的图床，目前仅允许[imgtp图床](https://www.imgtp.com/)，使用未经授权的图床托管图片会无法显示

使用本服务代表您已经阅读且同意本文的声明以及相关图床的服务条款以及隐私协议

## 全部命令 
<!-- todo -->

```
/imageframe select - 选择放置图像地图的物品框架
/imageframe create <name> <url> <width> <height> - 创建一个新的图像地图
/imageframe create <name> <url> selection - 在你选择的物品框架中直接创建一个新的图像地图
/imageframe create <name> <url> <width> <height> combined - 创建一个新的图像地图并获得其组合图像地图物品
/imageframe overlay <name> <url> - 在你手持的Minecraft原版地图上创建一个新的图像地图，增加一个覆盖层
/imageframe overlay <name> <url> selection - 在你选择的物品框架的Minecraft原版地图上添加覆盖层的图像地图
/imageframe clone <name> <new_name> - 创建一个与旧图像地图属性相同的新图像地图
/imageframe clone <name> <new_name> selection - 在你选择的物品框架中直接创建一个与旧图像地图属性相同的新图像地图
/imageframe clone <name> <new_name> combined - 创建一个与旧图像地图属性相同的新图像地图并获得其组合图像地图物品
/imageframe playback <name> pause - 切换动画图像地图的暂停状态
/imageframe playback <name> jumpto <seconds> - 跳转到动画图像地图的特定秒数
/imageframe refresh [optional:image_name] [optional:new_url] - 从源URL刷新你创建的地图
/imageframe info - 获取你手持的图像地图的相关信息
/imageframe get <name> - 获取一个自己创建的现有图像地图
/imageframe get <name> selection - 直接将自己创建的现有图像地图放在你选择的物品框架上
/imageframe get <name> combined - 以组合图像地图形式获取自己创建的现有图像地图
/imageframe delete <name> - 删除自己创建的现有图像地图
/imageframe rename <name> <new_name> - 重命名自己创建的现有图像地图
/imageframe list - 列出所有自己创建的现有图像地图
/imageframe marker add <image_name> <marker_name> <direction:0-15> <marker_type> [optional:caption] - 在你的地图上添加一个标记
/imageframe marker remove <image_name> <marker_name> - 从你的地图上移除一个标记
/imageframe marker clear <image_name> - 清除你的地图上的所有标记
/imageframe setaccess <name> <player> <permission> - 设置其他玩家对你的地图的访问权限
```