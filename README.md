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

contract MyToken {

    // public variables here
    string public tokenName = "Shinixhi";
    string public tokenAbbrv = "Shin";
    uint public totalSupply = 0;

    // mapping variable here
    mapping(address => uint) public balances;

    // mint function
    function mint(address _address, uint _value) public {
        totalSupply += _value;
        balances[_address] += _value;
    }

    // burn function
    function burn(address _address, uint _value) public {
        if (balances[_address] >= _value) {
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
