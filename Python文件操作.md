## Ptyhon 文件操作

#### 用shelve模块保存变量

存入变量

```python
>>> import shelve
>>> shelf_file = shelve.open('mydata')   # will create a mydata.db file on macOS
>>> names = ['Steven', 'Jack', 'Yolanda']
>>> shelf_file['names'] = names
>>> shelf_file.close()
```

读取变量

```python
>>> import shelve
>>> shelf_file = shelve.open('mydata')
>>> print(shelf_file['names'])
['Steven', 'Jack', 'Yolanda']
>>> list(shelf_file.keys())
['names']
>>> list(shelf_file.values())
[['Steven', 'Jack', 'Yolanda']]
>>> shelf_file.close()
```



#### 用pprint.pformat()函数保存变量

假定你有 一个字典，保存在一个变量中，你希望保存这个变量和它的内容，以便将来使用。 pprint.pformat()函数将提供一个字符串，你可以将它写入.py 文件。该文件将成为你自 己的模块，如果你需要使用存储在其中的变量，就可以导入它。

```python
>>> import pprint
>>> names = [{'name': 'Steven', 'age': 29}, {'name': 'Jane', 'age': 26}]
>>> fileObj = open('names.py', 'w')
>>> fileObj.write('names = ' + pprint.pformat(names) + '\n')
>>> fileObj.close()
```

倒入模块，取出变量

```python
>>> import names
>>> names.names
[{'name': 'Steven', 'age': 29}, {'name': 'Jane', 'age': 26}]
>>> names.names[0]
{'name': 'Steven', 'age': 29}
>>> names.names[1]['name']
'Jane'
```

