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

## Creating a blockchain network in Ganache.

We can download Ganache in https://www.trufflesuite.com/ganache. We open the app and create a new workspace called "election-dapp".

After creating the project in Ganache, we see that Ganache created 10 wallets. We see also the MNEMONIC word. We can see the wallets activity on MetaMask through this special word that Ganache created for us.

![](https://github.com/jcamilovelandiab/ElectionDAPP/blob/master/images/CreatingWorkspaceInGanache.PNG)

## Connecting Ganache with MetaMask.

We add the Metamask extension to Google Chrome. Next, we enter the Wallet Seed (MNEMONIC word) and create the account password.

![](https://github.com/jcamilovelandiab/ElectionDAPP/blob/master/images/EnteringSeedOnMetaMask.PNG)

Then, we create a new network in MetaMask for Ganache.

![](https://github.com/jcamilovelandiab/ElectionDAPP/blob/master/images/CustomizedRPC.PNG)

![](https://github.com/jcamilovelandiab/ElectionDAPP/blob/master/images/CustomizedRPC2.PNG)

Finally, we could access to the wallet. As we can see, it’s the same wallet with 100ETH that ganache created for us.

![](https://github.com/jcamilovelandiab/ElectionDAPP/blob/master/images/CustomizedRPC3.PNG)

## Deploying the Smart Contract with Remix.

After MetaMask and Remix are linked (They link to each other by themselves), we select the Injection Web3 environment and deploy the election contract.

![](https://github.com/jcamilovelandiab/ElectionDAPP/blob/master/images/DeployingContract.PNG)

MetaMask shows the cost of deploying the contract, and then we confirm the transaction.

![](https://github.com/jcamilovelandiab/ElectionDAPP/blob/master/images/CostOfDeployingContract.PNG)

And, we see the contract was deployed successfully.

![](https://github.com/jcamilovelandiab/ElectionDAPP/blob/master/images/TheContractWasDeployed.PNG)

In ganache we see something the transaction was executed, and it was a contract creation.
![](https://github.com/jcamilovelandiab/ElectionDAPP/blob/master/images/TheContractWasDeployedGanache.PNG)


In Metamask we see that the transaction was executed, and the wallet has less ETH.
![](https://github.com/jcamilovelandiab/ElectionDAPP/blob/master/images/TheContractWasDeployedMetaMask.PNG)

## Linking the website with the blockchain.
