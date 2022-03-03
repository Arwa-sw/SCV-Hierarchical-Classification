<style>
H1{color:Black !important;}
H2{color:DarkOrange !important;}
p{color:Black !important;}
</style>
# Blockhash/number/difficulty/coinbase
**which loads to generate bad randomness if they are used for source of randomness.**
  ## Describe:
 As a timestamp, other block information such as blockhash, 
 number, difficulty, and coinbase can control them by miners, which can 
 load them with insecure effects. Code_a uses blockhash to generate 
 which member is the winner. However, the gamble is not fair because miners 
can manipulate this operation.
  
**source:** https://immunebytes.com/time-dependency-in-smart-contracts/
## Its danger:
 It can be misused by miners to 
 manipulate the bloc info to unfairly gain benefits (e.g., by gambling). 
 The Run is a real world smart contract that is attacked using this 
 vulnerability.
## Solution:
 TAs for the timestamp, all the block info is not dangerous, but using them 
 with critical operations is. Thus, the most useful advice is to be aware 
 of using them in condition checks of critical operations and avoid using 
 them as the random seed. The commitment scheme is also helpful in this case.
## Tools can detect it:
The analysis tools: Oyente, Remix, 
SmartCheck, Securify, Mythril, Zeus, and Contractfuzzer can detect this 
vulnerability by using the variables
# Bad Randomness (Entropy Illusion)
## Describe:
 Due to the nature of the blockchain 
 it is challenging to create 

 unpredictable content in new blocks 
 using random numbers. It will be easy 

 to predict the number that is 
 generated with block information. 

 Applications such as gambling and 
 lottery contracts select winners 

 randomly, for which a common practice is to generate a pseudorandom number 

 based on some initial private seed. In code_a, a private seed is used in 
 
 combination with an iteration number and the keccak256 hash function to 
 
 determine if the caller wins. Even though the seed is private, it must  
 have been set via a transaction at 
 some point in time and thus is visible on the blockchain.

**source:** old_blockhash.sol
https://swcregistry.io/docs/SWC-120

## Its danger:
 In the Fomo3D attack, it is 
 real-world smart contracts that are attacked using this vulnerability. A 
 malicious attacker can bias the seed of the random number generator in his favour.
## Solution:
 There are several proposals for addressing this problem: using external sources of randomness via oracles, using cryptographic commit-reveal schemes for secrecy.  
## Tools can detect: 
Mythril     