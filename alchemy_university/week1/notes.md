# Notes from Alchemy University ETH Dev Bootcamp Course

## Blockchain Crypto
Blockchain: network of computers agree upon a common state of data with trust. 
Smart Contract: programs stored on a blockchain that run when conditions are met. Program is run without any "direct ownership, making it censorship resistant and transparently verifiable".
ECDSA: crypto algo used as the Digital Signing Algorithm by Bitcoin which uses elliptical-curves. More on this later (Note to self: do a deep dive post about this - https://blog.cloudflare.com/ecdsa-the-digital-signature-algorithm-of-a-better-internet/, https://cryptobook.nakov.com/digital-signatures/ecdsa-sign-verify-messages are good resources)
    - Bitcoin uses secp256k1. 
Consensus Mechanisms: Ways through which multiple nodes in chain come to an agreement for state. Proof of work is used for Bitcoin, Proof of stake is what ETH has transitioned to. 2 rules for Proof of Work:
1. You can't spend twice
2. Longest chain in network is considered the truth
Mining: Considered to be the "work" in Proof of Work. It's the act of adding new valid txns in the chain. A txn is considered valid if miner uses prev block header + new txn and hashes it and the output is below target difficulty. Target difficulty here refers to leading 0's in hash. and so if miner wants to add new block, it has to provide proof of work with 12 leading 0's (which is quite difficut). This also makes it harder for nodes to spam the network because it's very computationally expensive to generate hashes until certain requirements are met. 

### Blockchain Structure
Each block stores:
- index: position of block in the chain
- timestamp: record of when block was created
- previous hash: hash of previous block. Note this is what causes chain integrity because changing data in a previous block causes the hash to change which would result in needing to change all subsequent block hashes which need to be valid (and recall finding a single valid hash is already very expensive).
- data: can store custom data such as money, etc.
- nonce: number used to find valid ahsh
- hash: not stored in blobk but digital fingerprint representing block's contents. 