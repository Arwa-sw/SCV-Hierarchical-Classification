# Unchecked and failed to send

**which results in DoS with a failed call or frozen ether,(Insufficient gas send, Exception for external call not handled / Gasless Send / Out-of-gas send / Send without gas / failed)**

## Describe: 
When transferring ether to a contract, the recipient’s fallback function is executed. However, when using the send function for transferring, as 
the send function is limited to 2300 gas, the transfer may fail if the recipient’s fallback function needs more than 2300 gas, and the sender 
will get an out-of-gas exception. If this exception is not propagated, the 
sender can keep the ether while it appears to have been received.


## Its danger:
 King of The Ether Throne (KoET)

## Solution:
 can be prevented by using the Transfer function instead of Send as the former will revert the local transactions if the external transaction 
 reverts. However, if Send function is required to be used then the return 
 value of this function needs to be monitored. Another technique is to adopt a withdrawal pattern, wherein, each user is required to call an 
 isolated function that manages ether transactions and does not affect the rest of the contract execution. Therefore, making the transaction 
 management independent of the consequences of failed Send transactions  //  Use a.transfer() Consider to develop function that no need too much gas

## Tools can detect:
 Zeus / Vandal / Securify / SmartCheck / Oyente
