Step-1: Create an IAM role with below permissions

![image](https://user-images.githubusercontent.com/24622526/112564463-990c3380-8ddb-11eb-8a1d-6a8ce516067a.png)

Step-2: Create EC2 instances with IAM role
In this example, I am choosing t2.medium for master, t2.micro for nodes.

Step-3: Connect to all EC2 instances and update hostname

![image](https://user-images.githubusercontent.com/24622526/112565650-b8a45b80-8ddd-11eb-8028-90fff1f820eb.png)

Step-4: 

```
hostnamectl set-hostname <hostname>
```

here hostname = Private IPv4 DNS ex: ip-172-31-59-217.ec2.internal

run the below curl command to get "Private IPv4 DNS"

```
curl http://169.254.169.254/latest/meta-data/local-hostname
```

![image](https://user-images.githubusercontent.com/24622526/112565760-f86b4300-8ddd-11eb-9070-cb950e43a8f5.png)
