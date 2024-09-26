# Create a Token

This Solidity code defines a basic ERC-20-like token contract named MyToken. Here's a simple overview of its use and purpose:

Token Definition:

The contract defines a token with a name (shru_kshypp) and an abbreviation (SK2005).
It keeps track of the total supply of the token (newTotalValue).
Balance Management:

It uses a mapping to keep track of the balances of different addresses (newBalances).
Minting Tokens:

The nwmint function allows the creation of new tokens. It takes an address and a value as parameters, increases the total supply by the given value, and adds the value to the balance of the specified address.
Burning Tokens:

The newBurn function allows the destruction of tokens. It takes an address and a value as parameters, checks if the address has enough tokens to burn, and if so, decreases the total supply and the balance of the specified address by the given value.
This contract can be used to create and manage a simple cryptocurrency or token on the Ethereum blockchain, allowing for the minting and burning of tokens.

## Description

This project is a Solidity-based smart contract that implements a basic ERC-20-like token named MyToken. The primary purpose of this contract is to facilitate the creation, management, and transfer of a custom cryptocurrency on the Ethereum blockchain. The token is defined with a specific name (shru_kshypp) and abbreviation (SK2005), and it maintains a record of the total supply and individual balances of token holders. The contract includes functionalities for minting new tokens, which increases the total supply and assigns the new tokens to a specified address, and burning tokens, which decreases the total supply by removing tokens from a specified address. This project can be used as a foundational component for decentralized applications (dApps) that require a custom token for transactions, rewards, or other blockchain-based activities. It provides a straightforward and secure way to manage token supply and distribution, ensuring transparency and trust in the token's ecosystem.

## Getting Started

* mapping variable here
  mapping(address => uint) public newBalances;

  The provided Solidity code defines a smart contract named MyToken under the MIT license and compatible with Solidity version 0.8.18. This contract includes three public variables: newTokenName (initialized to "crimeXprime"), newTokenAbbrv (initialized to "SK"), and newTotalValue (initialized to 0), which store the token's name, abbreviation, and total supply, respectively. It also features a mapping newBalances to track the token balances of different addresses.

* mint function
    function nwmint(address _to, uint _value) public {
        newTotalValue += _value;
        newBalances[_to] += _value;
    }
    
    The nwmint function allows the creation of new tokens by increasing the total supply and adding the specified value to the balance of the given address. It takes two parameters: _to (the address to mint tokens to) and _value (the amount of tokens to mint).

* burn function
    function newBurn(address _from, uint _value) public {
        require(newBalances[_from] >= _value);
        newTotalValue -= _value;
        newBalances[_from] -= _value;
    }
    
    The newBurn function enables the destruction of tokens by reducing the total supply and subtracting the specified value from the balance of the given address. It includes a require statement to check if the address has enough tokens to burn. The function takes two parameters: _from (the address to burn tokens from) and _value (the amount of tokens to burn).

### Executing program

* Deploy the contract
* Go to the "Deployed Contracts" section
* Copy the contract address
* Interact with the contract by calling the mint and burn functions with appropriate parameters

