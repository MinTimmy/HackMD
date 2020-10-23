###### tags: `TCP/IP Protocol Suite`

# Chapter 3

## IEEE Standard
IEEE standard for LANs
![](https://i.imgur.com/ysH8Apc.png)

* IEEE Standar has a project, called "Project 802"
* Data link layer = MAC(Media access control) + LLC(Logical link control)
* MAC = Ethernet MAC(802.3), Token ring MAC(802.5), Token bus MAC(802.4)

## Ethernet Frame
Ethernet Frame
![](https://i.imgur.com/5vqyodd.png)

* Destination address & Source address are MAC address
* CRC: error detection information(FEC: forward error correction ).

## Ethernet Length
Maximum and minimum lengths
![](https://i.imgur.com/eDcYtlP.png)

* Minimum length: 64 bytes(512 bits)
* Muximum length: 1518 bytes(12,144 bits)
* padding: if the data is less than 64 bytes, it will padding something into the packet.

## Unicast, multicast and broadcast addresses
Unicast and multicast addresses
![](https://i.imgur.com/GZ1RBxO.png)
* The least significant bit of the first byte define the type of address.
* unicast: the bit is 0
* multicast: the bit is 1
* Broadcast: all bits are 1's.

## Ethernet Evolution
Ethernet evolution through four generations
![](https://i.imgur.com/ZSzAt8T.png)

## Standard Ethernet
Space/time model of a collision in CSMA
![](https://i.imgur.com/0lXIn1d.png)
* carrier sense multiple access with collision detection(CSMA / CD)

Collision of the first bit in CSMA/CD
![](https://i.imgur.com/MxGYCSV.png)

* 為什麼 ethernet 一定有延遲,無法完整同步(real time)
    * 原因：因為 CSMA/CD 的功能，每次都一定要先傳一個訊號判斷中途是否有其他訊號，干擾資料的傳遞，這一來一往，就一定會有延遲的問題。

* 為什麼 Frame size 一定有最小值，如果不足最小值還要用 padding 方式添加不需要的資料。
    * 原因：因為 CSMA/CD 的功能，每次都一定要先傳一個訊號判斷中途是否有其他訊號，如果發現中途有其他訊號，才可即時通知 sender ，如果資料量太少，傳遞速度太快，導致資料都已經到達 receiver ，但警告訊號還沒傳到 sender ，讓傳遞資料不完整。
     
* Example 3.3: In the standard Ethernet, if the maximum propagation time is 25.6 μs, what is the minimum size of the frame?

    * Solution: The frame transmission time is Tfr = 2 × Tp = 51.2 μs. This means, in the worst case, a station needs to transmit for a period of 51.2 μs to detect the collision. The minimum size of the frame is 10 Mbps × 51.2 μs = 512 bits or 64 bytes. This is actually the minimum size of the frame for Standard Ethernet, as we discussed before.


* Transmission rate = bps = 頻寬(Hz)
* Frame time = Frame size / Transmission rate

## Wireless lans
* IEEE has defined the specifications for a wireless LAN, called IEEE 802.11, which covers the physical and data limk layers.

Figure 3.13: Basic service sets(BSSs)
![](https://i.imgur.com/lcCZdEO.png)



Figure 3.14: Extended service sets(ESSs)
![](https://i.imgur.com/zZADYjV.png)

### MAC Sublayer
* CSMA/CA (carrier sense multiple access with collision avoidance)
Figure 3.15: CSMA/CA flow diagram!
[](https://i.imgur.com/YeK0JsW.png)

Figure 3.16: CSMA/CA and NAV
![](https://i.imgur.com/eGb1sxJ.png)

* DIFS: distributed interframe space
* RTS: request to send
* SIFS: short interframe space
* CTS: clear to send
* NAV: no carrier sensing
* ACK: acknowledgment(回函)

## Hidden station problem
Figure 3.19: Hidden station problem
![](https://i.imgur.com/0v9u09h.png)


Figure 3.20: Use of handshaking to prevent hidden station problem
![](https://i.imgur.com/zJF64p4.png)

Figure 3.21: Exposed station problem
![](https://i.imgur.com/4VaMIr8.png)
* B 傳遞 RTS 給 A ， A 項四周傳送 CTS ，如果此時 C 要傳遞資料給 A 就會失敗，即使 AC 之間沒有其他干擾訊號。

Figure 3.22: Use of handshaking in exposed station problem
![](https://i.imgur.com/ou6Oi1o.png)
