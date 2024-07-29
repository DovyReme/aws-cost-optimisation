# Key Cost Components
- Data Transfer Charges
  - How much data goes out?
- Service Usage Hourly Charges
  - How many NAT Gateways? (NAT GW Hours in CE)
- Service Data Processing Charges
  - How much data is processed? Through NAT etc. (NAT GW Bytes in CE)

# Data Transfer Charges
## Data Transfer Internet
- Data IN - No cost
- Data OUT - $/GB
## Data Transfer Cross-Region
- Data IN - No cost
- Data OUT - $/GB
## Data Transfer Cross-AZ (Regional DT)
- Data IN - $0.01/GB
- Data OUT - $0.01/GB
#### NOTE: Viewing AZs from different account might show as different names (1a might be 1c etc.) We need to stick to zone ID, not zone name.


# Cloud Networking
- Public IP Usage
- VPC Endpoint
  - Great way to reduce cost to use route table.
  - Use interface endpoints as they are much cheaper 0.01$/G+0.01$/hour)
- VPC Peering
  - No cost if data stays within AZ
- Transit Gateway
  - $/hour per attachment + data through / GB
  - Lower costs by centralising NAT gateways for many VPCs via one transit gateway.
- Elastic Load Balancers
  - Cost per hour + Per LCU/h.
  - For ALB no matter is it passing the AZ.
  - For NLB costs for cross AZ data transfer.
  - 
# Hybrid Networking
- Site-to-Site VPN 
  - Cost $/hour
  - DTO VPN $/GB
- Direct Connect
  - Cost $/h (4:52)
# What's Next?