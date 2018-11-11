# 自制游戏（进阶篇）

## 一个简单的接球游戏

玩家操控篮筐，接住随即发射的篮球，一旦漏了一个，游戏就失败。总的来看，不是一个简单的游戏，需要一定的意识，操作，反应。

![ ](https://github.com/xel96naga/swi-homework/blob/gh-pages/photo/123.gif?raw=true)

## 制作过程

首先，我们需要的是，玩家（篮筐）的移动。因为construct2每秒60帧，所以，如果你命令，按住左移动健时，移动距离为3，那么实际上，物体每秒移动了180个坐标的长度。

![ ](https://github.com/xel96naga/swi-homework/blob/gh-pages/photo/lanzi.png?raw=true)


然后，吐球器就很简单了。随便一画。

但是，如何做到随机球速呢？注意，如果你选择在一块开始给球一个水平向量，那么求会在半途停下来，导致制作失败。而且，球是有重力的，我们要求它做   **抛物线运动**

所以，给球这个物体增加了一个参数，speed。speed在一开始是一个随机值。
 
 ![ ](https://github.com/xel96naga/swi-homework/blob/gh-pages/photo/sets.png?raw=true)

 这样，每个球都会不一样。最后，给球加上重力属性，让它做加速运动。调节重力，使它速度合理。

 那么，球如何移动呢？

 这个简单。和篮筐的移动是一个道理，利用了每秒60帧。

 ![](https://github.com/xel96naga/swi-homework/blob/gh-pages/photo/move.png?raw=true)


 最后，加上死亡效果。我在layout下方画了一个物体，一条直线。一旦球撞到了这条直线，那么摧毁一切，游戏失败。

 # 完成了。不难吧。