# **Week 4 Lab Report**
## In real life, we sometimes misplace items and have trouble in finding them: my phone, my backpack, and my textbooks, you name it. Fortunately, I do not have such trouble while working on my computer even if I misplace files. Why? - because I can make use of the find command to find these files!

<br>

## In this report, I will introduce you to the three uses of find command and give you three examples of each usage. Now, let's get started!


<br>

> ## The **first** use of find command I will show you is to find files based on their names or naming patterns. This usage is similar to a real-life scenario when when want to find misplaced items based on its name, like "backpack." I will take three instances to illustrate this usage:

<br>

 ## ***1.*** In the first example, I want to find all .txt files in the "technial" directory whose names start from "pmed"." However, because there is a huge amount of .txt files in this directory that fits our criterion. Therefore, if we use our traditional method, we have to type each file's name in our command line, which is inefficient. To increase our efficiency, we can use a tool called "wildcard." Look at this command: 
```
$ cd technical
$ find -name "pmed*.txt"
```
 ## You may have noticed an asterisk before .txt, which is a wildcard symbol that substitute any character x that is between "pmed" and the file extension ".txt". As a result, any .txt files that starts from pmed will be returned by this code. Let's see the output of this command:
![Find all txt.files starting from pmed](Images/findnamepmed.png)
![Find all txt.files starting from pmed output](Images/finanamepmed2.png)
![Find all txt.files starting from pmed output2](Images/findnamepmed3.png)

<br>

## ***2.*** In the second example, We can also find .txt files whose names start with number 1, contains 2, and ends with 3 by this command:
```
$ find -name "1*3*2.txt"
```

## Let's see its output (do keep in mind that I'm already in directory "technical"):
![Find 1 2 3](Images/Find123.png)

 ## ***3.***: In our last example, let's find .txt files whose file names starts with "journal" and ends with number 3:
```
$ find -name "journal*3.txt"
``` 
![Find Journal](Images/Find%20Journal.png)

## According to these examples above, a find -name command that uses wildcard is really useful when we want to search files that have a specific pattern and increases our efficiency to a great extent.

<br>

> ## The **Second** usage of find command is to find files of a specific size. With this command, we can also keep track of the size of files. If we combine this command with the delete command (which I will introduce later), we can delete files of a specific size quickly. This is helpful if we want to delete all large files (size > 500 MB, let's say) to clear out computer's capacity. I'll take three examples to show you how to use this command:

<br>

## 1. In the ***first*** example, let's search for files in directory "technical" whose size is over 5 MB:
```
$ cd technical
$ find -size +5M
```

## Let's take a look at its output. Because no files in our directory is larger than 5M, this command did not give us any output:
![FindSizeOver5M](Images/Findsize%2B5.png)

<br>

## 2. In the ***second*** example, let's search for files in the technical directory with size less than 4 KB. We can use this command:
```
$ find -size -4k
``` 
## Now, let's see its output:
![FindSizeLess5KB](Images/FindSizeLessThan4K.png)

<br>

## 3. In the ***third*** example, let's find files with size larger than 4k and smaller than 8k. We can use this command:
```
$ find -size +4k -size -8k
```
## Let's see the output:
![Find size between 4k and 8k](Images/FindSizeBetween4and8.png)


> ## The **Third** usage of find command is to delete files based on their names or naming pattern. This command is especially helpful if I need to delete files with a specific naming pattern from an unorganized directory. If we just delete them one by one, it will waste us too much time. By using this command, we can delete all files we want precisely and completely. At the same time, we can even delete those files that occupy the largest storage to clear computer capacity with this command. I'll take three examples to show you how to use this command:

## 1. In the ***first*** example, let me delete all .txt files whose names start with "pmed" and end with "0." My command will return nothing and start with "sudo" because I'm doing some "advanced" operations other than reading files:
```
$ sudo find -name "pmed*0.txt" -delete
```
## After this, we can check if these files have been deleted by this command, which should return nothing:
```
$ find -name "pmed*0.txt" 
```

## Let's see our output:
![Find and delete 1](Images/Finddelete.png)

<br>

## 2. In the ***second*** example, let's delete all .txt files whose name start with "journal" and end with "0" by this command. As usual, we then check if these files have been deleted using the regular find command:
```
$ find -name "journal*0.txt" -delete
$ find -name "journal*0.txt"
```

## Let's see if the output is as expected:
![Find and delete 2](Images/Findanddelete2.png)

<br>

## 3. In our ***third*** example, let's delete all files with size less than 3 KB by this command:
```
$ find -size -3k -delete
$ find -size -3k
```
![Delete files by their size](Images/Deletebysize.png) 

<br>

## Alright, that's the end of today's lab report. Hope you like it and see you!



