
# Classes of IP Addresses

The IP address space is divided into five classes (A, B, C, D, and E) based on how many bits are allocated for network and host identification.

Breakdown of Each Class (With Example IPs)

## 🅰️ Class A (1.0.0.0 - 191.255.255.255 )

First Octet Range: 1-126

Network ID: First octet

Host ID: Remaining three octets

Total Networks: 2^7 = 128 (but 0.0.0.0 (has no meaning as all zero) and 127.x.x.x (used for loop back) are reserved) >>>>>Will explain why 1 bit less, not total 8 bit as total bit for network ID is 8

Total Hosts per Network: 2^24 - 2 = 16,777,214 (Total Hosts= 2^host bit -2)

📌 Example:

IP Address: 10.5.6.7

Network ID: 10.0.0.0

Host ID: 5.6.7

Subnet Mask: 255.0.0.0

## 🅱️ Class B ( 128.0.0.0 - 191.255.255.255 )

First Octet Range: 128-191

Network ID: First two octets

Host ID: Remaining two octets

Total Networks: 2^14 = 16,384 >>>>>>>>>Will explain why 2 bit less, not total 16 bit as total bit for network ID is 16

Total Hosts per Network: 2^16 - 2 = 65,534

📌 Example:

IP Address: 172.16.5.10

Network ID: 172.16.0.0

Host ID: 5.10

Subnet Mask: 255.255.0.0


## 🅲 Class C ( 192.0.0.0 - 223.255.255.255 )

First Octet Range: 192-223

Network ID: First three octets

Host ID: Last octet

Total Networks: 2^21 = 2,097,152 >>>>Will explain why 3 bit less, not total 24 bit as total bit for network ID is 24

Total Hosts per Network: 2^8 - 2 = 254

📌Example:

IP Address: 192.168.1.100

Network ID: 192.168.1.0

Host ID: 100

Subnet Mask: 255.255.255.0

## 🅳 Class D (Multicast) (224.0.0.0 - 239.255.255.255 )

Range: 224.0.0.0 – 239.255.255.255

Used for multicast applications (e.g., streaming, IPTV).

No subnetting required.

📌Example:

Multicast Group: 224.0.0.9 (RIP Protocol)

## 🅴 Class E (Reserved) ( 240.0.0.0. -255.255.255.255 )

Range: 240.0.0.0 – 255.255.255.255

Reserved for future use or research.

Not used in normal networking.



# Why few bits in first Octet are fixed in each class

A few bits in the first octet of each class are fixed to identify the class of the address quickly.




![image](https://github.com/user-attachments/assets/56528784-e3ec-485e-98ff-cc5ba9a3d393)




subnetting can be done on two basis 1. according to netwrok requirement 2. according to host requirement 


## What is Subnetting?
Subnetting is the process of dividing a large network into smaller subnetworks.
This helps in:
✅ Efficient IP utilization (no wastage of IPs).
✅ Better security & network management.
✅ Reducing network congestion.

## Subnet Mask
The Subnet Mask determines which part of an IP address belongs to the network and which part belongs to the host.





