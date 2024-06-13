# MyToken

This Solidity program is a basic token contract that demonstrates the fundamental functionalities of a token on the Ethereum blockchain. It includes minting and burning tokens, mapping balances, and maintaining a total supply. This program serves as an introductory example for those who are new to Solidity and want to learn how to create and manage tokens.

## Description

This program is a simple token contract written in Solidity, a programming language used for developing smart contracts on the Ethereum blockchain. The contract includes functionalities for minting new tokens, burning existing tokens, and keeping track of balances and the total supply. This program is designed as an educational tool for understanding the basics of token creation and management in Solidity.

## Getting Started

### Executing Program

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at [Remix Ethereum](https://remix.ethereum.org/).

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a `.sol` extension (e.g., `MyToken.sol`). Copy and paste the following code into the file:

```solidity
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.18;

contract MyToken {

    // Public variables
    string public tokenName = "META";
    string public tokenAbbrv = "MTA";
    uint public totalSupply = 0;
    
    // Mapping variable
    mapping(address => uint) public balances;

    // Mint function
    function mint(address _address, uint _value) public {
        totalSupply += _value;
        balances[_address] += _value;
    }

    // Burn function
    function burn(address _address, uint _value) public {
        if (balances[_address] >= _value) {
            totalSupply -= _value;
            balances[_address] -= _value;
        }
    }
}
```

To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.18" (or another compatible version), and then click on the "Compile MyToken.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "MyToken" contract from the dropdown menu, and then click on the "Deploy" button.

Once the contract is deployed, you can interact with it by calling the `mint` and `burn` functions. Click on the "MyToken" contract in the left-hand sidebar, and then use the functions as needed to mint and burn tokens.

## Authors

Metacrafter Chris  
[@metacraftersio](https://twitter.com/metacraftersio)

## License

This project is licensed under the MIT License - see the LICENSE.md file for details.
