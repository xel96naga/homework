# 自制游戏（进阶篇）

## 一个简单的接球游戏

玩家操控篮筐，接住随即发射的篮球，一旦漏了一个，游戏就失败。总的来看，不是一个简单的游戏，需要一定的意识，操作，反应。

![ ](https://github.com/xel96naga/swi-homework/blob/gh-pages/photo/123.gif?raw=true)

## 制作过程

首先，我们需要的是，玩家（篮筐）的移动。因为construct2每秒60帧，所以，如果你命令，按住左移动健时，移动距离为3，那么实际上，物体每秒移动了180个坐标的长度。

![ ](https://github.com/xel96naga/swi-homework/blob/gh-pages/photo/lanzi.png?raw=true)

