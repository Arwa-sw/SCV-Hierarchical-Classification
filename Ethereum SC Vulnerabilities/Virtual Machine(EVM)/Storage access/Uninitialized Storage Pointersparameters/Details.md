#Storage Usage (Modifying storage array by value )

 Modifying reference type parameters
 
Detect arrays passed to a function that expects reference to a storage array. Bob calls f(). Bob assumes that at the end of the call x[0] is 2, but it is 1. As a result, Bob's usage of the contract is incorrect. Ensure the correct usage of memory and storage in the function parameters. Make all the locations explicit. / Structs/Arrays/Mappings passed as arguments to a function may be by value (memory) or reference (storage) as specified by the data location (optional before solc 0.5.0). Ensure correct usage of memory and storage in function parameters and make all data locations explicit.
contract Memory {
    uint[1] public x; // storage
    function f() public {
        f1(x); // update x
        f2(x); // do not update x
    }
    function f1(uint[1] storage arr) internal { // by reference
        arr[0] = 1;   }
    function f2(uint[1] arr) internal { // by value
        arr[0] = 2;
    } }

