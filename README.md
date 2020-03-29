# Network Topic Research

## *Topic 1*

### What is an IP network?
- An IP network is a communication network that uses Internet Protocol (IP) to send and receive messages between one or more computers.
-An IP network requires that all hosts or network nodes be configured with the TCP/IP suite.
- The Internet is the largest and best known IP network.

### What is an IP?
- IP stands for Internet Protocol.
- There are two standards for IP addresses: IP Version 4 (IPv4) and IP Version 6 (IPv6).

### IPV4
- IPv4 uses 32 binary bits to create a single unique address on the network. An IPv4 address is expressed by four numbers separated by dots. Each number is the decimal (base-10) representation for an eight-digit binary (base-2) number, also called an octet. For example: 216.27.61.137

### IPV6
- IPv6 uses 128 binary bits to create a single unique address on the network. An IPv6 address is expressed by eight groups of hexadecimal (base-16) numbers separated by colons, as in 2001:cdba:0000:0000:0000:0000:3257:9652. Groups of numbers that contain all zeros are often omitted to save space, leaving a colon separator to mark the gap (as in 2001:cdba::3257:9652).

### With IPV4 (no submask) How many IP can we have in the world? (solution?)
- IPv4 uses 32-bit IP address, and with 32 bits the maximum number of IP addresses is 232—or 4,294,967,296. This provides a little more than four billion IPv4 addresses (in theory). The number of IPv4 available addresses is actually less than the theoretical maximum number.
- **A SOLUTION**: The principal solution for the shortage of IPv4 addresses is IPv6, which provides a much larger address space using 128 bits instead of 32 bits.  

### IP and Binary?
An IP can we converted into binary using a simple algorithm. The binary is how the computer sees and understands our IP.

### Little Demo Calculating IP's into binary
We take the IP address: 154.31.16.13 and start with the first part, which is 154.
- Question: Can I subtract 128 from 154? Answer: YES. So we assign 1 to 128.  
```
128	64	32	16	8	4	2	1
1	 
```	 	 	 	 	 	 
- Question: Can I subtract 64 from 26? Answer: NO. So we assign 0 to 64.
```
128	64	32	16	8	4	2	1
1	0
```	 	 	 	 	 	 
- Question: Can I subtract 32 from 26? Answer: NO. So we assign 0 to 32.
```  
128	64	32	16	8	4	2	1
1	0	0
```	 	 	 	 	 
- Question: Can I subtract 16 from 26? Answer: YES. So we assign 1 to 16.
```  
128	64	32	16	8	4	2	1
1	0	0	1
```	 	 	 	 
That will give us a remainder of 10. (26-16=10).
- Question: Can I subtract 8 from 10? Answer: YES. So we assign 1 to 8.
```  
128	64	32	16	8	4	2	1
1	0	0	1	1
```	 	 	 
That will give us a remainder of 2. (10-8=2).
- Question: Can I subtract 4 from 2? Answer: NO. So we assign 0 to 4.
```  
128	64	32	16	8	4	2	1
1	0	0	1	1	0
```	 	 
- Question: can I subtract 2 from 2? Answer: YES. So we assign 1 to 2.
```  
128	64	32	16	8	4	2	1
1	0	0	1	1	0	1
```	 
That will give us a remainder of 0. So for the rest of the values in our row, we can assign 0.  
```
128	64	32	16	8	4	2	1
1	0	0	1	1	0	1	0
```
**OUR FIRST IP OF 128 IS 10011010 IN BINARY.**

## *Topic 2*

### IPV4 Limits
- The lack of address space.
- Weak protocol extensibility.
- The problem of security of communications.
- Lack of quality of service support.
- Geographic limitations.

### IPV4 vs IPV6

- IPv4 is 32-Bit IP address whereas IPv6 is a 128-Bit IP address.
- IPv4 is a numeric addressing method whereas IPv6 is an alphanumeric addressing method.
- IPv4 binary bits are separated by a dot(.) whereas IPv6 binary bits are separated by a colon(:).
- IPv4 offers 12 header fields whereas IPv6 offers 8 header fields.
- IPv4 supports broadcast whereas IPv6 doesn’t support broadcast.
- IPv4 has checksum fields while IPv6 doesn’t have checksum fields
- IPv4 supports VLSM (Virtual Length Subnet Mask) whereas IPv6 doesn’t support VLSM.
- IPv4 uses ARP (Address Resolution Protocol) to map to MAC address whereas IPv6 uses NDP (Neighbour Discovery Protocol) to map to MAC address.

### What is submask?
A subnet mask hides, or "masks," the network part of a system's IP address and leaves only the host part as the machine identifier. A common subnet mask for a Class C IP address is 255.255.255.0. Each section of the subnet mask can contain a number from 0 to 255, just like an IP address. Therefore, in the example above, the first three sections are full, meaning the IP addresses of computers within the subnet mask must be identical in the first three sections. The last section of each computer's IP address can be anything from 0 to 255. For example, the IP addresses 10.0.1.201 and 10.0.1.202 would be in the same subnet, while 10.0.2.201 would not. Therefore, a subnet mask of 255.255.255.0 allows for close to 256 unique hosts within the network (since not all 256 IP addresses can be used).

### Little demo: Check if 2 IP's in the same network using submask.

***Step 1***
Obtain your IP address and subnet mask number.
- In Mac OS X, you can do this by accessing the System Preferences menu and selecting the "Network" option.
***Step 2***
Convert both numbers to binary. Binary is a numeric system in which only 1 and 0 are used.
***Step 3***
Compare the two binary numbers by columns. Wherever both numbers are 1, write down a 1.
***Step 4***
Obtain the second IP and subnet mask numbers.
***Step 5***
Convert these to binary.
***Step 6***
Perform the "AND" comparison with the second pair of numbers.

Compare the two results of the AND operations. If they are identical, the two IPs are on the same subnet. If they are not identical, they are not on the same subnet.
