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

```python
i = 1001
while i > 1000 and i < 10000 :
    # 假设，i的千位数是a，百位数是b，十位数c，个位数d
    # 求i的千位数
    a = i // 1000 # 当使用"//"进行除法运算时，它会返回商的整数部分，舍去小数点后的数值
    # 求i的百位数
    b = i // 100 % 10 
    # 求i的十位数
    c = i // 10 % 10
    # 求i的个位数字
    d = i % 10
    #print(i , a , b , c)
    
    # 判断i是否是水仙花数
    if a**4 + b**4 + c**4 + d**4 == i :
        print(i)
    i += 1
```
## 3. [质数](https://www.bilibili.com/video/BV1hW41197sB?p=49)
## 5. 编写一个程序，获取用户输入的任意数，判断其是否是质数

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
1*1=1
1*2=2 2*2=4
1*3=3 2*3=6 3*3=9
...                 9*9=81
```

```python
# 创建一个外层循环来控制图形的高度
i = 0
while i < 9:
    i += 1
    
    # 创建一个内层循环来控制图形的宽度
    j = 0
    while j < i:
        j += 1
        print(f"{j}*{i}={i*j} ",end="")

    print()
```

## 5. [break 和 continue](https://www.bilibili.com/video/BV1hW41197sB?p=52)

## 6. [质数练习的第一次优化](https://www.bilibili.com/video/BV1hW41197sB?p=53)

## 7. [质数练习的第二次优化](https://www.bilibili.com/video/BV1hW41197sB?p=54)

