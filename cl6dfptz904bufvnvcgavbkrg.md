## Web3 js in practical (Part-III)

#### API used for communication between frontend and smart contract

#### learn how to compile and deploy contracts using web3 js API

### Background:

In web3 js (Part-II), I discussed how to compile, deploy contracts on remix IDE and interact with smart contracts using web3 js

here’s the link to web3 js (Part-II):

[**Web3 js in practical (Part-II)**  
*learn how to interact with smart contracts using web3 js API*billypentester.medium.com](https://billypentester.medium.com/web3-js-in-practical-part-ii-937b035a8c0c "https://billypentester.medium.com/web3-js-in-practical-part-ii-937b035a8c0c")[](https://billypentester.medium.com/web3-js-in-practical-part-ii-937b035a8c0c)

Now, we’ll discuss about **how to generate abi, bytecode, compile, and deploy smart contracts using the web3 js** library.

### Pre-requisite:

Some prior knowledge is required related to:

1.  Advance Javascript (async-await, arrow function)
2.  Node JS (install, import libraries, FS module)
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

*   ***Install solidity compiler and import file system module***

const solc = require('solc')  
const *fs* = require('fs')

*   ***setup blockchain***

Ganache is a personal Ethereum blockchain that you can use to run tests, execute commands, and monitor transactions.

Download from here: [https://trufflesuite.com/ganache/](https://trufflesuite.com/ganache/)

After installation, open Ganache (quick start):

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1659520594966/JcopYi3Mm.png)

### Coding:

create a file “index.js” in the same folder and write some code.

> Import library and initialize provider (ganache network)

const Web3 = require('web3');  
const Contract = require('web3-eth-contract');  
const solc = require('solc')  
const *fs* = require('fs')

const web3 =   
new Web3(new Web3.providers.HttpProvider("HTTP://127.0.0.1:7545"));

Contract.setProvider('HTTP://127.0.0.1:7545');

use the ganache network (RPC server) address in HttpProvider

> Read smart contract

const fileContent = *fs*.readFileSync('demo.sol', 'utf8').toString();

read the smart contract from the external “demo.sol” file

> Structure and compile contract

var input = {

    language: "Solidity",

    sources: {

          "demo.sol": {

               content: fileContent,

          },

     },

     settings: {

          outputSelection: {

             "\*": {

                "\*": \["\*"\],

                },

           },

     },

};  
  

var output = JSON.parse(solc.compile(JSON.stringify(input)));

> Generate ABI , bytecode and create contract instance

ABI =   
output.contracts\["demo.sol"\]\["Owner"\].abi;

bytecode =   
output.contracts\["demo.sol"\]\["Owner"\].evm.bytecode.object;

const contract = new Contract(ABI);

> Deploy contract

web3.eth.getAccounts((*err*, *accounts*) => {

     defaultAccount = *accounts*\[0\];

     console.log("Default Account:", defaultAccount);

     contract

       .deploy({ data: bytecode })

       .send({ from: defaultAccount, gas: 3000000 })

       .on("receipt", (*receipt*) => {

          console.log("Contract Address:", *receipt*.contractAddress);

        })

       .then((*demoContract*) => {

 *demoContract*.methods.candidateName()

            .call({from:web3.eth.accounts\[0\]})

            .then(function(*result*) {

                console.log("Initial Value:", *result*);

            })

       });

});

#### here are the complete code files:

[**web3/Part-III · billypentester/web3**  
*follow billypentester and help him to grow community*github.com](https://github.com/billypentester/web3/tree/main/Part-III "https://github.com/billypentester/web3/tree/main/Part-III")[](https://github.com/billypentester/web3/tree/main/Part-III)

### Conclusion:

I discussed how to compile and deploy smart contracts using web3 js. There are many other frameworks to deploy smart contracts like **hardhat**, **truffle,** etc.

**web3 js documentation:** [https://web3js.readthedocs.io/en/v3.0.0-rc.5/](https://web3js.readthedocs.io/en/v3.0.0-rc.5/)

Wait!!! It’s too much annoying to write many lines of code just to deploy smart contracts.

Use Hardhat or truffle to test, compile, and deploy smart contracts :)

here’s the link to web3 js (Part-I):

[**Web3 js in practical (Part-I)**  
*learn basics about web3 js API*billypentester.medium.com](https://billypentester.medium.com/web3-js-in-practical-part-i-39fbbd65738b "https://billypentester.medium.com/web3-js-in-practical-part-i-39fbbd65738b")[](https://billypentester.medium.com/web3-js-in-practical-part-i-39fbbd65738b)