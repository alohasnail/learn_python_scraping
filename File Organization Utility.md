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













