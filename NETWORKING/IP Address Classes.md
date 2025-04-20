
# 🌐Classes of IP Addresses

The IP address space is divided into five classes (A, B, C, D, and E) based on how many bits are allocated for network and host identification.

![image](https://github.com/user-attachments/assets/b75d01c8-6029-497b-9b11-4cc49e34110c)


Breakdown of Each Class (With Example IPs)

## 🅰️ Class A (1.0.0.0 - 126.255.255.255 )

First Octet Range: 1-126

Network ID: First octet

Host ID: Remaining three octets

Total Networks: 2^7 = 128 (but 0.0.0.0 (has no meaning as all zero) and 127.x.x.x (used for loop back) are reserved) >>>>>Will explain why 1 bit less, not total 8 bit as total bit for network ID is 8 because first bit is fixed to 0 in first octet (left most) to identify the class for class A

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

Total Networks: 2^14 = 16,384 >>>>>>>>>Will explain why 2 bit less, not total 16 bit as total bit for network ID is 16 becaeuse first 2 bit is fixed to 10 in first octet (left most ) to identify the class for class B

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

Total Networks: 2^21 = 2,097,152 >>>>Will explain why 3 bit less, not total 24 bit as total bit for network ID is 24 becaeuse first 3 bit is fixed to 110 in first octet (left most ) to identify the class for class C

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



# 🌐Why few bits in first Octet are fixed in each class

A few bits in the first octet of each class are fixed to identify the class of the address quickly.



![image](https://github.com/user-attachments/assets/ab5fe230-3af0-45f0-9459-f2ba09e58900)



## Let's analyze why these specific patterns (0, 10, 110, etc.) were chosen.

## 🅰️ Class A: Starts with 0
The first bit is always 0 → This means Class A addresses range from 00000000 to 01111111.

First octet decimal range:

(00000000) base 2 = 0 (Reserved, not used)

​( 01111111 ) base 2 = 127 (But 127.x.x.x is reserved for loopback)

 So, usable range is 1 – 126.

✅ Why? This allows large organizations to have a massive number of host addresses.

## 🅱️ Class B: Starts with 10
The first two bits are always 10 → This means Class B addresses range from 10000000 to 10111111.

First octet decimal range:

(10000000 ) base 2 = 128

(10111111 ) base 2 = 191


So, usable range is 128 – 191.

✅ Why? This balances network and host bits, useful for medium-sized networks.

## 🅲 Class C: Starts with 110
The first three bits are always 110 → This means Class C addresses range from 11000000 to 11011111.

First octet decimal range:

(11000000) base 2 = 192
(11011111 ) base 2 = 223

So, usable range is 192 – 223.

✅ Why? It provides many small networks, each with fewer hosts.

## 🅳 Class D: Starts with 1110 (Multicast)
The first four bits are always 1110 → This means Class D addresses range from 11100000 to 11101111.

First octet decimal range:
 (11100000 ) base 2 = 224
 (11101111) base 2 = 239

So, usable range is 224 – 239.

✅ Why? These are not assigned to devices but used for multicasting (e.g., video streaming, IPTV).

## 🅴 Class E: Starts with 1111 (Experimental)
The first four bits are always 1111 → This means Class E addresses range from 11110000 to 11111111.

First octet decimal range:

(11110000) base 2 = 240
(11111111) base 2 = 255

So, usable range is 240 – 255.

✅ Why? Reserved for future experimental use.


# 🌐subnetting can be done on two basis 1. according to netwrok requirement 2. according to host requirement 


## What is Subnetting?
Subnetting is the process of dividing a large network into smaller subnetworks.
This helps in:
✅ Efficient IP utilization (no wastage of IPs).
✅ Better security & network management.
✅ Reducing network congestion.

## Subnet Mask
The Subnet Mask determines which part of an IP address belongs to the network and which part belongs to the host.

if u doing subnetting based on network lets say have to create 4 network(subnet)  in  192.168.1.0/24 

2 ^n >= total number of network (subnet) here n is network bit which is represented by 1

2 ^n >= 4 so value of n is 2 since this is class C ip where total number of network bit is /24 and need additional 2 network bit so total become 26 

New subnet mask: /26 (255.255.255.192).

![image](https://github.com/user-attachments/assets/01f364f5-e6fa-4af9-8661-86d6a6000eae)

![image](https://github.com/user-attachments/assets/48531454-7792-48bb-a87e-3498b052e54b)


but if you doing subnetting based on total number of host 

then 2 ^n -2 >= total number of host , here n is host bit which is represented by 0 and why minus 2 because:

🔁 One address is reserved for the network ID. when all host bits are 0 this  identifies the network itself, not any specific device. Used by routers to route packets to the right network.

📢 One address is reserved for the broadcast address. When all host bit are 1 this  identifies the Broadcast Address and to send a message to all hosts in the network. It’s basically: "Hey! Everyone in this subnet, listen!




