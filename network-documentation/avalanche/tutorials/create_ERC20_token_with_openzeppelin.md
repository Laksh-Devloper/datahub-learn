# Overview 

## Installation 🔰

Firstly we have to install open zeppelin(Contracts). Execute this command for installation.

    $ npm install @openzeppelin/contracts
If you are upgrading openzeppelin in future , it will not affect the contracts because 
OpenZeppelin Contracts features a stable API, which means your contracts won’t break unexpectedly when upgrading to a newer minor version.

### Usage 💻

Once installed, you can use the contracts in the library by importing them:
Import by this code below 

    // contracts/MyNFT.sol
    // SPDX-License-Identifier: MIT
    pragma solidity ^0.8.0;

    import "@openzeppelin/contracts/token/ERC721/ERC721.sol";

    contract MyNFT is ERC721 {
    constructor() ERC721("MyNFT", "MNFT") {
        }
    }
To keep your system secure, you should always use the installed code as-it-is, and neither copy-paste it from online sources, nor modify it yourself.
The library is designed so that only the contracts and functions you use are deployed, so you don’t need to worry about it needlessly increasing gas costs.
In simple words don't blindly copy paste the code from  any third party site because it may affect your financial balance. 
Be safe 

## Tokens ⬇️

Ah, the "token": blockchain’s most powerful and most misunderstood tool.
A token is a representation of something in the blockchain. This is something that we call money, time, services, shares in a company, a virtual pet, anything. 
By representing things as tokens, we can allow smart contracts to interact with them, exchange them, create or destroy them.
Beginners just undderstand  tokens in form of money or services.

### Creating ERC20 Token ☣️

ERC20 token is the most convient token, but remmember all tokens are equal no price difference or speciality is there.
An ERC20 token contract keeps track of fungible tokens: any one token is exactly equal to any other token; no tokens have special rights or behavior associated with them. 
This makes ERC20 tokens useful for things like a medium of exchange currency, voting rights, staking, and more.

ERC20 is the most widespread token standard for fungible assets, albeit somewhat limited by its simplicity and used widely and is trusted wisely. 

### Constructing an ERC20 Token Contract 🎊

Now you will be wondering what is contract ? Don't worry we are here to help you.
Contracts helps you minimize risk by using battle-tested libraries of smart contracts for Ethereum and other blockchains. 
It includes the most used implementations of ERC standards. Using Contracts, we can easily create our own ERC20 token contract, which will be used to track Gold (GLD), an internal currency in a hypothetical game.

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

Our contracts are often used via inheritance, and here we’re reusing ERC20 for both thebasic standard implementation and the name, symbol, and decimals optional extensions. 
Additionally, we’re creating an initialSupply of tokens, which will be assigned to the address that deploys the contract.


Congrats 🥳 That’s it! 

Once deployed, we will be able to query(find out) the deployer’s balance:

    > GLDToken.balanceOf(deployerAddress)
    1000000000000000000000
We can also transfer these tokens to other accounts:

    > GLDToken.transfer(otherAddress, 300000000000000000000)
    > GLDToken.balanceOf(otherAddress)
    300000000000000000000
    > GLDToken.balanceOf(deployerAddress)
    700000000000000000000


### Advantages of using open zeppelin 🌈

## The standard for secure blockchain applications

OpenZeppelin provides security products to build, automate, and operate decentralized applications. 

OpenZeppelin also protect leading organizations by performing security audits on their systems and products. 

OpenZeppelin is Focused on security using top level standard contracts security patterns and best practices. 

OpenZeppelin has modular approach which uses simple, robust code. Easy collaboration and auditing. 

OpenZeppelin is open source which means Community-driven and is used by the biggest players in the industry.

Thank you for reading 
Have a great day 🥰
