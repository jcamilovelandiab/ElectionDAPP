# Building a Simple DAPP

In this document we are going to build a basic election dapp.
We are going to use the following applications:
- Ganache: This app offers a personal ethereum blockchain which we can use to run tests, run commands, and inspect the state of the blockchain.
- Metamask: This is an extension for accessing Ethereum enabled distributed applications.
- Remix: It's an online Ethereum IDE. We are going to use this for testing and deploying our contracts.

# ElectionDAPP

## Election Contract
This is the contract we are going to deploy on the block chain. This is a simple contract, and as we can see it allows us to write our candidate’s name.
```
pragma solidity ^0.4.2;

contract Election {
    string public candidateName;

    constructor () public {
        candidateName = "Candidate 1";
    }

    function setCandidate (string _name) public {
        candidateName = _name;
    }
}
```
We open the Remix IDE, and we activate the active the following plugins in Settings:
- Solidity Compiler
- Deploy & Run transactions.

After the plugins activation, we go the Solidity Compiler tab and select the compiler version ```0.4.25+commit.59dbf8f1```, and then we create the file Election.sol and compile it.

![](https://github.com/jcamilovelandiab/ElectionDAPP/blob/master/images/CompilingElectionContract.PNG)

