![image](https://user-images.githubusercontent.com/24499265/128815003-f831333b-3362-4799-9406-98a7ffeadee2.png)
Here the statement if inside bracket this a list of statements.. Effect in each to tell wheather it allows or denies anything..AWS starts with implicit deny
i.e. starts with zero permission.
in picture above holiady/* signifies that it's applicable to the objects inside the bucket

Condition : This is an AND condition "Condition": {
            "DateGreaterThan": {"aws:CurrentTime": "2020-12-01T00:00:00Z"},
            "DateLessThan": {"aws:CurrentTime": "2020-12-25T06:00:00Z"}
so, if above condition is match, whole deny will become true and effective

![image](https://user-images.githubusercontent.com/24499265/128816111-16d18ac9-9f11-4e95-8a63-b504feb49f16.png)
Here only one statement is there .hurray.. but look carefully
above has not actin but **NotAction**..it basically denies anything that is not withis this action since top is deny (Inverse components)
but above applies only when the condition block equates to true
StringNotEquals is a comparision.. it's  comparing something not equals something..so essentially this will become true only when (in above case) region is not in the two shown there..so,deny when region is not from these two approved regions.. however NotAction ensures that 4 actions listed are not denied if they are from different regions.. being global policies, they log from us-east-1 so had to be excluded anyway
BTW above policy is just deny.it doesnt allow anything. in order for anyone to do anything another policy will allow has to be added

always start with checking how many statement the given policy has

![image](https://user-images.githubusercontent.com/24499265/128817835-fd9dfc6c-de78-44bf-a136-c1f54ca78a5a.png)

for 3 S3 Actions ListALlmyBuckets, GetBucketLocation and CreateBucket , resource needs to be * in the policy 
if resource jsut folder say "animaladdress" then its all permission is on the bucket if "animaladdress/*" then on the components in the buckets

Providing access to other account via ACL has one issue, when other account uploads it, parent account wont have any control over the file that other account uploads.. they will be owner (unless they decide to grant you the access)

Canomical account ID is used to provide account access through ACL to the bucket
for the files uplaoded by ACL or Bucket policies, owners are the account which uploaded the files not the account in which files were placed
Its it's a scenario about cross region or same region replication, creating an account and allowing other account to assume role helps since both can have acess to it now sice it was created by the id from same account (though assumed role was used)
