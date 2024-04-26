# Introduction

Hardhat is a development environment to compile, deploy, test, and debug your Ethereum software. It helps developers manage and automate the recurring tasks that are inherent to the process of building smart contracts and dApps, as well as easily introducing more functionality around this workflow.

## Installation

### Pre-requisites

- `Node.js`
    ```bash
    # remove old versions
    $ sudo apt remove nodejs
    # install nodejs
    $ sudo apt install nodejs
    ```
- `npm`
    ```bash
    # remove old versions
    $ sudo apt remove npm
    # install npm
    $ sudo apt install npm
    ```

### Creating a new project
    
- Create a new directory for your project
    ```bash
    $ mkdir my-project
    $ cd my-project
    ```
- Initialize a new npm project
    ```bash
    $ npm init -y
    ```
- Install Hardhat
    ```bash
    $ npm install --save-dev hardhat
    ```
- Initialize Hardhat
    ```bash
    $ npx hardhat
    ```
- Choose `Create an empty hardhat.config.js` and press enter


- Install the Hardhat plugin for ethers.js, we will use recommended plugins here
    ```bash
    $ npm install --save-dev @nomicfoundation/hardhat-toolbox
    ```
- Add the following lines to `hardhat.config.js`
    ```javascript
    require("@nomicfoundation/hardhat-toolbox");
    ```

## Writing and compiling contracts


### Writing contracts

- Create a new contract file in the `contracts/` directory
    ```bash
    $ touch contracts/Token.sol
    ```
- Write your contract in the file you just created.

### Compiling contracts

- Run the following command to compile your contracts
    ```bash
    $ npx hardhat compile
    Compiled 1 Solidity file successfully (evm target: paris).
    ```
    
## Testing contracts

### Writing tests

- Create a new test file in the `test/` directory
    ```bash
    $ touch test/Token.js
    ```
- Write your tests in the file you just created.

### Running tests

- Run the following command to run your tests
    ```bash
    $ npx hardhat test
    ```
