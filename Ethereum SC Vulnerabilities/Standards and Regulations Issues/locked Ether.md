# locked Ether
## Deffernt names:
 (locked money/ether / Freezing Ether/Frozen ether / Greedy Contracts / Ponzi Scheme (Do Not Refund))

## Describe: 
contracts that are unable to release Ether
freezing ether contracts can receive ether and can send ether to other 
addresses via delegatecall. However, they themselves contain no functions to send ether to other address/ This can happen due to the contract having 
a faulty or non existent function for sending Ether. It can also occur due to the contract relying on another contract for its money-spending 
functions and the callee contract having been deleted or not being usable anymore

The contracts programmed for receiving ether should implement a way of withdrawing it, in other words, call a transfer (recommended), send or 
call value at least once

## Its danger: ParitySig attack

## Solution:
 Never outsource critical function to other contracts. Never outsource critical function to other contracts/ Check the address before transferring
The contract receives ether, but there is no way to withdraw it. Implement a withdraw function or reject payments

## Tools can detect:
  SmartCheck/Slither/Securify
