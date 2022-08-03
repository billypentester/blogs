## Web3 js in practical (Part-II)

#### API used for communication between frontend and smart contract

#### learn how to interact with smart contracts using web3 js API

### Background:

In web3 js (Part-I), I discussed how to set up the environment, interact with the blockchain, and the basics of web3 js.

here’s the link to web3 js (Part-I):

[**Web3 js in practical (Part-I)**  
*learn basics about web3 js API*billypentester.medium.com](https://billypentester.medium.com/web3-js-in-practical-part-i-39fbbd65738b "https://billypentester.medium.com/web3-js-in-practical-part-i-39fbbd65738b")[](https://billypentester.medium.com/web3-js-in-practical-part-i-39fbbd65738b)

Now, we’ll discuss **how to interact with smart contracts using the web3 js** library.

### Pre-requisite:

Some prior knowledge is required related to:

1.  Advance Javascript (async-await, arrow function)
2.  Node JS (install and import libraries)
3.  Solidity (basics)

### Setup environment:

There are multiple tools and options to create and set up blockchain but here are some easy steps to set up everything quickly:

*   ***Initialize npm***

create a folder, and open it with vs code or your editor. Type command in terminal:

npm init -y

*   ***Install web3 js library***

npm install web3

*   ***Install web3-eth-contract library***

npm install web3-eth-contract

*   ***setup blockchain***

Ganache is a personal Ethereum blockchain that you can use to run tests, execute commands, and monitor transactions.

Download from here: [https://trufflesuite.com/ganache/](https://trufflesuite.com/ganache/)

After installation, open Ganache (quick start):

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1659520603685/LLddL15p4.png)

*   ***deploy smart contract***

Remix IDE helps you to compile and deploy your smart contract. Go to the remix official website: [https://remix.ethereum.org/](https://remix.ethereum.org/)

Write a simple smart contract in solidity editor:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1659520605750/tScPKkd2U.png)

In the environment tab, choose **web3 provider** and paste your ganache network (RPC server) address in the popup box:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1659520607258/tzPGuvxxa.png)

Now, compile the smart contract in the compilation tab and then deploy it. After that you’ve required 2 things:

1.  ABI (Application Binary Interface)
2.  Contract Address (on which contract is deployed)

Copy abi in the compilation tab at the bottom of the sidebar and copy the address of the contract in the deployment tab at the bottom of the sidebar.

### Coding:

create a file “index.js” in the same folder and write some code.

> Import library and initialize provider (ganache network)

const Web3 = require('web3');  
const Contract = require('web3-eth-contract');

const web3 =   
new Web3(new Web3.providers.HttpProvider("HTTP://127.0.0.1:7545"));

Contract.setProvider('HTTP://127.0.0.1:7545');

use ganache network (RPC server) address in HttpProvider

> create contract instance

Copy abi from remix IDE in the compilation tab, create an “abi.json” file, paste the whole abi and import it into the “index.js” file.

Copy contract address from remix IDE in deployment tab, and create an instance of contract.

const abi = require('./abi.json');

const contract =   
new Contract(abi, '0x4e4E06F369FF990183D2c4f4343c71df424ed035')

> interact with contract

**// call variable** 

contract.methods.candidateName()  
.call()  
.then(function(*result*) {

     console.log(*result*);

})  
  

**// call function**

contract.methods.setCandidate("bilal")  
.send({from:web3.eth.accounts\[0\]})  
.then(function(*result*) {

     console.log(*result*);

})

#### here are the complete code files:

[**web3/Part-II · billypentester/web3**  
*follow billypentester and help him to grow community*github.com](https://github.com/billypentester/web3/tree/main/Part-II "https://github.com/billypentester/web3/tree/main/Part-II")[](https://github.com/billypentester/web3/tree/main/Part-II)

### Conclusion:

I discussed how to interact with smart contracts using web3 js. Try some other methods for your practice :)

**web3 js documentation:** [https://web3js.readthedocs.io/en/v3.0.0-rc.5/](https://web3js.readthedocs.io/en/v3.0.0-rc.5/)

Wait!!! It’s too much time taking and a difficult way to open remix IDE and create contracts and compile and deploy.

In web3 js Part-III, I’ll discuss, how to compile and deploy a smart contract using web3 js.

here’s the link to web3 js (Part-III):

[**Web3 js in practical (Part-III)**  
*learn how to compile and deploy contracts using web3 js API*billypentester.medium.com](https://billypentester.medium.com/web3-js-in-practical-part-iii-6ed2080f84b7 "https://billypentester.medium.com/web3-js-in-practical-part-iii-6ed2080f84b7")[](https://billypentester.medium.com/web3-js-in-practical-part-iii-6ed2080f84b7)