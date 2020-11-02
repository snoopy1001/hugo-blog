---
title: "[笔记] pandas from_dict"
date: 2020-10-27
lastmod: 2020-10-27
draft: false
tags: ["Python", "pandas", "from_dict"]
categories: ["Python"]

---



## 介绍

官方文档

<iframe width=100% height=550px frameborder=0 scrolling=auto src=https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.from_dict.html></iframe>





## 示例

默认情况下，字典的键成为 DataFrame 的列：

```python
>>> data = {'col_1': [3, 2, 1, 0], 'col_2': ['a', 'b', 'c', 'd']}
>>> pd.DataFrame.from_dict(data)
   col_1 col_2
0      3     a
1      2     b
2      1     c
3      0     d
```

指定 orient='index' 使用字典键作为行来创建 DataFrame：

```python
>>> data = {'row_1': [3, 2, 1, 0], 'row_2': ['a', 'b', 'c', 'd']}
>>> pd.DataFrame.from_dict(data, orient='index')
       0  1  2  3
row_1  3  2  1  0
row_2  a  b  c  d
```

使用 ‘index’ 方向时，可以手动指定列名称：

```python
>>> pd.DataFrame.from_dict(data, orient='index',
...                        columns=['A', 'B', 'C', 'D'])
       A  B  C  D
row_1  3  2  1  0
row_2  a  b  c  d
```

## 参考

- pandas.DataFrame.from_dict https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.from_dict.html

- 如何将 Python 词典转换为 Pandas DataFrame https://www.delftstack.com/zh/howto/python-pandas/how-to-convert-python-dictionary-to-pandas-dataframe/