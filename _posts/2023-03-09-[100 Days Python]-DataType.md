---
layout: single
title:  "[100 Days python] D-2: DataType"
excerpt: "Day 1 - Python Print Function\nThe function is declared like this:\nprint("

categories: python
tags: [python, udemy, dr.angela]
toc: true
toc_sticky: true
 
date: 2022-03-09
# last_modified_at: 2020-05-25
---

# 1. DType
```python
# String
print("Hello" [2])  
# >> l: 대괄호 숫자 번쨰에 있는 철자 선택. 첫번째는 0번째 자리 [0] >> H

print("123" + "345")  
# 123345
# "" 안에 있으므로 문자열 취급. / +는 연산에선 덧셈, 문자열에선 결합


# integer
print(123 + 456) #579


# float
3.14159
mystery = 734_529.678
print(mystery)  
# 734529.678 : _ 은 큰 수를 쉽게 읽기 위한 용도일뿐, 프로그램에선 무시함.


# boolean
True
False
```


## 1-1. quiz
```python
street_name = "Abbey Road"
print(street_name[4] + street_name[7])  # yo : "" 할당된 변수값에 적용. ""내에선 공백도 문자열 취급
```

# 형식오류와 형 확인/변환
```python
num_char = len(input("What's your name? "))
#   print("Your name has" + num_char + " cahracters.") >>> TypeError: can only concatenate str (not "int") to str  문자열끼리만 엮기 가능
```

```python
print(type(num_char))  # int
```

# casting
```python
new_num_char = str(num_char)
print("Your name has " + new_num_char + " cahracters.")
```

#
```python
a = float(123)

print(70 + float("100.5"))  # 170.5
print(str(70) + str(100))  # 70100
```