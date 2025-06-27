# push_swap

## Contents

1. [Project Overview](#1-Project-overview)
2. [Project Structure](#2-Project-Structure)
3. [Description of individual steps](#3-Description-of-individual-steps)
4. [How to run](#4-How-to-run)

## 1. Project overview

For this project I was given a set of integer values, 2 stacks and a set of instructions to manipulate both stacks. My goal was to write a C program called push_swap that calculates and displays the shortest sequence of Push_swap instructions needed to sort the given integers.  
I had the following operations at my disposal:

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

1. [Parsing](#parsing)
2. [Window Setup and Texture Rendering](#Window-Setup-and-Texture-Rendering)
3. [Game Logic and Input Handling](#Game-Logic-and-Input-Handling)

## 3. Description of individual steps

The Push_swap project challenged me to sort a stack of integers using a limited set of operations while minimizing the number of moves. I implemented a C program that efficiently sorted the numbers by manipulating two stacks and applying operations like swaps, pushes, and rotations.

In my implementation of the Push_swap project, I utilized linked lists for the stacks to efficiently manage the data. I pushed all numbers onto stack B, except for the last three, which I sorted directly. After that, the core algorithm began.

For each number in stack B, I calculated its optimal position in stack A, considering the number of operations needed to move it there. By evaluating all possible moves, I selected the least costly one to position the number in stack A. I repeated this process, selecting the most efficient operations, until stack B was empty and stack A was completely sorted.

```
Stack A    Stack B

[5]        [4]   -> before 5  (push to A)                              = 1 Move  
[11]       [2]   -> before 5  (rotate B, push to A)                    = 2 Moves  
[17]       [92]  -> behind 17 (reverse rotate B, push to A, rotate A)  = 3 Moves  
```

This approach combined efficient data manipulation with careful algorithm optimization, ensuring minimal operations while achieving the desired sorted order.

## 4. How to run

Clone repository
```
git clone https://github.com/dhuss42/so_long.git push_swap
cd push_swap
make
./push_swap
```

navigate into repository
```
cd so_long
```

run make
```
make
```

run programm
```
./so_long maps/valid/valid1.ber 
```

