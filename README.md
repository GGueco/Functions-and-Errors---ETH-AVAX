# Functions and Errors Project

## Description

This is a project that shows functions and error-handling techniques in Ethereum smart contracts. 

### Executing program


```javascript
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

contract kantoGeneration{
    address public player;
    string public starterPokemon;

    constructor() {
        player = msg.sender;
    }

    function chooseStarter(uint8 choice) public {
        require(choice >= 1 && choice <= 3, "1 for Charmander, 2 for Bulbasaur, and 3 for Squirtle only.");

        string memory pokemon;

        if (choice == 1) {
            pokemon = "Charmander[Fire Type Starter]";
        } else if (choice == 2) {
            pokemon = "Bulbasaur[Grass Type Starter]";
        } else if (choice == 3) {
            pokemon = "Squirtle[Water Type Starter]";
        } else {
            revert("Don't be too picky, only pick the number of 1-3 Kanto starters."); 
        }
        assert(player != address(0));
        starterPokemon = pokemon;
    }
}


```

