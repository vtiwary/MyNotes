STS generates temporray credentails whenever STS:AssumeRole* is called which is used by Identity which called AssumeRole
Similar to Access Key and Secret Key and they Expire
limited access and are requested by an Idenitity (AWS or external (Web Identity Federations :))
as long as they are defined in the trust policy of the role, i.e. who can assume that role

![image](https://user-images.githubusercontent.com/24499265/127251280-5f456537-f1a6-4521-8527-34894bcf6c6f.png)

**Revoke IAM TEMP ROle secruity Credentials**
People assuming the same role will get same permissions, it's not feasible to assign different permissions based on who is assuming the role
* Temp credentails can't be cancelled but they expire.. but deleting the role , change permission can do but not desirable
* Changing trust policy will only help while assuming hte role, once temp credentials are alrady provided, it doesnt help
* Better option is AWSRevokeOlderSessions inline Deny, conditioanl on when the credentials are issued
* then legimitate users are free to assume policies again
* Manully we can't invalidate temp credentails
* ![image](https://user-images.githubusercontent.com/24499265/127253216-24818372-eb45-43fb-8547-f8700b66a6d2.png)
