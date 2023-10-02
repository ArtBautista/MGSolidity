# Project: Create a Token

This Solidity program is a simple "Create a Token" program that shows the basic structure and features of the Solidity programming language. This program allows the programmer to get a basic understanding of how things work in Solidity .
## Description

The "Create a Token" program is a simple contract written in Solidity. This Contract mainly has two functions one that could burn a token and the other mints a token, additionally has a variable "Balances" that could check how many tokens does that address holds and lastly the "TotalSupply" variable
allows the user to check how many total supplies of that token.

## Getting Started
### Executing program

To run this program, you can use Remix, an online tool that allows you to develop and test Solidity smart contracts. To start, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., MDGToken.sol). Copy and paste the following code into the file:
```
// SPDX-License-Identifier: MIT
pragma solidity 0.8.18;

/*
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
*/

contract MyToken {

    // public variables here
    string public tokenName = "MaldGate";
    string public tokenAbbrv = "MDG";
    uint public totalSupply = 0;
    // mapping variable here
    mapping(address => uint) public balances;
    // mint function
    function mint(address _address, uint _value)public{
        totalSupply += _value;
        balances[_address] += _value;
    }
    // burn function
    function burn(address _address, uint _value)public{
        if (balances[_address] >= _value){
            totalSupply -= _value;
            balances[_address] -= _value;
        }
    }
}
```
To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.4" (or another compatible version), and then click on the "Compile MDGToken.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "MDGToken" contract from the dropdown menu, and then click on the "Deploy" button.

Once the contract is deployed, you can then now click on the dropdown menu and to mint or add some tokens you'll have to interact with the "mint" function, input in the address of your choice and input how many tokens you want mint in the value section, Now that is done
if you want to see how many supplies are there in the token you can click the "TotalSupply" and it will output the tokens total supply. But if you want to check the individual balance of that address you can interact with the "Balances" mapping variable and put in the address of your choice into it.
Lastly, to burn or deduct some tokens you can click on the dropdown menu beside the "burn" text and input in the address of your choice and input how many tokens you want burn in the value section. Take note that if you want to burn more than or equal of the Total Supply it will execute the code but will not pull through in burning all the token in the supply.


## Authors

Art Bautista
[Art Bautista's Email](202010553@fit.edu.ph)


## License

This project is licensed under the MIT License - see the LICENSE.md file for details
