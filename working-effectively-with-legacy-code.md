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