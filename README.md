# Title:
$\color[rgb]{1,0,1} Quiz system$

# Description:
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

![Screenshot (632)](https://user-images.githubusercontent.com/66069469/208203386-e736ee6b-f66f-4d94-9c28-57b84b3c3027.png)
* In order for the system to be used for academic purposes and to quickly and simply
measure student progress, we expect that in the future the user will be able to manually
add the needed questions.
# Procedure:
![IM](https://user-images.githubusercontent.com/66069469/208192747-ca146169-32a9-49f0-8a36-5416b2297a38.png)

* For printing our desired strings, we have built up 10 variables from VAR1 to VAR11, and we have also utilised Q1 to Q10 and QA1 to QA10 for printing our desired questions and their answers.

![image_2022-12-16_20-17-59](https://user-images.githubusercontent.com/66069469/208192944-0a9204f4-b96f-4731-8321-889466fd1274.png)

* We have now reached the first level. We started by printing a new line, and after that, we used an input to compare the carriage return. It will move to the QSN1 level if it is equal.


![image_2022-12-16_20-25-05](https://user-images.githubusercontent.com/119314929/208194098-bb994d3e-dabd-4560-bcb8-6ecc4219ee0a.png)

* We shall now address the query. We'll pick 1 level and 1 input, and we'll compare it to the right response. The QSN2 level will be reached if it is equal; else, the QSNW2 level will be reached.

![image_2022-12-16_20-30-20(1)](https://user-images.githubusercontent.com/119314929/208196213-92a29f59-5a51-4c32-8774-5d8910b53bd4.png)


* In QSN2, level BL will be increased for correct answers, after which the same input process will be used.

![image_2022-12-16_20-36-42](https://user-images.githubusercontent.com/119519190/208255266-d2c33c93-0471-4d74-9e52-dcab61b2841a.png)
 
* To convert our inner ascii to decimal in the exit level and make the user's understanding of the marks achieved easier, we added 48 with BL.

# Flowchart:

 ![image_2022-12-16_21-25-13](https://user-images.githubusercontent.com/119519190/208255996-8b650005-86eb-4129-bbf9-e7444f266103.png)




