# Exposed functions

## Diffrent Names:
Secrecy failure.

**which results in failure to use cryptography Failure to use cryptography
 (Public access to critical private data/private modifier / Keeping Secrets / Secrecy failure/failure to keep secrets / Exposed functions
 or secrets.**

## Describe:
Due to the public nature of the Ethereum blockchain (transaction data),
everything used in a smart contract is visible to all external
observers, even private state variables and local variables.
Thus, restricting the visibility access does not assure that the 
variables or functions are secret, which permits any attackers to
look at the transactions related to the target contract and 
figure out the state of all variables. 

## Its danger:


## Solution:
 Using cryptographic techniques can help to prevent this vulnerability, such as timed commitments, and defining all visibility modifiers explicitly. 
 Furthermore, developers must understand all aspects of blockchain and account for the Ethereum blockchain's lack of privacy.

## Tools can detect:


