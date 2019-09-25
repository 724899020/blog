---
redirect_from:
  - "/python/python输出文件时带utf8bom"
interact_link: content/E:\code\businessDevOps\opsbook\content\python/python输出文件时带UTF8BOM.ipynb
kernel_name: python3
has_widgets: false
title: 'Python输出文件时带utf8bom'
prev_page:
  url: /逻辑工作法.html
  title: '逻辑工作法'
next_page:
  url: /python/参数.html
  title: '参数'
comment: "***PROGRAMMATICALLY GENERATED, DO NOT EDIT. SEE ORIGINAL FILES IN /content***"
---
# 原来的操作



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
# coding:utf-8

with open(args.out_path, 'r') as ff:
    content = ff.read()
    # Ensure that the section spacers are comments since they'll be YAML list items by default
    content = content.replace("- '{}'".format(toc_spacer), '\n' + toc_spacer)
    content = content.replace("\\","/")

```
</div>

</div>



# 现在的操作



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
# coding:utf-8
import codecs

with codecs.open(args.out_path, 'r','utf_8_sig') as ff:
    content = ff.read()
    # Ensure that the section spacers are comments since they'll be YAML list items by default
    content = content.replace("- '{}'".format(toc_spacer), '\n' + toc_spacer)
    content = content.replace("\\","/")

```
</div>

</div>

