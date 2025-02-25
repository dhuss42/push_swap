# push_swap

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

