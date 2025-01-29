---
layout: project
type: project
image: img/maths2.jpg

title: "Flash Card Mini-game"
date: 2024
published: true
labels:
  - C
  - Unix
  - emacs
summary: "A flash card mini game that I made as one of the assignments for ICS 212"
---


This was a short assignment that I did for my ICS 212 class. The objective for this assignment was to utilize custom functions and in this case, I made functions that multiplied numbers and either returned a message displaying if the input was correct or incorrect. The main goal of this assignment was to practice using Unix as well as creating a makefile to make an executable program. Another useful tool that I learned was to seed random generator using UNIX time.

Here is some code that illustrates how I randomly generated numbers and keeping track of the correct/incorrect amount of questions answered:

```cpp
48   while(num < questions) {
49     /*Generate a random number from 1 to 9*/
50     int firstNum = rand() % 9 + 1;
51     int secondNum = rand() % 9 + 1;
52 
53     /*Display question to user and store inputted answer into recordedAnswer                                                                                                                                                                
54       variable*/
55     printf("Q%d: What is %d times %d? ", questionNumber, firstNum, secondNum);
56     int recordedAnswer = (int)getdouble();
57 
58     /*If the user answers the question correctly, call checkCalculation                                                                                                                                                                     
59      function, then increment correctCount*/
60     if(checkCalculation(firstNum, secondNum, recordedAnswer)) {
61       correctCount++;
62     }
63     /* Otherwise, increment incorrectCount */
64     else {
65       incorrectCount++;
66     }
67     /* Increment questionNumber and num, so that the question number now corresponds                                                                                                                                                        
68      correctly. Increment num to keep track of the number of questions that the user has                                                                                                                                                    
69      completed */
70     questionNumber++;
71     num++;
72   }
```

Here is the example output of the code displayed in the terminal:

```cpp
Multiplication flash card program!
This program is designed for single-digit multiplication problems.
How many questions would you like to answer? 2
Q1: What is 2 times 1? 2
Correct!
Q2: What is 9 times 5? 45
Correct!
~~~~~~~~~~~~~~~~~~~~~~~~~~~~
All questions answered, here are your results.
Number correct: 2
Number incorrect: 0
Percentage of correct: 100.00%
Percentage of incorrect: 0.00%
```




