# ipython 妙用

除了使用 IDE 來開發一個完整的程式，我們在做實驗，系統管理時，會希望一個指令一個動作，ipython 除了互動能力比較高之外，也增加了更多語法，讓系統管理跟資料分析更加方便。

## 方便複製貼上程式碼

```python
In [1]: a = 10

In [2]: print a
10
```

上面這段程式碼可以直接完整貼回 ipython 的 shell, 他知道你在複製貼上

## 算過的數值通通有記住

```python
In [3]: 5000 / 1.05
Out[3]: 4761.9047619047615

In [4]: Out[3]
Out[4]: 4761.9047619047615
```

預設有一個 Out list, 裡面都是之前 shell 每一行算過的數值

## 立刻看文件

```python
In [6]: random.choice?
Type:        instancemethod
String form: <bound method Random.choice of <random.Random object at 0x7f8c8107ba20>>
File:        /System/Library/Frameworks/Python.framework/Versions/2.7/lib/python2.7/random.py
Definition:  random.choice(self, seq)
Docstring:   Choose a random element from a non-empty sequence.
```
在任何 物件，function 後面加上 ?  就可以看文件。

有的時候，文件看不清楚，那就加上兩個?? 可以看清到程式碼。
```bash
In [48]: random.seed??
Type:        instancemethod
String form: <bound method Random.seed of <random.Random object at 0x7f8c8107ba20>>
File:        /System/Library/Frameworks/Python.framework/Versions/2.7/lib/python2.7/random.py
Definition:  random.seed(self, a=None)
Source:
    def seed(self, a=None):
        """Initialize internal state from hashable object.

        None or no argument seeds from current time or from an operating
        system specific randomness source if available.

        If a is not None or an int or long, hash(a) is used instead.
        """

        if a is None:
            try:
                a = long(_hexlify(_urandom(16)), 16)
            except NotImplementedError:
                import time
                a = long(time.time() * 256) # use fractional seconds

        super(Random, self).seed(a)
        self.gauss_next = None
```

## 呼喚系統上的執行擋

加上 ! 在前， ipython 就知道你要呼喚系統的命令

```bash
In [11]: !ls
README.md	_book		basic_ediotr	imgs.png	play_-		start_-
SUMMARY.md	basic		imgs.graffle	ipython		python

In [13]: !wc ~/.vimrc
       7      17     103 /Users/tim/.vimrc

In [14]: a = !cat ~/.vimrc

In [15]: a
Out[15]:
['syntax on',
 'set bg=dark',
 ':set tabstop=4',
 ':set shiftwidth=4',
 ':set expandtab',
 'ab utf8 # -*- coding: utf-8 -*-',
 '']

In [16]: !nslookup www.google.com
Server:		168.95.1.1
Address:	168.95.1.1#53

Non-authoritative answer:
Name:	www.google.com
Address: 74.125.203.99
Name:	www.google.com
Address: 74.125.203.147
Name:	www.google.com
Address: 74.125.203.105
Name:	www.google.com
Address: 74.125.203.103
Name:	www.google.com
Address: 74.125.203.104
Name:	www.google.com
Address: 74.125.203.106

```
還可以直接做 variable interpolation

```bash
In [24]: doamin_name = 'www.google.com.tw'

In [25]: !nslookup $doamin_name
Server:		168.95.1.1
Address:	168.95.1.1#53

Non-authoritative answer:
Name:	www.google.com.tw
Address: 74.125.203.94
```

回傳值放在一個 list 的子類別

## 練習

請用 ipython 查詢 open 的文件，請問他的文件說什麼？


