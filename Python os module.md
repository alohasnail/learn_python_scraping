## Python os module 

#### common functions

- os.path.join()

  ```python
  import os
  os.path.join('usr', 'bin', 'spam')
  # 'usr/bin/spam'
  ```

- os.getcwd()

- os.chdir(path)

- os.makedirs(path)

- os.path.abspath(path)

- os.path.isabs(path)

- os.path.relpath(path, start)

  ```python
  >>> os.path.abspath('.')
  '/Users/ym'
  >>> os.path.isabs('.')
  False
  >>> os.path.isabs(os.path.abspath('.'))
  True
  >>> os.path.relpath('C:\\Windows', 'C:\\spam\\eggs')
  '..\\..\\Windows'
  ```

- os.path.dirname(path)

- os.path.basename(path)

- os.path.split(path)

- os.path.sep

  ```python
  >>> path = '/etc/python/myblog/index.html'
  >>> os.path.dirname(path)
  '/etc/python/myblog'
  >>> os.path.basename(path)
  'index.html'
  >>> os.path.split(path)
  ('/etc/python/myblog', 'index.html')
  >>> path.split(os.path.sep)
  ['','etc','python','myblog','index.html']
  ```

- os.path.getsize(path)

- os.listdir(path)

  ```python
  >>> totalSize = 0
  >>> for filename in os.listdir('/etc/'):
    			totalSize += os.path.getsize(os.path.join('/etc',filename))
  ```

- os.path.exists(path)

- os.path.isfile(path)

- os.path.isdir(path)