# Solidity-sec-audit

## Prerequisites
  - Install [Docker](/Docker.md)
  - Pull [devopstestlab/solgraph](https://www.npmjs.com/package/solgraph) : `docker pull devopstestlab/solgraph`.
    
## Create the smart contract in solidity:
```
sudo mkdir data
cd data
sudo vi MyContracts.sol
```
Run this smart contract in the docker image we just pulled:
```docker run -it --rm -v $PWD:/data devopstestlab/solgraph```

View the image using: `xdg-open MyContracts.sol.png`

![image](https://github.com/Shantanu2911/Notes/assets/143939657/75b72907-3b87-4849-8f84-47bb7af6b675)



## Using slither:
```
docker pull trailofbits/eth-security-toolbox
```
Create a new mycontract.sol (Voting Blockchain):
```solidity
contract MyContract {
  uint balance;

  function MyContract() {
    Mint(1000000);
  }

  function Mint(uint amount) internal {
    balance = amount;
  }

  function Withdraw() {
    msg.sender.send(balance);
  }

  function GetBalance() constant returns(uint) {
    return balance;
  }
}
```

Mount the contracts data directory to the container and run it:
```
$ docker run -v $(pwd)/contracts:/contracts/ trailofbits/eth-security-toolbox bash -c "solc /contracts/mycontract.sol"
```
![image](https://github.com/Shantanu2911/Notes/assets/143939657/325b132e-502a-45ab-b400-b2832538fb6c)



Note that one could've directly opened an interactive terminal using `docker run -it -v $(pwd)/contracts:/contracts/ trailofbits/eth-security-toolbox bash`



# Slither

<ins>**Slither is a Solidity static analysis framework for identifying vulnerabilities and bad practices in smart contracts.**</ins>

## Why Slither

- **Security Analysis:** Detect common vulnerabilities like reentrancy bugs and integer overflows.
- **Gas Optimization:** Analyze gas consumption and identify inefficient code patterns.
- **Code Quality Checks:** Identify unused variables and functions for improved code quality.

## Usage

*Setup and usage examples in this repo.*

*install Slither
Begin with installing solc – Solidity compiler:*

```
sudo apt install software-properties-common
```
```
sudo add-apt-repository ppa:ethereum/ethereum
```
```
sudo apt install solc
```

*You should also install the solc-select. It is used for quick installation and switching between Solidity compiler versions.*

Simply run 
```
pip3 install solc-select
```

*After the solc and solc-select are installed with no errors, we can proceed to the Slither installation. It can be done in three ways:*

Using Pip:
``
pip3 install slither-analyzer
``
**check a smart contract using Slither**

*After you defined a contract that you want to check, the easiest way is just to run slither [target]. The target can be specified in several ways:*

**Example: slither SecureContract.sol**

*now put your smart contracts to check the threats and error in in ur smart contract*
*use this smart contrats to checks threats and error also u can use any code which u like to check :-*


```
pragma solidity ^0.4.15;

contract Missing{
    address private owner;

    modifier onlyowner {
        require(msg.sender==owner);
        _;
    }

    // The name of the constructor should be Missing
    // Anyone can call the IamMissing once the contract is deployed
    function IamMissing()
        public 
    {
        owner = msg.sender;
    }

    function withdraw() 
        public 
        onlyowner
    {
       owner.transfer(this.balance);
    }
}
```

*The easiest way to scan the local copy of a smart contract is to run slither with a contract name. Within seconds you will receive the results:*

```
slither mycontract.sol
```
*Now' u will be able to see the whats the threats and error ur smart constract contain (**error  will be in greeen colors**)*

**final interface**

**interface:--**

![image](https://github.com/Rjesh2006/slither_impli/assets/143868643/6cbc9709-4075-4efa-8bd2-056148ba80ea)
