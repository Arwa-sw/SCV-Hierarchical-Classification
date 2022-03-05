# Use of untrusted input (Non-validated arguments )

## Diffrent Names:
**Use of untrusted input (EC recover malformed input),Use of untrusted input (Public lib functions do not return nested arrays),Use of untrusted input (Skip empty string literal).**

## Describe: 
The arguments in a function are the parameters passed during an invocation of a method or a transaction. The arguments are used 
in the method for several operations and computations as the required logic. These method arguments should be checked and 
validated before passing to the method call since the unchecked arguments may cause malicious actions during the execution of the method.

## Its danger:
 integer over/under flow attack.

## Solution: 
Should be validated and handle the errors.

## Tools can detect: 
Securify.
