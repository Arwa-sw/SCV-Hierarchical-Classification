# Unsecure upgradeable contract

smart contract is immutable after deployment, but it also can be made 
upgradeable with some limitation (e.g., cannot have a constructor or cannot change the storage layout of the old version).

the vulnerability occurs when the developer is malicious and intentionally write a malicious upgradeable contract. 
or can occur when a contract relies on external contracts for critical 
functions and the external contracts can be dynamically updated
The developers have to ensure that they do not outsource critical 
functions to untrusted external contracts which are built such that their functionality can be dynamically updated.


