# Erroneous Visibility (Function Default Visibility )

## Diffrent Names:
**Erroneous Visibility (State Variable Default Visibility)
,Erroneous Visibility (Implicit visibility level )(Access Control)

## Describe:
 Visibility modifiers define whether you can access state variables and functions in four modifiers: external (only for functions, it means that
  they can be called from other contracts and transactions, but can not be called within the same contract) public (the default accessibility of 
  functions in solc < 0.5.0, access from the outside and inside the contract), internal (the default accessibility of state variables, 
  access from within the same contract and in deriving contracts), or private (only visible and accessible in the same contract). It is 
  important to restrict the access visibility of the functions and state variables in smart contracts, and also to know the default access. 
  It can be a very serious vulnerability if the developer misses them 
  unintentionally, which allows any malicious user to make unauthorized or 
  unintended state changes.

## Its danger: 
Parity multisignature wallet attack, by access the state variable, the attacker can own the wallet and steal the Ether.

## Solution:
 While new versions of Solidity will now hint and show warnings during compilation for functions that have no explicit visibility set, the 
 explicitly declared visibility access of functions and state variables
  can also help to prevent this vulnerability. Also, using linters such as 
  solhint can help to warn the developer of any implicit visibility. 

## Tools can detect: 
 Remix /  Securify  / Mythril / SmartCheck
