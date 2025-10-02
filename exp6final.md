<h1 style="text-align:center;">Experiment [6] : [Shell Programming- Loops]</h1>

### Name: Prapti Uniyal  Roll.: 590028360 Date: 15-09-2025

## AIM:
* [To Learn usage of loops in Bash Scripting]

## Requirements:
* [Any Linux Distro, any kind of text editor (vs code, vim, nano, etc)]

## Theory:

* Basic usage of loops to execute a block of code repeatedly.

### Loops:

1). for loop syntax and execution-

<p align="center">
<img align="center" src="forloop.jpg" width="900">
</p>

2). while loop syntax and execution-
<p align="center">
<img align="center" src="whileloop.jpg" width="900">
</p>

3). until loop syntax and execution-

<p align="center">
<img align="center" src="until.jpg" width="900">
</p>

### Loop Controls:

1). break- it is a control flow keyword used to immediately terminate the currently executing loop.  

2). continue- this keyword is a control statement used inside loops to skip the rest of the current iteration and immediately start the next one.

![alt text](<WhatsApp Image 2025-09-14 at 23.29.10_0875d5aa.jpg>)


### Shell functions:

Shell functions are named blocks of commands within a shell script designed for reuseability and organization.

Example- 
![alt text](<WhatsApp Image 2025-09-15 at 15.34.41_98f8e5b4.jpg>)


### Input/Output redirection:

It is a shell feature that allows alteration of the default input and output streams of commands.

1). Output redirection:

a) >  : overwrite
b) >> : append
c) 2> : redirect errors

2). Input redirection:

a) <  : input from file

![alt text](<WhatsApp Image 2025-09-14 at 23.30.40_eb26d33b.jpg>)

### Regular expressions:

These are powerful text patterns used for searching,matching,and manipulating text.

A comman linux command for searching test based on a regular expression pattern within files- grep

![alt text](<WhatsApp Image 2025-09-15 at 15.30.07_00e6a7e9.jpg>)

### Script debugging and troubleshooting:

It involves identifying and resolving issues within scripts to ensure their correcr functionality.

While troubleshooting generally focuses on identifying system- level issues , debugging specifically addressws errors within the code itself.

![alt text](<WhatsApp Image 2025-09-15 at 15.42.27_1bfb373c.jpg>)

## Procedure & Observations:

<h1 style="text-align:center;">Task [1]:[Palindrome Check]</h1>


## Task Statement:
* [To check if the number given by the user is a palindrome number or not.]

## Explanation:
* [using while loop wap to check if the number is a palindrome or not.]

## Command(s):
```
#!/bin/bash
echo "Enter a number: "
read num
rev=0
temp=$num

while [ $temp -gt 0 ]
do
    digit=$((temp % 10))
    rev=$((rev * 10 + digit))
    temp=$((temp / 10))
done

if [ $num -eq $rev ]
then
    echo "$num is a palindrome."
else
    echo "$num is not a palindrome."
fi

```

## Output:
<p align="center">
<img align="center" src="image-8.png" width="900">
</p><p align="center">
<img align="center" src="image-9.png" width="900">
</p>

<h1 style="text-align:center;">Task [2]: [Finding GCD & LCM]</h1>


## Task Statement:
* [Take two inputs from user and find the gcd and lcm of the two inputs.]

## Explanation:
* [This script will take input from user and will give the following output.]

## Command(s):
```
#!/bin/bash
echo "Enter two numbers: "
read a b

x=$a
y=$b
while [ $y -ne 0 ]
do
    temp=$y
    y=$((x % y))
    x=$temp
done
gcd=$x

lcm=$(( (a * b) / gcd ))

echo "GCD: $gcd"
echo "LCM: $lcm"

```

## Output:

<p align="center">
<img align="center" src="image-10.png" width="900">
</p>
<p align="center">
<img align="center" src="image-11.png" width="900">
</p>



<h1 style="text-align:center;">Task [3]: [Sorting numbers]</h1>

## Task Statement:
* [Input numbers separated by space and sort them in ascending and descending order]

## Explanation:
* [This script will compare the input values and sort them accordingly]

## Command(s):
```
#!/bin/bash
echo "Enter numbers separated by space: "
read -a arr

echo "Ascending Order: "
printf "%s\n" "${arr[@]}" | sort -n

echo "Descending Order: "
printf "%s\n" "${arr[@]}" | sort -nr

```

## Output:
<p align="center">
<img align="center" src="image-12.png" width="900">
</p>
<p align="center">
<img align="center" src="image-13.png" width="900">
</p>

<h1 style="text-align:center;">ASSIGNMENTS</h1>

<h1 style="text-align:center;">Exercise [1] : [Factorial of a number]</h1>

## Task Statement:
* [Write a function to calculate the factorial of a number using a loop]


## Command(s):

```
#!/bin/bash
read -p "Enter a number: " num

if ! [[ "$num" =~ ^[0-9]+$ ]]; then
    echo "Invalid input. Please enter a non-negative integer."
    exit 1
fi

factorial=1
for (( i=1; i<=num; i++ ))
do
    factorial=$((factorial * i))
done
echo "Factorial of $num is $factorial"

```

## Output: 

<p align="center">
<img align="center" src="image-40.png" width="900">
</p>

<h1 style="text-align:center;">Exercise [2]: [Counts appearances of a word in file]</h1>

## Task Statement:
* [write a script that reads a filename and counts how many times a given word appears in it]


## Command(s):

```
#!/bin/bash

read -p "Enter the filename: " filename
read -p "Enter the word to search: " word

if [ ! -f "$filename" ]; then
    echo "File '$filename' does not exist."
    exit 1
fi

count=$(grep -o -w "$word" "$filename" | wc -l)

echo "The word '$word' appears $count times in '$filename'."
```

## Output: 

<p align="center">
<img align="center" src="image-41.png" width="900">
</p>


<h1 style="text-align:center;">Exercise [3]: [Fibonacci series]</h1>

## Task Statement:
* [Write a script that generates the first N Fibonacci numbers using a while loop]


## Command(s):

```
#!/bin/bash

read -p "Enter how many Fibonacci numbers to generate: " n

if ! [[ "$n" =~ ^[0-9]+$ ]]; then
    echo "Please enter a valid non-negative integer."
    exit 1
fi

a=0
b=1
count=0

echo "First $n Fibonacci numbers:"

while [ $count -lt $n ]
do
    echo -n "$a "
    fn=$((a + b))
    a=$b
    b=$fn
    count=$((count + 1))
done

echo ""
```

## Output: 

<p align="center">
<img align="center" src="image-42.png" width="900">
<

<h1 style="text-align:center;">Exercise [4]: [Check whether the entered string is proper or not]</h1>

## Task Statement:
* [Write a script that validates whether the entered string is a proper email address using a regular expression]


## Command(s):

```
#!/bin/bash

read -p "Enter an email address: " email
pattern="^[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}$"
if [[ $email =~ $pattern ]]; then
    echo "Valid email address."
else
    echo "Invalid email address."
fi
```

## Output: 

<p align="center">
<img align="center" src="image-43.png" width="900">
</p>


<h1 style="text-align:center;">Exercsie [5]: [Explain debug output]</h1>

## Task Statement:
* [Write a script with an intentional error,run it with bash-x , and explain the debug output]


## Command(s):
```
#!/bin/bash

read -p "Enter a number: " number
square=$((numbr * numbr))  # 'numbr' is undefined
echo "Square of $number is $square"
```


## Output: 

EXPLANATION OF DEBUG OUTPUT:

- read -p "Enter a number: " number
-Bash shows the command being executed: reading input into.

- square=$((numbr * numbr)) 
-Bash tries to evaluate , but it's undefined — this is the intentional error.
 	
- labques5.sh: line 5 numbr: unbound variable
-Bash throws an error because  was never set.
	
- echo 'Square of 5 is'
-The final output is incorrect because  couldn't be calculated.


<p align="center">
<img align="center" src="image-44.png" width="900">
</p>

## Challenges faced:

* Remembering arithmetic syntax in Bash — used `(( ))` and `expr` where needed.

## Learning:

* Correct quoting and use of control constructs prevent common bugs.


## Result:
* The exercises and assignments were successfully completed for shell programming using loops.