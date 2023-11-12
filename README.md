Solidity Challenge


## Description

This Solidity Program Deals with the knowledge on how to program on Solidity and applying all of the following concepts:
Introduction to Data Types
Mapping in Solidity
Functions Demonstration
Conditional Statements

## Getting Started

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/

### Executing program

* Below are the Main Blocks of codes. We have created a functions and its data types inside of the contract Mytoken.

```
pragma solidity 0.8.18; //solidity version

contract MyToken {

    // public variables here
    string public name = "Hakuna"; 
    string public symbol = "HKN"; 
    uint public totalSupply = 0;

    // mapping variable here
    mapping(address => uint) 
    public balances;
    
    // mint function 
    function mint (address _address, uint value) public{ 
        totalSupply += value;
        balances [_address] = value;
    }

    // burn function
    function burn(address _address, uint _value) public{ 
        if(balances[_address] >= _value){
        totalSupply -= _value;
        balances[_address] -= _value;
        }
   }
}
```

## Help

Any advise for common problems or issues.
```
command to run if program contains helper info
```

## Authors

Contributors names and contact info

ex. Dominique Pizzie  
ex. [@DomPizzie](https://twitter.com/dompizzie)


## License

This project is licensed under the [NAME HERE] License - see the LICENSE.md file for details
