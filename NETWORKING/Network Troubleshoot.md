## 🌐 1. Networking Basics

📍 A. IP Addressing (Internet Protocol Address)

- An IP address is like the home address of a device in a network.

- Every device (laptop, smartphone, server, etc.) on a network gets an IP address.

This IP address helps in identifying and locating the device in the network.

## Two types of IPs:

- IPv4: 4 sets of numbers (e.g., 192.168.1.1) – most commonly used.

- IPv6: Newer format (e.g., 2001:0db8:85a3:0000:0000:8a2e:0370:7334) – supports more devices.

## Two categories:

- Private IP: Used within internal networks (e.g., 192.168.x.x, 10.x.x.x) – not accessible from the internet.

- Public IP: Used on the internet – assigned by your ISP.

🔧 Tools to check:

- `ipconfig` (Windows)

- `ifconfig `/ `ip a` (Linux/Mac)

## 🌍 B. DNS (Domain Name System)

DNS is like the phonebook of the internet.

Converts human-friendly names (like google.com) into IP addresses (142.250.64.78) that computers understand.

## How it works:
You type www.google.com.

Your system queries a DNS server.

DNS returns the IP address.

Your browser connects to that IP.

🔧 Tools to test DNS:

- `nslookup google.com`

- `dig google.com`

- `ping google.com`

## 🛣️ C. Routing
Routing is the process of sending data from one network to another.

Routers direct traffic between different networks.

If your device wants to communicate with a server on the internet, the router decides the path.

Key terms:
Default Gateway: The IP address of your router – acts as the exit point from your network.

Routing Table: List of known networks and the paths to reach them.

🔧 Check your default gateway:

- `ipconfig` or `route print` (Windows)

- `ip route` (Linux/Mac)

## 🛠️ 2. Troubleshooting Connectivity Issues

Here’s a step-by-step checklist to troubleshoot network issues:

## ✅ Step 1: Check Physical Connection
Is the Ethernet cable plugged in?

Is Wi-Fi turned on?

Are there any hardware issues (router/modem lights)?

## ✅ Step 2: Check IP Address

Run `ipconfig` or `ifconfig`:

Does your system have an IP?

Is it a valid IP or 169.254.x.x (means no DHCP response)?

# 🔍 What does 169.254.x.x mean?

This is an Automatic Private IP Addressing (APIPA) range defined by IPv4.

The full range is: 169.254.0.0 to 169.254.255.255

If your computer (or EC2 instance or other device):

- Is set to automatically obtain an IP address (via DHCP), but

- Does not get a response from the DHCP server,

Then it will self-assign an IP address from the 169.254.x.x range.

A device with 169.254.x.x usually:

- Cannot access the internet

- Cannot communicate with other devices outside its local network

- May only communicate with other devices on the same subnet that also have 169.254.x.x (rare case)

So it's a troubleshooting indicator that something went wrong with DHCP.

## ✅ Step 3: Check DNS Resolution

Try `nslookup google.com` or `ping google.com`.

If domain names don’t work, but IPs do, it's a DNS issue.

## ✅ Step 4: Check Network Reachability

Ping your default gateway.

Ping a public IP (e.g., 8.8.8.8 – Google DNS).

If it works, DNS is the likely issue.

Use `tracert` (Windows) or `traceroute` (Linux/Mac) to see the hops between your device and the destination.

## ✅ Step 5: Check Firewall/Security Settings

Firewalls or antivirus software may block traffic.

Disable temporarily to test (be cautious).

## ✅ Step 6: Check Router/Modem

Reboot your router/modem.

Check if other devices on the same network have connectivity.

## ✅ Step 7: Advanced Tools

- `netstat` – Shows open connections.

- `route print` – Shows the routing table.

- `arp -a` – Lists IP-to-MAC address mappings in your network.
