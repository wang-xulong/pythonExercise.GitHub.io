
函数的三种参数

默认参数：我们给某个参数赋予默认值，比如调用幂函数常常计算平方

可变参数：允许你传入0个或任意个参数，这些可变参数在函数调用时自动组装为一个tuple，`使用*`

关键字参数：关键字参数允许你传入0个或任意个含参数名的参数，这些关键字参数在函数内部自动组装为一个dict。，`使用**`

命名关键字参数：限制关键字参数的名字，仅仅接受某些特定的参数


```python
#默认参数
def power(x,n = 2):
    s = 1
    while n:
        s *= x
        n -= 1
    return s
print(power(2,6))
print(power(2))
```

    64
    4



```python
#可变参数
def mySum(*num):
    count=0
    for i in num:
        count += i
    return count
print(mySum(1,2,3,4,5,6,7,8,9))
print(mySum(*[1,2,3,4,5,6,7,8,9]))#在传入list或者tuple时，前面要添加*
```

    45
    45



```python
#关键字参数
def person(name,age,**kw):
    print('name: ',name)
    print('age: ',age)
    for k,v in kw.items():
        print("%s: %s"%(k,v))
```


```python
person('Bob',21,city='Beijing',score=30)
person('Tim',80,**{'iswedding':True,'city':'London'})#在传入Dict时，在前面加**
```

    name:  Bob
    age:  21
    city: Beijing
    score: 30
    name:  Tim
    age:  80
    iswedding: True
    city: London



```python
#命名关键字参数
def specialPerson(name,age,*,city):
    print(name,age,city)
specialPerson('Mark',33,city='shanghai')#关键字参数仅仅接受city，传入其他的会报错！
```

    Mark 33 shanghai



```python
#写文件
with open("./1.txt",'w') as f:
    for i in range(5):
        f.write("%s: Hello World\n"%i)
#读文件
with open("./1.txt",'r')as f:
    print(f.read())
```

    0: Hello World
    1: Hello World
    2: Hello World
    3: Hello World
    4: Hello World
    



```python
#.readline(),返回下一行
#用于读取所有行(直到结束符 EOF)并返回列表，该列表可以由 Python 的 for... in ... 结构进行处理。如果碰到结束符 EOF 则返回空字符串。
with open("./1.txt",'r')as f:
    print(f.readline())
    print('----------------')
    
    for i in f.readlines():
        print(i)
```

    0: Hello World
    
    ----------------
    1: Hello World
    
    2: Hello World
    
    3: Hello World
    
    4: Hello World
    



```python
#.tell()得到当前文件指针位置
with open("./1.txt",'r') as f:
    print(f.readline())
    print(f.tell())#注意每段结尾有一个换行符\n
```

    0: Hello World
    
    15



```python
#.seek()修改文件指针位置
with open("./1.txt",'r') as f:
    f.readline()#当前指针位置在第15
    f.seek(14)#往后退一个位置，即指向第一行的最后一个字符：\n
    print(f.readline())#仍然读第一行，但第一行只剩一个\n，因此输出一个换行（看不到内容！）
```

    
    



```python
#writelines() 方法用于向文件中写入一序列的字符串。
seq = ["hello python\n","Tim",'1,2,3']
with open("./1.txt",'a') as f:
    f.writelines(seq)
with open("./1.txt",'r') as f:
    print(f.read())
```

    0: Hello World
    1: Hello World
    2: Hello World
    3: Hello World
    4: Hello World
    hello python
    Timhello python
    Tim1,2,3



```python

```
