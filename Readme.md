# Solidity Token Contract:

A simple Solidity contract for minting and burning tokens, providing essential functionality for token creation and destruction.

## Description

This repository contains a Solidity contract named "MyToken" which implements a basic token functionality. The contract allows minting and burning of tokens, and provides public access to token-related information such as the token name, abbreviation, and total supply. The contract is written in Solidity version 0.8.10.

## Getting Started

Visit the Remix website at https://remix.ethereum.org/ to access the IDE.

Create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., token.sol).

Copy and paste the provided Solidity code into the file.

```javascript
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.10;

contract MyToken{
    // public variables here
    string public tokenName="ZETO";
    string public tokenAbbrv="ZET";
    uint public totalSupply=0;

    // mapping variable here
    mapping (address=>uint) public balance;

     // mint function
    function mint(address _address,uint value) public {
        totalSupply += value;
        balance[_address] += value;
    }

    // burn function
    function burn(address _address,uint value) public {
        require(balance[_address]>=value,"Value > balance");
        totalSupply -= value;
        balance[_address] -= value;
        
    }
}
```
To compile the code, go to the "Solidity Compiler" tab in the sidebar. Ensure that the "Compiler" option is set to a version 0.8.10 and click the "Compile" button.

Switch to the "Deploy & Run Transactions" tab. Choose the desired Ethereum Virtual Machine (EVM) environment, such as Remix VM (Shanghai).

Deploy the contract by clicking the "Deploy" button. Once deployed, you can interact with the contract using the available functions, such as mint and burn.

View the contract's details, including public variables like tokenName, tokenAbbrv, and totalSupply, by accessing their respective getter functions in the "Deployed Contracts" section.

## Token Contract Details

### License:
This project is licensed under the MIT License. Please see the "https://spdx.org/licenses/" for more details.

### Contract Details:
The contract, named MyToken, is implemented in Solidity version 0.8.10. It includes the following functionality:

### Public Variables:
tokenName:    A public string variable representing the name of the token. In this contract, the token name is set to "ZETO".
tokenAbbrv:   A public string variable representing the abbreviation of the token. Here, the token abbreviation is set to "ZET".
totalSupply:  A public uint variable representing the total supply of the token. The initial value is set to 0.

### Mapping Variable:
balance: A mapping variable that maps addresses to their corresponding token balances. It stores the balance of each address in the contract.

### Mint Function:
The mint function allows the creation of new tokens. It takes two parameters: _address, which represents the address to which the new tokens will be minted, and value, which specifies the amount of tokens to mint. This function increases the total supply of tokens and updates the balance of the specified address accordingly.

### Burn Function:
The burn function allows the destruction of existing tokens. It takes two parameters: _address, which represents the address from which tokens will be burned, and value, which specifies the amount of tokens to burn. This function requires that the balance of the specified address is greater than or equal to the specified value. If the condition is met, it decreases the total supply of tokens and updates the balance of the address accordingly.

## Contributing:
Contributions to this project are welcome. If you encounter any issues or have suggestions for improvements, please feel free to open an issue or submit a pull request.

## Authors:
Ashutosh Mittal
@AashutoshMitta9
