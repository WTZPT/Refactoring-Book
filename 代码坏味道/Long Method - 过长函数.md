# Long Method

## Extract Method - 提炼函数

找到函数中适合集中在一起的部分，将它们提炼出来形成一个新函数，并以其用途命名。一个好的函数名，读者可以通过名字了解函数的作用，根本不必去看其中写了什么。

**在提炼过程中会涉及以下几个问题**，

1、函数内有较多的参数和临时变量，书中推荐使用[Replace Temp with Query(120)](..\重新组织函数\Replace-Temp-with-Query.md)来消除这些临时元素

2、提炼的函数有过长的参数列表，书中推荐使用[Preserve Whole Object(288)](..\简化函数调用\Preserve-Whole-Object.md)或者[Introduce Parameter Object(295)](..\简化函数调用\Introduce-Parameter-Object.md)来让变得更加简洁些

3、函数中有较长和复杂的表达式，书中推荐使用[Introduce Parameter Object(295)](..\重新组织函数\Introduce-Explaining-Variable.md)来让变得更加精炼

## 提炼代码的信号

1. 注释
2. 条件表达式
3. 循环

