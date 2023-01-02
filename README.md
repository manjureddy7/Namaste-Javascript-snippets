# Namaste-Javascript-snippets

### How Javascript works?

Everything in JS works inside an Execution Context.

<img width="834" alt="image" src="https://user-images.githubusercontent.com/22653056/210219365-d829c6d9-33de-4ca8-acf0-e6bfec28ad02.png">

Execution Context contains two components. 1) Memory or Variable Environment where all the variables and functions will present 2) Code or Thread of execution where JS is executed by line by line.

<img width="853" alt="image" src="https://user-images.githubusercontent.com/22653056/210219681-e7cb1a7d-ecf5-4259-b08a-38d8711a4580.png">

<img width="606" alt="image" src="https://user-images.githubusercontent.com/22653056/210219886-7e087e81-646e-4b4a-b65f-ebd2363d947e.png">

As soon as the JS code runs, an execution context is created in TWO phases. 1. Memory creation phase 2. Code execution phase

In Memory creation phase all the variables and functions are placed in the memory block. The variables will get UNDEFINED as their initial value & functions will get their block of code as their values .
Once this phase is done, javascript is again run from top to bottom or line by line, the varibales inside the memory block will get their appropriate values.
When functions start executing, JS will again create a brand new Execution Context for that function instance and start allocating memory and updates the variables, once function execution is done, the EC will be deleted and brings the control to the GLOBAL thread of execution where this function being called.

Javascript has CALL STACK which manages the Execution contexts.

GEC -> Global Execution Context

E1 -> was one of the inner Execution context created by the functions

<img width="1277" alt="image" src="https://user-images.githubusercontent.com/22653056/210222659-c91399bc-2eb0-47e5-935c-62b37020c05a.png">

