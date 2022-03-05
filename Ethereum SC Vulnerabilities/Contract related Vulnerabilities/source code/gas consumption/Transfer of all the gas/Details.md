# transfer of all the gas

## Describe: 
send and transfer are built in functions, however send is low level 
counterpart of transfer. Send return false when the execution fails 
(payment operation), but transfer throws an exception x.transfer(y) is equivalent to require(x.send(y)).
add.call.value() specify gas, return Boolean, but does not propagate exception  
add.send() has default amount gas 2300, use with fallback() or send ether to payable
add.transfer() has default amount of gas 2300, propagate exception

 ## Its danger:


## Solution: 
Check the return value of send and use transfer

## Tools can detect: 
smartCheck,detect send or transfer which not in if statement