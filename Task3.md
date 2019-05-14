## Task3

## Dict字典

### 基本操作

```python
#创建
d = {'Michael': 95, 'Bob': 75, 'Tracy': 85}
print(d)
#增加
d['Mark'] = 99
print(d)
#修改
if 'Bob' in d:
    d['Bob'] = 21
print(d)
#删除
del d['Mark']
print(d)
```

    {'Michael': 95, 'Bob': 75, 'Tracy': 85}
    {'Michael': 95, 'Bob': 75, 'Tracy': 85, 'Mark': 99}
    {'Michael': 95, 'Bob': 21, 'Tracy': 85, 'Mark': 99}
    {'Michael': 95, 'Bob': 21, 'Tracy': 85}

### 字典的常用方法

* clear()

```python
#清除所有元素
d.clear()
d
```


    {}

* copy()浅拷贝


```python
dict1 =  {'user':'runoob','num':[1,2,3]}
 
dict2 = dict1          # 浅拷贝: 引用对象
dict3 = dict1.copy()   # 浅拷贝：深拷贝父对象（一级目录），子对象（二级目录）不拷贝，还是引用
 
# 修改 data 数据
dict1['user']='root'
dict1['num'].remove(1)
 
# 输出结果
print(dict1)
print(dict2)
print(dict3)
```

    {'user': 'root', 'num': [2, 3]}
    {'user': 'root', 'num': [2, 3]}
    {'user': 'runoob', 'num': [2, 3]}

* items()

```python
#以列表返回可遍历的(键, 值) 元组数组。
for k,v in dict1.items():
    print(k,v)
```

    user root
    num [2, 3]

* values()

```python
dict1.values()
```


    dict_values(['root', [2, 3]])

## set

### 基本操作


```python
#set的创建
basket = {'apple', 'orange', 'apple', 'pear', 'orange', 'banana'}
print(basket)                      # 这里演示的是去重功能
```

    {'apple', 'orange', 'pear', 'banana'}


集合（set）是一个无序的不重复元素序列。

可以使用大括号 { } 或者 set() 函数创建集合，注意：创建一个空集合必须用 `set()` 而不是 `{ }`，因为 `{ } `是用来创建一个空字典。


```python
#添加 1.add()  2.update() 其中参数可以是列表，元组，字典等
basket.add('potato')
print(basket)
basket.update([1,2],[3,4],{5,6},{7:'seven',8:'eight'})
print(basket)
```

    {'pear', 'banana', 'potato', 'apple', 'orange'}
    {1, 'pear', 2, 3, 4, 5, 6, 7, 8, 'banana', 'potato', 'apple', 'orange'}



```python
#删除 1.remove() 2.discard()
#后者在要删除元素不存在的情况下，程序不会报错
basket.remove(2)
basket.discard(3)
print(basket)
basket.discard(100)
```

    {1, 'pear', 4, 5, 6, 7, 8, 'banana', 'potato', 'apple', 'orange'}



```python
basket.remove(101)
```


    ---------------------------------------------------------------------------
    
    KeyError                                  Traceback (most recent call last)
    
    <ipython-input-18-c7e7e6f47d99> in <module>
    ----> 1 basket.remove(101)


    KeyError: 101

### 三目表达式

```python
result = 'a' if 2>3 else 'b'
result
```


    'b'


