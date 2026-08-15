
**Datacenters:**
	- Facilities with servers in racks with dedicated power, cooling and network infrastructure. Like on-prem infrastructure, but much larger.
	- With Azure, you don't interact with singular datacenters. More of a full region of them called 'Azure regions' and 'azure availability zones'. These provide resiliency and reliability.
![[Pasted image 20260624145309.png]]

**Regions:**
	- A geographical area where one or more datacenters are nearby to each other, networked and have low latency. Azure assigns and controls resources automatically to ensure workloads are balanced.
	- Some services (VM's) are not available in every location and require a specific region.

**Availability zones:**
	- Physically separate datacenters within an azure region with its own power, cooling and networking.
	- They're set up to be an isolation boundary. Meaning if one goes down, the other is there for redundancy.
	- They are all connected through high speed, private fiber-optic networks.
	- To ensure resiliency, there are a minimum of 3 separate availability zones in each region. But not all regions support zones.
![[Pasted image 20260624150123.png]]

**Using availability zones for workarounds**
	- Protect workloads by spreading across multiple zones in a region.
	- Place all VM's, storage, databases ect and replicate across multiple zones within the same region. There is a cost to this duplication and transferring data between zones.
	
Azure Services that support availability zones fall into 3 catagories:
	- Zonal - Pin the resource to a specific zone (VM's, managed discs, IP address')
	- Zone-redundant services: The platform replicates automatically across zones (for example, zone-redundant storage, SQL Database).
	- Non-regional services: Services are always available from Azure geographies and are resilient to zone-wide outages as well as region-wide outages.
![[Pasted image 20260624151034.png]]

**Region Pairs**
	- If a major attack/fail happens that effects multiple availability zones in a region, Azure has pairs for additional redundancy.
	- Usually in the same Geography (US, Europe, Asia) at least 300 miles away.
	- Allows replication incase of disaster (power cut/war/natural disasters ect). So, if a region in a pair was affected by one of these, services are automatically failed over to the other region of it's pair.
	- Not all services are auto-replicated. Users are advised to set up their own back-ups for these services.
![[Pasted image 20260624152219.png]]

**Additional advantages of Regional Pairs**
	- If an extensive Azure outage occurs, one region out of every pair is prioritized to make sure at least one is restored as quickly as possible for applications hosted in that region pair.  
	- Planned Azure updates are rolled out to paired regions one region at a time to minimize downtime and risk of application outage.   
	- Data continues to reside within the same geography as its pair (except for Brazil South) for data-residency and compliance purposes.
	- Most regions are paired in two directions, meaning they are the backup for the region that provides a backup for them (West US and East US back each other up). However, some regions, such as Brazil South, are paired in only one direction. In a one-direction pairing, the Primary region does not provide backup for its secondary region. Brazil South is unique because it's paired with a region outside of its geography. Brazil South's secondary region is South Central US. The secondary region of South Central US isn't Brazil South. Additionally, some regions (such as Italy North, Poland Central, and Israel Central) don't have a traditional region pair and instead rely on availability zones and geo-redundant storage for resiliency.

**Sovereign Regions**
	- These are instances of azure that are isolated from the main instance of azure.
	- Sometimes these are used for compliance or legal purposes.
	For example:
		- US DoD Central, US Gov Virginia, US Gov Arizona, and more: These regions are physical and logical network-isolated instances of Azure for U.S. government agencies and partners. These datacenters are operated by screened U.S. personnel and include additional compliance certifications.
		- China East, China North, and more: These regions are available through a unique partnership between Microsoft and 21Vianet, whereby Microsoft doesn't directly maintain the datacenters.