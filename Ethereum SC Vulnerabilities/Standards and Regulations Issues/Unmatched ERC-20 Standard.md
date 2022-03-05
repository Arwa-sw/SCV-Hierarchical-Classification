# Unmatched ERC-20 Standard

##  Deffrent name:
  Unmatched ERC20 Contract/interface / Unindexed ERC20 event parameters)

## Describe:
 ERC-20 is a set of rules, which represent a set of functions (in contract), allow developer to create his token on Ethereum blockchain. However, if the developer does not follow these rules strictly, it may lead to errors and failure when transfer the tokens

Sample code: Functions transfer and transfFrom return a Boolean value
contract Token{
    function transfer(address to, uint value) external;
    //...
}
## Its danger:

## Solution:
 Checking that the contract has strictly followed the ERC20 standard.

## Tools can detect: 
 SmartCheck/Slither/Mythril (func)

