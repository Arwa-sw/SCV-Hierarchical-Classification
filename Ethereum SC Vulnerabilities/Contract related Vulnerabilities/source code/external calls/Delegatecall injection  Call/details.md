# External call (Untrusted Call )

## Diffrent Names :
**(Delegatecall injection (dynamic libraries)) .**

## Describe:
The Delegatecall opcode is a message call exactly like the call opcode, except the code executed 
at the targeted address in the call opcode is run in the context of the external contract or
function, but with the delegatecall opcode it is run in the context of the calling contract. 
It is a useful way of to enabling the use of shared libraries and saving the storage space, 
but that can lead to unexpected code execution. 

 Furthermore, if the addresses are provided by the user, then it will be easy for a malicious user
  to call a malicious contract so they can  change storage values and potentially drain all funds from the contract.
  Also, if the address is hard-coded, then it does not give the flexibility to update the contract to be called over time.

## Its danger:
 Parity Multisig Wallet (Second Hack), in this contract the attacker could became the wallet’s 
 owner and could withdraw any funds at wallet's leisure (26,793 ETH (or ~6.1 million USD)).

## Solution:
It should take into consideration the possible call context of the calling contract as well as
the library contract. Also, it is recommended to use the library keyword for implementing
library contracts, which makes the library stateless and non-self-destructable, hence preventing attackers from modifying the state of the library directly, which prevents them from affecting the
 contracts that depend on the library's code.

## Tools can detect:
 none

