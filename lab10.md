# python 实验报告

1. 解方程

用python解方程就是方便。

首先我们要打开函数库

    from sympy import *

解方程在这个函数里

然后，定义变量xyzt

    x, y, z, t = symbols('x y z t')

如果不定义，会导致出错

然后就是解方程指令

    solve([Eq(。。。), Eq(。。。)], [, ])

输出 是方程的解

线性代数课本上第一章有不少方程组，它们都在增广矩阵里

    solve([Eq(x + 5*y, 2), Eq(-3*x + 6*y, 15)], [x, y])
    solve([x+y-2,x-y],[x,y])

以上是两种不同格式，可以输出解的答案。