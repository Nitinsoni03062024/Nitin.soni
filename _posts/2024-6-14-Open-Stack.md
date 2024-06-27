---
layout: post
title: OpenStack Cloud (Private Cloud) ?
---

# About Open Stack

- Platform: Cross-platform software
- Developer: Rackspace Technology
- Initial release: 21 October 2010 13 years ago

# What is OpenStack

OpenStack is a free, open standard cloud computing platform. It is mostly deployed as infrastructure-as-a-service in both public and private clouds, 
it is piesce of softwate when installed on cluster of phisical server offeres the users to create , run and manage virtial machine on top of it along with support to attach the connected storage atong with the networking services in a virtual formte knwo as a infrastructure as a service (IAAS).

> ** These are same composents of OpenStack**

![This is OpenStack Image](../images/openstack-components.jpg)


1. Horizaon (Dashboerd servaices)
2. NOVA  (Compute)
3. Glance (Image Service)
4. Swift (Object Storage)
5. Neutron (Network service)
6. Cinder (Volume service)
7. Hert (Orchestretor)
8. Ceilometer (Telemeter)
9. KeyStone (Identity)


> 1. **Dashboard Service (HORIZON)**

 When we work on any application, the dashboard that we see is what we call horizon in OpenStock. Horizon it's a GUI method of OpenStack service,  

- Provides simple self service UI for end-users
- Basic cloud administrator functions
- Define users, tenants and quotas
- No infrastructure managemen
  
> 2. **Compute Service (NOVA)** 

Nova is the OpenStack project that provides a way provision Compute instance (Aks Virtial Machine), nova support virtial machine, baremetal server and has limited supprt for system containers and nova run as a set of darmons on top of existing linux server to proide that service.

- Compute Nodes – hypervisors that run virtual machines
- Supports multiple hypervisors KVM, Xen, LXC, Hyper-V and ESX
- Distributed controllers that handle scheduling, API calls, etc
- Native OpenStack API and Amazon EC2 compatible API

> 3. **Galnce (Image service) :-** 

This provide the compute iamges repository, all instance launch from glance images

- Image service
- Stores and retrieves disk images (virtual machine templates)
- Supports Raw, QCOW, VMDK, VHD, ISO, OVF & AMI/AKI
- Backend storage : Filesystem, Swift, Gluster, Amazon S3


> 4. **Object Storage Service (Swift)**
 
-  Object Storage service
- Modeled after Amazon's S3 service
- Provides simple service for storing and retrieving arbitrary data
- Native API and S3 compatible API


> 5. **Neutrol Service (Network Service)**

Neutron is an OpenStack project that provides network connectivity as a service (NaaS) in virtual environments

> 6. **Block Storage Service (CINDER)** 

Block storage, object storage and file storage service is called Cinder in OpenStack.
Block Storage (Volume) Service
- Provides block storage for virtual machines (persistent disks)
- Similar to Amazon EBS service
- Plugin architecture for vendor extensions
eg. NetApp driver for Cinde

> 7. **Orchestration Tool**

Template based orchestration that support automatic creation of resources stacks

> 8. **OpenStack Monitoring and Metering (CEILOMETER)**

 Goal: To provide a single infrastructure to collect measurements from an entire OpenStack infrastructure; eliminate need for multiple agents attaching to multiple OpenStack projects
 Primary targets metering and monitoring; 
provides extensibility

> 9. **KeyStone (identity service) :-** 

Provide identity and authentication for all OpenStack Services


> **There have two types nodes planning of openstack**

 1. Single Node
 2. Multi Node

# Keep Learning....


