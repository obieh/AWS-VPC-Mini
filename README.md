# AWS-VPC-Mini
## This project will demonstarte how to create a VPC in AWS.

### Setting Up a Virtual Private Cloud(VPC).

* On Your AWS account search bar type "VPC" and click vpc from the output.

![](./img/Pasted%20image.png)

* Click 'Create VPC' to begin creating one.

![](./img/Pasted%20image%20(2).png)

* Select "VPC only", add a CIDR block of 10.0.0.0/16. Check "No IPv6 CIDR block", leave "Tenancy" at default and click "Create VPC"

![](./img/Pasted%20image%20(3).png)

* A success page indicating that the VPC was created succesfully.

![](./img/Pasted%20image%20(4).png)

* Navigate to 'your VPCs' to verify existence of the vpc.

![](./img/Pasted%20image%20(5).png)


### Setting Up Subnets.

* Click on 'Subnets' from the list of items on the left.

![](./img/Pasted%20image%20(6).png)

* On the subnet page click "Create subnet" toward the top right.

![](./img/Pasted%20image%20(7).png)

* Select the VPC id and the associted CIDR you just created.

![](./img/Pasted%20image%20(8).png)

* Enter a name for the subnet, choose availability zone, specify IPv4 CIDR and click "Add new subnet"

![](./img/Pasted%20image%20(9).png)

* Add a name, choose availability zone, a CIDR block for the second subnet.

![](./img/Pasted%20image%20(11).png)

* Click 'Create subnet' towards bottom left to effect subnet creation. You should see your subnets as below.

![](./img/Pasted%20image%20(12).png)