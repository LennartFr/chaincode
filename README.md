<img src="https://farm5.staticflickr.com/4503/37148677233_71edc5a37b_o.png" width="1041" height="53" alt="blueband">

# Chaincode

In a nutshell, Chaincode is a piece of code that is deployed into a network of Hyperledger fabric peer nodes that enables interaction with that network’s sharedbas ledger. In traditional programming the database plays a central role, and to access the database we use the SQL language. In Hyperledger, the Fabric is a distributed dataChaincode can be compared to the SQL language, although it's syntax is completely different.
Chancode, currently written in the Go language is installed and instantiated onto a channel’s peers by an appropriately authorized member. End users then invoke Chaincode through a client-side application that interfaces with a network peer. Chaincode runs network transactions, which if validated, are appended to the shared ledger and modify world state.

All communication can be inside Fabric and stored inside the blockchain, no emails/skype etc are needed, but interfaces (or integration) are need. For example a web page where user can login and make a quote or some other interactions. This web page is not responsibility of Fabric, developer must create the page and using Fabric SDK to start connecting web page (the interface) with Fabrick (back end). Or using the SDK to connect Fanric with some external system (email, CMS,ERP....)

Public and private keys are defining the identity of the user (shipper, carrier, auditor...)

You may think to them as username and password. Public key is like your username (or email address), it is publicly known any everyone can "send you a message", but when you send message you sign this message with your private key. Only your private key can sign your messages. If some other private key is used to sign message from your public key this will not work, or if somehow it works everyone will be able very easy to see that you are not the real person and that this message is fake.

So Public private keys define who you are and from there what you can do in the system, what data you can see, what interactions you can do.

We already build similar product with much more complicated work flow but in general is the same - I have a load then I look for trucks, ask for price, chose best price... 100% of communications and documents (insurance, payments, identity verification, load tracking...) are in Fabric.








Chaincode is a program, written in Go that implements a prescribed interface. Eventually, other programming languages such as Java, will be supported. Chaincode runs in a secured Docker container isolated from the endorsing peer process. Chaincode initializes and manages the ledger state through transactions submitted by applications.
<p>
A chaincode typically handles business logic agreed to by members of the network, so it similar to a “smart contract”. Ledger state created by a chaincode is scoped exclusively to that chaincode and can’t be accessed directly by another chaincode. Given the appropriate permission, a chaincode may invoke another chaincode to access its state within the same network.

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




