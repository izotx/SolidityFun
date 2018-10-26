# SolidityFun
Exploring different aspects of programming solidity

```
pragma solidity ^0.4.25;

contract Types{
    //Primitive types
    bool myBool = false; //Boolean can be true or false 
    /*
        Operators:
        ! (logical negation)
        && (logical conjunction, “and”)
        || (logical disjunction, “or”)
        == (equality)
        != (inequality
    */
    
    /*
    int / uint: Signed and unsigned integers of various sizes. 
    Keywords uint8 to uint256 in steps of 8 (unsigned of 8 up to 256 bits) 
    and int8 to int256. uint and int are aliases for uint256 and int256, respectively.
    */
    int8 myInt = -128; //Integer from -128 to 127 inclusive
    uint8 myUint = 255; //Usigned Integer from 0 to 255

    
    /*Fixed Point Numbers: Not supported yet.
        fixed / ufixed: Signed and unsigned fixed point number of various sizes. 
        Keywords ufixedMxN and fixedMxN, where M represents the number of bits taken 
        by the type and N represents how many decimal points are available. 
        M must be divisible by 8 and goes from 8 to 256 bits. N must be between 0 and 80, 
        inclusive. ufixed and fixed are aliases for ufixed128x18 and fixed128x18, 
        respectively.
        For example:
        fixed256x70
    */
    
    
    
    string myString; //
    uint8[] myStringArr;
    
    function myFunc(string s) public{
        myString = s;
    }
    
    
    /* Address
       address: Holds a 20 byte value (size of an Ethereum address). 
       Address types also have members and serve as a base for all contracts.
    */

    address myAddress;
    function assignAddress(){
        myAddress = msg.sender; //Address of contract e 
        myAddress.balance; //Balance 
        // myAddress.transfer(10)
    }   
    
    //Arrays
    /*Fixed Size: 
        bytes1, bytes2, bytes3, …, bytes32. byte is an alias for bytes1.
    */
    
    
  //Value Types 
  /*
      Every complex type, i.e. arrays and structs, has an additional annotation,
      the “data location”, about whether it is stored in memory or in storage. 
      Depending on the context, there is always a default, 
      but it can be overridden by appending either storage or memory to the type. 
      The default for function parameters (including return parameters) is memory, 
      the default for local variables is storage and the location 
      is forced to storage for state variables (obviously).

  */
  int[] numbers;
  function arrays(){
    numbers.push(5);
    numbers.length;
  }
  
  /**
   * Debugging 
    Solidity events give an abstraction on top of the EVM’s logging functionality. 
    Applications can subscribe and listen to these events through the RPC interface 
    of an Ethereum client. Events are inheritable members of contracts. When you call them, 
    they cause the arguments to be stored in the transaction’s log - a special data structure 
    in the blockchain.
  */
     event ValueChanged(address _from, int value);
     
     function changeValue(int _value) public{
         emit ValueChanged(msg.sender, _value);
     }
    
}
```
