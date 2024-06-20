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
Microsoft Entra ID p2 license

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

**Task 2**: I created a network interface named sc900-winvmXXX to be associated to NSG-SC900 and attached to virtual machine SC900-WinVM.<br />
A network interface can be attached to a virtual machine to enable a vm to communicate with internet, Azure and on-premises resources.<br />

**Task 3**: I created a virtual machine named SC900-WinVM<br />
username: sc900admin<br />
password: Decem@2443$$




















