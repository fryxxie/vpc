---

copyright:
  years: 2018, 2021
lastupdated: "2021-07-19"

keywords: quotas, vpc, resources, limits

subcollection: vpc


---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:external: target="_blank" .external}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:note: .note}
{:download: .download}

# Quotas and service limits
{: #quotas}

This document covers quotas and limits for {{site.data.keyword.vpc_full}} and the resources available within it.
{:shortdesc}

## Quotas
{: #vpcquotas}

The following tables show the quotas for various VPC resources.

To increase a quota for a particular resource, [contact support](https://{DomainName}/unifiedsupport/cases/form){: external}.
{:note}

### Compute resources
{: #vsi-quotas}

|   Resource     | Quota |
| ------- | ------ |
| vCPU |  200 per region  |
| RAM | 1600 GB per region |
| Bare metal servers | 25 per account |
| Instance storage | 18 TB per region |
| Floating IP addresses | 20 per zone |
| SSH keys | 200 per account |
{: caption="Table 1. Quotas for virtual server instances" caption-side="top"}

When you provision virtual server instances and dedicated hosts, the vCPU associated with these resources counts toward the vCPU quotas per region. Instances that are provisioned on dedicated hosts do not count against the vCPU quota. 

When you provision virtual server instances, the RAM and instance storage, along with vCPU, that is associated with the instances count toward the vCPU, RAM, and instance storage quotas per region.

### VPCs
{: #vpc-quotas}

|   Resource     | Quota |
| ------- | ------ |
| Virtual private clouds | 10 per region|
| Subnets | 15 per VPC |
| Address prefixes | 15 per VPC |
{: caption="Table 2. Quotas for the VPC service" caption-side="top"}

### Access control lists
{: #acl-quotas}

|Resource|Quota|
|--------|-----|
|ACLs| 25 per VPC |
|Rules| 100 per ACL |
{: caption="Table 3. Quotas for access control lists" caption-side="top"}

### Security groups
{: #security-group-quotas}

|Resource|Quota|
|--------|-----|
|Security groups|50 per VPC|
|Security groups| 5 per network interface (NIC) on a virtual server instance |
|Rules|50 per security group|
|Network interfaces|1000 per security group|
{: caption="Table 4. Quotas for security groups" caption-side="top"}

### VPN gateways
{: #vpn-quotas}

|Resource|Quota|
|--------|-----|
| VPN gateways| 9 per region, 3 per zone |
| VPN connections | 10 per VPN gateway |
| IKE policies | 20 per region |
| IPSec policies | 20 per region |
| Peer subnets | 50 across all connections of a VPN gateway, 15 per individual VPN connection |
| Local subnets | 50 across all connections of a VPN gateway, 15 per individual VPN connection |
| Route-based VPN gateway | 1 per zone per VPC |
{: caption="Table 5. Quotas for the site-to-site VPN gateway service" caption-side="top"}

### Load balancers
{: #load-balancer-quotas}

|Resource|Quota|
|--------|-----|
| Load balancers | 50 per region |
| Listeners | 10 per load balancer |
| Pools | 10 per load balancer |
| Members | 50 per pool |
| Policies | 10 per listener |
| Rules | 10 per policy |
| Security Groups | 5 per load balancer |
{: caption="Table 7. Quotas for load balancers" caption-side="top"}

### Distributed network load balancers
{: #dnlb-quotas}

All quotas as per region.
{: note}

| Entity                                | Quota | Comment                                                       |
| ------------------------------------- | ----- | ------------------------------------------------------------- |
| Number of service DNLBs in an account |  12 | Number of load balancers per account across all VPCs in the account |
| Number of service DNLBs in a VPC      |  12 | Number of load balancers per account per VPC |
| Number of listeners in load balancer  |  25 | Number of listeners per load balancer |
| Number of pools in load balancer      |  25 | Number of pools per load balancer |
| Number of members in a Pool           | 100 | Number of members per pool |
| Number of members on vNIC             |  25 | Number of members per vNIC |
{: caption="Table 8. Quotas for service distributed network load balancers" caption-side="top"}

### Routing tables and routes
{: #routing-tables-routes-quotas}

|Resource|Quota|
|--------|-----|
| Routing tables per VPC | Default limit: 15<br />Maximum limit: 200 |
| Routes per routing table | Default limit: 100<br />Maximum limit: 400 |
{: caption="Table 9. Quotas for routing tables and routes" caption-side="top"}

Each route has a destination property, which includes a prefix length (`/24` in `10.2.0.0/24`). The number of unique prefix lengths that are supported per custom routing table is 14. Multiple routes with the same prefix count as only one unique prefix.
{: note}

### Block storage volumes
{: #block-storage-quotas}

|Resource|Quota|
|--------|-----|
| Boot and secondary volumes | 300 total Gen 2 volumes per account in a region |
{: caption="Table 10. Quotas for block storage volumes" caption-side="top"}

You can increase this quota by opening a [support case](/docs/vpc?topic=vpc-getting-help) and specifying in which zone you need more volumes. Use this [support form](/docs/get-support?topic=get-support-using-avatar).

If you already have block storage volumes for Gen 1 Compute instances, you are limited to 300 total volumes for Gen 1 and Gen 2. For example, if you have 200 Gen 1 block storage volumes, you can request 100 Gen 2 block storage volumes for a total of 300.
{: note}

### Placement groups
{: #placement-group-quotas}

|Resource|Quota|
|--------|-----|
| Placement groups | 100 placement groups per account in a region |
| Instances | 12 instances per placement group per region with host_spread placement policy. |
| Instances | 4 instances per placement group per region with power_spread placement policy. |
{: caption="Table 11. Quotas for placement groups" caption-side="top"}

For the Beta release, the quotas for placement groups are set and can't be adjusted.
{: note}

## Service limits
The following table displays current VPC service limits. Unlike quotas, these limits can't be adjusted.

|Resource|Limit|
|--------|-----|
| VPCs with classic access | 1 per region|
| Network interfaces | 5 per instance |
| PCI network interfaces for bare metal servers | 8 per bare metal server |
| Public Gateways | 1 per zone per VPC |
| Remote rules for security groups |5 per security group|
| Secondary volumes per instance, attached when creating an instance |  4 secondary volumes |
| Secondary volumes per instance, for existing instances with fewer than 4 cores | 4 secondary volumes |
| Secondary volumes per instance, for existing instances with 4 cores or more | Up to 12 secondary volumes |
| Instance groups for auto scale and more | 200 per account|
| Instance group memberships  | 1000 per instance group|
{: caption="Table 12. Limits for VPC resources" caption-side="top"}
