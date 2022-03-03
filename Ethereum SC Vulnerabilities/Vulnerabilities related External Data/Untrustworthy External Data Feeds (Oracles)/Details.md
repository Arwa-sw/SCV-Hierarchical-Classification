<style>
H1{color:Black !important;}
H2{color:DarkOrange !important;}
p{color:Black !important;}
</style>
# Untrustworthy External Data Feeds (Oracles) 
**(Lack of Trusted Data Feeds (Oracles)/Lack of trustworthy / Off-chain Safety**

## Describe:
 Oracles are external sources of information (from services outside the blockchain), either from software (Big-data applications) or hardware (Internet-of-Things) that feed smart contracts and serve requests by other contracts to source data from outside the blockchain, such as from websites (e.g., websites). However, these data feeds which are brought to the blockchain also bring risk and it is hard to guarantee the trustworthiness of their sources. Which make it worse that there is a lack of a standard method in handling external 
 data feed.

## Source: 
 Chainlink Data Feeds   
https://ethereum.org/de/developers/docs/oracles/
 ## Its danger: 

## Solution:
 Check the return value of send. Secret contracts (Enigma's secret contracts). Use caution when making external calls Use of “town crier (TC)” tool
## Tools can detect: 
 Town Crier tool, it provides a bridge between HTTPS-enabled data websites and the  Ethereum blockchain.