
# Task 2

## 列表

### 基本操作

创建


```python
name = ['Tom','jarry','apple']
name
```


    ['Tom', 'jarry', 'apple']



append() : 追加元素到list尾部


```python
name.append('cat')
name
```


    ['Tom', 'jarry', 'apple', 'cat']



pop() : 删除list尾部的元素

pop(i) : 删除list中索引为i的元素

结果返回被删除的元素


```python
name.pop()
```


    'cat'




```python
name.pop(0)#删除第一个元素
```




    'Tom'




```python
name
```


    ['jarry', 'apple']




```python
#添加元素
alpha = ['a','b','c','d']

del alpha[3]
alpha
```


    ['a', 'b', 'c']



使用romeve()删除指定内容的元素


```python
alpha.append('b')#尾部增加'b'
alpha.remove('b')
alpha#结果删除了左边第一个
```


    ['a', 'c', 'b']



使用切片删除元素


```python
deleteC = alpha[0:1] + alpha[2:]
deleteC
```


    ['a', 'b']



拷贝

直接等号赋值是浅拷贝，使用[:]就是深拷贝了


```python
numbera = [1,2,3,4,5]
numberb = numbera
numberb.pop()#删除numberb最后一个元素
numbera#会影响numbera
```


    [1, 2, 3, 4]




```python
numbera = [1,2,3,4,5]
numberb = numbera[:]
numberb.pop()#删除numberb最后一个元素
numbera#不会影响numbera
```


    [1, 2, 3, 4, 5]



### 列表相关方法


```python
#合并
print([1,2,3,4]+[5,6,7,8])
#重复
print(['wxl']*6)
#迭代
for i in [1,2,3,4]:
    print(i)
```

    [1, 2, 3, 4, 5, 6, 7, 8]
    ['wxl', 'wxl', 'wxl', 'wxl', 'wxl', 'wxl']
    1
    2
    3
    4



```python
str1 = "123456789qwertyuiop"
print(str1[::3])#间隔选取
print(str1[::-1])#逆置
```

    147qrup
    poiuytrewq987654321

## 元组的基本操作

与列表的区别在于内容的不变性，元组的内部不容更改，但可以把若干元组通过+相连接从而创建新的元组！

其余与list功能一致，除去可能更改list内部元素的函数操作


```python
tup2 = (1, 2, 3, 4, 5 )
```



## string字符串


```python
var1 = 'Hello World!'
var2 = 'Mark'
print(var1+var2)
print(var1*3)
print('h' in var1)#判断字符h是否在var1中
print(r'haha\n')#取消转义
```

    Hello World!Mark
    Hello World!Hello World!Hello World!
    False
    haha\n



```python
#格式化
```


```python
print("My name is %s and weight is %d kg!" % ('Zara', 21))
```

    My name is Zara and weight is 21 kg!


