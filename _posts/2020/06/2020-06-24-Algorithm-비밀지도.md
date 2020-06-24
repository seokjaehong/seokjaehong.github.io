---
title: "ALGO_Programmers_비밀지도 "
categories:
  - TIL
  - Algorithm
tags:
  - Algorithm
toc: true
toc_label: "MyList"
---

### 내용 : 
n=5, arr1 :[9, 20, 28, 18, 11], arr2 :[30, 1, 21, 17, 28]
이진수로 변환했을 떄 n*n형태의 array가 있을때 한쪽에 1 이 있으면 #


<hr>

### 구현
  ```python
  def solution(n, arr1, arr2):
    def remove_bin(n,_list):
        a=_list[2:]
        if len(a)>=n:
            return a
        return ['0']*(n-len(a))+a

    def num2bool_list(num1,num2):   
        a=list(bin(num1))
        b=list(bin(num2))

        c=remove_bin(n,a)
        d=remove_bin(n,b)
        result=""
        for i,j in zip(c,d):
            if i+j=="00":
                result+=" "
            else:
                result+="#"
        return result
    answer=[]
    for i,j in zip(arr1,arr2):
        answer.append(num2bool_list(i,j))

    return answer
  ```

### 다른사람 코드 
 ```python

def solution(n, arr1, arr2):
    answer = []
    for i,j in zip(arr1,arr2):
        a12 = str(bin(i|j)[2:])
        a12=a12.rjust(n,'0')
        a12=a12.replace('1','#')
        a12=a12.replace('0',' ')
        answer.append(a12)
    return answer
 ```


### REMIND 
- rjust.. 
- 내 코드는 다시짜라.........string 처리 처음부터 다시 읽어봐야 겠다
- 
