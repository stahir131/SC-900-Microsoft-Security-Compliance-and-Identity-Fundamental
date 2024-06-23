**# SC-900-Microsoft-Security-Compliance-and-Identity-Fundamental**

**Skills Measured**

**Describe the concepts of security, compliance, and identity**

**Describe the capabilities of Microsoft Entra**

**Describe the capabilities of Microsoft security solutions**

**Describe the capabilities of Microsoft compliance solutions**

**Notes on SC-900 Labs**

Lab 00: Setup - Enable Microsoft 365 audit log

Login to M365 admin portal at admin.microsoft.com

Click on **"Compliance" > Audit**

Click **Start recording user and admin activity**

Close out of Compliance portal

**Module 1: Describe the function and identity types of Microsoft Entra ID**

**Lab_01: Explore Microsoft Entra ID User Settings**

In this lab, you'll access Microsoft Entra ID (previously referred to as Azure Active Directory). Additionally, you'll create a user and configure the different settings, including adding licenses.

Login to M365 admin portal> 

New User Sara Perez was created and added to group "Operations"

Microsoft 365 Business Premium was assigned

**Module 2: Describe the authentication capabilities of Microsoft Entra ID**<br />

**Lab_02: Microsoft Entra self-service password reset**

In this lab, you, as an admin, went through the process of enabling self-service password reset. With SSPR enabled, you'll then assume the role of a user to go through the process of registering for SSPR and also resetting your password. Lastly, you as the admin, learn where to access audit logs and usage & insights data for SSPR

**Module 3: Describe the access management capabilities of Microsoft Entra ID**

**Lab_03: Microsoft Entra Conditional Access**

Scenario: Explore conditional access MFA, as an admin. As the admin, I created a policy that will require user go through MFA when accessing any of the Microsoft Admin portals. From a user perspective, I saw the impact of the conditional access policy, including the process to register for MFA.

**Module 4 : Describe the identity protection and governance capabilities of Microsoft Entra**

**Lab_04: Explore Privileged Identity management**

Exploring Privileged Identity Management(PIM). PIM requires Microsoft Entra ID P2 licensing. In this lab I configured a user ITadmin with a Entra admin role through PIM. This admin role allows ITadmin to be able to create users and groups, manage licenses and more.

**Tasks**

Sign in to entra.microsoft.com

Under "Identity governance" select Privileged Identity management

Unable to proceed with task because my tenant does not have required license
Microsoft Entra ID P2 license

**Module 5: Describe the basic security capabilities in Azure**

**Lab_05: Explore Azure Network Security Groups (NSGs)**<br />
In this lab I explore the function of network security groups in Azure by creating a NSG  and assigning the NSG to the interface of a pre-existing virtual machine. I was able to observe the default inbound and outband rules, create new rules and test those rules. 

What is a Network Security Group: It is a layer of security that acts as a virtual firewall for controlling traffic in and out of virtual machines (via network interfaces) and subnets. It contains a set of security rules that allow or deny inbound and outbound traffic using the following 5-tuple:<br />
1. Protocol
2. Source IP address range
3. Source port range
4. Destination IP address
5. Destination port range

Also a NSG can be associated to many multiple network interfaces and subnets but each network interface or subnet can be associated to only one NSG.

**Task 1**: I created a resource group called SC900-ResGrp and a Network Security group named NSG-SC900. <br />
By default there are no custom security rules and no associated subnets or network interfaces. Default inbound rules deny all inbound traffic that is not from virtual network or an Azure load balancer. The outbound rules allow outbound traffic to internet and to other virtual networks but denies all others.

**Task 2**: I created a Windows 11 virtual machine named sc900-winvm .<br /> When a new azure vm is created other azure swrvices got created like the:
Disk, Network interface, virtual network, network security group and a Public IP address.

Additional network interface can be attached to a virtual machine to enable a vm to communicate with internet, Azure and on-premises resources.<br />

**Task 3**: I created a virtual machine named SC900-WinVM<br />
username: sc900admin<br />
password: Decem@2443$$<br />

I was able to create an Inbound rule on the NSG SC900-vm-nsg to allow RDP traffic.
i.  Source:Any
ii. Source port range: *
iii.Destination: Any
iv. Service: RDP
v.  Action: Allow

I also created 


I also created a NSG outbound rule to deny all traffic to the internet.
1. Source: any
2. SOurce port rages:*
3. Destination: Service Tag
4. Destination service tag: Internet
5. Service: Custom
6. Destination port ranges: *
7. Action: Deny

Cleaning up after getting more familiar with services within azure vm.

Module 6 : **Describe the capabilities of Microsoft security solutions**<br />
Lab_06: Explore Microsoft defender for Cloud**

Lab_07:** Describe the security cababilities of Microsoft Sentinel**
Decsribe threat detection and mitigation capabilities in Microsoft Sentinel.<br />
Microsoft Sentinel is a cloud-native security information and event management (SIEM) platform. It provides attack detection, threat visibility, proactive hunting, and threat response to help you stop threats before they cause harm.

**Task 1:**Create a Microsoft Sentinel instance

![image](https://github.com/stahir131/SC-900-Microsoft-Security-Compliance-and-Identity-Fundamental/assets/64047385/03d8fdb4-f017-4e3a-a13e-24e02631f094)

![image](https://github.com/stahir131/SC-900-Microsoft-Security-Compliance-and-Identity-Fundamental/assets/64047385/32883ed1-9cf5-4519-aaa3-31b409bd40d8)

Once created, click add.

![image](https://github.com/stahir131/SC-900-Microsoft-Security-Compliance-and-Identity-Fundamental/assets/64047385/53180f94-f59d-4a3d-87dc-cda09be9f661)

**Task 2**: Assigning Sentinel role to required users.<br />
It is a good practice to assign Sentinel role to user from the resource group level.<br />
To do this navigate to the "SC900-Sentinel-RG" click on the "Access control(IAM)" > Click "Roles" and search for Microsoft Sentinel > View some roles. Best practice is to assign the least privilege required for the role.<br />
**Task 3: Connecting to data source in Microsoft Sentinel**<br />
The Content hub is the centralized locaion to discover and manage out-of-the-bos(built-in) content. I used the content hub to deploy Microsoft Defender for Cloud solution for Microsoft Sentinel. This will allow to ingest security alerts from Microsoft Defender for Cloud.<br />
**Task 3: Connecting to data source**
Find and click the Microsoft Sentinel created "sc900-loganalytics-workspace" > click Content management > Content hub > Find Microsoft Defender for cloud > Select and install

![image](https://github.com/stahir131/SC-900-Microsoft-Security-Compliance-and-Identity-Fundamental/assets/64047385/3c941529-1606-4547-b0f0-a247487d491c)

Once installed, click on it and select "Manage". There are 2 Data Connectors and one Analytic Rule as shown below. The orange triangle indicates that some configuration need to be done. 

![image](https://github.com/stahir131/SC-900-Microsoft-Security-Compliance-and-Identity-Fundamental/assets/64047385/2e5c9a2c-1571-4ac9-9863-89de0b0eae2c)

Select "Subscription-based Microsoft Defender for Cloud (Legacy)" and select "Open connector page"

![image](https://github.com/stahir131/SC-900-Microsoft-Security-Compliance-and-Identity-Fundamental/assets/64047385/cfa96a0b-5488-4558-92d3-c537877d11ec)

Check the box next to the subscription name and select Connect

![image](https://github.com/stahir131/SC-900-Microsoft-Security-Compliance-and-Identity-Fundamental/assets/64047385/f54ff7be-80f8-428d-b86d-4f6e749c5509)

Select OK on the next pop-up. The status shows connected




