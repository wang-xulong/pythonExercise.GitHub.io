
# Task5

## 学习对excel及csv文件进行操作


```python
import pandas as pd 
#导入
df = pd.read_excel("./task5.xlsx")
df
```

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>9</th>
      <th>a</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>8</td>
      <td>b</td>
    </tr>
    <tr>
      <th>1</th>
      <td>7</td>
      <td>c</td>
    </tr>
    <tr>
      <th>2</th>
      <td>6</td>
      <td>d</td>
    </tr>
    <tr>
      <th>3</th>
      <td>5</td>
      <td>a</td>
    </tr>
    <tr>
      <th>4</th>
      <td>4</td>
      <td>b</td>
    </tr>
    <tr>
      <th>5</th>
      <td>3</td>
      <td>c</td>
    </tr>
    <tr>
      <th>6</th>
      <td>2</td>
      <td>d</td>
    </tr>
    <tr>
      <th>7</th>
      <td>1</td>
      <td>a</td>
    </tr>
    <tr>
      <th>8</th>
      <td>0</td>
      <td>b</td>
    </tr>
    <tr>
      <th>9</th>
      <td>-1</td>
      <td>c</td>
    </tr>
    <tr>
      <th>10</th>
      <td>-2</td>
      <td>d</td>
    </tr>
    <tr>
      <th>11</th>
      <td>-3</td>
      <td>a</td>
    </tr>
    <tr>
      <th>12</th>
      <td>-4</td>
      <td>b</td>
    </tr>
    <tr>
      <th>13</th>
      <td>-5</td>
      <td>c</td>
    </tr>
  </tbody>
</table>


文件的写入


```python
#写入
#首先创建一个DataFrame结构的数据（写入Excel文件必须得是Dataframe结构）
example = pd.DataFrame([['a', 'b'], ['c', 'd']],
                       index=['row 1', 'row 2'],
                       columns=['col 1', 'col 2'])
#创建一个新的Excel文件
with pd.ExcelWriter('output.xlsx') as writer:
    example.to_excel(writer)
writer.save()
```

## 类和对象

封装


```python
#定义一个类student,并将打印成绩的方法封装起来
class student():
    def __init__(self,name,score):
        self.name = name
        self.score = score
    def print_score(self):
        print('%s: %s' % (self.name, self.score))
```


```python
#初始化一个对象
stu1 = student('Tom',90)
#调用Print_score方法
stu1.print_score()
```

    Tom: 90


继承


```python
#首先定义一个父类animal
class Animal():
    def run():
        print("Animal is running")
#接下来定义两个子类，分别继承父类Animal
class Dog(Animal):
    def run():
        print("Dog is running")#子类的方法会继承父类
class Cat(Animal):
    pass
    #def run():
        #print("Cat is running")#子类的方法会继承父类
```


```python
Dog.run()
Cat.run()
```

    Dog is running
    Animal is running


多态


```python
def run_twice(animal):
    animal.run()
    animal.run()

#我们再继承一个类
class Tortoise(Animal):
    def run(self):
        print('Tortoise is running slowly...')
```


```python
run_twice(Tortoise())
```

    Tortoise is running slowly...
    Tortoise is running slowly...


在我们新增了Animal的子类后，我们可以在不修改run_twice()的情况下让其结果不同，这就是多态

## 正则表达式
## RE模块

强烈建议使用Python的r前缀，就不用考虑转义的问题


```python
import re
#识别字电话号码  ***-****
if re.match(r'^\d{3}\-\d{3,8}$', '010-12345'):
    print("OK")
else:
    print("Fail")
```

    OK



```python
#分割字符串

#按空格分割
print(re.split(r'\s+', 'a b             c'))
#也可以把, ;考虑进去
print(re.split(r'[\s\,\;]+','a,b;; c  d'))
```

    ['a', 'b', 'c']
    ['a', 'b', 'c', 'd']


## Datatime 模块


```python
from datetime import datetime 
now = datetime.now() # 获取当前datetime
now
```




    datetime.datetime(2019, 5, 18, 22, 25, 35, 743675)


