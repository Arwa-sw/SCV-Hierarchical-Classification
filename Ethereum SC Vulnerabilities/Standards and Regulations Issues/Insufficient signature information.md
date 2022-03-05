# Insufficient signature information (Replay attack )

## Defrent name:
Missing Protection against Signature Replay Attacks / Insufficient signature information / Signature Malleability / Lack of Proper Signature Verification / Insufficient signature information / Weak password)

## Describe: 

occurs in a contract that uses a signed message to authorize payments to participants (e.g., a micropayment channel contract) and the signed message can be used by the participants to claim authorization for a second action (replay attack), also can result in replay attacks in the same contract, across multiple contracts, or even across multiple blockchain

## Its danger: ERC-20 signature replay attack

## Solution: 
To avoid it within the same contract or across multiple contracts, the developer has to ensure that the contract’s signed message generation and authentication mechanism is properly implemented,  can be achieved by including the requisite information (e.g., nonce and contract address) in the message. The developer can also rely on trusted standards like the ERC-721 when implanting token functionality to avoid these problems.
Add an incremental nonce, the name of the blockchain and the address of the calling user into the signature. Use the information submitted by the calling user and the shared nonce to construct the hash value (i.e., byte32 h in transferProxy) to verify the signature
•	Store every message hash that has been processed by the smart contract. When new messages are received check against the already existing ones and only proceed with the business logic if it's a new message hash.
•	Include the address of the contract that processes the message. This ensures that the message can only be used in a single contract.
•	Under no circumstances generate the message hash including the signature. The ecrecover function is susceptible to signature malleability
There certainly are many possible ways to prevent such replay attacks, here are some of my ideas:
•	Avoid using transferProxy() completely
•	Make nonce start at a higher count than 0
•	Add chainID, name of the public chain in smart contracts
•	Add address(this) in keccak256()

## Tools can detect:  

