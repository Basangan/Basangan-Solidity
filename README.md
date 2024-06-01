The goal of this solidity smart contract is to develop, oversee, and utilize the functionalities of a fundamental token system called "Meta(MTA)". It enables the minting of new tokens, their addition, and their burning of withdrawn tokens.
# Getting Started

### Executing the program 
 I use remix: https://remix.ethereum.org/ to create this program.

// SPDX-License-Identifier: MIT
pragma solidity 0.8.25;

- *SPDX-License-Identifier: MI* : Indicates the lincense
- *pragma solidity 0.8.25;* : Specify the Version

As a contract that enables the user to mint and burn tokens, we refer to our variable as "Meta". This contract has functions for mining and burning tokens, as well as public variables and a mapping.


## Public Variables 
contract MyToken {

    // public variables here
    string public tokenName = "Meta";
    string public tokenAbbrv = "MTA";
    uint public totalSupply = 0;
- the public variables represent the tokenName with a value of "Meta", with its abbreviation of "MTA", and lastly, the total supply with a value of 0 

## Mapping Variable 
 // mapping variable here
 mapping(address => uint) public balances;

- A variable that associates Ethereum addresses with their token balances.

# Functions

## Mint Function 

    // mint function
    function mint (address _address, uint _value) public  {
        totalSupply += _value;
        balances[_address] += _value;
}

- This mint function allows the contract owner to mint or add specified amount and assign them to a specific address

## Burn Function 
    // burn function
    function burn (address _address, uint _value) public  {
        if (balances[_address] >= _value)
            totalSupply -= _value;
            balances[_address] -= _value;
    } 

- This burn function allows the contract owner to burn or remove new tokens and assign them from a specific address 

## License
This project is licensed under the MIT License - see the LICENSE.md file for details
