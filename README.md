# Python dasturlar

## 1-dastur. Fayllarni kengaytmasiga qarab saralash dasturi

```python

import os

path = '.'  # files path
files_list = os.listdir(path)

for file_ in files_list:
    file_name, extension = os.path.splitext(file_)
    extension = extension[1:]
    if extension == '':
        continue
    if os.path.exists(path + '/' + extension):
        os.replace(path + '/' + file_, path + '/' + extension + '/' + file_)
    else:
        os.makedirs(path + '/' + extension)
        os.replace(path + '/' + file_, path + '/' + extension + '/' + file_)

```
