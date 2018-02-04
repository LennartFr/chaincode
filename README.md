# Chaincode
<p>
Chaincode is a program, written in Go that implements a prescribed interface. Eventually, other programming languages such as Java, will be supported. Chaincode runs in a secured Docker container isolated from the endorsing peer process. Chaincode initializes and manages the ledger state through transactions submitted by applications.
<p>
A chaincode typically handles business logic agreed to by members of the network, so it similar to a “smart contract”. Ledger state created by a chaincode is scoped exclusively to that chaincode and can’t be accessed directly by another chaincode. Given the appropriate permission, a chaincode may invoke another chaincode to access its state within the same network.

## Step 1 [Learn Chaincode](https://github.com/IBM-Blockchain-Archive/learn-chaincode)
## [What is Chaincode?](http://hyperledger-fabric.readthedocs.io/en/release/chaincode4ade.html#what-is-chaincode)
## [Hyperledger Fabric Samples](http://hyperledger-fabric.readthedocs.io/en/release/samples.html)

~~~
Edit ~/.bash_profile 

export GOPATH=/Users/username/go 
export PATH=$GOPATH/bin:$PATH

Reload profile : source ~/.bash_profile
~~~

### [Chaincode API](http://hyperledger-fabric.readthedocs.io/en/release/chaincode4ade.html#chaincode-api)
### [Simple Asset Chaincode](http://hyperledger-fabric.readthedocs.io/en/release/chaincode4ade.html#simple-asset-chaincode)
### [Choosing a Location for the Code](http://hyperledger-fabric.readthedocs.io/en/release/chaincode4ade.html#simple-asset-chaincode)
### [Housekeeping](http://hyperledger-fabric.readthedocs.io/en/release/chaincode4ade.html#housekeeping)
### [Initializing the Chaincode](http://hyperledger-fabric.readthedocs.io/en/release/chaincode4ade.html#initializing-the-chaincode)
### [Invoking the Chaincode](http://hyperledger-fabric.readthedocs.io/en/release/chaincode4ade.html#invoking-the-chaincode)
### [Implementing the Chaincode Application](http://hyperledger-fabric.readthedocs.io/en/release/chaincode4ade.html#implementing-the-chaincode-application)

# Step 2: Putting it all together

### [Putting it All Together ](http://hyperledger-fabric.readthedocs.io/en/release/chaincode4ade.html#pulling-it-all-together)
### [Building Chaincode](http://hyperledger-fabric.readthedocs.io/en/release/chaincode4ade.html#building-chaincode)
### Testing Using dev mode[](http://hyperledger-fabric.readthedocs.io/en/release/chaincode4ade.html#testing-using-dev-mode)
### [Install Hyperledger Fabric Samples](http://hyperledger-fabric.readthedocs.io/en/release/chaincode4ade.html#install-hyperledger-fabric-samples)
### [Download Docker Images](http://hyperledger-fabric.readthedocs.io/en/release/chaincode4ade.html#download-docker-images)
### [Terminal 1 Start the Network](http://hyperledger-fabric.readthedocs.io/en/release/chaincode4ade.html#terminal-1-start-the-network)
### [Terminal 2 - Build & start the chaincode](http://hyperledger-fabric.readthedocs.io/en/release/chaincode4ade.html#terminal-2-build-start-the-chaincode)
### [Terminal 3 - Use the chaincode](http://hyperledger-fabric.readthedocs.io/en/release/chaincode4ade.html#terminal-3-use-the-chaincode)

# Step 3: testing the Chaincode
### [Testing new Chaincode](http://hyperledger-fabric.readthedocs.io/en/release/chaincode4ade.html#testing-new-chaincode)




