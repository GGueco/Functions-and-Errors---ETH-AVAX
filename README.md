# Functions and Errors Project

## Description

This is a project that shows functions and error-handling techniques in Ethereum smart contracts. It allows a user to deposit and withdraw funds from a balance, performs safe addition of numbers, and demonstrates how to use the require, assert, and revert statements for error handling. 

### Executing program


```javascript
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

contract functionsandErrors {
    uint256 public balance;

    function depositCash(uint256 amount) public {
        require(amount > 0, "Amount must be greater than zero");
        balance += amount;
    }

    function withdrawCash(uint256 amount) public {
        require(amount <= balance, "Not enough balance");
        balance -= amount;
    }

    function add(uint256 a, uint256 b) public pure returns (uint256) {
        uint256 result = a + b;
        assert(result >= a);
        return result;
    }

    function revertEx(uint num) public pure {
        if(num<=10){
            revert("Input must be greater than 10");
        }
    }
}


```

