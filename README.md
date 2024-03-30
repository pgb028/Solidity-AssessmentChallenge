## Description

This Solidity Program Deals with the knowledge on how to program on Solidity and applying all of the following concepts:
Introduction to Data Types
Mapping in Solidity
Functions Demonstration
Conditional Statements

The Solidity Challenge ETH PROOF BEGINNER EVM, contains a simple contract with a name of MyToken which contains two functions which are named burn and mint. And it also has a mapping variable named as balances. The burn functionality basically describes the code for burning or deduction of provided value from balances. Similarly, mint function has code which add the inputted value in the already existing balances.

## Getting Started

### Executing program

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. 
Save the file with a .sol extension. Copy and paste the following code into the file:

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

    To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.18" (or another compatible version), and then click on the "Compile myToken.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "myToken.sol" contract from the dropdown menu, and then click on the "Deploy" button.

Once the contract is deployed, you can interact with it by calling the tokenName, tokenAbbrv, totalSupply in order to check the Token Name, Abbreviation and total supply of the tokens. You can also use the mint function in order to add tokens to an address while burn function to destroy tokens of an address. Speaking of addresses, you can use a default address provided by the IDE, to do this look for a label "ACCOUNT" there you can see all the sample account provided by the IDE. Now, copy the address by clicking the "Copy account to clipboard" symbol. After copying the desired account you can now paste it on the address field of the balances, burn and mint functions then just put a value you want to mint or burn for that address. Lastly, after the fields are now populated you can now click "transact" in order to call the burn and mint functions.

## Authors

Contributors names and contact info
Paul Andre A. Gabriel[201811412@fit.edu.ph]

## License

This project is licensed under the MIT License - see the LICENSE.md file for details
