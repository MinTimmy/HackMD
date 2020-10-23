###### tags: `TCP/IP Protocol Suite`

# Chapter 4

## 4.2 Switching
### Circuit Switching
* In circuit switching, the whole message is sent from the source to the destination without being divided into packets.
* 兩端的硬體設備要一樣
* delicated Common Path
* 需要專使線路和資源
* 雖然傳輸速度快，隱私度極高，但成本高，浪費許多網路資源，並不符合經濟效益。
* Example: 過去的電話線，雙方要有相同的電話，同一條線路，才可通話
### Packet Switching 
* In packet switching, the message is first divided into manageable packets at the source before being transmitted. The packets are assembled at the destination.
* rate conversion
* 切成 packet 一個個傳出去
* VoIP: Voice over Internet Protocol (VoIP), also called IP telephony, is a method and group of technologies for the delivery of voice communications and multimedia sessions over Internet Protocol (IP) networks, such as the Internet.
* Two different approaches to route(sends) the packets.
    * Datagram approach
    * Virtual circuit approach


## 4.3  Packet Swithing at Network Layer
The network layer is designed as a packet-switched network. This means that the packet at the source is divided into manageable packets, normally called **datagrams**. 
### Connectionless Service
* 不用建立連線，走不同的路線。
* 資料不按次序抵達目標 router ，所以要由 Level 3 或 Level 4 來重新排列。
* In a connectionless packet-switched network, the forwarding decision is based on the destination address of the packet.

Figure 4.3   A connectionless packet-switched network
![](https://i.imgur.com/xVfx1wi.png)

Figure 4.4   Forwarding process in a connectionless network
![](https://i.imgur.com/bOrv4zK.png)

Figure 4.5   Delay in a connectionless network
![](https://i.imgur.com/kHLSkb1.png)

### Connection-Oriented Service 
* 先建立連線(Virtual circuit)，再完整地傳輸資料，以 PDU 為單位。
* PDU: In telecommunications, a protocol data unit (PDU) is a single unit of information transmitted among peer entities of a computer network. 
* In a connection-oriented packet switched network, the forwarding decision is based on the label of the packet.
* Teardown: 資料傳輸完後，把 Virtual circuit 拆除掉。

Figure 4.6   A connection-oriented packet switched network
![](https://i.imgur.com/7osKgwf.png)

Figure 4.7   Forwarding process in a connection-oriented network
![](https://i.imgur.com/2PgN78f.png)

Figure 4.8  Sending request packet in a virtual-circuit network
![](https://i.imgur.com/wIh3Q7N.png)

Figure 4.9   Setup acknowledgement in a virtual-circuit network
![](https://i.imgur.com/ar8CuRJ.png)

Figure 4.10   Flow of one packet in an established virtual circuit
![](https://i.imgur.com/zbMu7wM.png)

Figure 4.11   Delay in a connection-oriented network
![](https://i.imgur.com/ZwdGkZH.png)


## 4.4  Network Layer Services

Figure 4.12   An imaginary part of the Internet
![](https://i.imgur.com/OlwlS6d.png)

Figure 4.13   Services provided at the source computer
![](https://i.imgur.com/L3kiHN4.png)

Figure 4.14   Processing at each router
![](https://i.imgur.com/gV3jHQ9.png)

Figure 4.15   Processing at the destination computer
![](https://i.imgur.com/NE6T6IJ.png)

