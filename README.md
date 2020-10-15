# Lab 3

>本次lab安排：
>
>1. LAB2作业总结
>2. Project发布



## 获取及提交lab

**获取**：通过 `https://github.com/fdu-20ss-programming-A/lab3`或者`超星平台`获取。

**提交**：本次lab无提交内容。



## LAB2回顾

> LAB2中我们了解了C标准数学库<math.h>，进行了作业实践。接下来主要对LAB的作业进行讲解。

### Question 1

题目

> 输入一个实数，输出它的绝对值。

限制

> 实数为浮点数，输出结果保留三位小数。

示例

> 请输入实数：-2.4
>
> 该实数的绝对值为：2.400

参考答案：

```c
#include <stdio.h>
#include <math.h>
int main(){
    float num;
    printf("请输入实数：");
    scanf("%f", &num);
    float absNum = fabs(num);
    printf("该实数的绝对值为：%.3f", absNum);
    return 0;
}
```



### Question 2

题目

> 输入4个实数x~~1~~，y~~1~~，x~~2~~，y~~2~~，数据之间用空格隔开，表示两点坐标（x~~1~~，y~~1~~），（x~~2~~，y~~2~~）。计算并输出两点间的距离。

限制

> 实数为浮点数，输出结果保留两位小数

示例

> 请输入4个实数：1.0 2.0 3.0 4.0
>
> （1.0, 2.0）与（3.0, 4.0）两点之间的距离为：2.83

参考答案：

```c
#include <stdio.h>
#include <math.h>
int main(){
    double x1, x2, y1, y2, result;
    printf("请输入4个实数：");
    scanf("%lf %lf %lf %lf", &x1, &y1, &x2, &y2);
    result = sqrt(pow(x1 - x2, 2) + pow(y1 - y2, 2));
    /*
    or
    result = sqrt((x1 - x2)*(x1 - x2) + (y1 - y2)*(y1 - y2));
    */
    printf("(%f, %f)与(%f, %f)两点之间的距离为：%.2f", result);
    return 0;
}
```



### Question 3

题目

> 输入三角形的三边长，输出三角形的面积。**默认输入三角形存在**
>
> 提示：用海伦公式

限制

> 三边长为浮点数，输出结果保留两位小数

示例

> 请输入三角形的三边长：3.0 4.0 5.0
>
> 三角形的面积为：6.00

参考答案：

```c
#include <stdio.h>
#include <math.h>
int main(){
    double a, b, c, avg, s;
    printf("请输入三角形的三边长：");
    scanf("%lf %lf %lf", &a, &b, &c);
    avg = (a + b + c) / 2;/* 这里可以不用写avg = (a + b + c) / 2.0 */
    s = sqrt(avg * (avg - a) * (avg - b) * (avg - c));
    printf("三角形的面积为：%.2f", s);
    return 0;
}
```



### Question 4

题目

> 输入一元二次方程ax^2^+bx+c=0的系数a，b，c，假定满足b^2^-4ac>0，输出方程的两个根。

限制

> 系数均为整数，输出结果保留两位小数
>
> 两个根的输出顺序无要求

示例

> 请输入三个系数：1 1 -6
>
> 方程的两个根为：2.00，-3.00

参考答案：

```c
#include <stdio.h>
#include <math.h>
int main(){
    int a, b, c;
    double delta, result1, result2;
    printf("请输入三个系数：");
    scanf("%d %d %d", &a, &b, &c);
    delta = sqrt(pow(b, 2) - 4 * a * c);
    result1 = (-b + delta) / 2 * a;
    result2 = (-b - delta) / 2 * a;
    printf("方程的两个根为：%.2f，%.2f", result1, result2);
    return 0;
}
```



### Question 5

题目

> 输入存款金额money，存期year和年利率rate，根据公式计算存款到期时的本息合计sum（税前）

限制

> 存款金额、存期为整数，年利率为浮点数，输出结果保留两位小数

提示

> sum = money * (1 + rate) ^year^

示例

> 请依次输入存款金额，存期和年利率：1000 2 0.1
>
> 存款到期时的本息合计为：1210.00

参考答案：

```c
#include <stdio.h>
#include <math.h>
int main(){
    int money, year;
    double rate, result;
    printf("请依次输入存款金额，存期和年利率：");
    scanf("%d %d %lf", &money, &year, &rate);
    result = money * pow(1 + rate, year);
    printf("存款到期时的本息合计为：%.2f", result);
    return 0;
}
```



## Project发布

### Project获取及提交

**获取**：本次Project文档通过[本次lab](https://github.com/fdu-20ss-programming-A/lab3)以及`超星平台`获取。

**提交物**：将你的源代码与设计文档进行打包，命名为学号_ 姓名（如20302010000_

王明），作为提交物。

**提交**：提交至超星学习通对应的作业中。

**截止时间**：暂定北京时间12月30号23:59，面试时间待定



### Project内容

见[项目需求文档](https://github.com/fdu-20ss-programming-A/lab3/blob/main/project.pdf)。

游戏地图在lab3中maps文件夹下。



### Project参考

+ [推箱子游戏网页版](http://www.game-sokoban.com/)
+ [C语言项目结构](https://stackoverflow.com/questions/2360734/whats-a-good-directory-structure-for-larger-c-projects-using-makefile)# lab3
