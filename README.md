# my-shell

#CSE 333 - OPERATING SYSTEMS
##Programming Assignment # 1

1. (15 pts) A histogram is a representation of the distribution of numerical data. Write a shell
script that will create histogram of a file of numbers. Your program will take a filename as
an argument. The file will contain a number in between 0-9, inclusive, at each line. You
will count the occurrence of each number and print histogram. For example:
Ex:
$ cat file.txt
4552122761668
Ex:
$ ./myprog1.sh file.txt
0
1 **
2 ***
3
4 *
5 **
6 ***
7 *
8 *
9


2. (15 pts) Write a shell script that takes two command line arguments, first one being a string and
the second one being a number. The number has to have a length of either 1 or same as the
string. Your program should then convert the input string into a ciphered one using this number.
For each letter in the string, your program has to find another letter in the English alphabet
advancing over the alphabet corresponding digit times. For example:

Ex:
$ ./myprog2.sh apple 12345
brspj
Since b is one after a, r is two after p and so on. If the number has only one digit, then this digit
will be used for all the letters in the string.
Ex:
$ ./myprog2.sh zoo 8
hww


3. (15 pts) Write a shell script that will take an optional pathname as an argument. If your program
is run with no argument, then it will find the oldest file under current working directory and
delete it, after asking the user. If your program is run with a pathname as an argument, it will
find the oldest file under given pathname and delete it, after asking the user.

Ex:
$ ls -l
-r---w---- 1 std std 13107 Jun 20 2002 cask-of-amontillado.txt
-rw------- 1 std std 0 Jun 20 2005 french.txt
drwx------ 14 std std 456 May 25 2007 shakespeare
-rw------- 1 std std 0 Jun 20 2005 trees-and-other-poems.txt
$ ls -l shakespeare
-rw------- 1 std std 456 Jun 20 2005 barleby-scrivener.txt
-rw------- 1 std std 0 Jun 21 2005 calaveras-county.txt
$ ./myprogr3.sh
Do you want to delete cask-of-amontillado.txt? (y/n): y
1 file deleted
$ ./myprogr3.sh shakespeare
Do you want to delete barleby-scrivener.txt.txt? (y/n): y
1 file deleted


4. (20 pts) Write a shell script that takes a filename as an argument. Your program will change the
numbers to text for each number in between 0-9, inclusive.

Ex:
$ cat file.txt
Lorem ipsum dolor sit amet, consectetur adipiscing elit. 7 Suspendisse
vitae odio blandit, commodo nisl dignissim, 9 commodo est. Quisque
blandit laoreet ante id tincidunt. Vivamus in vestibulum sem. Duis ac
faucibus quam. Mauris posuere, sapien quis elementum porttitor, leo
turpis finibus erat, vel dapibus 00 lorem mauris in elit. Curabitur
quis massa sit amet ligula suscipit pulvinar.

Ex:
$ ./myprog4.sh
$ cat file.txt
Lorem ipsum dolor sit amet, consectetur adipiscing elit. seven
Suspendisse vitae odio blandit, commodo nisl dignissim, nine commodo
est. Quisque blandit laoreet ante id tincidunt. Vivamus in vestibulum
sem. Duis ac faucibus quam. Mauris posuere, sapien quis elementum
porttitor, leo turpis finibus erat, vel dapibus zerozero lorem mauris
in elit. Curabitur quis massa sit amet ligula suscipit pulvinar.
Note that the numbers are highlighted in bold only for readability concerns.


5. (25 pts) Write a shell script that takes a wildcard argument and a -R option. If your program is
run with no option, then it will find all the files whose name obeys the wildcard and copy them
into a directory named copied. If your program is run with -R option, your program will work
recursively. For example:

Ex:
$ ls
cask-of-amontillado.txt french.txt shakespeare trees-and-otherpoems.
txt
$ ls shakespeare
barleby-scrivener.txt calaveras-county.txt
$ ./myprog5.sh -R “c*.txt”
$ ls
copied cask-of-amontillado.txt french.txt shakespeare trees-and-otherpoems.
txt
$ ls copied
cask-of-amontillado.txt
$ ls shakespeare
copied calaveras-county.txt barleby-scrivener.txt
$ ls shakespeare/copied
calaveras-county.txt


 Bonus:You will get 10% extra credit if your program supports a Menu including all questions
above. Example:
$ ./myprog.sh
Please select an option:
1. Create histogram
2. Encryption
3. Delete oldest
4. Convert numbers
5. Organized files
6. Exit


These options must be printed inside a loop until “Exit” option is selected. When user enters one
choice, you should ask for the arguments if that option requires any. From the menu file, you will
call the chosen option with arguments.
