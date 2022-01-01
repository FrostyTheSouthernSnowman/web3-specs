# Overview of Connection Process

The short term GeoDiVMac connections that facilitate web3 for consumer use should follow the following guidlines. Longer-term nodes on the GeoDiVMac can be implemented in any way. The protocol specified here is for standardazation and compatibility with web browser, mobile apps, and other common consumer platforms.

Connection has up 3 phases.

If no peers are know, then:
- (1) Ask central node for peers
- (2) Connect to new peers
- (3) Get a list of more peers from current ones

If peers are known, then step 1 should be ommited.

## Connecting in Detail

All request are TCP and for step 3, the port will whichever one was specified in step 2.

1: A tcp packet on port 32321 containg the data `what nodes` is sent to a well known host. This host has a list of node IPs separated by white spaces and will return a list of avalible nodes. These nodes should be stored localy to avoid this step in the future.

2: A request is sent to the peers given by the central node. The request contains data `node connect` to which the new peers should respond with `port {port number}` where {port nnumber} is a the port that the GeoDivMac uses for comunication. Finaly, a TCP message is sent on the designated port containing `node ping` to which the node will respond with `node pong` which finishes the connection process.

3: A message containing the data `who peers` is sent to all the device's peers to which they will respond with a list of peer IPs separated by white spaces. These IPs are stored for later use.

