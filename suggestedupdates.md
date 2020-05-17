## Deploy a High-Availability Web App using CloudFormation

### Server.yml

1.	Suggestion: Always restart your apache server after making any changes in /var/www folder as sometimes your changes might not reflect.
2.	Suggestion: You could also take this minSize and maxSize as parameter. In this way, it will be easy to change he min and max size without changing the script code.
3.	It is a good practice to give a Name tag to every resource with value prefixed with a fixed value. Suppose you have a resource, say Public Subnet in a zone A and you named it to PubSubnet. And another EC2 with same name in region B.
This might create confusion that which EC2 is used for which purposes. In real world, you have a number of such instances. Such as
an EC2 for devs, another for testers, and further EC2 for each application. So in order to remove this confusion, always prefix
your Name tag. For eg, shown below
```
Tags:
    - Key: Name
      Value: !Sub ${EnvironmentName} Public Subnet (AZ1)
```
4.	Really nice implementation of GetAtt function. There are other intrinsic functions also provided by cloudformation. You can read more about them here.
5.	Now that you have learnt enough about infra, try to deploy a lambda function, that gets and puts some data in a database. You can also learn about best practices in Cloudformation.
6.	Now that you have learned basics of infra and instance deployment using cloudformation, we would suggest you to go through cloudformation best practices:
    - Deploying ec2 instances
    - General best practices
    - Related to security
7.	Students can deploy Windows Servers instead of Linux and use PowerShell scripts to showcase their Windows management skills. Students can use AWS Parameter Store to save sensitive data, such as credentials to showcase their attention to security. Students can use CloudWatch Alarms and CloudWatch custom metrics to showcase their performance and monitoring skills.
8.	Add and configure Bastion Host.


