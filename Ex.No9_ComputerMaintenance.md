# Ex.No: 9  Logic Programming –  Computer Maintenance Expert System
### DATE:19/9/24                                                                            
### REGISTER NUMBER :212222040046 
### AIM: 
Write a Prolog program to build a computer maintenance expert system.
###  Algorithm:
1. Start the program.
2. Write the rules for each fault in computer.
3. If system have printing problem, missing dots and no uniform printing then system fault on printer head.
4. If system have not printing, missing dots and spread inks then system fault on ribbon
5. If system have not printing, paper jam and out of paper then system fault on paper stuck in printer
6. Similarly define rules for all faults.
7. Define facts for system problems.
8. Find the fault of computer by passing query to system.
     
### Program:
```
fault(printer_head) :- 
 problem(not_printing), 
 problem(missing_dots), 
 problem(nonuniform_printing). 
fault(ribbon) :- 
 problem(not_printing), 
 problem(missing_dots), 
 problem(spread_ink). 
fault(paper) :- 
 problem(not_printing), 
 problem(paper_jam), 
 problem(out_of_paper). 
fault(motherboard) :- 
 problem(long_beep), 
 problem(short_beep). 
fault(hard_disc) :- 
 problem(two_short_beeps), 
 problem(blank_display). 
problem(not_printing). 
problem(missing_dots). 
problem(spread_ink). 
problem(two_short_beeps). 
problem(blank_display).
```
### Output:

![316294987-4bbffa8d-c1f8-4465-84c5-aeb70fa01051](https://github.com/user-attachments/assets/073ab23d-94f3-45b8-abfc-4ad5e241466c)

### Result:
Thus the simple omputer maintenance expert system was built sucessfully.
