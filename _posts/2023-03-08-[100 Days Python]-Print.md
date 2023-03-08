---
layout: single
title:  "D-1: print"
excerpt: "Day 1 - Python Print Function\nThe function is declared like this:\nprint("

categories: python
tags: [python, udemy, dr.angela]
toc: true
toc_sticky: true
 
date: 2022-03-08
# last_modified_at: 2020-05-25
---

<br>
<br>

# 1. 문제: 다음과 같이 출력되도록 코드짜기

 Day 1 - Python Print Function <br>
 The function is declared like this: <br>
 print('what to print')

## 1-1. answer-A
```python
#  \n 으로 줄바꿈 처리하여 한 번에
print("Day 1 - Python Print Function\nThe function is declared like this:\nprint('what to print')")
```

## 1-2. answer-B
```python
print("Day 1 - Python Print Function")
print("The function is declared like this:")
print("print('what to print')") #
```

### ** "" 대신 ''을 쓴 이유?
print("print("what to print")") <br>
문자열: print( / <b>코드: what to print</b> / 문자열: ) <br>
따옴표 내에 같은 따옴표를 쓰면 그 사이를 문자열 혹은 코드로 인식함


# 2. 문자열 결합
```python
print("Hello, " + "Omar")
```


<!-- ```python
``` -->


