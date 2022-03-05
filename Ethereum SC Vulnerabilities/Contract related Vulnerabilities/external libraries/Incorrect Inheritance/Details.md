# Incorrect Inheritance

## DiffrentNames:
Incorrect Inheritance Order,Multiple inheritance,missing-inheritance.
 
**which results in Incorrect Inheritance Order, Multiple inheritances,
 or Overridden by Delegate Call.**

## Describe:
 solidity supports multiple Inheritance, and it uses reverse C3 Linearization (decide based on priority) whenever happen confliction of two  or more base contracts define the same functions, however that may change the flow of expected behavior.


## Its danger:

## Solution: 
inherit contracts from more general  to more specific.

## Tools can detect: 
 Slither

