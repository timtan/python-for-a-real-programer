讓你的 Python 程式被使用

   3. 如何成為一個安裝包
   4. 如何編譯模組
   2. 成為一個系統工具




基本款

先建立一個資料夾，以後裡面放自己的程式碼。

```bash
mkdir /tmp/sample
cd /tmp/sample
vim setup.py
```

把下面的程式碼放進去 setup.py

```py
# 放進去 setup.py

#!/usr/bin/env python

from distutils.core import setup

setup(name='SetupSample',
        version='1.0',
        description='Example',
        author='Tim Hsu',
        author_email='tim.yellow@gmail.com',
        url='https://www.python.org/sigs/distutils-sig/',
     )
```

這裏都只放一些很靜態的資訊而已。


```bash
python setup.py
```

傻傻地執行，可以看到一些建議的步驟

```bash
usage: setup.py [global_opts] cmd1 [cmd1_opts] [cmd2 [cmd2_opts] ...]
   or: setup.py --help [cmd1 cmd2 ...]
   or: setup.py --help-commands
   or: setup.py cmd --help

```

空空如也，一樣可以安裝

```bash

timdeMacBook-Pro:PySetupExample tim$ python setup.py --help-commands
Standard commands:

  build            build everything needed to install
  build_py         "build" pure Python modules (copy to build directory)
  build_ext        build C/C++ extensions (compile/link to build directory)
  build_clib       build C/C++ libraries used by Python extensions
  build_scripts    "build" scripts (copy and fixup #! line)
  clean            clean up temporary files from 'build' command
  install          install everything from build directory
  install_lib      install all Python modules (extensions and pure Python)
  install_headers  install C/C++ header files
  install_scripts  install scripts (Python or otherwise)
  install_data     install data files
  sdist            create a source distribution (tarball, zip file, etc.)
  register         register the distribution with the Python package index
  bdist            create a built (binary) distribution
  bdist_dumb       create a "dumb" built distribution
  bdist_rpm        create an RPM distribution
  bdist_wininst    create an executable installer for MS Windows
  upload           upload binary package to PyPI
  check            perform some checks on the package

```

最後真的來裝一下吧

```
sudo python setup.py install
```

然侯來看裝完的東西吧

```
pip freeze | grep SetupSample
```

恩... 恭喜大家完成一個空空如也的套件...

這裏是完整的文件

https://docs.python.org/2/distutils/setupscript.html

##發佈你寫的一個模組

我們來發佈一個簡單的 Python 模組吧

```bash
vim hi.py
```

這裏是 hi.py 的內容

```py
def say_hi():
    print "hi"
```

然後更新 setup.py  (重點在最後一行)

```py
setup(name='SetupSample',
        version='1.0',
        description='Example',
        author='Tim Hsu',
        author_email='tim.yellow@gmail.com',
        url='https://www.python.org/sigs/distutils-sig/',
        py_modules = ['hi'], ## 這裏有差
     )
```

然後再裝一次

```bash
sudo python setup.py install
```

之後你在你系統的任何地方開啟 python shell 都可以  import hi

```py
In [3]: import hi

In [4]: hi.say_hi
Out[4]: <function hi.say_hi>

In [5]: hi.say_hi()
hi
```


## Scripts

Terminal 裡面的工具很帥（cat touch ls），我們也來做一個。

做一個 cat2  (偏不要加上副檔名 .py)

```py

#!/usr/bin/env python
print "meow~"

```

```py
#!/usr/bin/env python

from distutils.core import setup

setup(name='SetupSample',
        version='1.0',
        description='Example',
        author='Tim Hsu',
        author_email='tim.yellow@gmail.com',
        url='https://www.python.org/sigs/distutils-sig/',
        py_modules = ['hi'],
        ## below are some magic
        scripts=['cat2', ],
     )
```

再裝一次

```bash
sudo python setup.py install
```

然後你就得到了 cat2 這個指令

來執行看看吧

```bash
cat2
```



##最後

反安裝

```
pip uninstall SetupSample
```

```
pip freeze | grep Sam   #你會看到空空如也
```


把程式碼丟到 githib 上 （butbucket 也行）

這裏先提示一下作法：

先到 github 註冊帳號，開啟 Repository, 名字隨意

```bash
sudo rm -rf build
sudo rm -rf *.pyc
git init
git add *
git commit -m init

git remote add origin https://github.com/timtan/setup-py-example.git #這是你的 Repo，每人不同
git push -u origin master
```


之後

sudo pip install git+https://github.com/timtan/setup-py-example

git+  URL  都要自己加上去

上面的原因我忘了

你就可以直接裝你自己放在 github 的套件




