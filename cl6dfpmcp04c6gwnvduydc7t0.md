## Web3 js in practical (Part-I)

### Background:

Web3 js is an **Ethereum JavaScript API** that is used to interact with the Ethereum blockchain. It provides multiple methods that allow you to perform actions like sending Ethers from one account to another, creating smart contracts, interacting with smart contracts, and so much more.

This blog consist of 3 parts:

1.  basics of web3 js
2.  interact with a smart contract using web3 js
3.  compile and deploy smart contract using web3 js

In this blog, we’ll discuss **web3 js basics**, so let’s do something practical :)

### Pre-requisite:

Some prior knowledge is required related to:

1.  Advance Javascript (async-await, arrow function)
2.  Node JS (install and import libraries)

Node JS should be installed. To verify, type the command in CMD:

```
node -v
```

### Setup environment:

There are multiple tools and options to create and set up blockchain but here are some easy steps to set up everything quickly:

*   ***Initialize npm***

create a folder, and open it with vs code or your editor. Type command in terminal:

```
npm init -y
```

*   ***Install web3 js library***

```
npm install web3
```

*   ***setup blockchain***

Ganache is a personal Ethereum blockchain that you can use to run tests, execute commands, and monitor transactions.

Download from here: [https://trufflesuite.com/ganache/](https://trufflesuite.com/ganache/)

After installation, open Ganache (quick start):

![ganache](https://cdn.hashnode.com/res/hashnode/image/upload/v1659520586194/owOUqI_pM.png)

### Coding:

create a file “index.js” in the same folder and write some code.

> Import library and initialize provider (ganache network)

```
const Web3 = require('web3');

const web3 =   
new Web3(new Web3.providers.HttpProvider("HTTP://127.0.0.1:7545"));
```

use ganache network (RPC server) address in HttpProvider

> List all ganache accounts:

```
web3.eth.getAccounts((*err*, *accounts*) => {

     console.log("Accounts:", *accounts*);

})
```

> Get the balance of the account:

```
web3.eth.getBalance(web3.eth.accounts\[0\], (*err*, *balance*) => {

     console.log(web3.fromWei(*balance*, 'ether'));

})

```
***web3.eth.accounts\[0\]:*** *It refers to the first account.*

***web3.from Wei:*** *It converts balance from Wei to Ethers.*

> Send ethers from one account to another account

```
web3.eth.sendTransaction(  
    { from: web3.eth.accounts\[0\],   
      to: web3.eth.accounts\[1\],   
      value: web3.toWei('5', 'ether') },   
      (*err*, *transactionHash*) => {

          console.log(*transactionHash*);

})
```

***web3.toWei***: *It converts balance from Ethers to Wei.*

### Code:

%[https://github.com/billypentester/web3/tree/main/Part-I]

### Conclusion:

I discussed some basic and important methods but there are multiple other methods to interact with the blockchain.

**web3 js documentation:** [https://web3js.readthedocs.io/en/v3.0.0-rc.5/](https://web3js.readthedocs.io/en/v3.0.0-rc.5/)

Wait!!! Where’s the smart contract ?!

In web3 js (Part-II), I’ll discuss, how to interact with smart contracts.

