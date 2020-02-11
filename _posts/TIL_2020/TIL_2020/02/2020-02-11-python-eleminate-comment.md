---
title: "Python: Eliminate comment"
categories:
  - Python
tags:
  - Python
sidebar:
  nav: "docs"
toc: true
toc_label: "MyList"
---

### 파이썬으로 코드 주석제거하기 

코드에 작성된 주석을 정규표현식을 이용해서 제거하는 기능입니다. Python으로 작성합니다.

1. C언어
- 제거 할 주석 : // , #, /* */ (구간)
```
re.sub(re.compile(r'/*.*\*/', re.DOTALL), "", 
re.sub(re.compile(r"//.*[\n\\Z]"), "",
re.sub(re.compile(r"#.*[\n\\Z]"),"", code)))
```

2.  Java
- 제거할 주석 :  **/* */** , //, /* .*/ 
```
re.sub(re.compile(r'/*.*\*/', re.DOTALL), "", 
re.sub(re.compile(r"//.*[\n\\Z]"), "",
re.sub(re.compile(r'/*\*.*\*/',re.DOTALL), "",code)))
```

3. Python
- 제거할 주석 : #, """ """, ''' ''' 
```
re.sub(re.compile(r"#.*[\n\\Z]"), "", 
re.sub(re.compile(r'""".*"""', re.DOTALL), "",
re.sub(re.compile(r"'''.*'''", re.DOTALL),"",code)))
```