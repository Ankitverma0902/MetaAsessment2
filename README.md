# MyToken: A Simple ERC20-like Token Implementation on Ethereum

## Description
MyToken is a simple implementation of an ERC20-like token on the Ethereum blockchain. This smart contract includes basic functionalities such as minting new tokens, burning existing tokens, and keeping track of balances. It provides a foundational example for learning about blockchain technology and smart contract development using Solidity.

## Getting Started

### Token Details
- **Token Name**: META
- **Token Abbreviation**: MTA
- **Total Supply**: Variable, initially 0

### Balances Mapping
- Mapping of addresses to their respective token balances.

### Mint Function
- Allows increasing the total supply and the balance of a specified address.

### Burn Function
- Allows decreasing the total supply and the balance of a specified address, with checks to ensure sufficient balance.

## Installing

1. **Search Remix**: Go to [remix.ethereum.org](https://remix.ethereum.org/).
2. **Create a File**: Create a new file in Remix and name it `MyToken.sol`.
3. **Copy the Contract Code**: Copy and paste the following Solidity contract code into the `MyToken.sol` file:

```solidity
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.18;

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

    // Public variables here
    string public tokenName = "META";
    string public tokenAbbrv = "MTA";
    uint public totalSupply = 0;

    // Mapping variable here
    mapping(address => uint) public balances;

    // Mint function
    function mint(address _address, uint _value) public {
        totalSupply += _value;
        balances[_address] += _value;
    }

    // Burn function
    function burn(address _address, uint _value) public {
        require(balances[_address] >= _value, "Insufficient balance to burn");
        totalSupply -= _value;
        balances[_address] -= _value;
    }
}
```

4. **Compile the Contract**:
   - Click on the "Solidity Compiler" tab (looks like an "S" in the left sidebar).
   - Ensure the compiler version is set to 0.8.18.
   - Click the "Compile MyToken.sol" button.

5. **Deploy the Contract**:
   - Click on the "Deploy & Run Transactions" tab (looks like a "rocket" in the left sidebar).
   - Ensure the "Environment" is set to "JavaScript VM (London)" for local testing.
   - Click the "Deploy" button.

6. **Interact with the Contract**:
   - After deploying, your contract will appear under "Deployed Contracts" in the same tab.
   - You can expand it to see the available functions and variables.

## Executing Program

### Open Remix
1. **Create a New File**:
   - On the left panel, under the "File Explorer" tab, click on the "New File" button.
   - Name your file `MyToken.sol`.

2. **Copy the Contract Code**:
   - Copy and paste the provided Solidity contract code into the new file `MyToken.sol`.

3. **Compile the Contract**:
   - Click on the "Solidity Compiler" tab.
   - Ensure the compiler version is set to 0.8.18.
   - Click the "Compile MyToken.sol" button.

4. **Deploy the Contract**:
   - Click on the "Deploy & Run Transactions" tab.
   - Ensure the "Environment" is set to "JavaScript VM (London)" for local testing.
   - Click the "Deploy" button.

5. **Interact with the Contract**:
   - After deploying, your contract will appear under "Deployed Contracts" in the same tab.
   - You can expand it to see the available functions and variables.

6. **Test the Contract**:
   - **Check Initial State**: Click on `tokenName`, `tokenAbbrv`, and `totalSupply` to see their initial values. Click on `balances` and enter your address to see the initial balance (should be 0).

### Mint Tokens
To mint tokens, use the `mint` function:
```solidity
function mint(address _address, uint _value) public {
    totalSupply += _value;
    balances[_address] += _value;
}
```

### Burn Tokens
To burn tokens, use the `burn` function:
```solidity
function burn(address _address, uint _value) public {
    require(balances[_address] >= _value, "Insufficient balance to burn");
    totalSupply -= _value;
    balances[_address] -= _value;
}
```

## Output
Upon deploying and interacting with the MyToken contract, the following outputs can be observed:

- **Deployment**: The contract is deployed with the specified token name and symbol. Initial total supply is zero.
- **Minting Tokens**: Tokens are minted to the specified address, increasing the total supply and updating the recipient's balance.
- **Burning Tokens**: Tokens are burned from the specified address, decreasing the total supply and updating the holder's balance.

## Help
Focus on coding part and syntax so that chances of error are less.

## Authors
- **Ankit Verma** - *Initial work* 

## License
This project is licensed under the MIT License - see the LICENSE.md file for details
