# Transaction Order Dependence
**which results in a race condition**

## Describe:
 Each interaction with the contract fires a transaction, then the miner chooses the transactions to be verified and stored
 in the next block. 
 
 This scenario can be dangerous if the right order of the transactions is manipulated by miners 
 intentionally or deliberately.
  
 That has happened in several cases:
  1) The users invoke the smart contract at the same time 
 and include their transactions in a single block,
  which means multiple updates for the state of the smart contract, and the 
 order of those transactions can affect the new state of the blockchain.
  2) The contract owner changes the reward just when 
 the transaction is submitted to get the benefit. 
 3) The users offer a higher gas price in order to entice the miners to 
 first verify their transaction.
  In this code, the user can win ten ether if he can find the correct string that hashes to the target hash. 
 Transactions take some time before they are mined, and those that are not yet mined are put into the transaction pool.
  The attackers can get the answer from the transaction pool, send a transaction with a higher gas price 
 so that their transaction will be included in a block before the original.

## Its danger:
 ERC20 and Bancor.This creates a problem for contracts that rely on the state of the storage variables. 
 A malicious transaction might be picked first, causing the original transaction to fail (race-condition). 
 GovernMental attack, Run, and Bancor/ERC-20

## Solution:
 Use cryptographic commit-reveal schemes for secrecy and prioritizing transactions with higher gas. 

## Tools can detect:
 Oyente, Securify , Mythril, Zeus, Ethir, and SmartCheck.