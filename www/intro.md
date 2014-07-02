# Introduction #

Ripple is a decentralized, peer-to-peer network for moving value using cryptographic technology. For more on the big picture, consult [ripple.com](https://ripple.com/) and check out [our blog](https://ripple.com/blog/). 

# Ripple Client Applications #

The official web client for the Ripple Network is available at [https://ripple.com/client/](). In order to get an account on the network, you will have to find someone to give or sell you some amount of XRP in excess of the reserve requirement. In the future, official downloadable clients will also be available.

# Ripple APIs #

If you intend to act as a gateway, or if you are a developer with great ideas of how to use the Ripple Network, you will probably want to build a custom client application that you or your customers can use to send, receive, or observe funds on the Ripple Network.

Connecting to the Ripple Network generally means communicating with the Ripple Server software, [`rippled`](https://github.com/ripple/rippled) (pronounced "ripple-dee"). To get started, you can try running a few calls to retrieve information from public servers using the [Ripple API Tool](https://ripple.com/tools/api) or you try downloading and running your own instance of `rippled`. 

If you are building your own client, you have several options of interfaces that you can use to interact with the Ripple Network:

| Tool | Summary | Interface | Abstraction Level | Pros | Cons |
|------|---------|-----------------------|-------------------|------|------|
| [gatewayd](https://github.com/ripple/gatewayd) | Skeleton for implementing gateway functionality as a Node.js application | HTTP | Very high | ✓ Most functionality needed to operate a gateway is already implemented | ✗ Only intended for gateways <br> ✗ Requires Node.js |
| [Ripple-REST](?p=ripple-rest-api) | RESTful interface to `rippled` as a Node.js application | HTTP | High | ✓ Simple robust transaction submission <br> ✓ Broad HTTP-client support | ✗ Lacks access to a few features like viewing currency exchange offers <br> ✗ Requires Node.js |
| [ripple-lib](https://github.com/ripple/ripple-lib) | Reference implementation for accessing the WebSocket API | Javascript | Moderate | ✓ Simple robust transaction submission<span class='draft-comment'>(Confirm this)</span> <br> ✓ Good balance of simplicity and power | ✗ Javascript only (Clients for other languages are in progress) |
| [rippled WebSocket API](?p=web-sockets-api) | Powerful, asynchronous API built on the WebSocket protocol | [WebSocket](http://en.wikipedia.org/wiki/Websocket) | Low | ✓ Access to all Ripple functionality <br> ✓ Can be pushed ordered stream data | ✗ Fewer convenient abstractions <br> ✗ WebSocket clients are rare outside of Javascript |
| [rippled JSON-RPC API](?p=web-sockets-api) <!--note: that's not a typo, the websocket and json-rpc docs are on the same page--> | Powerful, synchronous API built on the [JSON-RPC convention](http://json-rpc.org/) | HTTP | Low | ✓ Access to almost all Ripple functionality <br> ✓ Broad HTTP-client support | ✗ Fewer convenient abstractions <br> ✗ Callbacks may arrive out of order <br> ✗ No incremental pathfinding |
