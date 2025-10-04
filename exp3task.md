<h1 style="text-align:center;">Experiment [3] : [Linux file and system manipulation]</h1>

### Name:Prapti Uniyal  Roll No.: 590028360  Date: 13-09-2025

### Aim:

* To practice Linux file manipulation commands, permissions and ownership, compressing and decompressing

### Requirements

* [Any Linux Distro, any kind of text editor (vs code, vim,nano, etc)].


## Theory

File manipulation involves operations like creating, reading, writing, moving, deleting or renaming files so that programs can store, retrieve or organize data.System manipulation means changing or controlling the computing environment—such as adjusting system settings, managing processes, and altering permissions or configurations.

## Procedure & Observations

## Exercise 1: Creating and Managing Files

### Task Statement:

Create files and manage timestamps using `touch`.

### Command(s):

```
touch newfile.txt
touch file1.txt file2.txt file3.txt
touch -t 202401151430 dated_file.txt
```

### Output:

<p align="center">
<img src="image-23.png" width="900">
</p>


## Exercise 2: Copying, moving and deleting Files

### Task Statement:

Use `cp`, `mv`, and `rm` to copy, rename, move, and delete files and directories.

### Command(s):

```
cp doc1.txt doc2.txt
mv old.txt new.txt
rm unwanted_file.txt
rm -r old_dir/
```

### Output:

<p align="center">
<img src="image-33.png" width="900">
</p>


## Exercise 3: Viewing File Contents

### Task Statement:

Display file contents using `cat`, `less`, `head`, and `tail`.

### Command(s):

```
cat filename.txt
less /var/log/syslog
head -n 5 filename.txt
tail -n 20 filename.txt
tail -f /var/log/syslog
```

### Output:

<p align="center">
<img src="image-24.png" width="900">
</p>


## Exercise 4: File Permissions and Ownership

### Task Statement:

Explore file permissions and ownership with `ls -l`, `chmod`, `chown`, and `chgrp`.

### Command(s):

```
ls -l
chmod 755 script.sh
chmod u+x script.sh
sudo chown newuser:newgroup file.txt
chgrp developers project.txt
```

### Output:

<p align="center">
<img src="image-25.png" width="900">
</p>


## Exercise 5: File Searching with `find`

### Task Statement:

Search files by name, type, size, and permissions using `find`.

### Command(s):

```
find /home -name "*.txt"
find /home -type f -size +100M
find /etc -name "*conf*"
find /tmp -type f -empty -delete
```

### Output:

<p align="center">
<img src="image-26.png" width="900">
</p>
<p align="center">
<img src="image-27.png" width="900">
</p>


## Exercise 6: Pattern Searching with `grep`

### Task Statement:

Search for patterns in files using `grep`.

### Command(s):

```
grep "error" /var/log/syslog
grep -i "Error" logfile.txt
grep -r "function" ~/code/
grep -n "TODO" *.txt
```

### Output:

<p align="center">
<img src="image-28.png" width="900">
</p>
<p align="center">
<img src="image-29.png" width="900">
</p>

## Exercise 7: File archiving and compressing

### Task Statement:

Create and extract archives using `tar`, compress and decompress with `gzip`/`gunzip`.

### Command(s):

```
tar -czf backup.tar.gz /home/user/documents
tar -xzf backup.tar.gz -C /restore/
gzip large.txt
gunzip large.txt.gz
```

### Output:

<p align="center">
<img src="image-30.png" width="900">
</p>
<p align="center">
<img src="image-31.png" width="900">
</p>


## Exercise 8: Creating Links

### Task Statement:

Create and test hard and symbolic links using `ln`.

### Command(s):

```
echo "Hello" > original.txt
ln original.txt link.txt
ln -s original.txt sym.txt
ls -li original.txt link.txt sym.txt
```

### Output:

<p align="center">
<img src="image-32.png" width="900">
</p>

## Challenges faced:

* Remembering numeric vs symbolic permissions in `chmod`. Fixed through repeated practice.

## Learning:

* Learned how to efficiently search files and patterns in Linux.
* Understood how to archive and compress files for better storage management.

## Result

Learned file and system manipulation efficiently with the help of the exercises performed above.





