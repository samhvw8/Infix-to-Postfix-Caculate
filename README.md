# Assembly Final Project
## Requirements
##### Problem
- Caculate Infix expression by convert to postfix expression then caculate in postfix  
- Infix expression condition:  
   1. Number is positive 
   2. Doesn't Contain parenthesis  

##### Another
1. Programing languages Assembly Mips
2. Simulator: [Mars](http://courses.missouristate.edu/KenVollmar/MARS/)

## Algorithm
### Convert To postfix

1.	Print operands as they arrive.  

2.	If the stack is empty or contains a left parenthesis on top, push the incoming operator onto the stack.  

3.	If the incoming symbol is a left parenthesis, push it on the stack.  

4.	If the incoming symbol is a right parenthesis, pop the stack and print the operators until you see a left parenthesis. Discard the pair of parentheses.  

5.	If the incoming symbol has higher precedence than the top of the stack, push it on the stack.  

6.	If the incoming symbol has equal precedence with the top of the stack, use association. If the association is left to right, pop and print the top of the stack and then push the incoming operator. If the association is right to left, push the incoming operator.  

7.	If the incoming symbol has lower precedence than the symbol on the top of the stack, pop the stack and print the top operator. Then test the incoming operator against the new top of stack.  

8.	At the end of the expression, pop and print all operators on the stack. (No parentheses should remain.)  

[Source](http://csis.pace.edu/~wolf/CS122/infix-postfix.htm)

### Calculate

1. Scan the Postfix string from left to right.  
2. Initialise an empty stack.  
3. If the scannned character is an operand, add it to the stack. If the scanned character is an operator, there will be atleast two operands in the stack.  
4. If the scanned character is an Operator, then we store the top most element of the stack(topStack) in a variable temp. Pop the stack. Now evaluate topStack(Operator)temp. Let the result of this operation be retVal. Pop the stack and Push retVal into the stack.  
5. Repeat this step till all the characters are scanned.  
6. After all characters are scanned, we will have only one element in the stack. Return topStack.  

## Preview

> Input Infix is: 3+3+3\*9\*9-3*9  
> Postfix is: 3 3 +3 9 *9 *+3 9 *-  
> Result is: 222  