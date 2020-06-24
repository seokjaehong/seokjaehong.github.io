---
title: "ALGO_Programmers_실패율 "
categories:
  - TIL
  - Algorithm
tags:
  - Algorithm
toc: true
toc_label: "MyList"
---

### 내용 : 각 스테이지마다 실패율을 산정해서 정렬

<hr>

### 구현
  ```python
  def solution(N, stages):
    r=[]
    for i in range(1,N+1):
        if len(stages)>0:
            r.append((i,stages.count(i)/len(stages)))
        else:
            r.append((i,0))
        stages = [x for x in stages if x!=i]
    gg = sorted(r, key=lambda x:x[1],reverse=True)
    answer = [x[0] for x in gg]
    return answer
  ```

### 다른사람 코드 
 ```python
def solution(N, stages):
    result = {}
    denominator = len(stages)
    for stage in range(1, N+1):
        if denominator != 0:
            count = stages.count(stage)
            result[stage] = count / denominator
            denominator -= count
        else:
            result[stage] = 0
    return sorted(result, key=lambda x : result[x], reverse=True)
 ```


### REMIND 
- list of dictionary vs list of tuple 속도 비교 해 볼 것 (장/단점)
- python lambda 정리할 것 
- 
