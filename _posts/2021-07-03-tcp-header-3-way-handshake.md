---
layout: post
title: "TCP header explained"
keywords: "security,tcp,3way"
---

TCP protocol helps in transfer of messages reliably, from one machine to another over the underlying IP network. The unit of transfer in a TCP protocol is named as TCP segment. Each segment has two parts, one is a TCP header, and the other is user/application data associated with it.

Now let's discuss about TCP header format

__TCP header format__


```
--------------------------------------------------------------
|       source port          |        destination port       |
--------------------------------------------------------------
|                       sequence number                      |
--------------------------------------------------------------
|                   acknowledgement number                   |
--------------------------------------------------------------
| header length | reserved flag | control flag | window size |
--------------------------------------------------------------
|       checksum             |         urgent pointer        |
--------------------------------------------------------------
|                       optional data                        |
--------------------------------------------------------------
|                                                            |
|                       user data field                      |
|                                                            |
--------------------------------------------------------------
```

1. Source port: This is a 16 bit field that specifies the port number of the sender.
2. Destination port: This is a 16 bit field that specifies the port number of the receiver.
3. Sequence number: the sequence number is a 32 bit field that indicates how much data is sent during the TCP session. When we establish a new TCP connection (3 way handshake) then the initial sequence number is a random 32 bit value. The receiver will use this sequence number and sends back an acknowledgment.
4. Acknowledgment number: This 32 bit field is used by the receiver to request the next TCP segment. This value will be the sequence number incremented by 1.
5. Header length: This is the 4 bit data offset field. It indicates the length of the TCP header so that we know where the actual data begins.
6. Reserved flag: These are 3 bits for the reserved field. They are unused and are always set to 0.
7. Flags: There are 9 bits for flags, we also call them control bits. We use them to establish connections, send data and terminate connections:
    * URG: urgent pointer. When this bit is set, the data should be treated as priority over other data.
    * ACK: used for the acknowledgment.
    * PSH: this is the push function. This tells an application that the data should be transmitted immediately and that we don’t want to wait to fill the entire TCP segment.
    * RST: this resets the connection, when you receive this you have to terminate the connection right away. This is only used when there are unrecoverable errors and it’s not a normal way to finish the TCP connection.
    * SYN: we use this for the initial three way handshake and it’s used to set the initial sequence number.
    * FIN: this finish bit is used to end the TCP connection. TCP is full duplex so both parties will have to use the FIN bit to end the connection. This is the normal method how we end an connection.
8. Window size: The 16 bit window field specifies how many bytes the receiver is willing to receive. It is used so the receiver can tell the sender that it would like to receive more data than what it is currently receiving. It does so by specifying the number of bytes beyond the sequence number in the acknowledgment field.
9. Checksum: The checksum is a 16-bit value. Sender TCP computes the checksum and sets it in the header, before sending it to the receiver. On the receiving side, again checksum is computed and matched. If the checksum does not match, means the segment is corrupted and needs to discard. The purpose of checksum is to make ensure that the TCP segment is not altered over the network.
10. Urgent pointer: These 16 bits are used when the URG bit has been set, the urgent pointer is used to indicate where the urgent data ends.
11. Optional data: This field is optional and can be anywhere between 0 and 320 bits.
12. User data field: This the last thing in the TCP header. Actual application data from users e.g HTTP. TCP delivers user data end to end reliably.

---

_This was a short overview of each field associated with a TCP header. For any follow up or queries feel free to contact me on my [mail](mailto:mamgainkunal@gmail.com)._

