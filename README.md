# Core-CodeBootcampG
**What is JavaScript?**
---
---
First Week challenges #
---
JavaScript is a text-based programming language used both on the client-side and server-side that allows you to make web pages interactive. Where HTML and CSS are languages that give structure and style to web pages, JavaScript gives web pages interactive elements that engage a user. 

What is JavaScript used for?
---
JavaScript is mainly used for web-based applications and web browsers. But JavaScript is also used beyond the Web in software, servers and embedded hardware controls. Here are some basic things JavaScript is used for:

 1. Adding interactive behavior to web pages
 2. Creating web and mobile apps
 3. Building web servers and developing server applications

Incorporating JavaScript improves the user experience of the web page by converting it from a static page into an interactive one. To recap, JavaScript adds behavior to web pages.

Tuesday
-----

## What is an interpreted language?
---
An interpreted language is a programming language which are generally interpreted, without compiling a program into machine instructions. It is one where the instructions are not directly executed by the target machine, but instead read and executed by some other program. Interpreted language ranges – JavaScript, Perl, Python, BASIC, etc.


My first Code on JavaScript
 
Click here --> [HELLO WORLD](https://spaces.w3schools.com/space/firstcodebm/editor)
  


Java language is compiled or interpreted?
---
Java can be considered both a compiled and an interpreted language because its source code is first compiled into a binary byte-code. This byte-code runs on the Java Virtual Machine (JVM), which is usually a software-based interpreter.

Create an algorithm to calculate the equivalent of your local currencty to USD
---
Variables

UsaMoney

LocalMoney = 7.55

Result = LocalMoney * UsaMoney

start
 1. How many $ would you like to calculate?
 2. UsaMoney ()
 3. Result = LocalMoney * UsaMoney
 4. "UsaMoney" $ is iqual to "Result" Quetzales
 
end 

---
Why is pseudocode helpful?
---

Pseudocode is a way of writing program in wich you represent the sequence of actions and and instruction, in a form that humans can easily understand. By doing Pseudocodo it will be easier to find a best solution to the problem.

 1. Create a pseudocode to calculate the aproximated age of a user base on the year they born.

Variables
1. ActualYear
2. UserYear
3. Age = ActualYear - UserYear

start

 1. enter current year.(ActualYear)
 2. enter the year you were born. (UserYear)
 3. Your age is(Age).
 
 end.
 
 
Flowcharts
---
It is a diagrammatic representation of the solution to a given problem, but more importantly, it provides a breakdown of the essential steps to solving the problem.



What is the most important part of a flow chart?
---

Readability is probably the most important aspect of a flowchart. As the diagrammatic representation of a process, the flowchart aims to offer a visual description of a process to help us understand what is going on.


------------------------------------------------------------

Wednesday
----
1. Learn about binary, decimal and hexadecimal numbers

A diario nosotros utilizamos el sistema decimal para contar, pero existen también otros sistemas de numeración, como lo son el binario y hexadecimal, donde en binario tenemos únicamente para contar el cero y el uno, para hexadecimal tenemos del 0 al 9 y luego de la “A” a la “F”

2. Translate the year you where born to binary, decimal and hexadecimal

Translate 2001 to binary
----



``` 
2001 / 2 = 1
1000 / 2 = 0
500 / 2 = 0
250 / 2 = 0
125 / 2 = 1
62 / 2 = 0
31 / 2 = 1
15 / 2 = 1
7 / 2 = 1
3 / 2 = 1
1  

Binary = 11111010001

```
Translate 2001 to Decimal
---


```
2001 / 10 = 1
200 / 10 = 0
20 / 10 = 0
2
Decimal = 2001
```
Translate 2001 to hexadecimal
----
```
2001 / 16 = 1
125 / 16 = D
7
Hexadecimal = 7D1
```

Translate 51966 into hexadecimal and binary
----
```
51966 / 2 = 0
25983 / 2 = 1
12991 / 2 = 1
6495 / 2 = 1
3247 / 2 = 1
1623 / 2 = 1
811 / 2 = 1
405 / 2 = 1
202 / 2 = 0
101 / 2 = 1
50 / 2 = 0
25 / 2 = 1
12 / 2 = 0
6 / 2 = 0
3 / 2 = 1
1
Binary = 1100101011111110
```
Translate 51966 to Hexadecimal
----
```
51966 / 16 = E
3247 / 16 = F
202 / 16 = A
12 = C
Hexadecimal = CAFE
```
4. Use a Low-level language, for example MIPS aseembler, to do so, you will need to follow this guide. We recomend to check the guide first but also this presentation could be helpful.

Completed
5. Base on the examples and the guide of the low-level language

5.1 Create a program to add two numbers given by the user 

```
.data
  welcome: .asciiz "\n Bienvenido\n"
  number1: .asciiz "\nIngrese el primer numero: "
  number2: .asciiz "\nIngrese el segundo numero: "
  firstNumber: .asciiz "\nPrimer numero: "
  secondNumber: .asciiz  "\nSegundo numero: "
.text
  main:
  	li $v0, 4
  	la $a0, welcome
  	syscall 
  	
  	li $v0, 4
  	la $a0, number1
  	syscall

  	li $v0, 5
  	syscall

  	move $t1, $v0

  	li $v0, 4
  	la $a0, number2
  	syscall

  	li $v0, 5
  	syscall

  	move $t2, $v0

  	li $v0, 4
  	la $a0, firstNumber
  	syscall
  	
  	li $v0, 1
  	move $a0, $t1
  	syscall
  	
  	li $v0, 4
  	la $a0, secondNumber
  	syscall
  	
  	li $v0, 1
  	move $a0, $t2
  	syscall
```
5.2 Create a program that display your name
----
```
.data
	welcome: .asciiz "\n welcome human\n"
	name: .asciiz "\nMy name is Kevin Curruchich "
	nickname: .asciiz  "\nBut you can call me Chiwy "
.text
	main:
		li $v0, 4
		la $a0, welcome
		syscall 
		
		li $v0, 4
		la $a0, name
		syscall

		li $v0, 4
		la $a0, nickname
		syscall
```
Thursday
----
1. Search for real word applications of Javascript

   JS lo podemos encontrar en muchas aplicaciones, principalmente fue creado para darle a las páginas web interacción con el usuario, en la actualidad existen varias tecnologías basadas en JS, como lo pueden ser las aplicaciones multiplataforma, donde tanto la parte del Frontend y del Backend están realizadas en JS
   
2. (optional but great) Watch this video

3. (optional but great) Watch this video Follow the github course, you can find it here














