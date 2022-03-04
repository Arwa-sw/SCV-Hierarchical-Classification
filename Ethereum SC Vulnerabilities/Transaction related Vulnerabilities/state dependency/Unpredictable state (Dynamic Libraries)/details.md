# Transaction Info Dependency 

## Deffreint Names:
**Unpredictable state and dynamic libraries.**

## Describe:

 It may occur in two cases:
  1) Because of dynamic library linking during runtime, which is a type of contract that cannot have mutable fields. 
  They can change the state of the contract that would call them even without knowing that they have changed.
   2) When the transactions have changed the contract state (by sending ether, which updates the contract's balance, or 
   changing data in the contract, which changes the storage root).
    Even if the user was fast enough to be the first to send a transaction, it is not guaranteed that such a transaction would be the first to be run. 
    Indeed, when miners group transactions into blocks, they are not required to preserve any order. 

## Its danger: 
GovernMental, Dynamic Libraries.

## Solution: 


## Tools can detect:
