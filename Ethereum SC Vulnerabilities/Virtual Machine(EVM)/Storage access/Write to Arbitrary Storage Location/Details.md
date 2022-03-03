<style>
H1{color:Black !important;}
H2{color:DarkOrange !important;}
p{color:Black !important;}
</style>
# Storage Usage(No restricted write /Misleading Data Location)
**which results in Overlap attack**

## Describe:
 There are three places to store data in Ethereum: 
 stack, memory, and storage. The compiler typically uses the stack, while memory and storage are used to 
 store variables. When the external function calls a contract, the function's variables store temporarily 
 in the memory location which contains two types of data storage locations, calldata, and stack (for 
 storing function parameters and local variables of value type respectively). Storage for permanently 
 storing data that is written on the blockchain and manually read from the blockchain. Stored data in 
 the storage is divided into two categories: value types and reference types that can be used to store 
 complex types. Store variables, including local and 
 state variables, are stored in storage by default, while function parameters are stored in memory, 
 whereas default to storage or memory for the local variables within functions is depending on their 
 type (elementry type are stored in memory and complex types in storage). And they are stored 
 sequentially in storage in Solidity.  Assigning values between locations in storage and memory is 
 crucial to understand: 1)between values in memory and storage creates independent copies of the 
 values, 2)also between values in memory and state variables create independent copies, 3)between 
 storage local and state variables are passed by references, and 4)between values with each other in 
 memory creates a reference. Storing data in the memory is cheaper (in gas-consuming) than storing in 
 storage(due to the permanently storing on the blockchain). Where the local variables in finction 
 may defalut in storage or memory,

## Its danger: 
Real-World Examples: Honey Pots: OpenAddressLottery and CryptoRoulette. It causes key state variables to 
be rewritten accidentally, and as a result, the function of the contract will be affected.  Overlap attack
## Solution:
 It is recommended that when dealing with complex types, you explicitly use the memory or storage 
 keywords to ensure they behave as expected. Which it is mandatory as of Solidity version 0.5.0.
## Tools can detect:
 filtering all Tx interacting to the supervised contract, then on each Tx seeking for SSTORE; if 
 this operation is preformed on an untracked slot, making its corresponding type, else verifying this 
 operation according to conditions: 1)unlocated bytes are written illegally, 2)a slot belonging to a 
 mapping variable is altered, 3)a slot of a non-string variable contain an in-string-format 
 value, 4)a huge value is stored in a slot that represents value of dynamic array.
