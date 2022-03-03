<style>
H1{color:Black !important;}
H2{color:DarkOrange !important;}
p{color:Black !important;}
</style>
# External call (Untrusted Call (Unchecked call return value) 

**which results in DoS Under External Influence or DoS with unexpected revert**

## Describe:
 external call in solidity may perform in different ways:

  1) a direct call function (externalContract.function()),

   2) send ether which usually using transfer built-in function (has default amount of gas 2300, propagate exception) (address.transfer(amount)),

  3)  or using send built-in function (has default amount of gas 2300, return boolean value) (address.send(amount)), or 
  4) call functions in another contract using call or delegatecall (specify the amount of gas, return boolean value), they also can transfer ether. The return Boolean 
  value indicates whether the call succeeded or not (do not propagate exception) (address.call.value()). Thus, 
  if the caller contract does not check the return value to make sure that the call succeeded, the execution will 
  resume even if the called contract throws an exception. code_a In the function sendTo which send amount of ether 
  to address (x), does not check the return value of send, and suppose that the send will always success by 
  changing the (suc) to true. Using transfer instead of 
  send or using send with checking the return value(e.g.,  require(x.send(amount)) ) , and also it is more secure 
  to let the user to pull the amount using withdraw function instead of push it.
  
## Its danger:
 real world contract suffer from this vulnerabilty: Etherpot and King of the Ether

## Solution:
 If you choose to use low-level call methods, make sure to handle the possibility that the call will fail by checking the return value.

## Tools can detect:
 none

