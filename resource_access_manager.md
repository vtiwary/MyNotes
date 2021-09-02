Availability zone ID.. these dont chagnes like azuseast1a, 1b changes

![image](https://user-images.githubusercontent.com/24499265/131612789-93fb82f9-3b5d-4b57-ba4b-2cc3f037d7d7.png)

RAM Specifications
![image](https://user-images.githubusercontent.com/24499265/131612907-2ac23a33-2d19-438c-a7b4-7802bc70d638.png)


![image](https://user-images.githubusercontent.com/24499265/131612628-2201c4d3-c3bd-4f7e-bc45-4fe234cb2d1e.png)
prior to use of Ram people used to use VPC Peering or Transit gatway ... Ram gives option to share resources within Org, 
any account or whole AWS org

Typically any sharing in RAM is invite and accept but under setting there is an option to share within Organisation and it wont require invite and accept
once resource share is created "under shared with me" in Resource Access Manager we will be able to see the VPC etc shared with us.. but it wont show who else it has been shared with, kind of separation

Though account which createdt he resources owns it in the shared VPC.. the account to which it has been shared can assign it's own name to the resouces valid only in that account

**When lauching EC2 now it supports two types of Keys
Supported types: RSA and ED25519. Amazon EC2 does not accept DSA keys.
Note that ED25519 keys are not supported for Windows instances, EC2 Instance Connect, and EC2 Serial Console.**

But one thing to note, participating accounts  can only see the resources shared with them.. if participating creates an EC2 inside the shared Subnet only creating account can see it others can't , even the owner of the shared resouces can't
