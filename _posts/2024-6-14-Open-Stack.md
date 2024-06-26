---
layout: post
title: OpenStack Cloud (Private Cloud) ?
---

# About Open Stack

- Platform: Cross-platform software
- Developer: Rackspace Technology
- Initial release: 21 October 2010; 13 years ago

# What is OpenStack

OpenStack is a free, open standard cloud computing platform. It is mostly deployed as infrastructure-as-a-service in both public and private clouds, 
it is piesce of softwate when installed on cluster of phisical server offeres the users to create , run and manage virtial machine on top of it along with support to attach the connected storage atong with the networking services in a virtual formte knwo as a infrastructure as a service (IAAS).

> **OpenStack has 4 principles**

1. Open Soureces
2. Open Design
3. Open Development
4. Open Community

![This is a OpenStack Images](../images/OpenStack-Architecture.png)

**Bare Metal**

In computer networking, a bare-metal server is a physical computer server that is used by one consumer, or tenant only.

**Approx 40 services is avialebl in OpenStack**

![This is same service of open stack](../images/oen.png)

1. **Dashboard Service (HORIZON)** :-

 When we work on any application, the dashboard that we see is what we call horizon in OpenStock. Horizon it's a GUI method of OpenStack service,  

 Dashboard
- Provides simple self service UI for end-users
- Basic cloud administrator functions
- Define users, tenants and quotas
- No infrastructure managemen

![This is image of horizon server GUI](../images/horizonservice.png)


2. **Compute Service (NOVA)** 

Nova is the OpenStack project that provides a way provision Compute instance (Aks Virtial Machine), nova support virtial machine, baremetal server and has limited supprt for system containers and nova run as a set of darmons on top of existing linux server to proide that service.

- Compute Nodes – hypervisors that run virtual machines
- Supports multiple hypervisors KVM, Xen, LXC, Hyper-V and ESX
- Distributed controllers that handle scheduling, API calls, etc
- Native OpenStack API and Amazon EC2 compatible API


   > -  **This services is must after nove installtion**

3. **KeyStone (identity service) :-** Provide identity and authentication for all OpenStack Services
   
4. **Galnce (Image service) :-** 
   
   This provide the compute iamges repository, all instance launch from glance images

- Image service
- Stores and retrieves disk images (virtual machine templates)
- Supports Raw, QCOW, VMDK, VHD, ISO, OVF & AMI/AKI
- Backend storage : Filesystem, Swift, Gluster, Amazon S3


5. **Neutron (Network service):-** This is responable for provisioing the virtual physical network that the compute instacne connecct to on boot,

6. **Placement :-**  This is tracking for inventroy available in a cloud AND assisting which provide og those will be used when creating virtual machine

7. **Block Storage Service (CINDER)**

Block storage, object storage and file storage service is called Cinder in OpenStack.

Block Storage (Volume) Service
- Provides block storage for virtual machines (persistent disks)
- Similar to Amazon EBS service
- Plugin architecture for vendor extensions
eg. NetApp driver for Cinde

8. **Network Service (Neutron)**

Network related all service coming under the network services (neutron)

Network Service 
- Provides framework for Software Defined Network (SDN)
- Plugin architecture 
- Allows integration of hardware and software based network solutions

9. **Image Storge Service (Glance)**

Whenever we launch any instance (VM's), to launch that instance or VM we need an ISO image which we call glance in openstack.

10. **Object Storage Service (Swift)**
   
-  Object Storage service
- Modeled after Amazon's S3 service
- Provides simple service for storing and retrieving arbitrary data
- Native API and S3 compatible API

   Swift service it's a swift service

11.  **Indentity Service (KeyStone)**
   
Keystone is an OpenStack service that provides API client authentication, service discovery, and distributed multi-tenant authorization by implementing OpenStack's Identity AP,

This is a mostinportant service, from the user managment and which service where is runing all over mamanged from keystone service.

1.  **OpenStack Monitoring and Metering (CEILOMETER)**

- Goal: To provide a single infrastructure to collect measurements from an entire OpenStack infrastructure; eliminate need for multiple agents attaching to multiple OpenStack projects
- Primary targets metering and monitoring; 
provides extensibility

> **hardware Requriment for Deployment of OpenStack**

![This is image of OpenStack](../images/hwreqs.png)


> # Step By Step Instance VM (NOVA) Creation Flow of OpenStack.


> We can unedersatant from this image,

![This is NOVA Working Flow](../images/NOVA-work-flow.webp)

{% highlight ruby %}

nova boot --flavor m1.small --image centos7 --nic net-id={private_network_id} --security-group norprod_sec_grp  --key-name my_key stack_testvm 

{% endhighlight %}

- Step:1 
  
  The Horizon Dashboard or OpenStack CLI gets user credentials and authenticates with identity service via REST API.

        - The identity service (Keystone) authenticate the user with the user credentials and then generates and send back an auth-token, that auth-token which will be used for sending the request to other components through REST-Call
  
- Step:2 

The Dashboard or OpenStack CLI converts new instance request specified in launch instance or nova boot command to a REST API request and sent it to nova-api
  
-  Step:3 
  
Then nova-api service gets the request and send that request to the identity service (Keystone) for validation of auth-token and access permission,

      - Keystone service validates the token and send the updated authentication headers with roles along with the permissions
  
- Step:4 
  
After getting the repsonse from keystone, then  nova-api checks for conflicts with nova-database and then it creates initial database entry for new instance or VM.
  
- Step:5 
  
nova-api sends the rpc.call request to nova-scheduler expecting to get updated instance entry with host id specified
  
- Step:6 
  
Now nova-scheduler picks the request from the queue
  
- Step:7 
  
nova-scheduler talks to nova-database to locate an appropriate host using filtering and weighing mechanism,4
  
        -  nova-scheduler returns the updated instance entry with the appropriate host ID after filtering and weighing
         nova-scheduler sends the rpc.cast request to nova compute for launching an instance on the appropriate host

- Step:8 
  
nova-compute picks the request from the queue and it sends the rpc.call request to nova-conductor to get the VM or instance info such as host id and flavor (RAM,CPU and Disk)

- Step:9 
  
nova-conductor takes the request from queue and communicate with nova-database,

          - nova-conductor gets the instance information
            now nova-compute picks the instance information from the queue

- Step:10 
  
nova-compute connects to glance-api by making a REST Call using auth-token and then nova-compute uses the image id to get the image URI from image service and loads the image from image storage
  
- Step:11 
  
glance-api validates the auth-token with keystone and after that nova-compute gets the image metadata
  
- Step:12 
  
Nova-compute make the REST-call by passing the auth-token to Network API (Neutron) to allocate and configure network so that vm gets the IP address

- Step:13 
  
Neutron-server validates the auth-token with keystone and after that nova-compute retrieves the network information.
  
- Step:14 
  
Nova-Compute makes the REST-call by passing the auth-token to Volume API to attach the volume to the instance or VM.
  
- Step:15 
  
cinder-api validates the auth-token with keystone and then nova-compute gets the block storage information.

- Step:16 
  
nova-compute generates data for the hypervisor driver and executes the request on the hypervisor using libvirt or API and then finally a VM is created on the hypervior. We can see that VM in Dashboard and also using “nova list” command.



# Keep Learning....


