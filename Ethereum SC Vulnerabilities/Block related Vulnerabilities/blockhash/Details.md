# Blockhash

 ##### **which loads to generate bad randomness if they are used for source of randomness.**
 
## Diffrent Names:

**Number,difficulty and coinbase.**
## Describe:
 As a timestamp,other block information such as blockhash,number,difficulty,and coinbase can control 
 them by miners, which can load them with insecure effects.
  Code_a uses blockhash to generate which member is the winner.However,the gamble is not fair because miners can manipulate this operation.

 ## Its danger:
  It can be misused by miners to manipulate the bloc info to unfairly gain benefits (e.g., by gambling). The Run is a real world smart contract that is attacked using this vulnerability. 

## Solution: 
As for the timestamp, all the block info is not dangerous, but using them with critical operations is. 
Thus, the most useful advice is to be aware of using them in condition checks of critical operations and avoid using them as the random seed. 
The commitment scheme is also helpful in this case.

## Tools can detect:
 **The analysis tools:** Oyente, Remix, SmartCheck, Securify, Mythril, Zeus, and Contractfuzzer can detect this vulnerability by using the variables. 

