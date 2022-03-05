# Under-priced opcodes

## Deffrent Names:

gas costly pattern, Gas overspent,Overcharging 

**which results in insufficient gas**

## Describe:
 Gas is the engine fuel in Ethereum, and it is required to execute each instruction in a smart contract and to verify each fired transaction by interacting with it. The developers need to specify a fee (amount of gas) for each instruction in their code, which incentivizes miners (as rewards = amount of gas * gas costs) to verify and process the transactions on the network. The different instructions in the contract consume different amounts of gas; some cost more and some less, but it should be limited. The developer may cause the running contract to stop if he writes a very costly pattern (e.g., putting costly gasinsrtuctions inside loops, nested calls, or using an array of unbound sizewithin lop) which can grow beyond the block gas limit. This can also be used by attackers to manipulate the instructions and keep them repeated until they run out of gas, at which point the subsequent instructions will be reverted. The function type should take in consideration that public function copies function arguments (Arrays) to memory, while external functions can read directly from calldata which is cheaper than memory allocation. Also, using inappropriate data type which can increase gas consumption.

## Its danger:
 GovernMental, can lead to Denial of Service conditions in smart contracts when the cost of executing a function exceeds the block gas limit.  //  If a contract maintains an array of unbound size, it can lead to a denial-of-service condition where the function that loops across the array’s values may exceed the block gas limit. This means that it is critical that developers do not loop over arrays that are expected to grow over time.

##  Solution:
 Avoid loops with big or unknown number /Use selfdestruct(x) Use “withdraw” pattern Reduce expensive operations / Using external instead of public if the function can only be called by external. / To lower gas consumption, it is recommended to use bytes instead of byte[]/ Using bytes instead of byte[]. / Avoid loops with big or unknown number of steps
 To lower gas consumption, if there are no internal functions call this function and the function parameters contain array, it is rcommended to use external instead of public / bytes is dynamicallysized byte array in Solidity, byte[] is similar with bytes, but bytes cost less gas than byte[] because it is packed tightly in calldata. EVM operates on 32 bytes a time, byte[] always occupy multiples of 32 bytes which means great space is wasted but not for bytes. Therefore, bytes takes less storage and costs less gas.

##  Tools can detect:
  Remix/SmartCheck/Gasper
