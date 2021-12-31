# Specifications for How Clients Can Access Web3
Clients are any machine outside the specific implementation trying to access resources inside the implementation. These include browsers, apps with web3 intergration, dapps, servers, etc. All such communication should be as seamless as possible.

# Guidelines
** Quick tip: implementations should try to provide an interface for client-side javascript like web browsers to accesss implementations

Blockchain implementations should set a node type for quick connections without downloading the blockchain data. These nodes can call smart contracts in a similiar way that one would call an API. These nodes should also get peers so that they aid in sending data across the network. **(OPTIONAL, WOULD BE USEFUL FOR IMPLEMENTATIONS THAT SUPPORT DISTRIBUTED WORKLOADS)** A option could also be set for the duration of the node (5 sec, 10 sec, 30 sec, 1 min, 5 min, etc.) So that the node can be used by the network to run tasks depending on how long it will remain connected.


# Overview

The short term GeoDivMac that facilitate web3 for consumer use should follow the following guidlines.

Connection has up 5 phases.

If no peers are know, then:
- (1) Ask central node for peers
- (2) Connect to new peers
- (3) Disconnect from central peers(s)
- (4) Get a list of more peers from current ones
- (5) store that list for future connections

If peers are known, then ommit steps 1 and 3 should be ommited.

## Connecting in Detail

1: A tcp packet on port 32321 containg the data `what nodes` is sent to a well known host. This host has a list of nodes and will return a list of avalible nodes.

2: A TCP connect request on port 32321 is sent to the peers given by the central node. The request contains data `node connect` to which the new peers should respond with `port {port number}` where {port nnumber} is a the port that the GeoDivMac uses for comunication. Finaly, a TCP message is sent on the designated port containing `here I am` to which the node will respond with `all set` which finishes the connection process.
