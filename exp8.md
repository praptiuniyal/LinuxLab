<h1 style="text-align:center;">Experiment [8] : [SHELL PROGAMMING]</h1>

### Name:Prapti Uniyal, Roll No.: 590028360, Date: 24-09-2025

### AIM: 

* [To learn some new commands in shell progamming and doing tasks based upon them]

## Requirements:

* [Any Linux Distro, any kind of text editor (vs code, vim,nano, etc)]

## Theory: 

These shell scripts demonstrate fundamental Linux process and system management techniques. They cover job control, file comparison, process counting, memory monitoring, and pattern matching using commands. Each script showcases interactive automation and real-time system insights through Bash scripting.

### Process control and signals:

Process can receive signals from the OS or the user to control execution.

Command:

* kill -1 : list all signals

* Some comman signals are:

1). SIGINT (2) : interuppt
2). SIGTERM (15) : terminate gracefully
3). SIGKILL (9) : force kill

<p align="center">
<img align="center" src="image-50.png" width="900">
</p>


### Process monitoring and resource usage:

It includes commands like- 

* top
* htop
* ps aux
* free -h
* uptime

<p align="center">
<img align="center" src="image-51.png" width="900">
</p>


### Process Communication

* command- ps aux | grep bash
 
It finds running processes with bash.

<p align="center">
<img align="center" src="image-52.png" width="900">
</p>

### Process Synchronization

Process synchronization in Linux is the coordination of multiple processes or threads to ensure data consistency and prevent race conditions when they access shared resources. This is crucial in multi-threaded and multi-process environments where concurrent access to shared data can lead to unpredictable and incorrect results.

* command- wait

Waits for a background job to finish

<p align="center">
<img align="center" src="image-53.png" width="900">
</p>

### Background processes and job control

A background process runs independently of the shell, allowing the user to continue interacting with the terminal while the process executes. This is useful for long-running tasks or when needing to perform other operations simultaneously.

* Add ' & ' at the end of a command to run it in background immediately.

* jobs - shows background jobs.

* fg % - brings job 1 to foreground.

* bg % - resumes job 1 in background.


<p align="center">
<img align="center" src="image-54.png" width="900">
</p>

### System monitoring and logging

System monitoring involves tracking various aspects of your Linux system in real-time or near real-time. System monitoring and logging in Linux are crucial for maintaining system health, troubleshooting issues, ensuring security, and analyzing performance.

* dmesg | less - system messages

* journalctl - system logs

* last - tells last logged in users

* who or we - users currently logged in

<p align="center">
<img align="center" src="image-55.png" width="900">
</p>
<p align="center">
<img align="center" src="Screenshot (14).png" width="900">
</p>
<p align="center">
<img align="center" src="image-56.png" width="900">
</p>


<h1 style="text-align:center;">Lab Task [1]: [Check file permissions]</h1>


## Command(s):

```
#!/bin/bash
echo "Enter filename:"
read file

if [ -e "$file" ]; then
    [ -r "$file" ] && echo "File is readable"
    [ -w "$file" ] && echo "File is writable"
    [ -x "$file" ] && echo "File is executable"
else
    echo "File does not exist."
fi
```

### Output: 

<p align="center">
<img align="center" src="exp8.1.png" width="900">
</p>


<h1 style="text-align:center;">Lab Task [2]: [String operations]</h1>


## Command(s):

```
#!/bin/bash
echo "Enter first string:"
read str1
echo "Enter second string:"
read str2

# String length
echo "Length of first string: ${#str1}"
echo "Length of second string: ${#str2}"

# Concatenation
concat="$str1$str2"
echo "Concatenated string: $concat"

# Comparison
if [ "$str1" = "$str2" ]; then
    echo "Strings are equal"
else
    echo "Strings are not equal"
fi

```

### Output: 

<p align="center">
<img align="center" src="exp8.2.png" width="900">
</p>



<h1 style="text-align:center;">Lab Task [3]: [Search for a pattern in a file]</h1>


## Command(s):

```
#!/bin/bash
echo "Enter filename:"
read file
echo "Enter pattern to search:"
read pattern

if [ -e "$file" ]; then
    echo "Matching lines:"
    grep "$pattern" "$file"
else
    echo "File not found!"
fi

```

## Output: 

<p align="center">
<img align="center" src="exp8.3.png" width="900">
</p>

### New command(s) used in the code-

* grep pattern file : searches for matching lines.

<h1 style="text-align:center;">Lab Task [4]: [Display system information]</h1>


## Command(s):

```
#!/bin/bash
echo "System Information:"
echo "-------------------"
echo "Date and Time: $(date)"
echo "Logged in users: $(who)"
echo "System Uptime: $(uptime -p)"
echo "Memory Usage:"
free -h
echo "Disk Usage:"
df -h

```

### Output: 

<p align="center">
<img align="center" src="exp8.4.png" width="900">
</p>

### New command(s) used in the code-

* date : current date and time

* who : list logged in users

* uptime -p : pretty uptime format

* free -h : memory usage in human-readable format

* df -h : disk usage


<h1 style="text-align:center;">ASSIGNMENT</h1>


## Exercise 1 : Write a script that starts a background job ,lists all the jobs,brings the job to the foreground and then terminates it.


## Command(s)

```
#!/bin/bash

echo "Starting a background job: sleep 100 &"
sleep 100 &

echo -e "\nListing all jobs:"
jobs

job_id=$(jobs -p)
echo -e "\nCaptured Job PID: $job_id"

echo -e "\nBringing job to foreground:"
fg %1


```

## Output :

<p align="center">
<img align="center" src="image-57.png" width="900">
</p>
* The command "jobs" does not give any output which means that the jobs are already terminated.

## Exercise 2 : Create a script that compares two files and displays whether their contents are identical or different.


## Command(s)

```
#!/bin/bash

if [ "$#" -ne 2 ]; then
    echo "Usage: $0 <file1> <file2>"
    exit 1
fi

file1="$1"
file2="$2"

if [ ! -f "$file1" ]; then
    echo "Error: '$file1' does not exist."
    exit 1
fi

if [ ! -f "$file2" ]; then
    echo "Error: '$file2' does not exist."
    exit 1
fi

if diff "$file1" "$file2" > /dev/null; then
    echo " The files '$file1' and '$file2' are IDENTICAL."
else
    echo " The files '$file1' and '$file2' are DIFFERENT."
fi
```

## Output :

<p align="center">
<img align="center" src="image-58.png" width="900">
</p>


## Exercise 3 : Write a script that counts the number of  processes currently being run by your user


## Command(s)

```
#!/bin/bash

user=$(whoami)

process_count=$(ps -u "$user" --no-headers | wc -l)

echo "User: $user"
echo " Number of running processes: $process_count"
```


## Output :

<p align="center">
<img align="center" src="image-59.png" width="900">
</p>


## Exercise 4 : Develop a script that monitors memory usage every 5 seconds and logs it into a file.

## Command(s)

```
#!/bin/bash

log_file="memory_log.txt"

# Header for the log file
echo " Memory Usage Log - $(date)" > "$log_file"
echo "Timestamp                | Used Memory (MB) | Free Memory (MB)" >> "$log_file"
echo "---------------------------------------------------------------" >> "$log_file"

# Infinite loop to log memory every 5 seconds
while true; do
    # Get memory stats using free -m
    mem_info=$(free -m | grep Mem)
    used=$(echo "$mem_info" | awk '{print $3}')
    free=$(echo "$mem_info" | awk '{print $4}')
    timestamp=$(date '+%Y-%m-%d %H:%M:%S')

    # Log to file
    echo "$timestamp |       $used         |       $free" >> "$log_file"

    # Wait for 5 seconds
    sleep 5
done
```

## Output :

<p align="center">
<img align="center" src="image-60.png" width="900">
</p>


## Exercise 5 : Write a script that prompts for a  filename and a search pattern, then displays the count of matching lines.

## Command(s)

```
#!/bin/bash

read -p " Enter the filename: " filename

# Check if file exists
if [ ! -f "$filename" ]; then
    echo " Error: File '$filename' not found."
    exit 1
fi

# Prompt for search pattern
read -p "Enter the search pattern: " pattern

# Count matching lines
match_count=$(grep -c "$pattern" "$filename")

echo " Number of lines matching '$pattern' in '$filename': $match_count"
```


## Output :

<p align="center">
<img align="center" src="image-61.png" width="900">
</p>


## Challenges faced:

* Forgetting to quote variables in conditions — resolved by using `"$var"` to avoid word splitting.

## Learning:

* Learned command-line argument handling for automation.

## Result:
* The exercises and assignments were successfully completed for Shell Progamming 