# 基本 Python 玩具

熟悉語法請在 ipython 上練習, 效果最好。

類似的工具還有 bpython 跟dreampy 或是開啟了自動完成的 python  console，但如果用沒有調整過的的 Python Shell, 那實在不酷了。

```bash
pip install ipython
```

安裝完以後，你在 command line 上就得到 ipython
```bash
Python 2.7.6 (default, Sep  9 2014, 15:04:36)
Type "copyright", "credits" or "license" for more information.

IPython 2.3.1 -- An enhanced Interactive Python.
?         -> Introduction and overview of IPython's features.
%quickref -> Quick reference.
help      -> Python's own help system.
object?   -> Details about 'object', use 'object??' for extra details.

In [1]:
```

這是變數的概念
```python
a = 10
a
```
請記住上面的語感，建立一個數字物件 10， 把 a 這個標籤貼到 10 這個物件上。

玩一下數學
```python
1+1
a * 2
a ** 3
```

猜一下怎麼做開根號?
```python
a**0.5
```

##字串是個物件

```python
a = "tim"
a.upper()
```

## list
```python
a = ['1','2','3']
a
```


"tim" 會建立字串物件，[1, 2, 3] 會建立 list 物件，然後讓初始值有三個數字。有一些類別太常使用，以及為了讓程式碼增加可讀性，會讓某些物件的建立方法不一樣跟上一張講的不一樣。 下面列出相等的寫法:

```python
a = ['1','2','3']
b = list('123')
a == b
```

更多基本的 tutorial, 請先參考 [Django Girls Taipei 的文件](http://djangogirlstaipei.herokuapp.com/tutorials/python/)


## 練習題

### Recursion 的美妙
```python
def fib(order):
    if order < 2:
        return order
    else:
        return fib(order-1) + fib(order-2)

for i in range(10):
    print fib(i)

#0
#1
#1
#2
#3
#5
#8
#13
#21
#34
```

請講講看這程式在做什麼？上面化成比較數學的寫法如下：

* fib(0) = 0
* fib(1) = 1
* fib(n) = fib(n-1) + fib(n-2)

那有一個組合數學的公式，請你回憶或是推導一下，用類似的方式做出來。

* C(n,r) = C(n-1,r-1) + C( n-1, r)
* C(n,n) = 1
* C(n,1) = n
* C(n,r) = 1  if r > n


這裏的 Ｃ是 Combination, 組合的意思。從 n 個橘子取 r 個橘子出來有幾種組合。

## 算一個數是不是質數

請先從基本定義著手

## 人肉積分

一樣是基本定義

```python
def anonymous(x):
    return x**2 + 1


def integrate(fun, start, end):
    step = 0.1
    intercept = start
    area = 0
    while intercept < end:
        intercept += step
        ''' your work here '''
    return area

print(integrate(anonymous, 0, 10))

```
