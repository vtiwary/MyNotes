There are 7 layers in OSI model
3 media and 4 host layer (physical -1, applicatin - 7th) .. it starts from application layers in source and ends at appliaction layer (i.e. chrome)  in destination, going from later 
7to 1 and then at destination 1 (physical i.e network card layer) to 7 
when talking at a layer x means later x and below.. like later 3 and has layer 1,2,3 capabilities

**Layer 1** Physical layer
physical is 0 and 1 and the agreement between devices on 0 and 1

Hub can be used but the feature here is if anything is received at one post it's transmitted to its all ports, including error and collisions
layer 1 : no device address, all data is processed by all devices
Like: Shouting in a Room full of people wihtut using any name
![image](https://user-images.githubusercontent.com/24499265/124416380-81e2c780-dd74-11eb-8a92-4a34f866a3d4.png)

layer 1 has no media controll access.. no control over who can transmit.. in layer 1 there are just network cards transmitting the information via voltage changes
Doesn't give uniquly identifiable devices

**Layer 2** Data Link layer
All layers above use data link later
MAC total 48 Bits.  brings in MAC address for each devices.. 24 bits by manufacturer,first 24 are OUI (Organization unique Idetifier).. assigned to companies building network hardware. Next 24 are NIC addderss (Network Interface card controller): togaterh 48 bits are gloally unique

provides frame
ET (EtherTYpe)(16 bit) tells which layer 3 protocol put originally put data in the frame
at destination layer 3 of destinatin is provided after extracting Payload usig ET
![image](https://user-images.githubusercontent.com/24499265/124418840-ff5d0680-dd79-11eb-93b3-2abef46c604d.png)

FCS Bits is to cehck for any error

**CSMA/CD in layer 2 Data link layer **
Carrier Sense Multiple Access : checks the layer 1 if anyone is transmiting (carrier) and transmits the frame
on receiving end it checks MACS address and realises its destined for itself
Layer 2 checks medium for any transmission happening. if it happens it will stop layer 1 from transmitting and will wait
Data before transimitting is encapsulated in a frame and at receving end its de-encapslated
if a collision is detected at layer two a eacch detecting devices jam and backoff for a random each (differetn for each hopefully)
if another collission happens random backoff  it will be for a higher time
Hub is layer one, even if devices connected to it run layer 2 we will have issues of collision (may be less though due to CDMA/CD on laptops) but its a dumb repeater machine so will have problems..better to use a switch 

![image](https://user-images.githubusercontent.com/24499265/126740770-1ac3e55e-67bc-406a-ac1b-3efa2556f80c.png)

it seems MAC address in frames so can update its MAC address table to know which MAC address is mapped to which port..
initially it forward to each port untill MAC mapping table is complete.. it doesnt transmit the same frame to sender (Intelligent eh)
Switch works on layer2.. Now we have identifiable devices and media access control and detect collission and workaround them. So unicast and broadcast communication

** Binary to Decimal for IP4 **

133.33.12.255 is dotted decimal notation (0-255 human readable) 32 bit (8 bit each-1 octat)
![image](https://user-images.githubusercontent.com/24499265/126743794-e4f6e367-c4ca-4f52-95f1-c335e1769b93.png)
all is if the number is more than the one in the Binary position value make it one and reduce the number in that octat they check against next binary postiion . if less make it 0 if not make it one and then reduce it till the end


**Democal to BInary IP4**
still need to use the table ..use the field and work with it 1 or 3
![image](https://user-images.githubusercontent.com/24499265/126744426-00bc3809-5a66-4020-99b0-47b44ce380ee.png)


**Layer 3 Network Layer**
If layer 2 netowrk, it would need to use same protocol and which wont be desirable at all times
Ethernet is for local area Network.. layer 2 moves frame from one MAC address to another within same Area..layer 3 can span accross multiple layer 2 network.. Provides IP address..

![image](https://user-images.githubusercontent.com/24499265/126744976-eeff5e6a-c649-4892-b06e-8f2c669f7e61.png)
when data package moves accorss network each time its de-encasualted and encapsulated with net details including Proprcol ET
 
 layer 3 packets..frames in layer 2 haveing source and destination as local however layer 3 its even opposite site of planet..these source and destination remains same..layer two frame changes each time packet hops to new netowrk
 
 Layer 3 IPv4 and IPv6
 Procol in this layer is provided by layer 4..can be ICMP, TCP and UDP.. this is to inform the layer 3 at destination to which layer 4 protocol to pass packet to
TTL  : how many hops package can move through ..after which can be discarded
Hop limit in Ipv6  same to TTL in IPv4


**IP Addresses**
IP has Netowrk part and host part. if network part matches then its same IP
![image](https://user-images.githubusercontent.com/24499265/126935483-eed6a887-e6e3-461b-83fe-26a6d5b896f5.png)

IP can be machine assigned(dynamic) or Human assigned (static)
Subnet mask allows host to determine if IP Address it needs to commmunicate is on same network or if it needs to use default gateway
255.255.0.0 is /16 ..if converted to binary it tells which  part is subnet (ones) and which part is host (zeros)
if. 11111111.11111111.00000000.00000000
if iP is 133.33.3.7 and its /16, starting ip is 133.33.0.0  (NET START) and NET END IS 133.33.255.255 ..i.e take all Zeros on host part and replace it with all Zeros

![image](https://user-images.githubusercontent.com/24499265/126937117-e512f078-668f-4838-bb26-2736f83cc089.png)

The ISP has a route table having mapping betwen destinatin and Next HOp/target.. higher the slashmore sepcific it is and moer preffered in case of multiple matches
![image](https://user-images.githubusercontent.com/24499265/126938031-14111cb1-251a-4c62-ad83-25a6f16b7d4f.png)

 route tables can be statically populated or using BGP (Boarder Gateway protocol) allowing them to exchage info regardign which network they know about. on a different note, when traffic is routed to AWS, its sent of Layer 2 which wll be the MAC Address of AWS using address resolution protocol (ARP).. this is used when we need to find MAC address of the remote destination but we dont know what it is and only know the IP Address
 ARP sits between layer 3 and 2 since while layer 2 frame is created it needs MAC addresses.for local and remote as well
 
 ![image](https://user-images.githubusercontent.com/24499265/126940765-14115143-b230-46fc-bb97-654f912bc6f0.png)
Routers are layer 3 devices meaning they understand layer 1-3
laptop/desktops will drop the packets not destined to it however router job is to route packet so it wont drop it, rather remove frame and keep the packet attached MAC of next destination using Routing table and calling ARP with that IP

![Uploading image.png…]()



 
 
 
 
 
















