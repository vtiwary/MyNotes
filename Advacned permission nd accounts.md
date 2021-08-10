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

All that was needed was access key, secret key and Token , using which anything can assume the role

Use revoke session.. it attaches an inline policy to the IAM Role as show below offcourse in UTC
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Deny",
            "Action": [
                "*"
            ],
            "Resource": [
                "*"
            ],
            "Condition": {
                "DateLessThan": {
                    "aws:TokenIssueTime": "2021-08-09T06:22:23.999Z"
                }
            }
        }
    ]
}

once it's applied, stole assumed role credentials can't be used and attacker has no way to invoke STS assuemd role persmission
But any services which had called Assumed role on this IAM Role will have similar issue..i..e. EC2 needs to restart to  get new set of credentials

