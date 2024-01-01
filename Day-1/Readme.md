## Day - 1 of #30DaysofBackend

# How does Internet work?

## Prologue

The functioning of the internet bears resemblance to the dial-in communication systems prevalent from the 1800s to the 1900s. Upon closer examination, the internet comprises intricate hierarchies that continue to evolve daily. When dialing your friend on the phone, the act of sending information occurs, and the details of how this transfer transpires remain temporarily obscured, akin to a black box. Similarly, within the realm of the internet, whether you're transmitting information, data, or reacting with an emoji to a meme, everything is conveyed through the internet's black box to reach the intended recipient.

## Introduction

The internet is present everywhere now – in your mobile, laptop, TV, air conditioner, refrigerator, and even in a light bulb. However, it gained widespread attention in the 1990s. The roots of its development, like packet-switching networks, go back to the 1950s, but we won't delve into that history here. While many may think of the internet as just connecting systems over a network, it's not as straightforward as it seems. Let's explore how the internet actually operates.

## Internet Protocol(IP) Addresses

Upon birth, individuals are named for identification, pets are given names, and animals are recognized by their breeds. Likewise, each system connected to the internet is assigned a distinct identity known as an IP Address. This address is presented in the format xxx.xxx.xxx.xxx, where each x can assume any value between 0 and 255, constituting an IPv4 address. As internet connectivity proliferates and the number of devices surges, the emergence of IPv6 becomes essential. IPv6 has a format of xxx.xxx.xxx.xxx.xxx.xxx, featuring 6 parts, with each x ranging from 0 to 255.

![image](https://github.com/nehruperumalla/30DaysofBackend/assets/41884444/9dd47a2c-ad53-4442-a1fb-2151255a1c53)


The image above depicts two computers, each assigned an IP address, connected to the internet. One computer has the IP address 1.2.3.4, while the other has 5.6.7.8. These computers can communicate and exchange information since they are linked to the internet. We'll explore the intricacies of the internet in more detail later.

## Communcation

Each computer possesses a distinct identity known as an IP address, allowing them to connect to the internet and engage in communication with other computers, treating the internet as a black box. However, the question arises: How do these computers communicate? Let's draw a parallel to our initial example of the internet being akin to dial-in phones. When I dial my friend on the phone, our communication is conveyed through electronic signals with varying frequencies.

Similarly, in the digital realm, when Computer A, with the IP address 1.2.3.4, sends information to Computer B, with the IP address 5.6.7.8, the information is initially converted into binary code consisting of 1s and 0s. While we understand this binary representation, the challenge is transmitting these 1s and 0s through the physical wires linking the internet and Computer B. The solution lies in using radio waves, employing two frequencies—one representing 1s and the other representing 0s—for efficient transmission.

![image-1](https://github.com/nehruperumalla/30DaysofBackend/assets/41884444/923b26d6-6de8-4175-8aad-5cd4119c78c3)


Let's go back to the fundamentals of networking with the OSI Model. Everything we've talked about so far falls under the protocol stack. Communication is crucial for every computer, and we'll explore in detail how communication occurs between two systems.

![image-2](https://github.com/nehruperumalla/30DaysofBackend/assets/41884444/3c5dc007-0a79-47a5-b765-64db660e249d)



The detailed illustration in the above picture expands on Diagram 1, replacing computers with layers of a network through which data passes. We've established that communication happens through waves, but how does it reach the destination, and how is the data transmitted?

1. Computer 1.2.3.4 wants to send the message "Hello" to computer 5.6.7.8.
2. The message, being lengthy, is divided into smaller chunks called packets.
3. Starting from the top application layer and progressing to the TCP layer, each packet is assigned the port number of the destination computer (more on ports later).
4. In the IP layer, each packet is assigned the destination IP address, which is 5.6.7.8.
5. The hardware layer converts the data to binary and transmits it as radio waves with different frequencies.
6. The packet stream is now on the internet, and the Internet Service Provider determines which destination router should receive these packets.
From that router to the destination computer, the data moves upstream through the aforementioned layers.
7. The hardware layer decodes the waves into binary information and packets.
8. The IP layer matches the assigned IP address of the packets.
9. The TCP layer matches the port number to which the data needs to be sent.
10. As the data reaches the top, the packets are reconstructed back into their original form, forming the message "Hello".

# Internet:

The image below provides a detailed view of Diagram 1. Our aim is to demystify the internet, moving away from treating it as a black box.

![image-3](https://github.com/nehruperumalla/30DaysofBackend/assets/41884444/95f32b1a-7ce9-4e36-8564-9afc5abc0fbc)

In this depiction, the computer with IP 1.2.3.4 sends packets to another computer with IP 5.6.7.8. The data then traverses through the modem, public network, model pool, and ISP Port Server before reaching the router connected to the ISP backbone (we will explore this in detail later). Subsequently, the ISP backbone determines the specific router to which the information should be sent.

## ISP Backbone:

We're familiar with our local Internet Service Providers (ISPs) that supply internet to us. These local ISPs obtain their bandwidth from Regional ISPs, which, in turn, borrow bandwidth from larger networks such as CerfNet, IBM, SprintNet, and others. Collectively, these entities constitute the ISP backbone. Each of those NSPs should connect to atleast 3 Network Access Points known as NAP, this is where packet switching happens.

The image below illustrates the infrastructure of the internet.

![image-4](https://github.com/nehruperumalla/30DaysofBackend/assets/41884444/0d222162-e9d4-45fd-a1cd-12ad3ffe266f)


## Internet Routing Hierarchy:

When a source computer is transmitting information to a target computer, how do the packets find their way? Are the packets broadcasted to every computer connected to the internet? Does the source computer have knowledge of the location of the target computer? The answers to these questions are no and no. To guide the packets to their destination, we utilize "Routing Tables" located in routers connected to the internet.

![image-5](https://github.com/nehruperumalla/30DaysofBackend/assets/41884444/899832e4-5119-433f-826e-c5fb2d722b7e)



Let's consider an example where I am sending a "Hello" message from a computer with the IP address 1.2.3.4 to my friend's computer with the IP address 5.6.7.8. Examining the flow using the above diagram, the black boxes connected to NSP and Regional ISP backbones represent routers.

We have two local area networks attached to computers. The packets are initially sent to the router connected to the Regional ISP. There, it checks the network with the destination IP in the routing tables of that router. If found, the packet is sent to that network; if not found, it moves up the backbone hierarchy to the next router, repeating the process. This continues until it reaches the NSP backbone, which holds the largest routing tables.

## Domain Name Service:

Up to this point, we've observed communication occurring between two computers based on their IP addresses. But what if we don't know the IP address and only have the server's name, like www.google.com? To address this issue, we have the Domain Name Service (DNS), which stores all the IP addresses corresponding to the textual representations of web server names.

Numerous computers connected to the internet host portions of the DNS database along with the software enabling others to access it. These computers are referred to as DNS servers. No single DNS server holds the entire database; they each maintain a subset of it. If a DNS server lacks the requested domain name, it redirects the requesting computer to another DNS server.


That's for How does Internet work.

# References:

https://web.stanford.edu/class/msande91si/www-spr04/readings/week1/InternetWhitepaper.htm

https://www.youtube.com/watch?v=TNQsmPf24go
