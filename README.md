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

![](./img/Pasted%20image%20(13).png)

### Creating Internet Gateway(IG).

* On the left pane, click 'Internet gateways' and click 'Create internet gateway' at the top right.

![](./img/Pasted%20image%20(14).png)

* Add a name for the Internet gateway and click "Create internet gateway"

![](./img/Pasted%20image%20(15).png)

* Now the internet gateway is created successfully. You should see a success page.

![](./img/Pasted%20image%20(16).png)

#### Internet gateway is not yet associated with any VPC. You have to attache the IG to the VPC created earlier.

* Select the IG and click "Actions" drop down menu and click "Attach to VPC.

![](./img/Pasted%20image%20(17).png)

* Select the VPC created earlier and click "Attach internet gateway"

![](./img/Pasted%20image%20(18).png)

* IG state should now indicates attached.

![](./img/Pasted%20image%20(19).png)

### Create Route Table

* on the left side bar click "Route Tables", then move towards top right and click "create route table".

![](./img/Pasted%20image%20(20).png)

* Enter a name for the route table, select the VPC created initially, then click "Create route table".

![](./img/Pasted%20image%20(21).png)

* A success page should pop up indicating that the route table have been created successfully.

![](./img/Pasted%20image%20(22).png)

* Now associted a subnet to the route table. Click on "subnet association tab" and click "edit subnet association", towards the right.

![](./img/Pasted%20image%20(23).png)

* Select the public subnet you cretated earliar and click "save association"

![](./img/Pasted%20image%20(24).png)

* If done properly, a success page should show up.

![](./img/Pasted%20image%20(25).png)

* Click on 'Routes' tab and move towards the right to click "Edit routes"

![](./img/Pasted%20image%20(26).png)

* Click "Add route" to add new route.

![](./img/Pasted%20image%20(27).png)

* Use 0.0.0.0/0 to allow all IPv4 routes in the destination then select 'internet gateway for the target and choose the internet gateway you created earliar.

![](./img/Pasted%20image%20(28).png)

* You see the edited route table if confgured correctly.

![](./img/Pasted%20image%20(29).png)

### Enable Outbound internet access via Nat Gateway
* Go to the NAT Gateways section and click "Create NAT gateway"

![](./img/Pasted%20image%20(30).png)

* Give the NAT gateway a name, Choose the private subnet and Select "private" for connectivity type.

![](./img/Pasted%20image%20(31).png)

* Now move down to bottom right and click "Create NAT gateway"

![](./img/Pasted%20image%20(32).png)

* A success notification shows to confirm.

![](./img/Pasted%20image%20(33).png)

* Select your NAT gateway and click 'Details' tab.

![](./img/Pasted%20image%20(34).png)

* Click on 'Subnet' to open subnet page.

![](./img/Pasted%20image%20(35).png)

* Select the route table, move down and click "Routes tab" and click "Edit routes"

![](./img/Pasted%20image%20(36).png)

* On the 'Edit routes' page click "Add route"

![](./img/Pasted%20image%20(37).png)

* Select "Destination" as 0.0.0.0/0, in the "Target" field, choose "NAT Gateway" and then select the NAT gateway you created and then click 'Save changes' to save.

![](./img/Pasted%20image%20(38).png)

* You should see a success page

![](./img/Pasted%20image%20(39).png)

* Click on the "Subnet association" tab and click "Edit subnet associations"

![](./img/Pasted%20image%20(40).png)

* Select the private network and click "save association"

![](./img/Pasted%20image%20(41).png)

* You see your private subnet associated.

![](./img/Pasted%20image%20(43).png)

## VPC Peering.

#### VPC peering is similar to linking two virtual offices in the cloud so that communication and data sharing can take place directly. This comes in handy when you have two VPCs and needs them to communicate. To demonstrate this, we will create two VPCs in same region.

* Head over to the VPC tab to begin creating a new VPC. Add name, a CiDR block and create the VPC.

![](./img/Pasted%20image%20(44).png)

* Create a second VPC with a different name and CIDR block.

![](./img/Pasted%20image%20(45).png)

* On the left hand-side menu, click "Peering connections", and click "Create peering connection" towards the top right.

![](./img/Pasted%20image%20(46).png)

* Add a name for the VPC, select the requester VPC. Be sure to select appropraite region.

![](./img/Pasted%20image%20(48).png)

* Proceed to select another VPC to peer. Select the accepter-VPC and then click "Create peering connection".

![](./img/Pasted%20image%20(49).png)

* You see a sucees page indicating VPC Peering connect have been created.

![](./img/Pasted%20image%20(50).png)

* Click "Actions" and select 'accept request'

![](./img/Pasted%20image%20(52).png)

* On the pop-up window, click 'Accept request'

![](./img/Pasted%20image%20(53).png)

* You have successfully established VPC peering.

![](./img/Pasted%20image%20(54).png)

* Niw click on the main route table ID of the acceptor VPC

![](./img/Pasted%20image%20(55).png)

* Select the route table, move down abit and click 'Routes' tab and then click 'Edit routes' towards middle right.

![](./img/Pasted%20image%20(56).png)

* On the edit routes window click 'Add route'

![](./img/Pasted%20image%20(57).png)

* At this point head over to the VPC page. Select the requester VPC, go down to the details tab and copy the CIDR block.

![](./img/Pasted%20image%20(58).png) 

* Now head back to the edit routes and paste the CIDR block on the 'Destination'

![](./img/Pasted%20image%20(59).png)

* Go back to the vpc window and copy the CIDR block of the acceptor VPC.

![](./img/Pasted%20image%20(60).png)

* Select the requester VPC and click on the main route table of the requester VPC.

![](./img/Pasted%20image%20(61).png)

* Select the route table and click on the route session tab and click 'Edit route'

![](./img/Pasted%20image%20(62).png)




