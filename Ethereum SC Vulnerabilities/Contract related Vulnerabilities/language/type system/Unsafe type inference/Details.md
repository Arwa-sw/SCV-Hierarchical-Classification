# Unmatched Type (Unsafe type inference)

## Describe:
 Type inference is supported in Solidity, which means that it can detect the type of variable  automatically. 
 For example: when the developer type var i = 42; Solidity defines the variable i as the smallest integer 
 type sufficient to store the right-hand side value (uint8),  but that may lead to security issues.

## Its danger:
 if the typecasting with the address, the EVM can be misled to run the attacker’s contract

## Solution: 

Currently, there is no feasible way to avoid the vulnerability just Explicitly declaring data types is recommended to avoid unexpected behaviors and/or errors.

## Tools can detect:  

