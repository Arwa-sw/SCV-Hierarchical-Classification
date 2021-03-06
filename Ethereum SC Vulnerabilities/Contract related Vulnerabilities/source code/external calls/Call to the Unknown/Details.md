# External call (Untrusted Call (Call to the Unknown))

## Describe:
 This vulnerability arises when a recipient fallback function is invoked because the called function does not exist or transfers ether to another smart contract. and may cause harm under certain conditions.

## Its danger:
 The DAO Attack, Known risks: Ether stealing/DoS with unexpected revert
 
 ## Solution:
Forcing libraries to be stateless mitigates attacks whereby attackers modify the state of the
library directly to affect the contracts that depend on the library’s code. Therefore, when 
using call, DelegateCall, the call-to-the-unknown attack that may change the state of the
victim contract can be prevented by building stateless libraries.  

## Tools can detect: 
Oyente, Remix, SmartCheck, Gasper, Mythril
