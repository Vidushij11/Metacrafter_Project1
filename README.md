# MyToken

This Solidity program is a simple "MyToken" program that demonstrates the basic syntax and functionality of the Solidity programming language. The purpose of this program is to add and burn tokens from an account.

## Description 

This program is a simple contract written in Solidity, a programming language used for developing smart contracts on the Ethereum blockchain. Inside this contract we have created a simple token, we have given tokenName called "Ginny" and tokenAbbrevation called "Gin" of type string and we have created a variable called tokenSupply initializing it with zero and variable type is uint and all are public you can access them from anywhere. Next we created mapping called accountBalances which will be consist of address(ethereum address) to uint(token value), which means the value of token this address will contain. Then we have created two functions called mintToken and burnToken both are public and takes two parameters called address and val. For minting new token we call mintToken function where we pass two parameter called address and val which we want to add in the given address, initially we will add this val to our tokenSupply and then we will go in this mapping call accountBalances and for the given address we will add this val in that given address account. we will update the account balance of that address, this is how minting will work. Similarly, for burning tokens we call burntoken function where we added some additional functionality like checking, we will check whether the accountBalances of the given address is greater than or equal to the given val, if the condition is true then we will decrement the the val from the tokenSupply and also from that address, this is how burnToken function will work.

## Getting Started

### Executing program

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., Metacrafter.sol). Copy and paste the following code into the file:

```javascript
pragma solidity ^0.8.0;

contract MyToken {

    // public variables here
    string public tokenName="Ginny";
    string public tokenAbbrevation="Gin";
    uint public tokenSupply=0;

    // mapping variable here
    mapping(address=>uint) public accountBalances;

    // mint token function
    function mintToken(uint _val, address _address) public{
        tokenSupply+=_val;
        accountBalances[_address]+=_val;
    }

    // burn tokens function
    function burnToken(uint _val, address _address) public{
        if(accountBalances[_address]>=_val){
            tokenSupply-=_val;
            accountBalances[_address]-=_val;
        }
    }
}

```

To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.0" (or another compatible version), and then click on the "Compile Metacrafter.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "MyToken" contract from the dropdown menu, and then click on the "Deploy" button.

Once the contract is deployed, you can interact with it by calling the mintToken function. Click on the "MyToken" contract in the left-hand sidebar, and then click on the "mintToken" function and enter the val value and address which we have copied from the account in the input box. Finally, click on the "transact" button to execute the function and you can check the account balance by clicking on "accountBalances" button and entering the address of the account whose balance you want to check and click call.

If you want to burn token you can click on the "burnToken" function and enter the amount of token you want to burn and enter the address of the account in the address box. Finally, click on the "transact" button and the tokens will be burned from that account.

## Authors

Vidushi Jaiswal

[@Vidushi](vidushij078@gmail.com)
