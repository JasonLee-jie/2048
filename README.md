# 2048
C game 2048
游戏说明:每次可以选择上下左右其中一个方向去滑动，每滑动一次，所有的数字方块都会往滑动的方向靠拢外，系统也会在空白的地方乱数出现一个数字方块，相同数字的方块在靠拢、相撞时会相加。不断的叠加最终拼凑出2048这个数字就算成功。
基础知识:要实现我们的 2048 小游戏，需要涉及一些数据结构的知识，以及一些 Linux 的系统调用。
辅助工具:为了方便在屏幕上使用字符绘图，我们还需要使用一个文本界面的屏幕绘图库 ncurses ，具体到操作就是在编译的时候需要加上 -lcurses 选项。
要实现 2048 游戏目前有两个关键点：
在满足条件情况下消除方块
允许在游戏主界面（16 宫格）中任意一格输出数据
其中第二点借助 ncurses 库可以较容易实现，但是第一点要稍微麻烦些。
第一点的实现思路是，我们创建一个与游戏地图相同维数的数组矩阵，通过数组矩阵来维护 2048 游戏中每个格子的数据与状态，从而玩家的移动操作都可以映射为对数组矩阵的操作。


让我们首先来完成一些基础工作，首先是引入头文件：
#include <stdio.h>
#include <stdlib.h>
#include <curses.h>
#include <unistd.h>
#include <signal.h>
#include <time.h>




