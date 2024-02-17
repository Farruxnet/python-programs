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
## 2-dastur. Binary search

```python
lst = [1, 2, 3, 6, 7, 9, 12, 36, 46, 59, 67, 69, 71, 73, 85, 96, 101]

for i, v in enumerate(lst, start=0):
    print(f'{i} => {v}')


def binary_search(lst, item):
    first = 0
    last = len(lst) - 1
    while first <= last:
        mid = (first + last) // 2
        if lst[mid] == item:
            return mid
        else:
            if item < lst[mid]:
                last = mid - 1
            else:
                first = mid + 1


print(binary_search(lst, 69))
```
