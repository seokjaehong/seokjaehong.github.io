---
title: "TIL_20200212"
categories:
  - TIL
  - Python
tags:
  - Python
  - sorting
toc: true
toc_label: "MyList"
---
### Python Sort

Dictionary로 구성된 List를 특정 key를 통해 정렬하기.

### 1. lambda를 이용해 정렬

```python
new_list = sorted(_list, key=lambda k: k['key'])
```

### 2-1.itemgetter를 이용해 정렬

```python
from operator import itemgetter
new_list = sorted(_list,key=itemgetter('key'))
```

### 2-2.reverse 

```python 
new_list = sorted(l, key=itemgetter('key'), reverse=True)
```

성능은 2-1번 방법을 이용하는 것이 좀 더 빠름.