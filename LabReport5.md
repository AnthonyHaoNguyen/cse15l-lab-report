# Part 1
## 1. 
![Image](aaaProcode.png) 
![Image](aaaProput.png)


Hi, for my `merge` method whenever I enter a null object as one of the arguments the test fails. Then it gives an error output with a `NullPointerException` and I think the bug creates an error whenever we enter an argument that doesn't work with the `compareTo()` method.


## 2. 
For this consider the `throw` command and think about what null is and trace through your code when null is input as an argument. Hope this helps and let me know if you need me to clarify anything. 


## 3. 
![Image](agood.png)
![Image](acode.png)


After trying the TA's response, the bug occured because the code didn't account for null because null is a special object that means an absence of a value, so it must be caught with some addition work in order to debug the bug. I changed the assert in the tests and created a throw `NullPointerException` in the code to catch if there a was a null anywhere in both input arguments.


## 4.
