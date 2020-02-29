Working Effectively with Legacy Code
===

**Author**: Michael C. Feathers

**Biography**:

Michael Feathers is founder and Director of R7K Research & Conveyance, which specialise in software and organisation design, and was previously Chief Scientist of Obtiva.

**Author link**:

https://twitter.com/mfeathers?lang=en

Chapter 1: Changing software
---

There is few things that push us to change software:

1. Adding a new feature or fixing a Bug
2. Improving design
3. Resource usage

**Adding a new feature or fixing a Bug**

They can be different, but the end goal will be the same: changing behaviour of a software based on a Client demand. 
If it's a new feature or a Bug is very often a point of view problem. Removing a feature for a Client is very often view as a Bug by the CLient, but not necessarily by team of engineers.

That steps involves _a change of beahviour_ and _a change of software structure_.

**Improving design**

It is more commonly called _Refactoring_. Most of the time to be able to maintain much better a project.
That step should not change any behaviour for the Client.

That step involves only a _change of software structure_.

**Resource usage**

That step is like _Refactoring_, but the goal is different. Here we want to improve the resource used by the program (time or memory)

That step only about _Optimizing_ and doesn't change any structure or behaviour.

Chapter 2: working with feedback
---

There is usually 2 ways of working with legacy :
- edit and pray
- Cover and modify

1. **Edit & Pray**: the process here is to understand as much as possible the code we want to modify,
doing the modification, testing and deploy. It usually requires to have colleagues to test to make sure nothing breaks.

2. **Cover & modify**: Writting tests that cover the block you want to modify, and then edit the code and deploy. It is a much safer solution.

Regression tests are good, but take too long to get feedback. We have to use **unit tests**.

Unit tests should be fast and make easier to localize a problem. Moore’s law, we expect unit test feedback to be instantaneous, no matter the size of the project

**The legacy code dilemma**: 
to modify code, we have to write test, to write test we often have to change code.

The real problem in write test are dependencies, we often have to change code and break dependencies to make it easier to test.

The legacy code change algorithm:
1. Identify change point
2. Find test points
3. Break dependencies
4. Write test
5. Make changes and refactor

Chapter 3: Sensing & separation
---

There is generally 2 reasons to break dependencies:
1. Sensing: break dependencies to _sense_ when we can’t access values our code compute.
2. Separation: break dependencies to _separate_ when we can’t have a piece of code in a test.

The main tool for sensing would be _fake collaborators_: we would use fake objects to sense the effects of our actions.

Mock objects are subset of fake objects, they do the same but also do some assertion internally.

Mock objects framework are not available on every language.

Chapter 4: The seam model
---

The definition of seam is:
A seam is a place where you can alter behaviour in your program without editing in that place.

The definition of enabling point is:
Every seam has an enabling point, a place where you can make the decision to use one behaviour or another.


There are 3 types of seams:

1. Preprocessing seam:  It is the way to replace methods during the preprocessing of the compilation. It is used for compiled language and interesting to use in C or C++
2. Link seams: Basically it is creating a new library to include while testing instead of the production library. It would make easier to load test objects instead of production ones.
3. Object seams: Using the power of Object Oriented languages to be able to modify some call methods to make it easier to test: Using dependency injections, or overwriting methods are the usual things to do.

Chapter 5: Tools
---
