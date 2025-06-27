# push_swap

## Contents

1. [Project Overview](#1-Project-overview)
2. [Project Structure](#2-Project-Structure)
3. [Description of individual steps](#3-Description-of-individual-steps)
4. [How to run](#4-How-to-run)

## 1. Project overview

For this project I was given a set of integer values, 2 stacks and a set of instructions to manipulate both stacks. My goal was to write a C program called push_swap that calculates and displays the shortest sequence of Push_swap instructions needed to sort the given integers.  

### I had the following operations at my disposal:

- sa (swap a): Swap the first 2 elements at the top of stack a.
- sb (swap b): Swap the first 2 elements at the top of stack b.
- ss : sa and sb at the same time.
- pa (push a): Take the first element at the top of b and put it at the top of a.
- pb (push b): Take the first element at the top of a and put it at the top of b.
- ra (rotate a): Shift up all elements of stack a by 1.
  - The first element becomes the last one.
- rb (rotate b): Shift up all elements of stack b by 1.
  - The first element becomes the last one.
- rr : ra and rb at the same time.
- rra (reverse rotate a): Shift down all elements of stack a by 1.
  - The last element becomes the first one.
- rrb (reverse rotate b): Shift down all elements of stack b by 1.
  - The last element becomes the first one.
- rrr : rra and rrb at the same time.

## 2. Project Structure

3.1 [Parsing](#31-parsing)  
3.2 [Algorithm](#32-algorithm)  

## 3. Description of individual steps

### 3.1 Parsing

In the main function, I started by checking the number of arguments. If there were more than two arguments, I created an array of the numbers as strings. If there were exactly two arguments, I split the single string into an array of strings. This way, my program could handle both formats: either several separate arguments or a single quoted string of space-separated numbers.

### 3.2 Algorithm

The strings were then checked to ensure they represented valid integers, did not exceed integer limits, and did not contain duplicates. If any of these tests failed, the program exited; otherwise, Stack A — in the form of a linked list — was populated. If the stack size was three or fewer, Stack A was sorted directly. If the stack size was four or five, an optimized algorithm was implemented utilizing both stacks A and B. For stack sizes above five, the following algorithm was applied:

I pushed all numbers onto stack B, except for the last three, which I sorted directly. After that, the core algorithm began.

For each number in stack B, I calculated its optimal position in stack A, considering the number of operations needed to move it there. By evaluating all possible moves, I selected the least costly one to place the number in stack A. I repeated this process, always choosing the most efficient operations, until stack B was empty and stack A was completely sorted.

```
Stack A    Stack B

[5]        [4]   -> before 5  (push to A)                              = 1 Move  
[11]       [2]   -> before 5  (rotate B, push to A)                    = 2 Moves  
[17]       [92]  -> behind 17 (reverse rotate B, push to A, rotate A)  = 3 Moves  
```

## 4. How to run

Clone repository
```
git clone https://github.com/dhuss42/so_long.git push_swap
cd push_swap
make
./push_swap
```

