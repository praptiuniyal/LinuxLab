<h1 style="text-align:center;">Experiment [4] : [Bash Scrpting]</h1>

### Name:Prapti Uniyal, Roll No.: 590028360, Date: 10-09-2025

### AIM: 
* [To Learn Basics of Bash Scripting.]

### Requirements:
* [Any Linux Distro, any kind of text editor (vs code, vim,nano, etc)]

### Theory: 

* Bash (Bourne Again SHell) is a command-line shell and scripting language for Unix-based operating systems.

* A shell script is a file containing commands.

* TYPES OF SHELL VARIABLES

1- user-defined

![alt text](userdef.png)

2- system variables

![alt text](systemvar.png)



* KEYWORDS

Reserved words like- if, then, fi, while,etc.

* OPERATORS

1- Arithmetic operators

+, -, *, % 

2- Comparision operators

-eq -ne -lt -le -gt -ge

* POSITINAL PARAMETERS

It is used to send inputs as arguments while executing a script.

command syntax-     ./script.sh arg1 arg2
     
$0- script name,
$1- first argument,
$2- second argument


### Procedure & Observations

<h1 style="text-align:center;">Task 1: [Hello World Script]</h1>



## Task Statement: 
* [Basic Usage of Shell Scripts]

## Explanation: 
* [Writing Begginer level Shell Scripts]

## Command(s):
```
#!/bin/bash
echo "Hello, World!"

```

#### Output:


![alt text](<WhatsApp Image 2025-09-11 at 22.22.17_f8bc099d.jpg>)

<h1 style="text-align:center;">Task 2: [personalized greeting Script]</h1>


## Task Statement: 
* [Basic Shell Script to callout user defined function.]

## Explanation: 
* [This Shell script will take input from user and store it in a variable and then call the variable which will output the stored value.]

## Command(s):
```
#!/bin/bash
echo "What is your name?"
read name
echo "Hello, $name! Welcome to Shell Scripting."

``` 

## Output:

<p align="center">

![alt text](<WhatsApp Image 2025-09-11 at 22.25.50_440232d6.jpg>)

<h1 style="text-align:center;">Task 3: [Arithmetic Operations in Shell Scripting]</h1>


## Task Statement:
* [Using Basic Arithmetic Operations in Shell Scripts]

## Command(s):
```

#!/bin/bash
echo "Enter first number: "
read num1
echo "Enter second number: "
read num2
echo "Addition: $((num1 + num2))"
echo "Subtraction: $((num1 - num2))"
echo "Multiplication: $((num1 * num2))"
echo "Division: $((num1 / num2))"

```

## Output:

![alt text](<WhatsApp Image 2025-09-11 at 22.28.34_aae7d09b.jpg>)

<h1 style="text-align:center;">Task 4: [Voting Eligibility]</h1>


## Task Statement:
* [Using Conditionals in Shell script ]

## Command(s):
```
#!/bin/bash
echo "What is your age?"
read age
if [ $age -ge 18 ]; then
    
    echo "You are eligible to vote!"
    
else 
    echo "You are not eligible to vote!"

fi

```

## Output:
<p align="center">

![alt text](image-4.png)


## Challenges faced and learning outcomes:

* Did not face any challenge as just, just need to practice.

## Result
* The tasks were successfully completed for Basic Shell Scripting.
