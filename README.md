This is a program in Solidity that provides basic functionalities to mint new tokens and burn existing ones, following the specified requirements.

## Description
This program contains a simple contract with name MyToken, which contains two functions named as burn and mint, and a mapping variable named as balances.The burn functionality basically describes the code for burning or deduction of provided value from balances. 
Similarly, mint function has code which add the inputted value in the already existing balances.

 REQUIREMENTS
    1. Your contract will have public variables that store the details about your coin (Token Name, Token Abbrv., Total Supply)
    2. Your contract will have a mapping of addresses to balances (address => uint)
    3. You will have a mint function that takes two parameters: an address and a value. 
       The function then increases the total supply by that number and increases the balance 
       of the “sender” address by that amount
    4. Your contract will have a burn function, which works the opposite of the mint function, as it will destroy tokens. 
       It will take an address and value just like the mint functions. It will then deduct the value from the total supply 
       and from the balance of the “sender”.
    5. Lastly, your burn function should have conditionals to make sure the balance of "sender" is greater than or equal 
       to the amount that is supposed to be burned.
## Getting Started

### Executing program

To run this program, I have used online Remix Solidity IDE. You can visit the Remix website at https://remix.ethereum.org/ . Extension used for creating a new file is .sol , example: fileName.sol

// SPDX-License-Identifier: MIT
pragma solidity 0.8.18;  

contract MyToken {

    // public variables here
    string public name = "Hakuna"; 
    string public symbol = "HKN"; 
    uint public totalSupply = 0;

    // mapping variable here
    mapping(address => uint) public balances;
    
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

Once the contract is deployed, you can interact with it by calling the tokenName, tokenAbbrv, totalSupply in order to check the Token Name, Abbreviation and total supply of the tokens. 
You can also use the mint function in order to add tokens to an address while burn function to destroy tokens of an address. 
Speaking of addresses, you can use a default address provided by the IDE, to do this look for a label "ACCOUNT" there you can see all the sample account provided by the IDE. 
Now, copy the address by clicking the "Copy account to clipboard" symbol. After copying the desired account you can now paste it on the address field of the balances, burn and mint functions then just put a value you want to mint or burn for that address. 
Lastly, after the fields are now populated you can now click "transact" in order to call the burn and mint functions.

## Authors

Paul Andre Gabriel[201811412@fit.edu.ph]

## License

This project is licensed under the MIT License - see the LICENSE.md file for details
