# viptela-meraki-integration

This toolkit enables Meraki and Umbrella customers to streamline always on connectivity from a Cisco Meraki Branch site to Cisco Viptela Vedge. Extending secure and automated connectivity to between Cisco Meraki Branch sites and Vedge Hubs.

# Architecture
image

1) Obtain Cisco Meraki API Key and Org Name

    a) The API Key and Org Name will be needed for the script to configure your Meraki device. 

    b) To view your Organization name navigate to Organization > Settings, the name will be displayed at the top. (As seen below)
    
    c) For access to the API, first enable the API for your organization. 

    d) Navigate to Organization > Settings > Dashboard API access 

    e) Enable the API 
    
    f) Navigate to the my profile page and generate an API key 

     Note: The API key is associated with a Dashboard administrator account.   

# Cisco Meraki Workflow 

Initially, there will be no tagged Meraki networks so the script will sleep and perform the same GET to obtain any networks with the relevant tag. In order to deploy a new branch, the user would navigate to Organization > Overview and select the checkbox next to the network that you wish to connect. 

Once the network is tagged appropriately, connectivity is then automatically established. A customer VPN tunnel in the Umbrella dashboard is created with a matching network name to that of the Meraki branch. Site1 will be named Site1 in both the Vmanage and Meraki dashboard. Additionally, a site to site VPN will appear on the site to site VPN page. (As seen below)

Note: The script also assumes VPN is already turned on for the specific MX. For the tunnel to come up, interesting traffic needs to be generated.

Once interesting traffic has been generated, the tunnel will appear up in both the Meraki and Vmanage Dashboards:

Additionally, in the Meraki Event Log, a event with a timestamp is generated when the tunnel becomes established:

# Additional References 

https://documentation.meraki.com/zGeneral_Administration/Organizations_and_Networks/Organization_Menu/Manage_Tags 

https://documentation.meraki.com/zGeneral_Administration/Support/Contacting_Support
