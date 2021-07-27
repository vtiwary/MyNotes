**DDOS**
Designed to overload website/API and compete against legitimate connections
Distributed: Hard to block individual IPs/ranges
3 categories of DDOS attack
 1)Application Layer: HTTP Flood: easy to request a page but takes lot of effort to respond.. this impalence is exploited here
 2) Protocol based attack i.e. SYN Floods--> take advantage of connection based natured of TCP/IP (3 step hand shake). If they send SYN Flood,  server will try to contact the client (2nd step) which isnt there anyway as client IP is spoofed and server hangs for certain druartion and which chew up resources
 3) VOlumetric Attack such as DNS amplification--> how a DNS resolution request has to respond with large amount of data and spoofed anyway
 Applixation layer attack
 ![image](https://user-images.githubusercontent.com/24499265/127184021-c46d43b4-8ad6-4644-8712-17276b4b2972.png)

Protocol based
![image](https://user-images.githubusercontent.com/24499265/127184350-04fe291a-fd60-48a1-8176-6049f3562ad1.png)

Volumetric attack
Instead of Affecting app server it will affect connection to APp serer since all responses will go to APp server from DNS serveres as spofed ip will be of APp server
takes tiny size to bring down lager servers
![image](https://user-images.githubusercontent.com/24499265/127185591-14d337db-737a-40b6-8046-30108c46bcbd.png)


**SSL/TLS**
helps with privacy and Data integrity between client and server
Privacy by encryption
Asymteric then symmetric as symetric one is computationally mor efficient
* identity (cleint server or both verified): capable of 2 way verificagtions wheatehr server or client are who they say they are
* but typically server is the one which is ver
![image](https://user-images.githubusercontent.com/24499265/127191072-526f40c5-0493-406f-853f-84b1330509ed.png)


![image](https://user-images.githubusercontent.com/24499265/127196551-556c36b0-ede7-43f7-a570-4de7c42d3205.png)


 

