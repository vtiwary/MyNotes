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

**CSMA/CD in layer 2**
Carrier Sense Multiple Access : checks the layer 1 if anyone is transmiting (carrier) and transmits the frame
on receiving end it checks MACS address and realises its destined for itself
Layer 2 checks medium for any transmission happening. if it happens it will stop layer 1 from transmitting and will wait












