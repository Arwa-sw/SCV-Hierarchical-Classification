# Redundant fallback function

## Describe:
 fallback function is an important function executed 1)as default when no 
 function in the contract matches the given function, 2)whenever the 
 contract receives plain ether (need payable modifier to receive ether), or 3)when interfaces are incorrectly specified. The fallback function 
 should be with external visibility and a payable modifier to receive 
 ether unless it throws an exception, without name, arguments, or return 
 
 value. The rejection of payment causes a redundant fallback.
Solidity 0.6.x split the work of fallback into two functions, fallback function for ether transferring and receive function when none functions matching.

## Its danger:
 incorrect design of fallback function may cause Dao attack

## Solution: there is much researches studied this vulnerability, the useful advice is to avoid make fallback functions big because it only rely on 2300 gas, thus it must be simplistic and inexpensive.

## Tools can detect:
  SmartCheck, it detects the vulnerability by check whether there is a 
  function and it detect only if the compiler version no lower than 0.4.0, It is already built-in compiler 0.4.0.

