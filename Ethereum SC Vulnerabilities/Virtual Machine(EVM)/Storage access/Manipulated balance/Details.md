<style>
H1{color:Black !important;}
H2{color:DarkOrange !important;}
p{color:Black !important;}
</style>
# Manipulated balance
**which results in stealing ether.** 

## (Strict Balance Equality/Equality on the balance / Manipulated balance/Unsecured Balance / stealing ether)

## Describe: 
This vulnerability is also known as the "forcing ether to contract" vulnerability. When the smart 
contract uses the this.balance and address(this).balance methods in the conditional statement, an 
attacker can use this vulnerability to obtain all the money.
when a contract’s balance is left exposed to theft. This can arise due to programmer error: for example, 
in Solidity, a contract’s constructor function is not qualified with a dedicated keyword and giving it a 
name that differs from the contract’s name turns it into a public function

## Its danger:
Rubix

## Solution: 

Since the attackers can only add the amount of the balance, we can use a range to replace “==”. In this 
case, attackers cannot affect the logic of the programs. Using the defect in Listing 1 as an 
example, we can modify the code in L21 to “if (this.balance   10 ether&& this.balance <11 ether)”   
Use nonstrict inequality on balances

## Steps To Reproduce:

Setup a smart contract with a few valid Coinbase wallets and 1 final faulty wallet (always throw 
exception when receiving funds smart contract for example)
Transfer appropriate funds to smart contract.

Execute smart contract adding the set amount of ether to the Coinbase wallets without ever actually leaving 
the smart contract wallet because the complete transaction fails at the last wallet.
Repeat until you have more than enough ethereum in your Coinbase wallet.
Cash out, transfer to off site wallet

## Tools can detect: 
 Zeus / Vandal / Maian