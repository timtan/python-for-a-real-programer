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

更多基本的 tutorial, 請先參考[Django Girls Taipei 的文件](http://djangogirlstaipei.herokuapp.com/tutorials/python/)


