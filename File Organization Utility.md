## File Organization Utility

### shutil

shutil, or called shell utility, it provides functions like copy, move, or delete files.

#### copy & move

- shutil.copy(source, destination)

- shutil.copytree(source, destination)

  ```python
  >>> import shutil
  >>> shutil.copy('/usr/python/config.json', './sample')  # Copy file to folder 
  >>> shutil.copy('/etc/config/a.txt', './config/a.json') # Copy file to folder, and rename
  >>> shutil.copytree('/etc/config', '/tmp') # Copy whole config folder to /tmp folder
  ```

- shutil.move(src, dest)

  Note : The destination folder must be exist, otherwise it encounters FileNotFoundError

  

#### delete

- os.unlink(path) - delete a file specified by path
- os.rmdir(path) - delete an empty folder
- shutil.rmtree(path) - delete whole folder, including all sub folders and files contained.



#### send2trash

Using shutil to delete file is very dangerous, the detelted file can not be recovered. Instead, can use a third party module named `send2trash`, it will move these deleted files to trash bin, so it still can be recovered later. 

```python
>>> import send2trash
>>> send2trash.send2trash('./sample.txt')  # delete file sample.txt in current dir, the file will be moved to system transh bin
```



#### walk through whole directory

`os.walk()` can walk through the whole directory, including all sub directories and files.

```python
>>> import os
>>> for dirname, subdirs, files in os.walk('/etc'):
  			print(f'current fold is {dirname}')
    		for subdir in subdirs:
        		print(f'Sub folder of {dirname} : {subdir}')
        for file in files:
          	print(f'File inside {dirname} : {file}')
```















