# Computer networking

- what is a socket?
- how is the host identified? how is the socket in the host identified?
- There are four different dimensions that a transport protocol can provide:
    - Data realiability
    - Security
    - Throughput
    - Timing

## Transport layer protocols: TCP or UDP

TODO when to use each?

### TCP

- Connection-oriented: handshake and duplex connection.
- Reliable data transfer: when one application passes a stream of bytes into a 
  socket, it can count on TCP to deliver that same stream of bytest to the receiving 
  socket.
- Congestion control mechanism: ensures data is transmitted efficiently without 
  overwhelming the network.

### UDP

- Connectionless: no handshake
- Unrealiable data transfer: it does not guarantee that the data will arrive at 
  the end and in case it arrive it can be out of order.
- Does not have congestion control

## Application layer protocols

#### HTTP 

- What does it mean that it is a stateless protocol.
- Persistent and non-persistent TODO
- Message parts
