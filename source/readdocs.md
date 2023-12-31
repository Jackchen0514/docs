# How to use read the docs by sphinx

!!! note
    Thie is a note

## ubuntu20.04 install sphinx

Update the Package List:
```bash
sudo apt update
sudo apt upgrade
```


Install Python and pip:
```bash
sudo apt install python3-pip
```

Install Sphinx:
```
pip3 install sphinx
```

Verify Installation:
```
sphinx-build --version
```

Optional: Install the Sphinx RTD Theme:
```
pip3 install sphinx_rtd_theme
```

Then, in your Sphinx project's conf.py file, you can set the theme by modifying the html_theme variable:
```
html_theme = "sphinx_rtd_theme"
```

Start a New Sphinx Project:
```
mkdir mydocs
cd mydocs
sphinx-quickstart
```

## Show Markdown Docs

install recommonmark:
```
pip3 install recommonmark
```

in 'conf.py' file, add text:
```
# 在文件顶部添加：
from recommonmark.parser import CommonMarkParser

# 在文件中找到 source_suffix 配置项，并添加 .md 扩展名：
source_suffix = ['.rst', '.md']

# 添加 Markdown 解析器：
source_parsers = {
    '.md': CommonMarkParser,
}

```

create a new Markdown file, such as 'example.md'
```
# My Markdown Page

This is a sample page written in Markdown.
```

Add a new Markdown file to 'index.rst'
```
.. toctree::
   :maxdepth: 2
   :caption: Contents:

   example
```

build docs
```
make html
```

review docs
in `mydocs/build/html`, find `index.html` file
open it with chrome

## build project On Read the Docs

create or update `requirements.txt` file:
```
recommonmark
```


配置Read the Docs以使用requirements.txt:

登录到Read the Docs并进入您的项目的管理页面。
在“Admin”部分，选择“Advanced Settings”。
在“Requirements file”字段中，输入requirements.txt的路径（相对于项目的根目录）。
保存更改。

触发新的构建

