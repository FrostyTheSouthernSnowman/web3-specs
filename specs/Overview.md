# Specifications for How Clients Can Access Web3
Clients are any machine outside the specific implementation trying to access resources inside the implementation. These include browsers, apps with web3 intergration, dapps, servers, etc. All such communication should be as seamless as possible.

# Guidelines
** Quick tip: implementations should try to provide an interface for client-side javascript like web browsers to accesss implementations

Blockchain implementations should set a node type for quick connections without downloading the blockchain data. These nodes can call smart contracts in a similiar way that one would call an API. These nodes should also get peers so that they aid in sending data across the network. **(OPTIONAL, WOULD BE USEFUL FOR IMPLEMENTATIONS THAT SUPPORT DISTRIBUTED WORKLOADS)** A option could also be set for the duration of the node (5 sec, 10 sec, 30 sec, 1 min, 5 min, etc.) So that the node can be used by the network to run tasks depending on how long it will remain connected.
