

* Every packet has [source IP, destination IP]



# OSI

* pdu : protocol data unit.
* Top --> down

| Layer              | pdu                                                   | What it do                                                          |
| ------------------ | ----------------------------------------------------- | ------------------------------------------------------------------- |
| Physical           | Bits                                                  | Sends raw bits                                                      |
| DLL (Mac address)  | Frame [Mac addr, IP packet, trailer]                  | Ensure node-to-node delivery of data within the same local network. |
| Network            | Packet [IP header, TCP segment]                       | sending data between networks                                       |
| Transport layer    | segments (TCP), Datagram (UDP) <br>[TCP header, Data] | End to end communication between apps                               |
| Session layer      | Data (open and close a converstioan)                  | Manages connections between two computers                           |
| presentation layer | Data (Encryption, decryption, compression)            | Handles data format and security                                    |
| application        | Data, HTTP, HTTPS, ssh, DNS, FTP                      | Closes layer to the user where applications communicate             |



# TCP/IP

* From bottom to top.

| Layer          | OSI                                |
| -------------- | ---------------------------------- |
| Network access | physical, DLL                      |
| Internet       | Network                            |
| Transport      | Transport                          |
| Application    | Session, presentation, application |
