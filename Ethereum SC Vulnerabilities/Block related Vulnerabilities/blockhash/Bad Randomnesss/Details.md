# Bad Randomness (Entropy Illusion)

## Describe:
 Due to the nature of the blockchain, it is challenging to create unpredictable content in new blocks using random numbers.
  It will be easy to predict the number that is generated with block information.
   Applications such as gambling and lottery contracts select winners randomly, for which a common practice is to generate a pseudorandom number based on some initial private seed.
    In code_a, a private seed is used in combination with an iteration number and the keccak256 hash function to determine if the caller wins.
     Even though the seed is private, it must have been set via a transaction at some point in time and thus is visible on the blockchain.

## Its danger:
 In the Fomo3D attack, it is real-world smart contracts that are attacked using this vulnerability.
  A malicious attacker can bias the seed of the random number generator in his favour.

## Solution:
 There are several proposals for addressing this problem:using external sources of randomness via oracles,using cryptographic commit-reveal schemes for secrecy.  
## Tools can detect:
 Mythril     
