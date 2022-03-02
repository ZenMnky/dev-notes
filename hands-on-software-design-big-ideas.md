# Big Ideas from O'Reilly Live: Hands-on Software Design
by Dr. Venkat Subramaniam
- an award-winning author, founder of Agile Developer, Inc., creator of agilelearner.com, and an instructional professor at the University of Houston.


## What does it mean to create good, lightweight software design?

### **What is good design?** (interactive question)
- reusable code
- simple
- flexible
- maintainable
- easy to understand
- loosely coupled
- resilient to change
- extensible
- easy to add new features
- robustness
- testable
- modular
- separation of concerns
- minimalistic 👈
- it works 👈
- relevant to the problem 👈
- consistent 👈
- well documented 👈
- cost beneficial 👈

> "A good design is not the one that correctly predicts the future, it's one that makes adapting to the future affordable."

## Characteristics of Good Design:
- Simple
- Fewer moving parts
- Relevant
- High Cohesion and low/loose coupling

### Cohesion
- Like things are together, and unlike things are apart
- Why is high cohesion a good thing?
	- Reduces the frequency of change to code
	- The cost of change is minimized when the code is highly cohesive
- Two categories of cohesion:
	- Technology based cohesion
		- example: client server architecture
	- Domain based cohesion
		- example: microservices

### Coupling
- Linking things together so that they are dependent
- A tightly coupled system is a monolithic one, with few or no independent parts. [1] 
- A loosely coupled system consists of objects or components that can be interchanged without affecting the whole [1] 

> "Cohesion describes how strongly the internal contents of a routine are related to each other. Coupling describes how strongly a routine is related to other routines. The goal is to create routines with internal integrity (strong cohesion) and small, direct, visible, and flexible relations to other routines (loose coupling)" [2]

## 🌟 Kent Beck's 4 Rules of Simple Design
1. Passes all the tests
2. Reveals its intentions
3. Removes duplication
4. Fewest elements

In the order of high to low priority.

## SLAP > SRP

### Single Responsibility Principle (SRP)
- The reason for change for a function or a module of code should be minimal
- *"Single Reason for Change Principle"*, may be a better way to understand this
- This is really about cohesion
- SRP should be in every level of the code - functions, classes, modules, applications, libraries...     


### 👉 **Single Level of Abstraction Principle (SLAP)**
- A long or short function is not about the number of lines of code. It's about the number of levels of details or abstraction that the function deals with.

Example of SLAP:
```js
const number = [ 1, 2, 3, 4, 5, 6, 7, 8, 9, 10];

const result = numbers.filter((e) => return e % 2 === 0)
	.map(e => e * 2)
	.reduce((total, e) => total + e)

// not too noisy, and kind of easy to read
// still cohesive
// But, still leaves us wanting more - 
// still some cognitive load

//  ------------------------------------------------------------------
// 👉 "Don't make me think" - software engineering principle
// -------------------------------------------------------------------

// A better way:

const number = [ 1, 2, 3, 4, 5, 6, 7, 8, 9, 10];

const isEven = e => e % 2 === 0;
const double = e => e * 2;
const sum = (a, b)  => a + b;

const result = numbers.filter(isEven)
	.map(double)
	.reduce(sum)

// less noisy
// easier and quicker to understand
// good names represent abstractions
// it is now easier to unit test the logic in each stage of the pipeline as well
// the functions we created are also reuseable where needed


```



## Fundamental Software Design Principles

### DRY
- Don't Repeat Yourself
- Single Source of Truth
	- every piece of knowledge should have a single, unambiguous, authoritative source of representation
- 👉 refers to duplication of effort and not just duplication of code
	- if we do manual verification/testing, then we are violating DRY
	- if we do manual deployment, then we are violating DRY

### ⭐ YAGNIy
- You Aren't Gonna Need It (yet)
- We are smarter tomorrow than today
	- We have more information, more context, more clarity, ect, as time goes on
- Avoid doing things that are really not necessary
- If we keep our design and code minimum it is easier to extend later than if we write a lot now
- Do not create abstraction or interfaces or generalize at the first sitting
- When you see a change arise, ask if similar changes will be needed in the future and then generalize at the time

### Open-Closed Principle
- A software module must be open for extension, but closed for modification
- It is more expensive to modify existing code than to add a very small piece of new code
- Abstraction and Polymorphism are the key





## Outside references
- [1] Richard, Leinecker. (2000). "COM+ Unleashed" | https://learning.oreilly.com/answers/results/?question=what+is+coupling&page=1

- [2] Trott, James. Shalloway, Alan. (2004). "Design Patterns Explained: A New Perspective on Object-Oriented Design, Second Edition" | https://learning.oreilly.com/answers/results/?question=what+is+coupling&page=2
