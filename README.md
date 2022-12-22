# Title:
 Quiz-system

# Project Description:
* Quiz system is an exam form of MCQs in which,we have set 10 questions.
 For each right answer 1 mark will be increased and for each 
wrong answer nothing will be added to the total points 
and at the end of the quiz total marks will be shown.

* For this aim we are using assembly language for 8086 microprocessor,
The simplest programming language for any CPU is assembly language.
A programmer can only use operations that are really implemented on
the physical CPU when using assembly language. Assembly language is
not portable across different processor families and lacks high-level 
conveniences like variables and functions. Assembly language is the most
potent programming language for computers, and it provides programmers
with the understanding they need to create efficient code in high-level languages.
Every serious programmer should make the time and effort to learn assembly language.

![Screenshot (677)](https://user-images.githubusercontent.com/66069469/208452435-e4a40702-8b0a-454d-bff8-7bc95fe0285c.png)

* In order for the system to be used for academic purposes and to quickly and simply
measure student progress, we expect that in the future the user will be able to manually
add the needed questions.
# Procedure:
```ruby
.MODEL SMALL
.STACK 100H

.DATA    

VAR1 DB '                ...*** WELCOME TO YOUR QUIZ ****...$'
VAR2 DB 'Rules : $'
VAR3 DB 'For Every Correct answer you will get 1 point.$'
VAR4 DB 'For Every Wrong answer 1 Point will cut from your total point.$'
VAR5 DB 'Press Enter to start the quiz : $'


VAR6 DB 'Right Answer....$'
VAR7 DB 'Wrong Answer....$'
VAR8 DB 'You have successfully completed your quiz.$'
VAR9 DB 'Your Total obtained point is : $'
VAR10 DB 'Press 1 to Re-attempt quiz or 0 to Exit.$'   
VAR11 DB '                    *** best wishes.! ***$' 


Q1 DB '1. the purpose of the microprocessor is to control$'
QA1 DB '   a) memory    b) taskes    c) processing$'
Q2 DB '2. the intel 8086 microprocessor is a ........processor$'
QA2 DB '   a) 8bit    b) 16bit    c) 32bit$'
Q3 DB '3. Which of the following is not a status flag in microprocessor?$'
QA3 DB '   a) Direction flag    b) Overflow flag    c) Index flag$'
Q4 DB '4. Which of the following is not a condition flag?$'
QA4 DB '   a) Auxiliary carry flag    b) Trap flag    c) Zero flag$'
Q5 DB '5. Operation code field is present in....$'
QA5 DB '   a) machine language instruction    b) assembly language instruction    c) none of the mentioned$'
Q6 DB '6. If a W-bit value is ‘1’ then the operand is of....$'
QA6 DB '   a) 2 bits    b) 4 bits    c) 16 bits$'
Q7 DB '7. Which of the following instruction is not valid?$'
QA7 DB '   a) PUSH AX    b) MOV DS, 5000H    c) MOV AX, BX$'
Q8 DB '8. The instruction that supports addition when carry exists is....$'
QA8 DB '   a) ADD    b) ADD & ADC    c) ADC$'
Q9 DB '9. The instruction, CMP to compare source and destination operands it performs$'
QA9 DB '   a) subtraction    b) division    c) addition$'
Q10 DB '10. PUSH operation$'
QA10 DB '   a) decrements SP    b) increments SP    c) increments SS$'  
```
* For printing our desired strings, we have built up 10 variables from VAR1 to VAR11, and we have also utilised Q1 to Q10 and QA1 to QA10 for printing our desired questions and their answers.
```ruby
START:
	MOV BL, 0  
        CALL NL
	LEA DX,VAR5
	MOV AH,9
	INT 21H
	MOV AH, 1 ;--------------read char from input------------
	INT 21H
	CMP AL, 0DH ;----------ascii enter
	JE QSN1
	JNE START
```
* We have now reached the first level. We started by printing a new line, and after that, we used an input to compare the carriage return. It will move to the QSN1 level if it is equal.
```ruby
QSN1:
	CALL NL
	LEA DX,Q1
	MOV AH,9
	INT 21H
	CALL NL
	LEA DX,QA1
	MOV AH,9
	INT 21H
	CALL NL
	MOV AH, 1
	INT 21H
	CMP AL, 'a'
	JE QSN2
 	JNE QSNW2      
```
* We shall now address the query. We'll pick 1 level and 1 input, and we'll compare it to the right response. The QSN2 level will be reached if it is equal; else, the QSNW2 level will be reached.
```ruby
 QSN2:
	CALL NL
	LEA DX,VAR6
	MOV AH,9
	INT 21H
	MOV BL,0
	INC BL  ;-----------------------1st inc
	CALL NL
	CALL QN2 
	CALL INPUT
	CMP AL, 'b'
	JE QSN3  
	JNE QSNW3                             
 
```

* In QSN2, level BL will be increased for correct answers, after which the same input process will be used.
```ruby
EXITW:

	CALL NL
	LEA DX,VAR7
	MOV AH,9
	INT 21H
	CALL NL
	CALL NL  
	LEA DX,VAR8
	MOV AH,9
	INT 21H 
	CALL NL
 	CALL NL
    
	LEA DX,VAR9
	MOV AH,9
	INT 21H
	
	ADD BL,48 ;add 0
	MOV AH,2   
	
	MOV DL, BL
	INT 21H
	
	JMP EXIT1
 ```
* To convert our inner ascii to decimal in the exit level and make the user's understanding of the marks achieved easier, we added 48 with BL.

# Program Phases:

 ![image_2022-12-16_21-25-13](https://user-images.githubusercontent.com/119519190/208255996-8b650005-86eb-4129-bbf9-e7444f266103.png)

# Run program videos:
[Watch It!](https://youtube.com/playlist?list=PLo6dFyeKk2ZqIWqZsFqWnfU_d60VCo3yE)
# How to run the program:
Download and setup EMU8086 

# This Project was under supervision of:
 Dr. Abd-Elhamid Al-Etaby

# Team members:
* [Ahmed Saber](https://github.com/Ahmed-Saber-01)
* [Basma Ashraf](https://github.com/basma10ashraf)
* [Hanan Ahmed](https://github.com/hananAhmed45200)
* [Radwa Mohamed](https://github.com/Radwa200023)
* [Adham Mohsen](https://github.com/Adham-Mohsen00)


