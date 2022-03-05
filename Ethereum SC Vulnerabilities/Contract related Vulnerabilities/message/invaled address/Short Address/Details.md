# Short address:
 when a function has been called, the function selector
 specifies the first four bytes of the call
 data for a function call and the rest data arranges arguments in chunks
  of 32 bytes, and EVM adds extra zeros automatically to the encoded 
  arguments if it is shorter than expected to make up for 32 bytes.
   However, that can be easily exploited by omitting the very last
    zero from the ether address and adding extra hex zeros to the 
    end of tokens if the function arguments are (address addr, uint tokens) 
which amplifies the number of tokens being sent. 