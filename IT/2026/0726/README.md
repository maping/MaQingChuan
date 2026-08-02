# 循环

## 1. [while 练习](https://www.bilibili.com/video/BV1hW41197sB?p=47)

### 1.1 
```python
# 练习1：
# 求100以内所有的奇数之和
# 获取所有100以内数
i = 0
# 创建一个变量，用来保存结果
result = 0
while i < 100 :
    i += 1
    # 判断i是否是奇数
    if i % 2 != 0:
      result += i
print('result =', result)
```

### 1.2
```python
# 练习2：
# 求100以内所有7的倍数之和，以及个数
i = 7

# 创建一个变量，来保存结果
result = 0

# 创建一个计数器，用来记录循环执行的次数
# 计数器就是一个变量，专门用来记录次数的变量
count = 0

while i < 100:
    # 为计数器加1
    count += 1
    result += i
    i += 7

print('总和为：', result, '总数量为：', result)
```

## 2. [水仙花数](https://www.bilibili.com/video/BV1hW41197sB?p=48)

```python
#  编写一个程序，求 1000以内 所有的水仙花数
# 提示：水仙花数是指一个 n 位数（n≥3 ），它的每个位上的数字的 n 次幂之和等于它本身（例如：1^3 + 5^3 + 3^3 = 153）。
i = 100
while i < 1000:
    # 假设，i的百位数是a，十位数b，个位数c
    # 求i的百位数
    a = i // 100 # 当使用"//"进行除法运算时，它会返回商的整数部分，舍去小数点后的数值
    # 求i的十位数
    # b = i // 10 % 10
    b = (i - a * 100) // 10
    # 求i的个位数字
    c = i % 10
    # print(i , a , b , c)
    
    # 判断i是否是水仙花数
    if a**3 + b**3 + c**3 == i :
        print(i)
    i += 1
```

## 3. [质数](https://www.bilibili.com/video/BV1hW41197sB?p=49)

```python
# 获取用户输入的任意数，判断其是否是质数。
num = int(input('输入一个任意的大于1的整数：'))

# 判断num是否是质数，只能被1和它自身整除的数就是质数
# 获取到所有的可能整除num的整数
i = 2
# 创建一个变量，用来记录num是否是质数，默认认为num是质数
flag = True
while i < num:
    # 判断num能否被i整除
    # 如果num能被i整除，则说明num一定不是质数
    if num % i == 0 :
        # 一旦进入判断，则证明num不是质数，则需要将flag修改为false
        flag = False
        # 跳出循环
        break
    i += 1

if flag :
    print(num,'是质数')
else :
    print(num,'不是质数')
```

## 作业
观看以下视频，下节课提问知识点

## 4. [循环嵌套](https://www.bilibili.com/video/BV1hW41197sB?p=51)
```python
# 编写一个程序，打印99乘法表
# 1*1=1
# 1*2=2 2*2=4
# 1*3=3 2*3=6 3*3=9
...                 9*9=81
# 创建一个外层循环来控制图形的高度
i = 0
while i < 9:
    i += 1
    
    # 创建一个内层循环来控制图形的宽度
    j = 0
    while j < i:
        j += 1
        print(f"{j}*{i}={i*j} ",end="")

    print
```
## 5. [break 和 continue](https://www.bilibili.com/video/BV1hW41197sB?p=52)

## 6. [质数练习的第一次优化](https://www.bilibili.com/video/BV1hW41197sB?p=53)

## 7. [质数练习的第二次优化](https://www.bilibili.com/video/BV1hW41197sB?p=54)

```python
# 编写一个程序，求 100000以内 所有的质数

# 模块，通过模块可以对 Python 进行扩展
# 引入一个 time 模块，来统计程序执行的时间
from time import *
# time()函数可以用来获取当前的时间，返回的单位是秒
# 获取程序开始的时间
# 优化前：
#   10000个数 12.298秒
#   100000个数 没有结果
# 第一次优化
#   10000个数 1.577秒
#   100000个数 170.645秒
# 第二次优化
#   10000个数 0.068秒
#   100000个数 1.646秒
#
# 36的因数
#   2 18
#   3 12
#   4 9
#   6 6
#   
begin = time()

i = 2
while i <= 100000:
    flag = True
    j = 2 
    while j <= i ** 0.5:
        if i % j == 0:
            flag = False
            # 一旦进入判断，则证明i一定不是质数，此时内层循环没有继续执行的必要
            # 使用break来退出内层的循环
            break
        j += 1
    if flag :
        # print(i)  
        pass
    i += 1

# 获取程序结束的时间
end = time()

# 计算程序执行的时间
print("程序执行花费了：",end - begin , "秒")
```


## 8. 思考：你能进一步优化质数练习吗？

