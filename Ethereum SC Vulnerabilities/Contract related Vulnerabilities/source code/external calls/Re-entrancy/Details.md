<style>
H1{color:Black !important;}
H2{color:DarkOrange !important;}
p{color:Black !important;}
</style>

# External call (Reentrancy) 

## Describe: 
It is the most famous one and the most dangerous. It occurs when an external call falls in recursively calling, which allows the attacker to 
get multiple funds (till drain the funds or the transaction runs out of gas) without reflecting the change in the state of the caller's 
contract. It can happen within a single function or across external functions or contracts. In code_a, the attacker can execute the withdraw 
multi times  till the call step (msg.sender.send(fundsToBeMoved);)  without update the state of the contract (balances[msg.sender] = 0;  ).


**Sorce:** DAO.sol, https://github.com/blockchainsllc/DAO/blob/develop/DAO.sol
## Its danger: 
it was responsible of the DAO attack and SpankChain Attack the attacker could steal $150M, and caused to split Ethereum Blockchain into two chain by a hard fork.

## Solution: 
it can avoid it by follow the Check-effect-interact pattern, or mutex pattern. It also recommended to use the built-in transfer() function when sending ether to external contracts.

## Tools can detect:
 most of the analysis tools can detect this vuknerability Slither, Remix IDE, SmartCheck, F* Framework, Mythril, Oyente, Securify, Zeus, ContractFuzzer, Vandal, Ethir, and ReGuard
