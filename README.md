# Namaste-Javascript-snippets

### How Javascript works?

Everything in JS works inside an Execution Context.

<img width="834" alt="image" src="https://user-images.githubusercontent.com/22653056/210219365-d829c6d9-33de-4ca8-acf0-e6bfec28ad02.png">

Execution Context contains two components. 1) Memory or Variable Environment where all the variables and functions will present 2) Code or Thread of execution where JS is executed by line by line.

<img width="853" alt="image" src="https://user-images.githubusercontent.com/22653056/210219681-e7cb1a7d-ecf5-4259-b08a-38d8711a4580.png">

<img width="606" alt="image" src="https://user-images.githubusercontent.com/22653056/210219886-7e087e81-646e-4b4a-b65f-ebd2363d947e.png">

As soon as the JS code runs, an execution context is created in TWO phases. 1. Memory creation phase 2. Code execution phase

Memory allocation phase- all the variables  and functions get their memory allocated in the memory with undefined and the entire code  respectively. 

Code execution phase - in this phase  thread execution happens and all the variables get their actual values which were assigned to them and as function is invoked, a new execution environment gets created in the code part, and again there are two phases, memory allocation phase and code execution phase. And the cycle repeats.


Javascript has CALL STACK which manages the Execution contexts.

GEC -> Global Execution Context

E1 -> was one of the inner Execution context created by the functions

<img width="1277" alt="image" src="https://user-images.githubusercontent.com/22653056/210222659-c91399bc-2eb0-47e5-935c-62b37020c05a.png">

<img width="863" alt="image" src="https://user-images.githubusercontent.com/22653056/210222930-8ce3c557-f751-4f56-a3df-68288bb96837.png">

Call stack is also known as

<img width="966" alt="image" src="https://user-images.githubusercontent.com/22653056/210222981-66f70b7b-4d21-4b88-a166-6fffe35d7312.png">



