# Overview 

## Installation

    $ npm install @openzeppelin/contracts
    
OpenZeppelin Contracts features a stable API, which means your contracts won’t break unexpectedly when upgrading to a newer minor version.

### Usage

Once installed, you can use the contracts in the library by importing them:

    // contracts/MyNFT.sol
    // SPDX-License-Identifier: MIT
    pragma solidity ^0.8.0;

    import "@openzeppelin/contracts/token/ERC721/ERC721.sol";

    contract MyNFT is ERC721 {
    constructor() ERC721("MyNFT", "MNFT") {
        }
    }
To keep your system secure, you should always use the installed code as-is, and neither copy-paste it from online sources, nor modify it yourself. The library is designed so that only the contracts and functions you use are deployed, so you don’t need to worry about it needlessly increasing gas costs.

## Tokens

Ah, the "token": blockchain’s most powerful and most misunderstood tool.A token is a representation of something in the blockchain. This something can be money, time, services, shares in a company, a virtual pet, anything. By representing things as tokens, we can allow smart contracts to interact with them, exchange them, create or destroy them.

### ERC20

An ERC20 token contract keeps track of fungible tokens: any one token is exactly equal to any other token; no tokens have special rights or behavior associated with them. This makes ERC20 tokens useful for things like a medium of exchange currency, voting rights, staking, and more.

ERC20 is the most widespread token standard for fungible assets, albeit somewhat limited by its simplicity.

### Constructing an ERC20 Token Contract

Using Contracts, we can easily create our own ERC20 token contract, which will be used to track Gold (GLD), an internal currency in a hypothetical game.

Here’s what our GLD token might look like.

    // contracts/GLDToken.sol
    // SPDX-License-Identifier: MIT
    pragma solidity ^0.8.0;

    import "@openzeppelin/contracts/token/ERC20/ERC20.sol";

    contract GLDToken is ERC20 {
    constructor(uint256 initialSupply) ERC20("Gold", "GLD") {
        _mint(msg.sender, initialSupply);
        }
    }

Our contracts are often used via inheritance, and here we’re reusing ERC20 for both the basic standard implementation and the name, symbol, and decimals optional extensions. Additionally, we’re creating an initialSupply of tokens, which will be assigned to the address that deploys the contract.


That’s it! Once deployed, we will be able to query the deployer’s balance:

    > GLDToken.balanceOf(deployerAddress)
    1000000000000000000000

We can also transfer these tokens to other accounts:

    > GLDToken.transfer(otherAddress, 300000000000000000000)
    > GLDToken.balanceOf(otherAddress)
    300000000000000000000
    > GLDToken.balanceOf(deployerAddress)
    700000000000000000000



