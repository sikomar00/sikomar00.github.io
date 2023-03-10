---
layout: single
title: "[100 Days python] D-2: DataType"
excerpt: "print(Hello [2])  >> l: 대괄호 숫자 번쨰에 있는 철자 선택. 첫번째는 0번째 자리 [0] >> H"

categories: python
tags:
  - python
  - udemy
  - dr.angela
toc: true
toc_sticky: true

date: 2022-03-09
slug: "[100-days-python]-2-datatype"

# last_modified_at: 2020-05-25
---

<br>

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
print(street_name[4] + street_name[7])  
```
yo : street_name에 할당된 변수값(Abbey Road)에 적용. ""내에선 **공백도 문자열** 취급: 공백의 자리값은 **[5]**

<br>
<br>

# 2. 형식오류와 형 확인/변환
```python
num_char = len(input("What's your name? "))
```
입력한 이름의 철자 길이를 num_char에 할당

## 2-1. 형식오류

```python
print("Your name has" + num_char + " cahracters.") 
문자열 + 정수값변수 + 문자열
```
TypeError: can only concatenate str (not "int") to str <br>>> 문자열끼리만 엮기 가능

## 2-2. 타입확인
```python
print(type(num_char))  # int
```
type: 괄호 안 데이터의 타입을 알려줌

## 2-3. casting, 데이터 형 변환
```python
new_num_char = str(num_char)
print("Your name has " + new_num_char + " cahracters.")
```
정수값인 num_char를 문자열로 변환하여 new_num_char에 할당
### 2-3-1. int > float
```python
a = float(123)

print(70 + float("100.5"))  # 170.5
print(str(70) + str(100))  # 70100
```
<br>

# 3. 두 자리 정수의 각 자릿값을 더해주는 함수
```python
two_digit_number = input("Type a two digit number: ") 

print(int(two_digit_number[0] + two_digit_number[1]))
```

## 3-1. answer-A
```python
print(int(two_digit_number[0] + two_digit_number[1]))
```
## 3-1. answer-B
```python
first_digit = two_digit_number[0]
second_digit = two_digit_number[1]
result = int(first_digit) + int(second_digit)
print(result)
```
<br>

# 4. Operator
```python
print(6 / 3)  # 2.0 나누기는 늘 부동소수 형태도 표현됨.
print(2**8)
```

# 5. BMI Calculator
```python
height = input("enter your height in m: ")  # m로 입력 !!!
weight = input("enter your weight in kg: ")
``` 

```python
print(type(height))
print(type(weight))

BMI = float(weight) / float(height)**2

print("Your BMI is " + str(BMI))
``` 
float(height): m단위이므로, float 변환 해주지 않으면, 1m, 2m --- 로 소수점 자리를 표현 할 수 없어짐.

이 상태로 출력하면 소수점 아래로 값이 길게 나오므로, 정수형으로 변환

```python
BMI_as_int = int(BMI)
print(BMI_as_int)
``` 

<br>

# 6. 올/내림 & F-string
```python
# 반올림 round()
print(round(8 / 3))  # 2.666... > 3
# 자릿수 지정 반올림 round(수식, 지정자릿수)
print(round(8 / 3, 2))  # 2.666... > 2.67
# 버림 //
print(8 // 3)  # 2

# 변수지정 & 재연산
result = 4 / 2  # >>> result 값은 2.0
result /= 2     # 2.0을 2.0으로 나눈 값
print(result)   # 1.0
``` 

## 6-1. F-string
```python
height = 1.8
isWinning = True

print(
    f"your score is {score}, your height is {height}, you are winning is {isWinning}")
``` 
F-string: 문자열과 타 데이터타입 혼합

<br>

# 7. 인생 남은 시간
```python
age = input("What is your current age? ")
``` 

```python
days_remaining = (90 - age_as_int) * 365
weeks_remaining = (90 - age_as_int) * 52
months_remaining = (90 - age_as_int) * 12

message = f"You have {days_remaining} days, {weeks_remaining} weeks, and {months_remaining} months left."
print(message)
``` 

<br>

# 8. tip calculator
```python
print("Welcome to the tip calculator.")
bill = float(input("What was the total bill? $"))
tip = int(input("What percentage tip would u like to give? 10, 12, or 15? "))
people = int(input("How many people to split the bill? "))

tip_as_percent = tip / 100
total_tip_amount = bill * tip_as_percent
total_bill = bill + total_tip_amount
bill_per_person = total_bill / people

# final_amount = round(bill_per_person, 2)  # 
final_amount = "{:.2f}".format(bill_per_person)


print(f"Each person should pay: ${final_amount}")
``` 

 <details>
<summary>소수점 2번쨰 0까지 표시되는 방법??</summary>
<div markdown="1">
:.2f 형식함수
먼저 { } 안에 :(콜론)을 넣어주고, .(점)을 찍은다음, 표시하고자 하는 자리수를 적고, float타입을 표시하는 f를 적습니다.<br>
>> {:.2f} <br>
그리고 이 중괄호 안에 들어가는 것이 무엇을 표시하는 것인지 밝혀주기 위해서
format함수를 쓰고 그 다음에 변수를 적어줍니다. <br>
>> {:.2f}.format(height)
</div>
</details> 


<!-- 
<br>

# 
```python

``` 

 <details>
<summary> title </summary>
<div markdown="1">

</div>
</details> 
-->