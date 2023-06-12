# Building a simple network

### Task description

Here you can find the task: https://github.com/becodeorg/BXL-k4MK4r-1/blob/main/content/01.Network/00-Network_basics_(Pretraining)/projects/Build_simple_network.md

### Realisation

#### Overlook

![image](https://github.com/RombinatoR/building_a_simple_network/assets/133594002/429845d0-4dce-439e-94c3-29af803496ad)

#### The 3 client PCs and the Web Server

All 3 PCs have been granted respectively **192.168.1.10/24**, **192.168.1.11/24**, **192.168.1.12/24** addresses, and as default gateway, Router0 (**192.168.1.1** on interface g0/0/0)

Web Server has been given the last host address **192.168.1.254/24**; with, as default gateway, also *192.168.1.1* as it sits on the same side of the router.

##### DNS

As a quick example for this simple network, I added a domain name *www.gandalf.com* and the address of that domain (on the same machine, so 192.168.1.254/24)

![image](https://github.com/RombinatoR/building_a_simple_network/assets/133594002/d2348a61-932c-44a0-b3a6-187b3624b493)

#### Switch0

As simple as it could be: I simply left the interfaces on trunk, so that the switch replicates the entrant packets through all its connected interfaces.
Obviously not a wonderful idea in a real situation (VLANs, or routers help tunneling the traffic inside the network), but hey, this is meant to be *simple*.

#### Router0

More interesting but still as simple as it could've been made. Two static routes:
- One that drives the incoming traffic to 192.168.1.0/24 through the interface g/0/0 (192.168.1.1/24)
- One that drives the exiting traffic through the interface g/0/1. In practice, it'll just be a route to 0.0.0.0/0; the default route.






