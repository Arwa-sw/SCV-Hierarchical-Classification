# Mishandled exceptions

## Deffrent Names:
exception disorders

 **which result in DoS through improper exception handling.**

## Describe:
 There are some cases in Solidity where exceptions occur when an unexpected event happens in the code: 1) call-stack reaches limit of 
 1024, 2)the called logic invokes throw, 3)run out of gas, 4)some methods 
 throw exception or return Boolean value (send, call, delegatecall and callcode). 

In external call, if an exception thrown in the callee contract should be 
propagated to the caller, and the caller must explicitly check the return value from the callee to verify that the call was executed successfully 
and the transaction is reverted entirely. However, in Solidity that does 
not happen always, which allow the attackers to exploit. For example 
function send, which is used to send Ether, do not throw an exception on 
failure, but rather report the status by returning a boolean. If this 
return value is unchecked, the caller continues its execution even if the 
payment failed, which can easily lead to inconsistencies. Besides, if the external function contains many operations that falls out of gas, an 
exception will trigger, which also need to handle and propagate to the caller.

## Its danger: 
King of Ether Throne attack, GovernMental attack, The DAO attack, and Integer Over/Under flow attack. As a result of this vulnerability, it can cause:
 1)Failing to check the return values after a function call
 2)Failure to handle errors
  3)send failed
  4) Send Ethers without checking the conditions
   5)Failing to store and protect data.
## Solution:
 to avoid it
 1)let a caller contract check and address the discrepancy
 2)Handle errors in external calls
 3)Set up a pull payment system to isolate each external call into an independent transaction
  4) use Check Effect Interaction

## Tools can detect:
 Mythril, Oyente , Remix, SmartCheck, Securify, F* Framework, Zeus, Contractfuzzer, Vandal.

