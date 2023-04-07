---
layout: single
title: "[100 Days python] D-2: DataType"
excerpt: type, 형식오류, 캐스스티팅, 각 자릿값 더하기, 연산자자, bmi calc, 올/내림, 남은인생, 팁calc

categories: python
tags:
  - dr.angela
  - python
  - udemy
  - type
toc: true
toc_sticky: true

date: 2023-03-08T23:30:05.000Z
slug: "[100-days-python]-2-datatype"

# last_modified_at: 2020-05-25
---

<br>

# 1. Data Type
```python
# String
print("Hello" [2])  # >> l: 대괄호 숫자 [n]번째 철자 선택. 첫번째는 0번째 자리 [0] >> H
print("123" + "345")  # 123345 / "" 안에 있으므로, 정수가 아닌 문자열 취급.

# integer
print(123 + 456) #579

# float
mystery = 734_529.678
print(mystery) #734529.678 : _ 은 큰 수를 쉽게 읽기 위한 용도일뿐, 프로그램에선 무시함.

# boolean
True
False
```

## 1-1. quiz
```python
street_name = "Abbey Road" 일 때,
print(street_name[4] + street_name[7]) ??
```
**>>> yo** <br>
street_name에 할당된 변수값(Abbey Road)에 적용. " "내에선 **공백도 문자열** 취급: 공백의 자리값은 **[5]**

<br>

# 2. 형식오류와 형 확인/변환

```python
num_char = len(input("What's your name? "))
```
입력한 이름의 철자 길이를 num_char에 할당: int 타입

## 2-1. 형식오류, 타입확인, 변환(casting)

```python
# 형식오류
print("Your name has" + num_char + " cahracters.") 
                문자열 + 정수값변수int + 문자열
# TypeError: can only concatenate str (not "int") to str
# >>> 문자열끼리만 엮기 가능 > 타입 변환 필요

# 타입확인: type()
print(type(num_char))  # int

# 변환(casting)
new_num_char = str(num_char) 
#정수값 num_char를 문자열로 변환 > new_num_char에 할당
print("Your name has " + new_num_char + " cahracters.")
```

## 2-2. int > float
```python
a = float(123) # 123.0

print(70 + float("100.5"))  # 170.5
print(str(70) + str(100))  # 70100 : 70|100 문자열 그대로 이어줌.
```
<br>

# 3. 두 자리 정수의 각 자릿값을 더해주는 함수
Write a program that adds the digits in a 2 digit number. e.g. if the input was 35, then the output should be 3 + 5 = 8
```python
two_digit_number = input("Type a two digit number: ") 
```
## 3-1. answer-A
```python
A========================================
print(int(two_digit_number[0]) + int(two_digit_number[1]))

A-1?========================================
print(int(two_digit_number[0] + two_digit_number[1]))

B: 자릿값 별 변수 적용======================
first_digit = two_digit_number[0]
second_digit = two_digit_number[1]
result = int(first_digit) + int(second_digit)
print(result)

C========================================
number = int(input("2 digits num? \n"))
print(type(number))
print(number[0] + number[1])
```

A-1: 자리별 값의 합 아님: 각 자리별 두 (숫자형태의) "문자열"이 순서대로 합쳐진 다음(int + int가 아닌, str + str), 정수형으로 변환. <br>
*14) 1 + 4 => 5가 아닌 "1" + "4" => 14*
<br>

# 4. Operator
```python
print(6 / 3)  
print(2**8)
```
***2.0*** : 나누기는 늘 부동소수 형태도 표현됨. <br>
***256***
<br>

# 5. BMI Calculator
> Write a program that calculates the Body Mass Index (BMI) from a user's weight and height. <br> The BMI is calculated by dividing a person's weight (in kg) by the square 제곱 of their height (in m): <br> **Warning** you should convert the result to a whole number.

```python
height = input("enter your height in m: ")  # m로 입력 !!!
weight = input("enter your weight in kg: ")
``` 
## 5-1. answer
```python
# print(type(height))
# print(type(weight)) >> input(입력함수)로부터 받는 값은 문자열

BMI = float(weight) / float(height)**2
print(f"Your BMI is {BMI}")

# 소수점 너무 기니까 정수형으로 치환
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
score = 12
height = 1.8
isWinning = True
print(
    f"your score is {score}, your height is {height}, you are winning is {isWinning}")

print(f"your name has {len(input("name? "))} letters!") 
# f-string: unmatched '('
``` 
F-string: 문자열과 타 데이터타입 혼합

<br>

# 7. 인생 남은 시간
> Create a program using maths and f-Strings that tells us how many days, weeks, months we have left if we live until 90 years old.
> 
> **Example Output** <br> You have 12410 days, 1768 weeks, and 408 months left.
> 
> **Warning** <br> your output should match the Example Output format exactly, even the positions of the commas and full stops.

```python
age = input("What is your current age? ")
``` 
<br>

## 7-1. Answer
```python
age_as_int = int(age)

days_remaining = (90 - age_as_int) * 365
weeks_remaining = (90 - age_as_int) * 52
months_remaining = (90 - age_as_int) * 12

message = f"You have {days_remaining} days, {weeks_remaining} weeks, and {months_remaining} months left."
print(message)
``` 

<br>

# 8. tip calculator
> If the bill was $150.00, split between 5 people, with 12% tip. <br> Each person should pay (150.00 / 5) * 1.12 = 33.6 <br> 
> Format the result to 2 decimal places = 33.60 <br> 
> Thus everyone's share of the total bill is $30.00 plus a $3.60 tip. <br> 
> 
> **Tip**: There are 2 ways to round a number. You might have to do some Googling to solve this.💪
> 
> **Example Input** <br> 
> Welcome to the tip calculator! <br> 
>What was the total bill? ***$124.56*** <br> 
>How much tip would you like to give? 10, 12, or 15?  ***12*** <br> 
>How many people to split the bill? ***7***
>
> **Example Output** <br> You have 12410 days, 1768 weeks, and 408 months left.
> 
> **Warning** <br> your output should match the Example Output format exactly, even the positions of the commas and full stops.

## 8-1. Answer

```python
print("Welcome to the tip calculator.")
bill = float(input("What was the total bill? $"))
tip = int(input("What percentage tip would u like to give? 10, 12, or 15? "))
people = int(input("How many people to split the bill? "))

tip_as_percent = tip / 100
total_tip_amount = bill * tip_as_percent
total_bill = bill + total_tip_amount
bill_per_person = total_bill / people

# final_amount = round(bill_per_person, 2)
final_amount = "{:.2f}".format(bill_per_person)

print(f"Each person should pay: ${final_amount}")
``` 
<br> 
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

<br> 
<br> 

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