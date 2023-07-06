# Solidity-Assessment
The last project to demonstrate code that generates a simple token contract is Solidity. This will give Solidity beginners a quick overview of the processes needed to create, burn, and check the balances of tokens. 

## Description

For creating smart contracts that function on the Ethereum Virtual Machine, the programming language Solidity was created. In order to complete this project, a contract with two variables—public variables for coin information and mapping variables for converting addresses to balances—must be created. Then, two functions are available: the mint function, which increases the overall supply by that amount and increases the balance of the address by that amount, and the burn function, which operates in opposite to the mint function by destroying tokens. To ensure that the balance is more than or equal to the amount that should be burned, burn functions incorporate conditionals.

## Getting Started

### Executing program

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., Crisologo.sol). Copy and paste the following code into the file:
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
    string public tokenName = "AISENCARL";
    string public tokenAbbrv = "AC";
    uint public totalSupply = 0;

    // mapping variable here
   mapping(address => uint) public balances;

    // mint function
   function mint (address _address, uint _value) public {
    totalSupply += _value;
    balances[_address] += _value;
   }
    // burn function
    function burn (address _address, uint _value) public {
      if (balances[_address] >= _value) {    
      totalSupply -= _value;
      balances[_address] -= _value;
        }
    }

    }
Select "Solidity Compiler" from the list of tabs in the left sidebar to compile the code. Click "Crisologo.sol" after that, then "Compile Code" after that, and watch for the green check to show up in the "Solidity Compiler" logo. The contract can then be deployed using the "Deploy & Run Transactions" tab in the left-hand sidebar after the code has been compiled. Click "Deploy" after selecting the "Crisologo.sol" contract from the drop-down menu. You can engage with the contract after it's ready for usage by enlarging the Deployed Contracts section under the address. Your deployed contract can be expanded by simply pressing the arrow button on the left side of it. Now that you have created a contract, you can interact with it. Simply enter the required data to set up the changes, including the address (just copy the account address), the token's value, and the quantity of tokens you want to mint, burn, and then trade. To check it, simply choose "balances".

## Authors

Aisencarl C. Crisologo
