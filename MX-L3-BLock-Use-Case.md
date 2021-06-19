{{Orchestrating Meraki Policies from SecureX Threat Response}}
=====================================
{{Blocking a destination in MX L3 Security Rules from SecureX Threat Response}

The time required to investigate source of threat & then orchestrate policies in the network to block that threat throughout a large Enterprise Network is critical for organizational security. This code leverages the Meraki API's to orchestrate a deny rule in MX Security policies, which can be trigger directly from Threat Response

To run this workflow, import the code in SecureX Orchestration manually. This will create an Atomic Action which you can use it in your workflow. You need to define HTTP Target as below:

- Display name: Meraki
- Account Keys: No Account Keys - True
- HTTP- Protocol: HTTPS, Host/IP Address: api.meraki.com, port 443, PATH:/api

You need to add this Target into the workflow you are creating. In the workflow, add the "SecureX", "response" in the Category field.

In addition to above, you need below information to be updated in the variables:

 - Meraki API Key
 - Network ID

Once added, you can execute this workflow directly from SecureX Threat Response. You can right click on either IP or domain in your investigation window and you will see your newly created workflow will be listed there
