# Unrestricted
## Deffrent Names:

Unprotected self-destruct,Unprotected suicide 

**which results in Destroyable/Suicidal Contracts or Force-Sending Ether by Suicide**

## Describe:
 When a smart contract is no longer needed, we can stop interacting with it by calling the self-destruct function (which invokes the SUICIDE 
 opcode). It does not delete the related information and code from the blockchain, but the users can not interact with it anymore. Self-destruct 
 takes a single argument of type address, and when the owner calls the self-destruct function, all remaining funds at its address are 
 transferred to that address without invoking the fallback function of the recipient. It is also considered a vulnerability as an attacker can 
 exploit it to force the sending of funds to any contract.



## Its danger:
 parity multisig attack / " I accidentally killed it" bug, kill contract account so its associated contract bytecode and storage are deleted forever.

## Solution: 
to mitigate by enforcing advanced authentication (e.g, multifactor 
authentication) to assure that a suicide operation must be approved by multiple parties, and must also ensure that the contracts do not depend on 
third party contracts that might be deleted in the future rendering their own contracts unusable.

## Tools can detect: 
 Remix IDE / Slither / Zeus / Vandal / Maian / Securify / teEther /  Mythril  
