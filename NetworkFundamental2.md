**Layer 5 Onwards**
NAT (Network Address Translation) 
NAT was created to address shortage of IPV4 addresses .. to private devices gives access and translate it back and gives security as Well

TYpes:
1) Static NAT: 1 private to 1 public
2) Dynamic NAT: Pool of public IPS..large private IP but less public IP
3) PAT (Port address translation) Many private IP to one public (NAT Gateway)
Port to identify individual IPs.. IPv6 NAT doesn't makes sense

Below is Static NAT
![image](https://user-images.githubusercontent.com/24499265/127029456-7a5b36fa-e6dc-472b-804f-f845ec484db5.png)

**DYnamic NAT**
private IP to public mapping is allocation based on temp basis..here public IP is less
If public pool is exhausted, if another private device asks for it, it will fail to get the Public IP
![image](https://user-images.githubusercontent.com/24499265/127090634-e01cfc11-edee-4a61-9def-eb6fb0288846.png)

**Post address translation** (PAT)
that's how aws NAT Gateway works : Many to 1 mapping architecture
![image](https://user-images.githubusercontent.com/24499265/127091295-9c96ed25-f3f6-4da2-92e0-0a6ecaa3d24c.png)
NAT Gateway 1) take IP packet, change source IP to self and port of one of it's know ports from the ephemeral of the private device
2) Creates a NAT table of Private IP, Private Port to Public IP and Public Port
3) when traffic (response) returns, refers to the NAT Table , translates the Private port and IP and forwards it to the client


**IP Addressing and Subnetting**
Public IPV4 addresses are assigned by Authority
Private ones can be assigned freely..  
IP Ranges CLass A, B and C.. Class A: 3 Octets are free 1 subnetted (for  network).. clss B 2 and class c only 1.. 
![image](https://user-images.githubusercontent.com/24499265/127092399-1854b79b-1d9b-40ab-a658-6c382ce47174.png)

Private network
![image](https://user-images.githubusercontent.com/24499265/127092891-4eec140d-5532-4379-a7fb-93f0e1b695cc.png)

