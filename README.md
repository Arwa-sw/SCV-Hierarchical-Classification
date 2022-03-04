# **SCV-Hierarchical-Classification**
**Hierarchical classification of security vulnerabilities in smart contracts according to their domain and the distinction between causative vulnerabilities and resulting vulnerabilities.**

In order to avoid the difference in naming of the vulnerabilities, we proposed a hierarchical classification that divides the scope of vulnerabilities into 6 domains: Block, Transaction, Contract, Virtual Machine, External Data Feeds (Oracle), and Standards and Regulations Issues. 

It is possible to add new domains or shorten several domains to a more inclusive domain. 
Figure 2 depicts the proposed classification for all collected vulnerabilities, which is the result of our review. We have reorganized them into 6 domains, then each domain has been branched into several levels. 

The number of levels depends on the depth of the vulnerabilities' causes, which gives a clear picture of the causes and consequences of the vulnerability.

 Besides, our proposed classification links the vulnerability with other relevant vulnerabilities, making it easy to detect and avoid them with a common solution.
Firstly, to have a better understanding of smart contract vulnerabilities, causes, and consequences, we based on the definitions of NSIT (National Institute of Standards and Technology), CVE (The Common Vulnerabilities and Exposures), CWE (common weakness enumeration), and the Wikipedia website to distinguish between them.

 They defined the vulnerability as any weakness or error in the design, implementation, operation, or internal control of smart contracts that attackers could exploit to perform unauthorized actions or cause damage to achieve their goals. 

 It can happen because of unanticipated interactions between different components of smart contract applications (DApps): the smart contract itself, the user of the smart contract, the miner, or the blockchain platform. 

 On the other hand, the cause is the root of the vulnerability that triggers the vulnerability, where the consequence is its impact.

  We highlighted the vulnerability with red, the cause with orange, and the consequence with purple.

**Based on these definitions, we organized the vulnerabilities into the domains as follows:** 

## Block related Vulnerabilities:
The vulnerabilities in this domain are the result of using variables such as timestamp, blockhash, number of blocks, or coinbase as a random seed or as a condition check.

 There are two known vulnerabilities caused by using these variables:

 <ul>
<li>Timestamp Dependence</li>
      
<li>Blockhash</li>
    <ul>
     <li>Bad Randomness (Entropy Illusion)</li>
    </ul>
  </ul>



