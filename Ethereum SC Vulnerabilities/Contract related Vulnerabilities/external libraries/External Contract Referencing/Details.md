# External Contract Referencing

## Describe:
 interacting with or referencing to external contracts via external message calls, which can mask malicious actors’ intentions in some nonobvious ways.
It will be worse If a conditional statement (if, for, while) depend on external call, that if the callee fails  (throw or revert) the caller will be prevented from completion the execution.  


## Its danger: 
Re-Entrancy Honey Pot. The attecker can replace the expected target contract with a malicious contract.

## Solution:
 use the new keyword and hard code any external contract addresses if they are known.

## Tools can detect:  
none.

