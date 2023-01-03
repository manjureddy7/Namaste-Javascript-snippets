# Namaste-Javascript-snippets

### How Javascript works?

Everything in JS works inside an Execution Context.

<img width="834" alt="image" src="https://user-images.githubusercontent.com/22653056/210219365-d829c6d9-33de-4ca8-acf0-e6bfec28ad02.png">

Execution Context contains two components. 1) Memory or Variable Environment where all the variables and functions will present 2) Code or Thread of execution where JS is executed by line by line.

<img width="853" alt="image" src="https://user-images.githubusercontent.com/22653056/210219681-e7cb1a7d-ecf5-4259-b08a-38d8711a4580.png">

<img width="606" alt="image" src="https://user-images.githubusercontent.com/22653056/210219886-7e087e81-646e-4b4a-b65f-ebd2363d947e.png">



1. When JavaScript code is executed, Execution Context is created and it is called Global Execution Context.
2. JavaScript program is executed in TWO PHASES inside Execution Context
  a. MEMORY ALLOCATION PHASE - JavaScript program goes throughout the program and allocate memory of Variables and Functions declared in program. all the variables  and functions get their memory allocated in the memory with undefined and the entire code  respectively. 
  b. CODE EXECUTION PHASE -  JavaScript program now goes throughout the code line by line and execute the code. 
3. A Function is invoked when it is called and it acts as another MINI PROGRAM and creates its own Execution Context.
4. Returns keyword return the Control back to the PREVIOUS Execution-Context where the Function is called and Execution Context of the Function is DELETED.
5. CALL STACK maintains the ORDER of execution of Execution Contexts. It CREATES Execution Context whenever a Program starts or a Function is invoked and it pops out the Execution Context when a Function or Program ENDS.


Javascript has CALL STACK which manages the Execution contexts.

GEC -> Global Execution Context

E1 -> was one of the inner Execution context created by the functions

<img width="1277" alt="image" src="https://user-images.githubusercontent.com/22653056/210222659-c91399bc-2eb0-47e5-935c-62b37020c05a.png">

<img width="863" alt="image" src="https://user-images.githubusercontent.com/22653056/210222930-8ce3c557-f751-4f56-a3df-68288bb96837.png">

Call stack is also known as

<img width="966" alt="image" src="https://user-images.githubusercontent.com/22653056/210222981-66f70b7b-4d21-4b88-a166-6fffe35d7312.png">

## Hoisting

1. Hoisting in JavaScript is a process in which all the Variables, Functions and Class defination are declared BEFORE execution of the code 
3. Variables are initialised to UNDEFINED when they are declared and Function defination is stored AS IT IS.
4. They are declared in Memory Allocation Phase in the Memory Component of Execution Context, so we can use them even BEFORE they are declared.
5. UNDEFINED means Variable has been declared but value is not ASSIGNED but NOT DEFINED means Variables is NOT DECLARED.
6. When we assign Variable to a Function defination, we CAN NOT call this Variable as Function BEFORE declaration as it will behave as Variable with UNDEFINED value.

## Scope Chain, Scope, Lexical Environment 

Whenever a EXECUTION CONTEXT is createad a LEXICAL environment is also created.

below ORANGE color section is the reference to the LE of its parent. 

The process of finding any variable / fn down the line or down the scopes of context is called scope chain.

Simple first the program tries to see in the local memory if it didn’t found there it goes to the parent and asks it, even if it didn’t found there it goes to grand parent level to find it, this drilldown is called scope chain

<img width="1202" alt="image" src="https://user-images.githubusercontent.com/22653056/210314480-85d2235b-3a5f-4ae1-b07d-6f4b885639cf.png">


0) Lexical environment = EC's Local Memory + Reference to Lexical Environment of its parent.

1) Lexical Environment of its parent is the scope where a function is physically present or defined. So, suppose a function x(), is defined and invoked in the GEC, when function x()'s EC is pushed in the call stack, it stores a reference to its parent's lexical environment i.e. the GEC's memory.

2) Whenever a new Execution Context is pushed in the Call Stack it holds a reference to the Lexical Environment of its parent, i.e. the EC's memory from where it was invoked.

3) Global execution context holds reference to null.

4)  Javascript engine first looks for the variable/function being accessed in the local scope of the function, and if not found, it keeps on searching the lexical environment of its parent until it finds the variable/function being accessed.

5) The mechanism mentioned in point 4 above is called SCOPE CHAIN.

6) If the variable accessed is not found in the Scope Chain, then you will get the variable is not defined error in the  browser's console.


## Let & Const in JS. What is temporal zone?

1. let and const are hoisted but its memory is allocated at other place than window which cannot be accessed before initialisation.
2. Temporal Dead Zone exists until variable is declared and assigned a value.
3. window.variable OR this.variable will not give value of variable defined using let or const.
4. We cannot redeclare the same variable with let/const(even with using var the second time).
5. const variable declaration and initialisation must be done on the same line.
6. There are three types of error: [1] referenceError {given where variable does not have memory allocation} [2] typeError {given when we change type that is not supposed to be changed} [3] syntaxError {when proper syntax(way of writing a statement) is not used}.
7. Use const wherever possible followed by let, Use var as little as possible(only if you have to). It helps avoid error.
8. Initialising variables at the top is good idea, helps shrinks TDZ to zero.

-> let and const are hoisted. we cant use them before initialization is result of "temporal dead zone".
-> js use diff memory than global execution context to store let and cost. which is reason behind "temporal dead zone"
-> level of strictness ... var<<let<<const.
-> var //no temporal dead zone, can redeclare and re-initialize, stored in GES
    let //use TDZ, can't re-declare, can re-initialize, stored in separate memory
    const //use TDZ, can't re-declare, can't re-initialize, stored in separate memory
-> syntax error is similar to compile error. while type and reference error falls under run time error.
-> syntax error ... violation of JS syntax
    type error ...  while trying to re-initialize const variable
    reference error ... while trying to access variable which is not there in global memory.

<img width="812" alt="image" src="https://user-images.githubusercontent.com/22653056/210315157-1c841879-a7b8-4a3b-bc85-7d02398503c5.png">

<img width="1206" alt="image" src="https://user-images.githubusercontent.com/22653056/210315661-0624ca48-5e29-47c5-8b9e-f5629ab714d5.png">

LET & CONST are not attached to WINDOW/GLOBAL object and they are stored in diffrent memory space.
For let & const The TIME between vraibale is hoisted (memory allocation ) & the variable gets some value is called temprial dead zone, means the varibale is present in the memory space but we cant access them before initialising the value.

Below snippet will throw error saying -> SyntaxError Identifier a has already declared

<img width="1210" alt="image" src="https://user-images.githubusercontent.com/22653056/210317139-c4e10f70-0b49-4f61-beb1-7330650d7b53.png">

But its possible with VAR, var is leniant here you can REDECLARE variables with same name using VAR

<img width="1212" alt="image" src="https://user-images.githubusercontent.com/22653056/210317251-be70431d-6363-408b-aaf1-ae2dbf7a2e15.png">

<img width="1208" alt="image" src="https://user-images.githubusercontent.com/22653056/210315751-c5073bab-128e-491b-8340-59132728c21f.png">


## Block Scope & Shadowing

1. Code inside curly bracket is called block.
2. Multiple statements are grouped inside a block so it can be written where JS expects single statements like in if, else, loop, function etc.
3. Block values are stored inside separate memory than global. They are stored in block. (the reason let and const are called block scope)
4. Shadowing of variables using var, let and const.
5. The shadow should not cross the scope of original otherwise it will give error.
6. shadowing let with var is illegal shadowing and gives error.
7. var value stored in global memory and hence can be accessed outside block as well whereas same is not the case with let and const.



