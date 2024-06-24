# MyToken Smart Contract

## Overview

MyToken is a basic Ethereum token implemented using Solidity. The contract provides functionalities for minting and burning tokens while keeping track of each address's token balance.

## Description

MyToken is a simple smart contract designed to demonstrate the basic principles of token creation, management, and destruction on the Ethereum blockchain. The contract includes features to mint new tokens, thereby increasing the total supply, and burn existing tokens, thereby decreasing the total supply. It maintains a mapping of each address to its corresponding token balance, ensuring accurate tracking of token distribution.

## Getting Started

### Executing Program

To run this program, you can use Remix, an online Solidity IDE. Follow these steps to interact with the contract:

1. **Go to Remix**:
   Open your web browser and go to [Remix](https://remix.ethereum.org/).

2. **Create a New File**:
   - Click on the "+" icon in the left-hand sidebar.
   - Save the file with a `.sol` extension (e.g., `MyToken.sol`).

3. **Copy and Paste the Code**:
   ```solidity
   // SPDX-License-Identifier: MIT
   pragma solidity 0.8.18;

   contract MyToken {

       // Public variables
       string public tokenName = "Shinixhi";
       string public tokenAbbrv = "Shin";
       uint public totalSupply = 0;

       // Mapping to store balances
       mapping(address => uint) public balances;

       // Mint function to create new tokens
       function mint(address _address, uint _value) public {
           totalSupply += _value;
           balances[_address] += _value;
       }

       // Burn function to destroy tokens
       function burn(address _address, uint _value) public {
           require(balances[_address] >= _value, "Insufficient balance to burn");
           totalSupply -= _value;
           balances[_address] -= _value;
       }
   }
   Compile the Code:

4. **Click on the "Solidity Compiler" tab in the left-hand sidebar.**
Ensure the compiler version is compatible with pragma solidity 0.8.18.
Click "Compile MyToken.sol".
Deploy the Contract:

5. **Click on the "Deploy & Run Transactions" tab in the left-hand sidebar.**
Select "MyToken" from the dropdown menu.
Click "Deploy".

6. **Interact with the Contract:**

Mint Tokens:

In the "Deployed Contracts" section, find the mint function.
Enter the address (e.g., 0xYourAddress) and the value (e.g., 100).
Click "transact" to call the mint function.
Check Balances:

In the "Deployed Contracts" section, find the balances mapping.
Enter the address you minted tokens to (e.g., 0xYourAddress).
Click "call" to check the balance.
Burn Tokens:

In the "Deployed Contracts" section, find the burn function.
Enter the address and the value you want to burn (e.g., 50).
Click "transact" to call the burn function.
Check Balances Again:

Repeat the balance check to ensure tokens were burned.
**Help
For common issues, ensure:**

You have correctly deployed the contract.
You are entering the correct parameters for minting and burning tokens.
Transactions are confirmed in Remix (look for the green checkmark or success message).

## Authors
Emerson D. Muli II - eidmuli@mymail.mapua.edu.ph

## License
This project is licensed under the MIT License - see the LICENSE file for details.
