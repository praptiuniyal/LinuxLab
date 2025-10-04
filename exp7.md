<h1 style="text-align:center;">Experiment [7] : [Shell programming,process and scheduling]</h1>

### Name: Prapti Uniyal  Roll No.: 590028360  Date: 21-09-2025

### Aim:

To automate repetitive system tasks such as backing up files,monitoring system resources, etc.

### Requirements

* [Any Linux Distro, any kind of text editor (vs code, vim,nano, etc)].


## Theory

Every program running in Linux is a process identified by a unique process ID (PID). Shell programming allows automation of tasks including spawning and controlling processes.

* Commands

1). ps- this command is used to display information about currently running processes. It stands for "process status".

![alt text](image-34.png)

2). top- it is a powerful utility for real-time system monitoring and data execution processes.

![alt text](image-35.png)

3). pstree- it is used to display a tree like structure of running processes,showing their parent-child relationship.

![alt text](image-36.png)

* Killing process

"killing a process" refers to the act of terminating a running program or application.This is typically done when the process becomes unresponsive,consumes excessive resources.

![alt text](image-37.png)

* Process Prioritization

It refers to managing the "nice value" of a process,which influences how the linux kernel allocates CPU time among competing processes.

![alt text](image-38.png)

* Scheduling processes
 
It uses the command "at",this command in linux provides a method for scheduling commands or scripts to be executed once at a specific time in the future.

Syntax- at [OPTIONS] TIME [DATE]

![alt text](image-39.png)

## Procedure & Observations

<h1 style="text-align:center;">Task [1]: [Check the existence of a file]</h1>

### Task Statement:

Wap a shell program to check if the given file exists or not.

### Command(s):

```
#!/bin/bash
echo "Enter filename: "
read file

if [ -e "$file" ]
then
    echo "File exists. Contents are:"
    cat "$file"
else
    echo "File does not exist."
    echo "Do you want to create it? (y/n)"
    read choice
    if [ "$choice" = "y" ]; then
        touch "$file"
        echo "File $file created."
    fi
fi

```

### Output:

<p align="center">
<img src="7task1.jpg" width="900">
</p>

<h1 style="text-align:center;">Task [2]: [Print numbers from 1 to 10]</h1>

### Task Statement:

Wap a shell program to print numbers from 1 to 10.

### Command(s):

```
#!/bin/bash
for i in {1..10}
do
    echo $i
done

```

### Output:

<p align="center">
<img src="7task2.jpg" width="900">
</p>


<h1 style="text-align:center;">Task [3]: [Count lines,words and characters]</h1>


### Task Statement:

Wap a shell program to count lines,words and characters.

### Command(s):

```
#!/bin/bash
if [ $# -eq 0 ]
then
    echo "Usage: $0 filename"
    exit 1
fi

file=$1

if [ -e "$file" ]
then
    echo "Lines: $(wc -l < $file)"
    echo "Words: $(wc -w < $file)"
    echo "Characters: $(wc -m < $file)"
else
    echo "File not found!"
fi

```

### Output:

<p align="center">
<img src="7task3.jpg" width="900">
</p>


<h1 style="text-align:center;">Task [4]: [Find factorial using function]</h1>

### Task Statement:

Wap a shell program to find factorial of a number.

### Command(s):

```
#!/bin/bash
factorial() {
    num=$1
    fact=1
    while [ $num -gt 1 ]
    do
        fact=$((fact * num))
        num=$((num - 1))
    done
    echo $fact
}

echo "Factorial of 5 is: $(factorial 5)"
echo "Factorial of 7 is: $(factorial 7)"
echo "Factorial of 10 is: $(factorial 10)"

```

### Output:

<p align="center">
<img src="7task4.jpg" width="900">
</p>

<h1 style="text-align:center;">ASSIGNMENT</h1>


## EXERCISE 1 :  [Write a script that monitors the top5 processes consuming the most CPU and logs them into a file every 10 seconds]


## Command(s):

```
#!/bin/bash

# Log file name
logfile="cpu_log.txt"

echo "Monitoring top 5 CPU-consuming processes every 10 seconds..."
echo "Log file: $logfile"
echo "Press Ctrl+C to stop."

while true
do
    echo "------ $(date) ------" >> "$logfile"
    ps -eo pid,ppid,cmd,%mem,%cpu --sort=-%cpu | head -n 6 >> "$logfile"
    echo "" >> "$logfile"
    sleep 10
done

```

### Output: 

<p align="center">
<img align="center" src="image-46.png" width="900">
</p>


## EXERCISE 2 : Write a script that accepts a PID from the user and displays its details(state,parent process,memory usage)


## Command(s):

```

#!/bin/bash

read -p "Enter the PID: " pid

if [ ! -d "/proc/$pid" ]; then
    echo "Process with PID $pid does not exist."
    exit 1
fi

state=$(grep -i "State" /proc/$pid/status | awk '{print $2}')
ppid=$(grep -i "PPid" /proc/$pid/status | awk '{print $2}')
vmrss=$(grep -i "VmRSS" /proc/$pid/status | awk '{print $2, $3}')

echo "Process ID: $pid"
echo "State: $state"
echo "Parent Process ID: $ppid"
echo "Memory Usage (VmRSS): $vmrss"

```

### Output: 

<p align="center">
<img align="center" src="image-47.png" width="900">
</p>




## EXERCISE 3 : Modify the factorial function to check if input is negative,if yes, display an error message.

## Command(s):

```
#!/bin/bash

read -p "Enter a number: " num

if [ "$num" -lt 0 ]; then
    echo "Error: Factorial is not defined for negative numbers."
    exit 1
fi

fact=1
for (( i=1; i<=num; i++ ))
do
    fact=$((fact * i))
done

echo "Factorial of $num is: $fact"
```

### Output: 

<p align="center">
<img align="center" src="image-48.png" width="900">
</p>


## EXERCISE 4 : Write e a script that accepts a filename as an argument.If the file exists,display the number of lines starting with a vowel


## Command(s):

```
#!/bin/bash

if [ -z "$1" ]; then
    echo "Usage: $0 <filename>"
    exit 1
fi

filename="$1"

if [ ! -f "$filename" ]; then
    echo "Error: File '$filename' not found."
    exit 1
fi

count=$(grep -iE '^[aeiou]' "$filename" | wc -l)

echo "Number of lines starting with a vowel: $count"
```

### Output: 

<p align="center">
<img align="center" src="image-49.png" width="900">
</p>


## Challenges faced:

Remembering the `crontab` time format. Solved by using online crontab generators and practice.

## Laerning:

* Gained hands-on knowledge of process creation and termination.

## Result

All the exercises and tasks were completed successfully and these tasks helped a lot in learning about killing process, scheduling, etc.
