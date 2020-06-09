*Code Wars.*

 In a far far away galaxy …
….a spacecraft named “Falcon 1000” had a crash. Please help rioters to repair the engine. A translator  R2 D2 is partly broken. You need to write a code using 
R2 D2, but it's able to do only a few commands.

Testing could be done here - https://gameindriver.ru


R2 D2 syntaxis 

Damaged R2 D2 accept only positive integers and constants no more than 2^32. It only accepts lower case variables. If there are numbers, they are regarded as constants. By default every variable equals 0.

mov ax bx 

save the value of the variable bx in the variable ax. Also note that bx may be
constant, i.e. you can write mov ax 99, then the number 99 is stored in a variable ax.

add ax bx 

Sum a and b and save the sum in a. (add ax 42 increases a to 42)

label mylabel

create a note with a title mylabel for the next code string. This note could be used to jump with jl command. Name can consists of letters or numbers.

Jl ax bx my label

​If ax < bx then you go to the code line – mylabel, and the following code string is executed. Otherwise the command after jl is executed

print ax

(print 123 #output 123)

input ax
(doesn’t work)

Example 1.

Print sum of two integers

mov a 1
mov b 2
add a b 
print a 
(#output 3)

Example 2. 

Print numbers from 1 to N.

mov n 10
mov a 0
label loop
add a 1
print a
jl a n loop 
(#output 1 2 3 4 5 6 7 8 9 10)

Example 3. 

Find the biggest of two numbers

mov a 42
mov b 20
jl b a result
mov a b
label result
print a 
(#output 42)

Part A consists of 8 tasks.

Part B.
You need to write R2 D2 language interpreter in any coding language you like.

Example.
c3po_interpreter.py – your interpreter in Python
input.txt – file with input data (numbers 10 and 20 in our case)
sum.r2d2 – code of the program in R2 D2


Part C
Create a translator to R2 D2. 
When translating, code is generated in your programming language. Those. source code in R2-D2 language after translation no longer participates in the process. Your program received by translation must be compiled or run through its interpreter

Example.
c3po_itranslatr.py – your interpreter in Python
input.txt – file with input data (numbers 10 and 20 in our case)
sum.r2d2 – code of the program in R2 D2
sum.py – generated Python source code


It will be executed:
# python c3po_translator.py sum.r2d2 sum.py
Text of sum.py could look like:
a = input()
b = input()
a = a + b
print(a)

Further this program can run without R2 D2
# python sum.py < input.txt
#30
