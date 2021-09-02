![image](https://user-images.githubusercontent.com/24499265/131787685-41032f0f-0976-467d-b0cf-46ff4663c7f3.png)

some of them are global so per account quotes.. for example IAM is 5000 per account for users and it's hard limit
so, if an application needs mroe than 5000 users then we have to use something other than IAM, hence wil have pronounced architectural impact

Search Service "Service Quotas" same  way you search EC2 or otehr servics .. and will get to the quotas dashboard
in aws services, there you can type th service and see the qutoes.. current, default and it also says if it's adjustable or not

over here you can click on a particular item and select request quotas increase

If it's an organization, we can define a template for quota increase which will reduce overhead for the child accounts
We can use cloudwathc alarms gto notify us  automatically whenever a specified quota reaches a percentage 
of the maximum or reaches the maximum level

also , we can use suport on the top of the console we can select support center and select limit increase or Tech suport or billing 
(this is old method for service quota icnrease) Use "Service quotas" instead

same can be achieved duing Command line , including quotas increase

aws service-quotas list-service-quotas --service-code cloudformation

aws service-quotas list-aws-default-service-quotas --service-code xray #defailt quotes




