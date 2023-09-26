# Simple Token Creation

This Solidity program is a simple "Create a token" program that demonstrates the basic syntax and functionality of the Solidity programming language. This contract is a simple implementation of a custom token called MyToken. It allows minting new tokens, burning existing tokens, and tracking balances of token holders.

## Description

This Solidity code is a simple contract named myToken that provides three functions: createToken, revertToken, and assertToken. It seems to be a basic implementation of a token creation contract, with some validation checks.

Here's a description of each function:

createToken: This function is declared as public pure, which means it doesn't modify the contract's state and doesn't read from storage. It takes an input parameter _balances of type uint (unsigned integer). The function checks if the _balances value is greater than 100 using a require statement. If the condition is not met, it throws an exception with an error message.

revertToken: Similar to createToken, this function is also declared as public pure. It takes an input parameter _balances of type uint. It checks if _balances is less than or equal to 100 using an if statement. If the condition is true, it uses the revert function to revert the transaction with a custom error message.

assertToken: This function is also declared as public pure. It takes an input parameter _balances of type uint. It uses the assert function to check if _balances is equal to 0. If the condition is false, the function will throw an exception.

The contract doesn't have any state variables or additional functionality besides these three functions. It is worth noting that the functions are marked as pure, which means they don't interact with the blockchain or modify any state variables. They are purely for testing and validation purposes.

## Getting Started

### Executing program

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the left-hand sidebar. Save the file with a .sol extension (e.g., myToken.sol). Copy and paste the following code into the file:

```javascript
// SPDX-License-Identifier: MIT
pragma solidity >=0.7.0;

contract myToken {

    function createToken(uint _balances) public pure {
        require(_balances > 100,"To create a token, your balance should be above 100. ");
    }
    
    function revertToken(uint _balances) public pure {
        if(_balances <= 100){
            revert("Your token was not created, due to insufficient balance.");
        }
    }

    function assertToken(uint _balances) public pure {
        assert(_balances==0);
    }
}

```

To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to graater than 0.7.0, and then click on the "Compile myToken.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "myToken" contract from the dropdown menu, and then click on the "Deploy" button.

Once the contract is deployed, you can interact with it by calling the the following functions: createToken function, revertToken function and assertToken. To functionality you have to give balances value.
