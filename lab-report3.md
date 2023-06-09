# Lab Report 3 | Researching Commands (Grep)
### Renato Pimentel
Source: All commands that appear were found by reading the manual in git for grep/ using the command `man grep`.

`grep -l`
```
$ grep -l "base pairs" ./technical/plos/*.txt
./technical/plos/journal.pbio.0020190.txt

$ grep -l "banks" ./technical/biomed/*.txt
./technical/biomed/1477-7827-1-27.txt
./technical/biomed/bcr571.txt
./technical/biomed/bcr605.txt
./technical/biomed/gb-2001-2-3-research0008.txt
./technical/biomed/gb-2002-3-12-research0083.txt
```
When using grep with `-l` added, it will print the path to the files with the inputted string, instead of printing the mathcing lines. I could see this being useful if you needed to organize files with specific contents in a folder.

`grep -c`
```
$ grep -c "chemicals" ./technical/biomed/*.txt
...
./technical/biomed/1471-2121-3-19.txt:12
./technical/biomed/1471-2121-3-2.txt:2
./technical/biomed/1471-2121-3-21.txt:2
./technical/biomed/1471-2121-3-22.txt:1
./technical/biomed/1471-2121-3-25.txt:0
./technical/biomed/1471-2121-3-30.txt:2
...

$ grep -c "evolution" ./technical/biomed/*.txt
...
./technical/biomed/1471-2180-3-10.txt:0
./technical/biomed/1471-2180-3-11.txt:5
./technical/biomed/1471-2180-3-13.txt:12
./technical/biomed/1471-2180-3-15.txt:2
./technical/biomed/1471-2180-3-4.txt:0
...
```
*I shortened the output but it will still perform the the command on all the files inside of the inputted directory or file.*

When using `-c` with grep, it will print the paths to all the files in the directory. But additionally show a number on the end of the path with how many times the inputted word appears in the file. I can see this being useful if you are in a company and are logging entries. You can use this command to search how many times an error or certain event has occured.

`grep -i`
```
$ grep -i "DIPRIME" ./technical/biomed/*.txt        
./technical/biomed/1471-2164-3-16.txt:          labeled using Rediprime II Random 
Prime Labeling System

$ grep -i "DiPREnoRPhINE" ./technical/biomed/*.txt  
./technical/biomed/1471-2210-2-5.txt:          3H-diprenorphine ( 3H-DIPR; 3H-DIPR, 
54 Ci/mmol, 
```
When you use `i` with grep, it will do a case-insensitive search of the inputted pattern on the directory inputted. I can see this being useful if you are searching for a specific patter but are uncertain of the case senstivity of the file(s). Using this specific command will allow you to match the pattern no matter if the letters are uppercase, lowercase, or mixed even.

`grep -e`
```
$ grep -e "mountain" -e "sunrays" -i ./technical/biomed/*.txt
...
./technical/biomed/1471-2458-2-6.txt:          high-risk leisure pursuits, such as mountain climbing,
./technical/biomed/1472-6785-2-7.txt:        characteristics in the Intermountain West. 
Although a
./technical/biomed/1472-6785-2-7.txt:        geographically restricted area (Fig. 1), the 
Intermountain
./technical/biomed/1472-6785-2-7.txt:        the abundance and diversity of fungi in the
Intermountain
./technical/biomed/1472-6785-2-7.txt:          The Intermountain West is topographically and     
./technical/biomed/1472-6785-2-7.txt:          The Intermountain West consists of two biogeographic
...

$ grep -e "suns" -e "bombastical" -i ./technical/biomed/*.txt
./technical/biomed/1471-5945-1-3.txt:          tanning history, use of suntan lotions and sunscreens,
```
When using `-e` with grep, it will allow the user to input mutiple patterns to search for in the directory or file. Also when we use it with one of the functions before `-i` it will do the search without consdering the cases of letters. It will be useful in a autograder setting, because you can just directly compare patterns between two students if you think something is suspicious.
