---
layout: single
title: "[100 Days python] D-3: Conditional"
excerpt: " "

categories: Blog
tags:
  - dr.angela
  - python
  - udemy
toc: 2023-04-03T02:57:14.281Z
toc_sticky: 2023-04-03T02:57:11.694Z

date: 2023-04-03T02:56:50.782Z
# last_modified_at: 2020-05-25
---
<br>

# 1.흐름제어: if / else / 조건연산자 

## water level  >  drain? continue?
```python
water_level = 80
if water_level > 80:
    print("Drain water")
else:
    print("Continue")
```
## rollerCoaster height
```python
print("Welcome to the Rollercoaster!")
height = int(input("What is your height in cm? "))

if height >= 120:
    print("u can ride!")
else:
    print("Sorry, u have to grow talled before u can ride it.")
```
## 1-1. Even or Odd
> Write a program that works out whether if a given number is an odd or even number.
> 
> Even numbers can be divided by 2 with no remainder.
> e.g. 86 is **even** because 86 ÷ 2 = 43
> 
> 43 does not have any decimal places. Therefore the division is clean.
> e.g. 59 is **odd** because 59 ÷ 2 = 29.5
> 
> 29.5 is not a whole number, it has decimal places. Therefore there is a remainder of 0.5, so the division is not clean.
> 
> The **modulo(나머지 : %)** is written as a percentage sign (%) in Python. It gives you the remainder after a division.<br>
> e.g. <br>
> 6 ÷ 2 = 3 with no remainder. >>> 6 % 2 = 0 <br>
> 5 ÷ 2 = 2 x **2** + 1, remainder is 1. >>> 5 % 2 = 1 <br>
> 14 ÷ 4 = 3 x **4** + 2, remainder is 2. >>> 14 % 4 = 2 <br>
> 
> **Warning** <br>
> your output should match the Example Output format exactly, even the positions of the commas and full stops.
> 
> Example Input ~ output 1 <br>
> 43 ~ This is an odd number.
>
> Example Input ~ output 2 <br>
> 94 ~ This is an even number.

```python
number = int(input("Which number do you want to check? "))
```
### 1-1-1 Answer
```python
if number % 2 == 0:
    print("This is an even number.")
else:
    print("This is an odd number.")
```
```
= / ==의 차이?
if number % 2 = 0:
if number % 2 == 0:
```

## 1-2. BMI 2.0

>Write a program that interprets the Body Mass Index (BMI) based on a user's weight and height. 
>It should tell them the interpretation of their BMI based on the BMI value.
>- Under 18.5 they are underweight
>- Over 18.5 but below 25 they have a normal weight
>- Over 25 but below 30 they are slightly overweight
>- Over 30 but below 35 they are obese
>- Above 35 they are clinically obese.
> <br>
> 
>The BMI is calculated by dividing a person's weight (in kg) by the square of their height (in m): weight / height ** 2
> <br>
> 
>**Warning**  <br>
>you should **round** the result to the nearest whole number. The interpretation message needs to include the words in bold from the interpretations above. <br>
> e.g. **underweight, normal weight, overweight, obese, clinically obese**.
> <br>
> 
>Example Input <br>
>weight = 85 <br>
>height = 1.75 <br>
> <br>
>Example Output <br>
>85 ÷ (1.75 x 1.75) =  27.755102040816325 <br>
>Your BMI is 28, you are slightly overweight. 

```python
height = float(input("enter your height in m: "))
weight = float(input("enter your weight in kg: "))
```
### 1-2-1 Answer
```python
BMI = round(weight / height**2)

if BMI < 18.5:
    print(f"Your BMI is {BMI}, you are underweight")
elif BMI < 25:
    print(f"Your BMI is {BMI}, you are normal weight")
elif BMI < 30:
    print(f"Your BMI is {BMI}, you are slightly overweight")
elif BMI < 35:
    print(f"Your BMI is {BMI}, you are obese")
else:
    print(f"Your BMI is {BMI}, you are clinically obese")
```

### 1-2-2 Wrong 1
```python
BMI = round(weight / height**2)

if BMI < 18.5:
    print(f"Your BMI is {BMI}, you are underweight")
elif 18.5 <= BMI < 25:
    print(f"Your BMI is {BMI}, you are normal weight")
elif 25 <= BMI < 30:
    print(f"Your BMI is {BMI}, you are slightly overweight")
elif 30 <= BMI < 35:
    print(f"Your BMI is {BMI}, you are obese")
elif BMI < 35:
    print(f"Your BMI is {BMI}, you are clinically obese")
```

- 첫번째 if에서 18.5 미만 수는 모두 걸러지므로, elif 문에 다시 이전 조건을 더할 필요는 없음.
- 마지막 elif조건은, BMI가 35이상인 경우를 커버하지 못함.

### 1-2-3 Wrong 2
```python
BMI = round(weight / height**2)

if 35 > BMI:
    print(f"Your BMI is {BMI}, you are clinically obese.")
elif 30 > BMI:
    print(f"Your BMI is {BMI}, you are obese.")
elif 25 > BMI:
    print(f"Your BMI is {BMI}, you are slightly overweight.")
elif 18.5 > BMI:
    print(f"Your BMI is {BMI}, you have a normal weight.")
else:
    print(f"Your BMI is {BMI}, you are underweight.")
```
- 첫 if 조건에 가장 큰 기준값이 적용된 경우, 이후 조건에서 걸러져야할 값이 해당 조건까지 내려가지 못하고 큰 기준값에 걸러져 버림.

## 1-3. Leap year

> Write a program that works out whether if a given year is a leap year. A normal year has 365 days, leap years have 366, with an extra day in February. The reason why we have leap years is really fascinating, <br>
> 
> This is how you work out whether if a particular year is a leap year. 
> 
> <br>
>> on every year that is evenly divisible by 4 <br>
>>>**except** every year that is evenly divisible by 100
>>>>**unless** the year is also evenly divisible by 400<br>
>
>e.g. <br> 
>The year 2000: <br>
>2000 ÷ 4 = 500 (Leap) <br>
>2000 ÷ 100 = 20 (Not Leap) <br>
>2000 ÷ 400 = 5 (Leap!) <br> 
>So the year 2000 is a leap year. <br>
>
>But the year 2100 is not a leap year because: <br>
>2100 ÷  4 = 525 (Leap) <br>
>2100 ÷ 100 = 21 (Not Leap) <br>
>2100 ÷ 400 = 5.25 (Not Leap) <br>
>
> **Warning** <br>
>your output should match the Example Output format exactly, even the positions of the commas and full stops.
>
>Example Input / Output <br>
>2400 / Leap year.
>
>Example Input / Output <br>
>1989 / Not leap year.

```python
year = int(input("Which year do you want to check? "))
```

```python
if year % 4 == 0:
    if year % 100 == 0:
        if year % 400 == 0:
            print(f"{year} is leap year")
        else:
            print(f"{year} is not leap year")
    else:
        print(f"{year} is not leap year")
else:
    print(f"{year} is not leap year")
```
<br>

# 2. Multiple continuous if(다중 연속 if문): RollerCoaster cost

```python
height = float(input("What is your height in cm? "))
bill = 0

if height >= 120:
    age = int(input("How old? "))
    if age <= 12:
        bill = 5
        print("Child ticekts are $5.")
    elif age <= 18:
        bill = 7
        print("Youth tickets are $7.")
    elif 45 <= age <= 55:
        bill = 0
    else:
        bill = 12
        print("Adult tickets are $12.")

    wants_photo = input("Do you want a photo taken? Y or N. ")
    if wants_photo == "Y":
        bill += 3
    # add $3 to their bill
    print(f"You have to pay ${bill}")

else:
    print("go home")

```

## 2-1. Pizza Order
>you've got a job at Python Pizza. Your first job is to build an automatic pizza order program. Based on a user's order, work out their final bill.
>
>Small Pizza: $15<br>
>Medium Pizza: $20<br>
>Large Pizza: $25<br>
>
>Pepperoni for Small Pizza: +$2<br>
>Pepperoni for Medium or Large Pizza: +$3<br>
>Extra cheese for any size pizza: + $1<br>
>
> Example Input / Output<br>
>size = "L"<br>
>add_pepperoni = "Y"<br>
>extra_cheese = "N"<br>
>
>Your final bill is: $28.<br>

```python
print("Welcome to Python Pizza Deliveries!")
size = input("What size pizza do you want? S, M, or L \n")
add_pepperoni = input("Do you want pepperoni? Y or N \n")
extra_cheese = input("Do you want extra cheese? Y or N \n")
```
<br>

```python
bill = 0

if size == "S":  # str 형식 지켜주기
    bill += 15
elif size == "M":
    bill += 20
else:
    bill += 25

if add_pepperoni == "Y":
    if size == "S":
        bill += 2
    else:
        bill += 3

if extra_cheese == "Y":
    bill += 1


print(f"Your final is: ${bill}")
```


## 2-2. Love Calc
>You are going to write a program that tests the compatibility between two people.
>To work out the love score between two people:
>
>Take both people's names and check for the number of times the letters in the word TRUE occurs. Then check for the number of times the letters in the word LOVE occurs. Then combine these numbers to make a 2 digit number.
>
>For Love Scores <span style="color: red">**less than 10** or **greater than 90**</span>, the message should be:
>"Your score is <span style="color: red">X</span>, you go together like coke and mentos."
>
>For Love Scores <span style="color: yellow">**between 40** and **50**</span>, the message should be:
>"Your score is <span style="color: yellow">y</span>, you are alright together."
>
>Otherwise, the message will just be their score. e.g.:
>"Your score is <span style="color: green">z</span>."
>
>e.g. <br>
>name1 = "Angela Yu" <br>
>name2 = "Jack Bauer"<br>
>
>T occurs 0 times<br>
>R occurs 1 time<br>
>U occurs 2 times<br>
>E occurs 2 times<br>
>Total = 5<br>
>
>L occurs 1 time<br>
>O occurs 0 times<br>
>V occurs 0 times<br>
>E occurs 2 times<br>
>Total = 3<br>
>
>Love Score = 53<br>
>Print: "Your score is 53."<br>
>=========================<br>
> Example Input 1<br>
>name1 = "Kanye West"<br>
>name2 = "Kim Kardashian"<br>
>
> Example Output 1<br>
>Your score is 42, you are alright together.<br>
>
> Example Input 2<br>
>name1 = "Brad Pitt"<br>
>name2 = "Jennifer Aniston"<br>
>
> Example Output 2<br>
>Your score is 73.<br>
>
>The testing code will check for print output that is formatted like one of the lines below:
```
"Your score is 47, you are alright together."
"Your score is 125, you go together like coke and mentos."
"Your score is 54."
```

<br>

***Starter!***
```python
print("Welcome to the Love Calculator!")
name1 = input("What is your name? \n")
name2 = input("What is their name? \n")
```