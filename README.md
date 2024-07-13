// public variables here
    string public newTokenName = "shru_kshypp";
    string public newTokenAbbrv = "SK2005";
    uint public newTotalValue = 0;

    // mapping variable here
    mapping(address => uint) public newBalances;


    The provided Solidity code defines a smart contract named MyToken under the MIT license and compatible with Solidity version 0.8.18. This contract includes three public variables: newTokenName (initialized to "crimeXprime"), newTokenAbbrv (initialized to "SK"), and newTotalValue (initialized to 0), which store the token's name, abbreviation, and total supply, respectively. It also features a mapping newBalances to track the token balances of different addresses.

    
    // mint function
    function nwmint(address _address, uint _value) public{
        newTotalValue += _value;
        newBalances[_address] += _value;
    }


    The nwmint function in the MyToken Solidity contract is designed to increase the total supply of the token and update the balance of a specified address. The function takes two parameters: an address (_address) and a value (_value). When nwmint is called, it performs two main actions: first, it adds the specified _value to the newTotalValue variable, which represents the total supply of the token. This effectively increases the overall token supply by the given amount. Second, it increases the balance of the specified _address in the newBalances mapping by the same _value. This means the address provided as a parameter will have its token balance increased by the specified amount. By updating both the total supply and the individual balance, the nwmint function ensures that the creation of new tokens is accurately reflected in the contract's state, allowing for controlled token issuance and balance management.


    // burn function
    function newBurn (address _address, uint _value) public{
        if(newBalances[_address] >= _value){
            newTotalValue -= _value;
            newBalances[_address] -= _value;
        }
    }


    The newBurn function in the MyToken Solidity contract is designed to reduce the total supply of the token and decrease the balance of a specified address, effectively destroying tokens. This function takes two parameters: an address (_address) and a value (_value). When newBurn is called, it first checks if the balance of the specified _address in the newBalances mapping is greater than or equal to the _value to be burned. This conditional check ensures that the address has enough tokens to be burned, preventing negative balances. If the condition is met, the function proceeds to decrease the newTotalValue variable by the _value, reducing the overall token supply. Simultaneously, it deducts the same _value from the balance of the specified _address in the newBalances mapping. By performing these actions, the newBurn function effectively reduces the total number of tokens in circulation and updates the individual balance of the address, maintaining the integrity of the token supply and preventing overdrawing from any address.
