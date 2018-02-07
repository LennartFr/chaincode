<img src="https://farm5.staticflickr.com/4503/37148677233_71edc5a37b_o.png" width="1041" height="53" alt="blueband">

# Chaincode

In a nutshell, Chaincode, currently written in the Go Language, is a piece of code that is deployed into a network of Hyperledger fabric peer nodes that enables interaction with that network’s share ledger. In traditional programming the database plays a central role, and to access a database we use the SQL language. In Hyperledger, the Fabric is a distributed database and chaincode is used in a simular way to SQL, although it's syntax is completely different.
<p>
Chancode is installed and instantiated onto a channel’s peers by an appropriately authorized member. End users then invoke Chaincode through a client-side application that interfaces with a network peer. Chaincode runs network transactions, which if validated, are appended to the shared ledger and modify world state.
<p>
A chaincode typically handles business logic agreed to by members of the network, so it similar to a “smart contract”. 
<p>  
Ledger state created by a chaincode is scoped exclusively to that chaincode and can’t be accessed directly by another chaincode. Given the appropriate permission, a chaincode may invoke another chaincode to access its state within the same network.

<img src="https://farm5.staticflickr.com/4523/38243385192_43d682cf94_o.png" width="910" height="483" alt="Hyperledger helloworld 2">
<p>
  

[Develop Chaincode video](https://www.youtube.com/watch?v=5AtAA9ZMAA4)

<p>
  Architecture.
The  validating  peers  run  a  BFT  consensus  protocol  for  executing  a  replicated  state
machine that accepts three types of transactions as operations:

## Deploy transaction:
Takes a chaincode (representing a smart contract) written in Go as a parameter; the
chaincode is installed on the peers and ready to be invoked.

## Invoke transaction:
Invokes a transaction of a particular chaincode that has been installed earlier through
a deploy transaction; the arguments are specific to the type of transaction; the chaincode executes the
transaction, may read and write entries in its state accordingly, and indicates whether it succeeded or
failed.

## Query transaction:
Returns an entry of the state directly from reading the peer’s persistent state; this
may not ensure linearizability.
<p>
Each chaincode may define its own persistent entries in the state.  The blockchain’s hash chain is
computed over the executed transactions and the resulting persistent state.
<p>
Validation of transactions occurs through the replicated execution of the chaincode and given the
fault assumption underlying BFT consensus, i.e., that among then validating peers at most f < n/3
may “lie” and behave arbitrarily, but all others execute the chaincode correctly.  When executed on top
of PBFT consensus,  it is important that chaincode transactions are deterministic,  otherwise the state
of  the  peers  might  diverge.   A  modular  solution  to  filter  out  non-deterministic  transactions  that  are
demonstrably diverging is available and has been implemented in the SIEVE protocol [3].

https://www.zurich.ibm.com/dccl/papers/cachin_dccl.pdf


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

<img src="https://farm5.staticflickr.com/4503/37148677233_71edc5a37b_o.png" width="1041" height="53" alt="blueband">

# Step 2: Putting it all together

### [Putting it All Together ](http://hyperledger-fabric.readthedocs.io/en/release/chaincode4ade.html#pulling-it-all-together)
### [Building Chaincode](http://hyperledger-fabric.readthedocs.io/en/release/chaincode4ade.html#building-chaincode)
### Testing Using dev mode[](http://hyperledger-fabric.readthedocs.io/en/release/chaincode4ade.html#testing-using-dev-mode)
### [Install Hyperledger Fabric Samples](http://hyperledger-fabric.readthedocs.io/en/release/chaincode4ade.html#install-hyperledger-fabric-samples)
### [Download Docker Images](http://hyperledger-fabric.readthedocs.io/en/release/chaincode4ade.html#download-docker-images)
### [Terminal 1 Start the Network](http://hyperledger-fabric.readthedocs.io/en/release/chaincode4ade.html#terminal-1-start-the-network)
### [Terminal 2 - Build & start the chaincode](http://hyperledger-fabric.readthedocs.io/en/release/chaincode4ade.html#terminal-2-build-start-the-chaincode)
### [Terminal 3 - Use the chaincode](http://hyperledger-fabric.readthedocs.io/en/release/chaincode4ade.html#terminal-3-use-the-chaincode)

<img src="https://farm5.staticflickr.com/4503/37148677233_71edc5a37b_o.png" width="1041" height="53" alt="blueband">

# Step 3: testing the Chaincode
### [Testing new Chaincode](http://hyperledger-fabric.readthedocs.io/en/release/chaincode4ade.html#testing-new-chaincode)




