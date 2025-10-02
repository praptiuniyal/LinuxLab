<h1 style="text-align:center;">Experiment [2] : [Basic Commands]</h1>

### Name:Prapti Uniyal, Roll No.: 590028360, Date: 03-09-2025

### AIM: 
* [To Learn Basic commands in linux.]

### Requirements:
* [Any Linux Distro, any kind of text editor (vs code, vim,nano, etc)]

### Theory: 
<h1 style="text-align:center;">BASIC NAVIGATION COMMANDS</h1>

* ls ( List ) : It displays the contents of a directory . When executed without any arguments, it displays the files and subdirectories within the current directory.The function can be modified using various flag options to control the output format and information displayed .  

1). ls -l : provides “long listing” showing detailed information  such as file permissions , number of links , owner and group, size and modification time .  

2). ls -a : displays all files including hidden files . 

3). ls -h : it is used with -l , displays the file sizes in a human readable form .  

4). ls -r : contents of subdirectories is listed recursively .  

5). ls –colour : displays a coloured output  

<p align="center">
<img align="center" src="exp2ls.jpg" width="900">
</p>


* cd  (change directory) : Helps us in moving from one directory to another.           

cd.. : moves up to the parent directory  

cd : cd without arguments  runs to the user’s home directory  

cd- :  returns to the previously accessed directory 

<p align="center">
<img align="center" src="cd.jpg" width="900">
</p>


* pwd( print working directory ) : It is used to to display the full, absolute path of the current directory where the user is located within the file program.  

<p align="center">
<img align="center" src="image-15.png" width="900">
</p>


* mkdir( make directory ): It is used to make the directory  

syntax : mkdir file_name 

<p align="center">
<img align="center" src="image-16.png" width="900">
</p>


* rmdir ( remove directory ) : It is used to delete a directory syntax : rmdir file_name

<p align="center">
<img align="center" src="mkdir.jpg" width="900">
</p>


### File Operations :  

1). touch  
2). cp ( copy )  
3). mv ( move )  
4). rm ( remove  )  

* touch : It help us to create a new file  

syntax : touch new_file_name.

<p align="center">
<img align="center" src="image-17.png" width="900">
</p>

* cp ( copy ) : The cp command is used to copy files and directories . 

syntax : cp source_file destination_file  

<p align="center">
<img align="center" src="2.txt" width="900">
</p>
<p align="center">
<img align="center" src="22.txt" width="900">
</p>

* mv ( move ) : It relocates the file or directory form  a source location to a destination within the file system.

<p align="center">
<img align="center" src="mv.jpg" width="900">
</p>
<p align="center">
<img align="center" src="pr.jpg" width="900">
</p>

* rm (remove ) : It removes the files and directories from the file system .

<p align="center">
<img align="center" src="rm.jpg" width="900">
</p>


### File viewing and editing :

!). cat  
2). less or more  
3). head and tail  
4). nano or vim  

* cat ( concatenate ) : Its main functions are to display contents of one or more files directly to the standard output. It is used to combine the contents of multiple files into a single output stream.  

<p align="center">
<img align="center" src="image-18.png" width="900">
</p>
 
* less or more : The less and more commands are both used to view the contents of the text files . The ‘ more’ command displays the content page by page , allowing us to move forward only . The ‘less’ command is the enhanced version of ‘more’ command . ‘less’ command allows us to move forward and backward allowing us to navigate throughout the entire file . 

<p align="center">
<img align="center" src="more.jpg" width="900">
</p>
<p align="center">
<img align="center" src="less.jpg" width="900">
</p>


* head and tail : The head and tail command are command-line utilities used to display specific portions of a file .  

<p align="center">
<img align="center" src="head.jpg" width="900">
</p>
<p align="center">
<img align="center" src="tail.jpg" width="900">
</p>


* nano or vim :  These both are command- line text editor . They help us creating and editing the text files within the terminal.

<p align="center">
<img align="center" src="image-20.png" width="900">
</p>
<p align="center">
<img align="center" src="nano.jpg" width="900">
</p>


### User Management :   

1 whoami 
2 who  
3 passwd  
4 sudo ( superuser do )  

 
* whoami : The ‘whoami’ command is used to display the username of the current effective user ID.  

<p align="center">
<img align="center" src="image-20.png" width="900">
</p>


* who :  It is used to display the information about users who area currently logged into the system.  

<p align="center">
<img align="center" src="image-22.png" width="900">
</p>

* passwd : This command is used in Linux to change the password.

<p align="center">
<img align="center" src="pass.jpg" width="900">
</p>

* sudo( superuser do ) : It allows the user to execute the commands as other user , typically superuser ( root ).

<p align="center">
<img align="center" src="vim.jpg" width="900">
</p>


### System Management   

1). uname  
2). df ( disk free )  
3). top or htop  
4). history   


* uname : It is used to provide the details about the  operating system kernel, hardware, and other system-related attributes. 

* df ( disk free ) : It is a command used to display information about the total , used and available disk space for file systems mounted on the system. 

<p align="center">
<img align="center" src="df.jpg" width="900">
</p>

* df -h : It displays the information about the total , used and available disk space in a human readable form.


* top and htop : ‘top’ and ‘htop’ both are command-line utilities used for real time monitoring of system processes and resource usage.  

<p align="center">
<img align="center" src="top.jpg" width="900">
</p>
<p align="center">
<img align="center" src="htop-1.jpg" width="900">
</p>
<p align="center">
<img align="center" src="htop1.jpg" width="900">
</p>


* history : It displays the history of commands executed on the terminal.  

<p align="center">
<img align="center" src="his.jpg" width="900">
</p>

-------------------------------------------------------------

### Procedure & Observations

<h1 style="text-align:center;">Exercise 1: [File System Navigation]</h1>

## Command(s):

 1. Go to your home directory
cd

 2. Check your current location
pwd

 3. Create a project structure
mkdir -p projects/linux_practice/{scripts,documents,backup}

 4. Navigate to the scripts folder
cd projects/linux_practice/scripts

 5. Create some files
touch setup.sh cleanup.sh readme.txt

 6. List the files with details
ls -la

 7. Go back to linux_practice directory
cd ..

 8. List all subdirectories
ls -la


#### Output:

<p align="center">
<img align="center" src="sysnav.jpg" width="900">
</p>

<h1 style="text-align:center;">Exercise 2: [File Operations and Permissions]</h1>


## Command(s):

 1. Go to documents folder
cd ~/projects/linux_practice/documents

 2. Create a text file
echo "This is a practice document" > practice.txt

 3. Check current permissions
ls -l practice.txt

 4. Make it readable by everyone
chmod 644 practice.txt

 5. Copy to backup folder
cp practice.txt ../backup/

 6. Create a backup with timestamp
cp practice.txt ../backup/practice_backup_$(date +%Y%m%d).txt

 7. List backup folder contents
ls -la ../backup/


## Output:

<p align="center">
<img align="center" src="fop.jpg" width="900">
</p>

<h1 style="text-align:center;">Exercise 3: [Text Eiting and Viewing]</h1>


## Command(s):


 1. Create a larger file for practice
cd ~/projects/linux_practice/documents
seq 1 50 > numbers.txt

 2. View first 10 lines
head numbers.txt

 3. View last 5 lines
tail -n 5 numbers.txt

 4. Search for specific number
cat numbers.txt | grep "25"

 5. Edit the file with nano
nano numbers.txt
 Add a comment at the top: "# Number list from 1 to 50"
 Save with Ctrl+O, exit with Ctrl+X

 6. View the modified file
cat numbers.txt


## Output:

<p align="center">
<img align="center" src="fop.jpg" width="900">
</p>

<h1 style="text-align:center;">Exercise 4: [System Exploration]</h1>

## Command(s):

 1. Check system information
uname -a

 2. Check disk usage
df -h

 3. See your recent commands
history 10

 4. Check who's logged in
who

 5. Find your username
whoami

 6. Check current processes (press 'q' to quit)
top


## Output:

<p align="center">
<img align="center" src="sysexplore.jpg" width="900">
</p>


<h1 style="text-align:center;">Exercise 5: [Cleanup]</h1>


## Command(s):

 1. Go to practice directory
cd ~/projects/linux_practice

 2. Remove a test file safely
rm -i documents/numbers.txt

 3. Remove empty directory (if any)
 First try: rmdir backup  # This might fail if not empty
 Then: rm -r backup       # This removes directory and contents

 4. List what remains
ls -la

 5. Check history of your session
history | tail -20


## Output:

<p align="center">
<img align="center" src="cleanup.jpg" width="900">
</p>
<p align="center">
<img align="center" src="cleanup2.jpg" width="900">
</p>

 <h1 style="text-align:center;"> [LAB EXAM/TASKS]</h1>

## Task [1]: [Directory navigation]


### Output: 

<p align="center">
<img align="center" src="2task1.jpg" width="900">
</p>


## Task [2]: [Directory navigation]


### Output: 

<p align="center">
<img align="center" src="2task2.jpg" width="900">
</p>



## Task [3]: [Directory navigation]


### Output: 

<p align="center">
<img align="center" src="2task3.jpg" width="900">
</p>


## Task [4]: [File permissions]


### Output: 

<p align="center">
<img align="center" src="2task4.jpg" width="900">
</p>



## Task [5]: [File viewing]


### Output: 

<p align="center">
<img align="center" src="2task52.jpg" width="900">
</p>
<p align="center">
<img align="center" src="2task51.jpg" width="900">
</p>



## Task [6]: [Text editing]


### Output: 

<p align="center">
<img align="center" src="2task6.jpg" width="900">
</p>


## Task [7]: [System information]


### Output: 

<p align="center">
<img align="center" src="2task7.jpg" width="900">
</p>


## Task [8]: [File organization]


### Output: 

<p align="center">
<img align="center" src="2task8.jpg" width="900">
</p>


## Task [9]: [Process and history]


### Output: 

<p align="center">
<img align="center" src="2task9.jpg" width="900">
</p>
<p align="center">
<img align="center" src="2task92.jpg" width="900">
</p>


## Task [10]: [Comprehensive cleanup]


### Output: 

<p align="center">
<img align="center" src="2task10-1.jpg" width="900">
</p>
<p align="center">
<img align="center" src="2task10-2.jpg" width="900">
</p>

## Challenges faced:

* Was unable to understand the `umask` calculation in the begining which I overcame by revising the subtraction method.

## Learning:

* Understood file permissions and their significance.
* Learned how to use `chmod` and `umask` effectively.


## Result: 
* All the exercises and tasks were successfully completed for basic commanmds and file system permissions