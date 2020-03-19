---
title: "Python : args vs kwargs"
categories:
  - TIL
  - Python
tags:
  - Python
  - args 
  - kwargs
toc: true
toc_label: "MyList"
---
## *args vs **kwargs

Python에서 함수를 호출할 때 많이 사용하는 `*args` 와 `**kwargs`에 대해서 알아본다. 
사실 반드시 `*args` 와 `**kwargs`라고 꼭 쓸필요는 없지만, 보통 이렇게 사용한다. (`*vars` or `**vars` 이렇게 사용해도 무관하다. )

### 1. ***args**

- 보통 함수에 몇개의 인수를 전달할지 모를 때 사용하는데, `*args`는 `키워드 인자가 아닌 변수`를 전달할때 사용한다.

```python
def test_var_args(f_arg, *args):
    print('first arg:', f_arg)
    for arg in args:
        print('other arg:', arg)

test_var_args('hong', 'number1', 'number2', 'number3')
```

```python
first arg: hong
other arg: number1
other arg: number2
other arg: number3
```

### 2. ****kwargs**

- `키워드 인자`를 전달할 때 사용한다.

```python
  def say_hi(**kwargs):
    for k,v in kwargs.items():
      print("{0} ={1}".format(k,v))
>>> say_hi(name="hong)
name =hong
```
