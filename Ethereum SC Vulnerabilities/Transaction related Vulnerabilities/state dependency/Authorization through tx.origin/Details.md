# Transaction Info Dependency

**(Authorization through tx.origin)** 

## Describe:
 tx.origin is a global variable that refers to the original EOA that initiated the transaction.
  If it is used for authorization purposes rather than msg.sender (check the address that originally initiated the call), 
  it may be that the actual owner is conned into calling a malicious contract which in turn calls the victim contract, then the 
 authorization fails. Contracts can call each others’ public functions. tx.origin is the first account in the call chain 
 (always an externally owned one, i.e., not a contract); msg.sender is the immediate caller. 
 For instance, in a call chain 
 A → B → C, from the C’s viewpoint, tx.origin is A, and msg.sender is B. in the cod_a, function transferTo can be maliously exploited.

## Its danger: 
The failure of permission checks can cause serious consequences. 
For example, if someone passes the permission check for the suicide function, he/she can destroy the contract and steal all the ethers. Failing to store and protect data.

## Solation:
 Use msg.sender instead of tx.origin for authentication.However,in some cases, such as denying external contracts from 
 calling the current contract, it is useful to use tx,origin in the form of require(tx.origin == msg.sender)which will 
 prevent intermediate contracts from being used to call the current contract.

## Tools can detect:
 Remix IDE/ Slither / Oyente  / Remix / SmartCheck / 
 Gasper / Securify   / Mythril / Vandal / Zeus .