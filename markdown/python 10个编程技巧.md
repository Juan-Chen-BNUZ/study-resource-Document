# python 10个编程技巧

## 1、变量转换（Swapping Variables)

```Python
  a = 1
  b = 2

  tmp = a
  a = b
  b = tmp
```

可改写为：

```Python
  a,b = b,a
```

## 2、字符串格式化(String Formatting)

最初版本

```Python
  name = "Ross"
  country = "China"
  age = 28

  print("Hi, I'm" + name + ". I'm from " + country + ". And I'm " + str(age) + ".")
```

百分号格式化("%S"-string字符串。"%d"-decimal十进制数)

```Python
  name = "Ross"
  country = "China"
  age = 28

  print("Hi, I'm %s. I'm from %s . And I'm %d." % (name,country,age))
```

format函数

```Python
  name = "Ross"
  country = "China"
  age = 28

  print("Hi, I'm {}. I'm from {} . And I'm {}.".format(name,country,age))
  //进阶，索引传参。都传入的是name
  //print("Hi, I'm {0}. Yes, I'm {0}！".format(name))
```

f-string最简单写法(Python3.6以上版本)

```Python
  name = "Ross"
  country = "China"
  age = 28
  // 花括号是表达式。如age可写为age+1，输出为29
  print(f"Hi, I'm {name}. I'm from {country} . And I'm {age}. " )

```

## 3、Yield语法(Yield Statement)

```Python
"""
斐波那契数列
"""
    def fibonacci(n):
        a = 0
        b = 1
        num = []
        for _ in range(n):
            nums.append(a)
            a, b = b, a + b
        return nums

    for i in fibonacci(10):
        print(i)
```

Yield语法修改后：

```Python
"""
 yield计算出后立马返回该元素
 return则是全部计算完后返回列表
"""
    def fibonacci(n):
        a = 0
        b = 1
        for _ in range(n):
            yield a    //yield表示每当计算出一个元素，立马跑出这个元素
            a, b = b, a + b

    for i in fibonacci(10):
        print(i)
```

## 4、列表解析时（List Comprehension)

```Python
"""
对水果list进行操作
"""
    fruit = ["apple" , "pear" , "pineapple" , "orange" , "banana"]
    for i in range(len(fruit)):
        fruit[i] = fruit[i].upper()

    //所有字母大写
    fruit = [x.upper() for x in fruit]

    //筛选过滤列表中的元素（选择a开头的水果）
    filtered_fruit = [x for x in fruit if x.startswitj("a")]
```

## 5、Enumerate函数(Enumerate Function)

```Python
"""
对水果list进行操作
"""
    //输出元素及其对应索引值
    fruit = ["apple" , "pear" , "pineapple" , "orange" , "banana"]
    for i,x in enumerate(fruit):
        print(i,x)
```

## 6、遍历(Looping)

### 6.1、反向便利（Looping Backwars)

```Python
"""
对水果list进行操作
"""
    //从后向前的反向输出reversed
    fruit = ["apple" , "pear" , "pineap0ple" , "orange" , "banana"]
    for i,x in enumerate(reversed(fruit)):
        print(i,x)
```

### 6.2、顺序（正向）遍历(Looping in Sort Order)

```Python
"""
对水果list进行操作
"""
    //按顺序输出sort
    fruit = ["apple" , "pear" , "pineap0ple" , "orange" , "banana"]
    for i,x in enumerate(sort(fruit)):
        print(i,x)
```

## 7、字典的合并操作（Dictionart Merging）

```Python
    a = {"ross": "123456","xiaoming": "abc123"}
    b = {"lilei": "111111","zhangsan" :"12345678"}

    //一般写法，合并字典
    c = {}
    for k in a:
        c[k] = a[k]
    for k in b:
        c[k] = b[k]

    //优化写法(**,在python中代表解包（unpacking）)
    c = {**a,**b}
```

## 8、三元运算符（Ternary Operator）

```Python
    if score > 60:
        s = "pass"
    else:
        s = "fail"

//优化写法
s = "pass" if score > 60 else "fail"
```

## 9、序列解包（Sequence Unpacking）

```Python
"""
序列解包，序列可以是list,tuple,range……
"""

// 一般写法，取出字和名
name = "San Zhang"

str_list = name.split(" ")
first_name = str_list[0]
last_name = str_list[1]

//优化写法
name = "San Zhang"
first_name ,last_name = name.split(" ")
```

## 10、With语句（With Statement）

```Python
"""
打开文件流，必须使用close将文件流关闭，否则将一直占用系统资源。
如果使用"with"语句，则无需调用close，将在with语句执行完后，自动关闭。
"""

// 打开文件
f = open("somefile.txt","r")
s = f.read
// 关闭文件流
f.close()

// with优化写法，无需调用close
with open("somefile.txt","r") as f:
    s = f.read

```
