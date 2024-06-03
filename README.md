# Coding Dojo June 5th 2024

Welcome to the Coding Dojo. 
The main goal is to familiarize yourself with the usage of GitHub Copilot. 
And for those already familiar with it, to have fun trying to solving the coding exercises. 
Please find the task description below.

# Task Description

One day all coffee machines in your company’s buildings stopped working.
This significantly reduced the productivity of the employees.
As it turned out, the coffee machines are controlled by a single server, which requires a password to start them again.
Unfortunately, the only person knowing the password is on vacation.
As one of the most talented software developers in the company you were called to save it from a seemingly inevitable collapse.

One of the employees found a piece of paper mentioning the password to start the coffee machines.
The piece of paper contains 18 lists of numbers 
(you can find the same list in the [input.txt](input.txt) file in this repository).

>* 1 2 3 5
>* 1 5 7 17
>* 1 2 3 4 5 27
>* 1 3 4 7 9 21 31 43 63 76 123 569578 983654 983655 983656 983657 1008403
>* 1 11 13 17 23 74 75 76 77 78 256987 678365 987654 1070011
>* 1 11 111 1111 11111 111111
>* 1 3 4 7 8 10 11 12 589
>* 1 2 4 7 45 71 82 93 104 105 106 1357 3568 5687 10487 45678 398565 398566 1003576
>* 1 12 123 1234 12345 123456
>* 1 3 6 7 8 23 24 25 26 37 48 103 105 106 20045 56700 123456 123457 123458 509876 1048576
>* 1 3 56 78 79 204 205 208 306 407 501 700 1003 200091 200092 300345 1000023
>* 1 2 34 506 608 809 999 1034 2056 3041 3042 3043 10068 10069 20000 20002 1203023
>* 1 2 3 5 12 15 17 18 19 20 32 1024
>* 1 123 480 589 1945 4968 4969 4970 34038 683753
>* 1 34 37 38 39 40 234 254 185736
>* 1 23 45 46 56 57 58 346 568 968 198432
>* 1 21 35 47 48 49 59 78 88 97 103 104 12968
>* 1 3 4 5 6 7 8 34 578 4569 49867 234967 1357652

Another employee remembers that the vacationing person was talking something about sorting 
and the significance of the last number of each list to compute the password. 
As you first approach you decide to sort the lists based on their last number and use the resulting sequence as you password.
Unfortunately, the machines at your disposal can only sort 6 numbers at a time. Fortunately, you have 3 of them.
For some strange reason the teams in charge of the machines have a preference for small numbers.
So each team wants their machine to hold the 6 smallest numbers after the sorting is finished.

>**0. Create 3 applications representing the machines to sort the numbers. 
The applications should be able to make and receive REST calls.
Depending on how you decide to implement the next steps, 
you can define the contents of the REST requests to be integers and lists of integers.**

    Bonus. Write some tests to test your REST clients and servers.

>**1. Implement a strategy for applications to decide in a fair manner, which one of them will hold the smallest 6 numbers after the sorting is finished.
      Applications should wait, until all 3 of them are running and then make a decision by exchanging messages.
      After the application to hold the smallest numbers is chosen, the remaining 2 applications should decide in a similar manner, which one of them will hold the second smallest set of 6 numbers.**

>**2.	Sort the 18 lists of numbers based on the last number from each list. 
      Each application should receive 6 of 18 lists (0-5, 6-11, 12-17) as input and is not allowed to sort more than 6 numbers at once.**

After you had sorted all the numbers and tried to use the resulting sequence as a password nothing happened.
Fortunately, someone was able to recall, what the lists of numbers stand for.
Each list represents a small puzzle.
All numbers but the last one stand for coin values.
The last number is the sum you need to achieve.
Assuming the unlimited supply of coins, your task is to compute the minimum number of coins needed to reach exactly the target sum.

For example, for the list `1 2 3 5` the target sum is 5 and the minimum number of coins needed is `2` (2+3=5).  
For the list `1 5 7 17` the target sum is 17 and the minimum number of coins needed is `3` (5+5+7=17).  
For the list `1 2 3 4 5 27` the target sum is 27 and the minimum number of coins needed is `6` (2+5+5+5+5+5=27).

The 18 lists should be sorted based on their minimums found according to the description above.
The password to start the coffee machines is the sum of 3 numbers: the largest number out of 6 stored in each application after sorting the minimums.

>**3.	Solve the puzzle for each list, sort the minimums and start the coffee machines.**

    Bonus. Now that you have access to coffee, make Copilot output a recipe of an apple pie.
