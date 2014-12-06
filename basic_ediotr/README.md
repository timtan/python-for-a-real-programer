# 寫程式的工具
身為 Python 工程師，你在寫程式的過程，你會常常用到下列不同的工具。

* 編輯器: VIM, SublimeText3
* IDE: Eclipse + Pydev, PyCharm


## 編輯器跟 IDE 的差別

編輯器會幫助我們編輯，讓編輯文字的工作更順手。 IDE 會對程式語言有支援。

編輯器會直接面對檔案跟資料夾，而且你為了優化寫程式的過程，通常還要自己裝編輯器額外的套件，所以你會慢慢地對你所用的程式語言的細節非常了解。但缺點是設定耗時，編輯器套件跟套件間也有相衝突的機會（比如說熱鍵就有可能衝突)。

而使用IDE，可以想像成是一個已經裝好許多套件的編輯器，而且都幫你設定好，不可能相衝突了。缺點就是剛使用時會覺得很複雜，以及因為事先裝好了很多套件，執行速度會比只使用編輯器較慢。而且 IDE 對寫程式有很多的輔助，有時會讓工程師失去用其他工具寫程式的能力。

## VIM 的 Quick Tips

之前已經順便裝好了 vim

馬上來試試看:

```bash
vim test.py
```
進入了 vim 以後，請瞭解 vim 有兩個常用模式（其實是六個）insert mode 跟 normal Mode.

在 normal mode, 鍵盤上所有的按鍵都是熱鍵,都有你意想不到的功能，而這個模式不是讓你正常打字用的。

當你鍵入 i, 你就進入的 insert mode. 這時就可以正常打字了。 這時請貼上下面的程式碼

```python
# -*- coding: utf-8 -*-
import random
possible = [ u'剪刀', u'石頭', u'布']
print random.choice(possible)
```

最後存擋，要再回到 normale mode (按 esc)，然後連續按 ZZ (大寫喔)。

然後你可以在 bash  的 shell 執行剛剛的程式碼:
```bash
python test.py
```

不過預設的 vim 相當的陽春。我們需要調整一下 vim 的設定才方便寫 python

```bash
vim ~/.vimrc
```
.vimrc 也是一個普通的文字檔，所以編輯的步驟是不變的。 進入 insert mode, 才能編輯，編輯完，要到 normal model 才能按 ZZ 存檔離開。

```vim
:set tabstop=4
:set shiftwidth=4
:set expandtab
```

這時候，再回去編輯原來的 test.py 應該會覺得畫面比較好看。

之後會再多帶一點點 vim 的技巧。

# PyCharm

一開始使用會相當混亂，可以在使用 vim 還有 pycharm 搭配使用，互相了解優點，最後找出你最喜歡的工作方式。而且 PyCharm  還有 vim 的 plugin, 不過都等到很熟悉以後再去玩。

想辦法建立一個 Project, 並且建立一個 first.py 。我們就在 first.py 裡面練習。

請在 pycharm 裡面一個字一個字 key 下面的程式碼，如果有自動補齊出現，請按 enter, 讓 pycharm 幫你補齊。

```python
a = list()
a.append(10)
a.append(3)
a.append(9)
print a
a.sort()
print a
```

並且看一下 Run 裡面的第一個選項是什麼意思，以及熱鍵是什麼？

你可以把程式碼內的 10, 3, 9 換換數字，並且再度執行看看（用熱鍵）

編輯，並且按熱鍵執行的循環，可以好好熟悉。

## 練習

觀察下面的行為， pycharm 的反應，若是可以看到電燈泡出現，請試著點電燈泡。

* 把 list() 換成 listx()
* 把其中一個 a.append 換成 b.appedn
* 把上面的 append 故意把一個字母打錯字
* 多打一行 pigg = 10

上面都會出現各種錯誤，請都靠 pycharm 來幫你訂正錯誤。



