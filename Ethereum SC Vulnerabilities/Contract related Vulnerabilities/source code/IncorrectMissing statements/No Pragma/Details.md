# Floating 

## Diffrent Names :
**No Pragma Floating,No Pragma,Outdated Compiler Version ,Compiler version not fixed ,Unspecified Compiler Version .**

## Describe: 
The smart contract code starts with pragma  solidity number to define the 
compiler version, and different versions have different APIs/instructions.  
Adding ^ (caret sign) to the number of the complier (e.g., ^0.5.4) means 
can be compiled with any Solidity version starting from 0.5.0 to 0.5.x.
 However, to ensure that version of the complier is the same with which 
 the contract has been tested and encounters all compile errors, it should lock the floating pragma, i.e. by not using ^ in pragma solidity.


## Its danger:
 The compiler failed to compile the code with Solidity 0.4.1 but succeeded 
 with version 0.4.23. The compiler, when writing code using version 0.4.23, 
 should show a warning suggesting that you alter your pragma version to match your compiler version.

## Solution: 
Be fixed to the version that you are intending to deploy your contracts with.
## Tools can detect:  
SmartCheck, Slither 

This can be done simply by checking pragma or if the ^ keyword exists in pragma and if it does check whether the version is lower than the compiler.