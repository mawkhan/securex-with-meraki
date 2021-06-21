# securex-with-meraki
Cisco SecureX Workflows with Meraki MX Firewall


# Blocking a destination in MX L3 Security Rules from SecureX Threat Response

The time required to investigate source of threat & then orchestrate policies in the network to block that threat throughout a large Enterprise Network is critical for organizational security. This code leverages the Meraki API's to orchestrate a deny rule in MX Security policies, which can be trigger directly from Threat Response


{{Configuration Steps}

1) Logged into https://securex.cisco.com/ and navigatte to SecureX orchestration
2) Define targets by navigating to Targets on the left hand side as show below:

![1](https://user-images.githubusercontent.com/86117124/122742851-bb71f800-d2c9-11eb-8ab1-09cabf632339.png)

3) Add new target with below settings:

- Display name: Meraki
- Account Keys: No Account Keys - True
- HTTP- Protocol: HTTPS, Host/IP Address: api.meraki.com, port 443, PATH:/api

![12](https://user-images.githubusercontent.com/86117124/122756621-fed46280-d2d9-11eb-9b36-b3f0b1b78ad1.png)

![13](https://user-images.githubusercontent.com/86117124/122756629-0267e980-d2da-11eb-9e4c-38ad311e4b7a.png)


4) Now goto "workflows", choose "atomic" and select import as shown below:

![2](https://user-images.githubusercontent.com/86117124/122753545-c3d03000-d2d5-11eb-8451-a9a5a20d3bcc.png)

5) Click on import and then paste the code which you have copied from this repository and then click import

![3](https://user-images.githubusercontent.com/86117124/122753560-c92d7a80-d2d5-11eb-93d9-71db401edf23.png)

6) Now Atomic Action has been imported, open the newly imported Atomic Action

![4](https://user-images.githubusercontent.com/86117124/122753569-cdf22e80-d2d5-11eb-93b8-626155edcaa9.png)

7) Now you have to update the two variables " Meraki API Key" & " Network ID". Network ID will be the ID of your Meraki Network. Also you need to update the Target which you have created earlier

![5](https://user-images.githubusercontent.com/86117124/122753578-d2b6e280-d2d5-11eb-91b9-1443633537c6.png)

![11](https://user-images.githubusercontent.com/86117124/122755965-19f2a280-d2d9-11eb-9337-1f89959c6ab8.png)

8) At this stage, you are ready to Run this workflow directly from same window or you can execute this from SecureX Threat Response. Open the threat response page, start any investigation and then from the observable graph, you can righ click on any observable ( IP or Domain ) and select the workflow which you have just imported "Blocking URL/IP in Meraki MX Firewall

![6](https://user-images.githubusercontent.com/86117124/122753593-d6e30000-d2d5-11eb-8bc5-6831597cfb3d.png)

![7](https://user-images.githubusercontent.com/86117124/122753609-dc404a80-d2d5-11eb-9aea-4092e17aecb7.png)

9) Now go back to orchestration page where atomic action was already open, you can click on "view Runs" to validate whether your workflow was sucessfully executed

![8](https://user-images.githubusercontent.com/86117124/122753624-e19d9500-d2d5-11eb-96ec-27426ca89a43.png)

![9](https://user-images.githubusercontent.com/86117124/122753638-e5311c00-d2d5-11eb-9e9c-72fcd63955dd.png)

![10](https://user-images.githubusercontent.com/86117124/122753654-e8c4a300-d2d5-11eb-82ec-58a09a2afa06.png)

You have now seccessfully orchestrate a Layer 3 deny rule while doing threat hunting from SexureX Threat Response
