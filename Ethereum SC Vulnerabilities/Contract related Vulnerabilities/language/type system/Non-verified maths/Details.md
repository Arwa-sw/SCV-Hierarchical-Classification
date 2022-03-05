# Non-verified maths (Integer under/overflow (IO /Unchecked math / Integer division / Floating Point & Precision) which results in Floating-Point \& Precision, Integer under/overflow, or Dos. 

## Describe: 
Over/underflow vulnerability means that the value of integer variable falls out of its range (above the maximum or under minimum value) as a result of an arithmetic operation, or due to the overflow of a loop counter which falls in infinite loop. Besides, neither the Solidity compiler nor the EVM enforces integer overflow/underflow detection, and the floating point data types are not supported in Solidity which needed to develop by developer using the standard integer data types, however if done improperly incorrect results shall develop.  Besides, the developers should consider to: (1) integer division, in Solidity, will be rounded down; (2) order of operations; (3) high precision to low precision conversion should only be done following mathematical operation

## Its danger: 
over/under flow attack / BECToken attack / BeautyChain Token bug / (the Proof of Weak Hands Coin (PoWHC) 866 ether was liberated from its contract)
the funds of a contract could become completely frozen.

If the process of using integer types for floating point representations is done improperly, it can produce errors which can be especially pernicious when the faulty result relates to financial transactions.

## Solution: 
Use SafeMath libraries for all arithmetic, as well the require() function, which allows value checking

## Tools can detect:
 SmartCheck , Mythril, Oyente,  Zeus
