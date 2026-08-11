# 1. 作业讲解：试着编程解答这道题
Suppose that w, x, y, z,(x + y),(x + z),(234 + z), and (234 − z) are 8 different prime numbers. If w + x + y = 234, and each of y and z is less than 50, the value of w − y isSuppose that w, x, y, z,(x + y),(x + z),(234 + z), and (234 − z) are 8 different prime numbers. If w + x + y = 234, and each of y and z is less than 50, the value of w − y is

## 1.1 解题思路
由题目推断，需要知道 300 以内的质数：
- 50 以内的质数有：2、3、5、7、11、13、17、19、23、29、31、37、41、43、47
- 100-200 以内的质数有：101 103 107 109 113 127 131 137 139 149 151 157 163 167 173 179 181 191 193 197 199
- 200-300 以内的质数有：211 223 227 229 233 239 241 251 257 263 269 271 277 281 283 293

【逻辑推理】
- 由 w + x + y = 234，得知 w，x，y 中必有一个是 2，这里不妨就大胆假设 x=2
  - 因为三个质数相加为偶数，必然其中一个数为 2，否则三个质数相加为奇数。
  - 又已知 (2 + z)，(234 + z)，(234 - z) 都是质数
  - 且 z 小于 50，z 的约束条件最多，所以优先考虑 z 的可能值
  - 从较大的 z 的可能值，开始尝试，以减少计算量，符合条件的只有 3，5，11，17，29，41
    - 尝试 z = 41（质数）❌
      - 234 + 41 = 275（质数）❌   
    - 尝试 z = 29（质数）❌
      - 234 + 29 = 263（质数）✅
      - 234 - 29 = 205（质数）❌
    - 尝试 z = 17（质数）❌
      - 234 + 17 = 251（质数）✅
      - 234 - 17 = 217（不是质数）❌
    - 尝试 z = 11（质数）❌
      - 234 + 11 = 245（不是质数）❌
    - 尝试 z = 5（质数）✅
      - 234 + 5 = 239（质数）✅
      - 234 - 5 = 229（质数）✅
  
  至此，得出 x = 2，z = 5 。接下来，根据 w + x + y = 234，推导出 w + y = 234 - 2 = 232。
  - y 为质数，且 y 小于 50，从较大的 y 的可能值，开始尝试，以减少计算量
    - 尝试 y = 47（质数）❌
      - w = 232 - 47 = 185（不是质数）❌
    - 尝试 y = 43（质数）❌
      - w = 232 - 43 = 189（不是质数）❌
    - 尝试 y = 41（质数）✅
      - w = 232 - 41 = 191（质数）✅

  至此，得出所有的未知数取值：
  - x = 2
  - y = 41
  - z = 5
  - w = 191

最后，w - y = 191 - 41 = 150，选项(B)正确。
>$\color{red}{数识：2 是唯一的偶数质数；三个质数相加为偶数，必然有一个数是 2。}$

>$\color{red}{技巧：先确定约束条件最多的变量，约束越多，越容易确定。}$

## 1.2 编写 Python 程序求解
```python
# 定义一个函数，用来判断一个数是否是质数
def is_prime(num):
    # 判断num是否是质数，只能被1和它自身整除的数就是质数
    # 获取到所有的可能整除num的整数
    i = 2
    # 创建一个变量，用来记录num是否是质数，默认认为num是质数
    flag = True
    while i <= num ** 0.5: # i 只需计算到 根号 num 且必须是小于等于，只有小于会有 4 9 49 被漏掉
        # 判断num能否被i整除
        # 如果num能被i整除，则说明num一定不是质数
        if num % i == 0:
            # 一旦进入判断，则证明num不是质数，则需要将flag修改为false
            flag = False
            # 跳出循环
            break
        i += 1

    return flag

# 设置变量初始值都为 2
x = 2
y = 2
z = 2
w = 2

# 循环遍历各个变量
while x < 229 :
    if is_prime(x) :
        #print("x=",x)
        y = 2 # 重新初始化 y，思考一下为什么要初始化？
        while y < 50 :
            if is_prime(y) and is_prime(x+y) :
                #print("y=",y)
                z = 2 # 重新初始化 z，思考一下为什么要初始化？
                while z < 50 and z != y : # 思考一下为什么要加 z != y
                    if is_prime(z) and is_prime(x+z) and is_prime(234+z) and is_prime(234-z) :
                        # print("z=",z)
                        w = 2 # 重新初始化 w，思考一下为什么要初始化？
                        while w < 229 :
                            if is_prime(w) :                  
                                if w + x + y == 234 :
                                    print("="*10)
                                    print("x=",x)
                                    print("y=",y)
                                    print("z=",z)
                                    print("w=",w)
                                    print("w-y=",w-y)                                    
                            w += 1
                    z += 1
            y += 1
    x += 1
```
输出如下：
```console
x= 2
y= 41
z= 5
w= 191
w-y= 150
```
>重要说明：不加 `z != y` 会导致有三组答案
```console
========== (x + y) 和 z 相等，不符合题目条件要求
x= 2
y= 3
z= 5
w= 229
w-y= 226
========== y 和 z 相等，不符合题目条件要求
x= 2
y= 5
z= 5
w= 227
w-y= 222
========== 唯一正确答案
x= 2
y= 41
z= 5
w= 191
w-y= 150
```
>说明：这里没有增加其它的这些数都是不同的质数判断，是因为只加`z != y` 已经得出唯一正确答案了。

优化程序
```python
# 循环遍历各个变量
while x < 229 and is_prime(x) :
    y = 2 # 重新初始化 y，思考一下为什么要初始化？
    while y < 50 :
        w = 234 - x - y                            
        if is_prime(y) and is_prime(x+y) and is_prime(w) :
            z = 2 # 重新初始化 z，思考一下为什么要初始化？              
            while z < 50 and z != y : # 思考一下为什么要加 z != y
                if is_prime(z) and is_prime(x+z) and is_prime(234+z) and is_prime(234-z) :
                    print("="*10)
                    print("x = ",x)
                    print("y = ",y)
                    print("z = ",z)
                    print("w = ",w)
                    print("w-y = ",w-y)                                    
                z += 1
        y += 1
    x += 1
```

# 2. 列表

## 2.1 [EMS 项目-添加员工](https://www.bilibili.com/video/BV1hW41197sB?p=65)

## 2.2 [EMS 项目-删除员工](https://www.bilibili.com/video/BV1hW41197sB?p=66)

## 作业
看以下视频
- 1️⃣[EMS 项目-添加员工](https://www.bilibili.com/video/BV1hW41197sB?p=65)
- 2️⃣[EMS 项目-删除员工](https://www.bilibili.com/video/BV1hW41197sB?p=66)
