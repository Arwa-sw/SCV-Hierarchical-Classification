The vulnerabilities in this domain result from using variables such as timestamp, blockhash, number of blocks, or coinbase as a random seed or as a condition check. 
There are two known vulnerabilities caused by using these variables: 
(1) timestamp dependence, which leads to a time constraint, 
and (2) blockhash/number/difficulty/coinbase, which loads to generate bad randomness.
