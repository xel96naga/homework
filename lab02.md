# 我的第一个自制游戏


我的理想就是为中国做一款举世闻名的大游戏，今天，我完成了第一个自己创作的小游戏（虽然有点模仿）。这是梦想的一大步。

 ![ ](https://github.com/xel96naga/swi-homework/blob/gh-pages/1g.gif?raw=true)


# 这是一个非常难的小游戏

我模拟《以撒的结合》的操作方式射击的，虽然只有四关，但是机关重重，暗藏杀机，还有许多未被发现的套路，技巧。

我敢说，没有一个人可以一遍通关。



## 制作对于我一个新手来说，很难的。

首先，做场景，因为我设计了4关，而且需要让4关的所有的敌人，在一开始就全都动起来（因为怪物会繁殖，拖时间久了，就会更难），所以我没有选择建立4个layout，而是把四个场景都放在一个地图内。

宏观来看是这样的

![ ](https://raw.githubusercontent.com/xel96naga/swi-homework/gh-pages/photo/43XHHX%7DVO58LI%5DF_6O4F4W3.png)


我保证每个场景会饱满的出现在同一个屏幕内，直到死亡或者通关。视角跟着地图走，而不是跟着主角走。


### 第一次写程序就46个event，真的好难啊


![ ](https://github.com/xel96naga/swi-homework/blob/gh-pages/photo/X8NZWRJFW%7DG6~QH67%60579O.png?raw=true)


仔细看，这些event有的是为了操作，比如WSAD移动，5213不同方向的射击。
有的是为了子弹杀人，减血。
还有的就是视角转换，通关，死亡，胜利，都会进入不同的视角。


## Construct2 真好玩

我不得不说我是个初学者。

举几个操作的例子把。

比如，敌人的随机移动

![ ](https://raw.githubusercontent.com/xel96naga/swi-homework/gh-pages/photo/mo9.png)
 
 可以可看出，我调用了不少的随机函数，随机敌人每一秒在X,Y轴上的运动，是敌人的运动随机
 random（-xxx，xxx）就是这样了



再说，打怪与掉血，杀死

![ ](https://raw.githubusercontent.com/xel96naga/swi-homework/gh-pages/photo/aaa.png)

设计health参数，描述血量，当health=0 时，死亡。当然，如果怪物只有1滴血，可以直接destory（摧毁）。

最后，移动用方向键显然不符合现在人的习惯。我把他调成WSAD,并且改了移动速度

![ ](https://raw.githubusercontent.com/xel96naga/swi-homework/gh-pages/photo/kkk.png)

其他的一些操作再次不便枚举了，总之，一步一步来。高楼是一块一块砖头推成的，游戏event再多，也是一点一点拼出来的。




# 希望我还能做出更好的游戏


