# Stack size limit: 
(Stack overflow /Call Stack Limit/call stack’s depth limit) 
we have considered it as a vulnerability that results in a stack overflow.

## Describe: 
The EVM is a stack machine, which means that it operates bytecode instructions on a virtual stack. The maximum size of this stack is 1024, 
but if it is exceeded and reaches the limit of calls, then an exception is thrown and the call is aborted. The attackers can exploit this limitation 
by generating nested calls till the call stack is full and failing any other external calls made by the victim contract. Due to the lack of 
handling exceptions at low level, the victim contract will not be aware of this failure.

## Its danger:
 GovernMental, If the vulnerable contract does not contain the correct 
 exception handling, then the vulnerable contract will be attacked through this vulnerability when invoked

## Solution: 
 It  has been eliminated by the hard fork for EIP-150, which re-defines 
 the gas-consumption rules of external calls to make it impossible to reach 1024 in call stack depth.

## Tools can detect:
 OYENTE / Securify / MAIAN / SmartCheck
