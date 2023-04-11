---
layout: single
title: "[100 Days python] D-1: print"
excerpt: print, 문자열연산출력, len, variable, band name generator

categories: python
tags:
  - dr.angela
  - python
  - udemy
  - print
toc: true
toc_sticky: true

date: 2022-03-08

# last_modified_at: 2020-05-25
---

<br>
# 1. 문제: 다음과 같이 출력되도록 코드짜기

 > Day 1 - Python Print Function <br> The function is declared like this: <br> print('what to print')

## 1-1. answer-A: \n
```python
#  \n 으로 줄바꿈 처리하여 한 번에
print("Day 1 - Python Print Function\nThe function is declared like this:\nprint('what to print')")
```

## 1-2. answer-B: print 분절
```python
print("Day 1 - Python Print Function")
print("The function is **declared** like this:")
print("print('what to print')") @@@
```

### 1-@@@. " " 대신 ' '을 쓴 이유?
" " 겹사용 하는 경우)
```
print("print("what to print")")
what to print 를 코드로,
" 사이에 있는 print와 )가 문자열로 인식됨.
``` 
따옴표 내에 같은 따옴표를 쓰면 그 사이를 문자열 혹은 코드로 인식함
<br>

# 2. 문자열 연산
```python
#문자열 더하기
print("Hello, " + "Omar") #  Hello, Omar

#문자열 곱하기
print("Hello," * 3)  # Hello,Hello,Hello,
```
## 2-1. 입력함수: Hello, (내이름)!
```python
print("Hello " + input("What is your name? "))
```

## 2-2. 입력한 이름의 글자수를 프린트 해주는 함수: len
```python
A=====================================================
name_length = len(input("What is your name? "))
print(name_length)
print(len(input("What is your name? ")))

B=======================================================
name = input("you name?")
print(f"your name has " + str(len(name)) + " letters!")

C=======================================================
print(f"your name has " + str(len(input("name? "))) + " letters!")
```
<br>

# 3. 변수
```python
name = input("What is your name? ")
leng = len(name)
print(leng)
```
## 3-1. 변수 a, b 저장값을 치환하는 프로그램 짜기
Write a program that switches the values stored in the variables a and b.
```python
#🚨 Don't change the code below 👇
a = input("a: ")
b = input("b: ")
# 🚨 Don't change the code above 👆

# 이 사이 어떤 코드가 들어가야 할까?

# 🚨 Don't change the code below 👇
print("a: " + a)
print("b: " + b)
```

### 3-1-1. answer
```python
c = a
a = b
b = c
```
<br>

# 5. Band Name Generator
1. Create a greeting for your program.
2. Ask the user for the city that they grew up in.
3. Ask the user for the name of a pet.
4. Combine the name of their city and pet and show them their band name.
5. Make sure the input cursor shows on a new line:
   
```python
A=====================================================
print("Hello! I'm Band Name Generator!\nplease respond the following questions to make Band Name.")

city = input("In which city you grew up? \n")  
# 줄바꿈은 큰따옴표 안에 있어야 함
pet_name = input("What's the name of your pet? \n")
print("Your Band Name is " + city + " " + pet_name)

B=====================================================
print("welcome!")
print(f"Your Band name is " +
      input("in which city do u live?\n") + " " + input(" your pet name?\n")+"s!!!")
      
```
<!-- <details>
<summary>접기/펼치기 버튼</summary>
<div markdown="1">

| 제목 | 내용 |
| ---- | ---- |
| 1    | 1    |
| 2    | 10   |

</div>
</details> -->


<!-- ```python
``` -->


