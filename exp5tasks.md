<h1 style="text-align:center;">Experiment [5] : [Shell Programming]</h1>

### Name: Prapti Uniyal  Roll.: 590028360 Date: 10-09-2025

### AIM:
* [To Learn Basic Conditional Statements in Bash Scripting]

### Requirements:
* [Any Linux Distro, any kind of text editor (vs code, vim, nano, etc)]

### Theory:
* [Basic usage of conditions and arrays in bash scripting.]

1- ARRAYS IN BASH

<p align="center">
<img align="center" src="image-5.png" width="900">
</p>



2- CONDITIONAL STATEMENTS

if, else, elif, case, etc.


## Procedure & Observations:


<h1 style="text-align:center;">Task 1: [Prime Number Check]</h1>

## Task Statement:
* [To check if the number given by the user is a prime number or not.]

## Explanation:
* [using if else loop wap to check if the number is a prime number or not.]

## Command(s):
```
#!/bin/bash
echo "Enter a number: "
read num
flag=0
for ((i=2; i<=num/2; i++))
do
    if [ $((num % i)) -eq 0 ]
    then
        flag=1
        break
    fi
done

if [ $flag -eq 0 ]
then
    echo "$num is a prime number."
else
    echo "$num is not a prime number."
fi
```

### Output:
<p align="center">
<img align="center" src="image-6.png" width="900">
</p>
<p align="center">
<img align="center" src="image-7.png" width="900">
</p>



<h1 style="text-align:center;">Task 2: [Sum of Digits]</h1>

## Task Statement:
* [Take input from user and give the sum of two digits.]

## Explanation:
* [This script will take input from user and will give the following output.]

## Command(s):
```
#!/bin/bash
echo "Enter a number: "
read num
sum=0
while [ $num -gt 0 ]
do
    digit=$((num % 10))
    sum=$((sum + digit))
    num=$((num / 10))
done

echo "Sum of digits: $sum"
```

### Output:
<p align="center">
<img align="center" src="WhatsApp Image 2025-09-11 at 23.24.02_e9973eba.jpg" width="900">
</p>



<h1 style="text-align:center;">Task 3: [Armstrong Number Check]</h1>

## Task Statement:
* [Take input user and give the sum of Armstrong number of n digits is a number equal to the sum of its digits raised to the power n. Example: 153 = 1^3^ + 5^3^ + 3^3^ ]

## Explanation:
* [This script will tell if the number entered by the user is an armstrong number or not.]

## Command(s):
```
#!/bin/bash
echo "Enter a number: "
read num
temp=$num
n=${#num}   # number of digits
sum=0

while [ $temp -gt 0 ]
do
    digit=$((temp % 10))
    sum=$((sum + digit**n))
    temp=$((temp / 10))
done

if [ $sum -eq $num ]
then
    echo "$num is an Armstrong number."
else
    echo "$num is not an Armstrong number."
fi
```

### Output:
<p align="center">
<img align="center" src="WhatsApp Image 2025-09-11 at 23.30.28_73329e26.jpg" width="900">
</p>



## Result:
* The tasks were successfully completed for Basic Shell Programming.