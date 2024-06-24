MyToken Smart Contract
This Solidity program is a simple token contract that demonstrates basic token management functionalities including minting and burning tokens. The purpose of this contract is to provide a starting point for those who are new to Solidity and want to get a feel for how token contracts work.

Description
MyToken is a contract written in Solidity, a programming language used for developing smart contracts on the Ethereum blockchain. The contract defines a token with a name and abbreviation, and includes functions to mint and burn tokens. This contract serves as a simple and straightforward introduction to Solidity programming and token management, and can be used as a stepping stone for more complex projects in the future.

Getting Started
Executing Program
To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Step-by-Step Instructions
Create a New File:

Go to the Remix website.
Click on the "+" icon in the left-hand sidebar.
Save the file with a .sol extension (e.g., MyToken.sol).
Copy and Paste the Code:

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
    string public tokenName = "Shinixhi";
    string public tokenAbbrv = "Shin";
    uint public totalSupply = 0;

    // mapping variable here
    mapping(address => uint) public balances;

    // mint function
    function mint (address _address, uint _value) public{
        totalSupply += _value; 
        balances[_address] += _value;
    }
    // burn function
    function burn (address _address, uint _value) public{
        if (balances[_address] >= _value){
            totalSupply -= _value; 
            balances[_address] -= _value;
        }
    }

}

Compile the Code:

Click on the "Solidity Compiler" tab in the left-hand sidebar.
Ensure the "Compiler" option is set to "0.8.18" (or another compatible version).
Click on the "Compile MyToken.sol" button.
Deploy the Contract:

Click on the "Deploy & Run Transactions" tab in the left-hand sidebar.
Select the "MyToken" contract from the dropdown menu.
Click on the "Deploy" button.
Interact with the Contract:

Click on the "MyToken" contract in the left-hand sidebar under "Deployed Contracts".
To mint tokens, input the address and value, and then click the "mint" button.
To burn tokens, input the address and value, and then click the "burn" button.
