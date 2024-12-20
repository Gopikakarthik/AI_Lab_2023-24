# Ex.No: 6   Logic Programming – Factorial of number   
### DATE:5/9/24                                                                          
### REGISTER NUMBER :212222040046 
### AIM: 
To  write  a logic program  to solve Towers of Hanoi problem  using SWI-PROLOG. 
### Algorithm:
1. Start the program
2.  Write a rules for finding solution of Towers of Hanoi in SWI-PROLOG.
3.  a )	If only one disk  => Move disk from X to Y.
4.  b)	If Number of disk greater than 0 then
5.        i)	Move  N-1 disks from X to Z.
6.        ii)	Move  Nth disk from X to Y
7.        iii)	Move  N-1 disks from Y to X.
8. Run the program  to find answer of  query.

### Program:
```
move(1,X,Y,_) :-
write('Move top disk from '),
write(X),
write(' to '),
write(Y),
nl.
move(N,X,Y,Z) :-
N>1,
M is N-1,
move(M,X,Z,Y),
move(1,X,Y,_),
move(M,Z,Y,X).
```
### Output:

![277081949-5e3a259c-1483-4801-916c-9cba49dd0e7f](https://github.com/user-attachments/assets/de0b4243-f539-424e-9148-45a94cf6a4c6)

### Result:
Thus the solution of Towers of Hanoi problem was found by logic programming.
