# VMworld US 2016 Breakout Sessions

Below you will find two lists which contains all VMworld US 2016 Break sessions organized by either online playback URL or if you wish to download the videos for offline viewing. Enjoy!

## Session Playback URLs
For complete list of all session playback URLs, please see **[playback-urls.md](playback-urls.md)**

## Session Download URLs
~~For complete list of all session download URLs, please see **[download-urls.md]()**~~ (Due to changes made on Media Site, the download URLs are no longer valid)

## Session JSON Files
For those interested in extracting more information from the raw data, I have also published a snapshot of the VMworld sessions in JSON.

* [most_popular_session.json](most_popular_session.json)
* [all_general_session.json](all_general_session.json)
* [all_spotlight_session.json](all_spotlight_session.json)
* [cloud_infrastructure.json](cloud_infrastructure.json)
* [cloud_native_apps.json](cloud_native_apps.json)
* [cloud_management.json](cloud_management.json)
* [devops.json](devops.json)
* [end_user_computing.json](end_user_computing.json)
* [hybrid_cloud_vcloud_air_network.json](hybrid_cloud_vcloud_air_network.json)
* [hybrid_cloud_vcloud_air.json](hybrid_cloud_vcloud_air.json)
* [hyper_converged_infrastructure_and_storage.json](hyper_converged_infrastructure_and_storage.json)
* [networking_and_security.json](networking_and_security.json)
* [software_defined_datacenter.json](software_defined_datacenter.json)
* [technology_futures.json](technology_futures.json)
* [virtualizing_applications.json](virtualizing_applications.json)

Here's quick PowerShell snippet on how you might retrieve some of the details:

```console
$json = Get-Content -Raw -Path ./cloud_infrastructure.json | ConvertFrom-Json

$session_example = $json.PresentationDetailsList[0]

$session_example.Name
INF8172 - vSphere Client Roadmap: Host Client, HTML5 Client, and Web Client

$session_example.Presenters
Id             : 058f2ba310b545169fbedeba74b24ddd2a
Name           : Dennis Lu, VMware
Prefix         :
FirstName      :
MiddleName     :
LastName       : Dennis Lu, VMware
Suffix         :
BioUrl         :
Email          :
ImageName      :
ImageUrl       :
AdditionalInfo :
Hash           : 1653170437
ParentResource : 303ff270-e939-4300-9e8e-8cb17fbdfa47

Id             : 27fe55cb0afc4d6895782bc3d068a73b2a
Name           : Radostin Tsanev, VMware
Prefix         :
FirstName      :
MiddleName     :
LastName       : Radostin Tsanev, VMware
Suffix         :
BioUrl         :
Email          :
ImageName      :
ImageUrl       :
AdditionalInfo :
Hash           : 808722679
ParentResource : 303ff270-e939-4300-9e8e-8cb17fbdfa47
```

## Session View Statistics

One thing I had noticed on the VMworld site when watching a session is that it includes a "Views" count. I thought it would be cool to share some of the statistics on top views from our customers/partners and what sessions they found interesting. Below are the results for the Top 10 for all VMworld sessions as well as Top 10 for each category. I will periodically update the site with the latest snapshot of the data.

**Last Updated: 10/31/16**

## Top VMworld US 2016 Sessions
|# |Session|Views|
|---|---|---|
| 1 | INF9047 - Managing vSphere 6.0 Deployments and Upgrades | 1020 |
| 2 | INF8225 - The vCenter Server and Platform Services Controller Guide to the Galaxy | 916 |
| 3 | INF8430 - vSphere 6.x Host Resource Deep Dive | 600 |
| 4 | NET7514 - PowerNSX and PyNSXv: Using PowerShell and Python for Automation and Management of VMware NSX for vSphere | 585 |
| 5 | INF8255 - Evolving the vSphere API for the Modern Era | 583 |
| 6 | NET7907 - Advanced Network Services with NSX | 537 |
| 7 | INF8108 - Extreme Performance Series: vCenter Performance Deep Dive | 451 |
| 8 | CNA7741 - From Zero to VMware Photon Platform | 441 |
| 9 | NET7861R - Multisite Networking and Security with Cross-vCenter NSX: Part 2 | 401 |
| 10 | STO7534 - Virtual SAN - Day 2 Operations | 395 |

## All General Session
|# |Session|Views|
|---|---|---|
| 1 | Monday, August 29 - Competitive Advantage in the Multi-Cloud Era | 283 |
| 2 | Tuesday, August 30 - Competitive Advantage in the Multi-Cloud Era | 259 |

## All Spotlight Session
|# |Session|Views|
|---|---|---|
| 1 | CTO9943 - VMware Chief Technology Officer Panel - Trends and Futures | 230 |
| 2 | STO7875 - A Day in the Life of a VSAN I/O | 106 |
| 3 | INF8045 - vSphere High Availability Best Practices and Tech Preview | 101 |
| 4 | INF9205R - Troubleshooting vSphere 6 Made Easy: Expert Talk | 44 |
| 5 | NET8193R - The Architectural Future of Network Virtualization | 43 |

## Cloud Infrastructure
|# |Session|Views|
|---|---|---|
| 1 | INF8108 - Extreme Performance Series: vCenter Performance Deep Dive | 451 |
| 2 | INF9151 - Getting to Zero: Zero Downtime, Zero Data Loss with vSphere Fault Tolerance | 183 |
| 3 | INF8755R - Troubleshooting vSphere 6: Tips and Tricks for the Real World | 161 |
| 4 | INF9944R - What's New with vCenter Server | 157 |
| 5 | INF8375 - What's New with vSphere | 155 |
| 6 | INF8845 - vSphere Logs Grow Up! Tech Preview of Actionable Logging with vRealize Log Insight | 150 |
| 7 | INF8780R - vSphere Core 4 Performance Troubleshooting and Root Cause Analysis, Part 1: CPU and RAM | 120 |
| 8 | INF8850 - vSphere Platform Security | 117 |
| 9 | INF8045 - vSphere High Availability Best Practices and Tech Preview | 116 |
| 10 | INF8260 - Automated Deployment and Configuration of the vCenter Server Appliance | 111 |

## Cloud Management
|# |Session|Views|
|---|---|---|
| 1 | MGT8770 - Managing Microsoft Azure with the vRealize Suite | 229 |
| 2 | MGT9457 - Understanding the Value of vRealize Network Insight | 129 |
| 3 | MGT8080 - vRealize Reference Architecture: Design, Deploy, and Realize Value at High Speed and Amaze Your Customers! | 112 |
| 4 | MGT8543 - Simpler Extensibility in vRealize Automation 7.0 with the Event Broker | 107 |
| 5 | MGT7685R - Insight into the World of Logs with VMware vRealize Log Insight | 91 |
| 6 | MGT8085 - Save Time With Everything and Anything as a Service (XXXAAS) using vRealize Automation (vRA) | 77 |
| 7 | MGT7751R - A Technical Deep Dive into VMware Integrated OpenStack | 76 |
| 8 | MGT9184 - Day 2 Automated Operations with vRealize Automation 7.0 and the Event Broker Service, a Deep Dive. | 70 |
| 9 | MGT7671 - What's New in VMware Integrated OpenStack Version 3.0! | 67 |
| 10 | MGT9220 - vRealize Automation and NSX Design Experts Panel | 63 |

## Cloud Native Apps
|# |Session|Views|
|---|---|---|
| 1 | CNA7741 - From Zero to VMware Photon Platform | 441 |
| 2 | CNA8986 - Running Docker on Your Existing Infrastructure with vSphere Integrated Containers | 317 |
| 3 | CNA7524 - Photon Platform, vSphere, or Both? | 142 |
| 4 | CNA8986R - Running Docker on Your Existing Infrastructure with vSphere Integrated Containers | 121 |
| 5 | MGT7804 - Container Management with vRealize Automation | 102 |
| 6 | CNA7454 - Introduction to Containers as a Service | 100 |
| 7 | CTO7964 - Cloud Native Buzzwords (Demystified) for Dummies | 96 |
| 8 | CNA8897 - Continuous Integration and Continuous Deployment for Containers: Confidently Promote Your Code into Production | 57 |
| 9 | CNA8145 - From Today to ''CNA'': VMware Technologies and DevOps Frameworks as a Service | 44 |
| 10 | CNA9994-QT - VMware's Cloud Native Stack | 40 |

## DevOps
|# |Session|Views|
|---|---|---|
| 1 | INF8255 - Evolving the vSphere API for the Modern Era | 583 |
| 2 | DEVOP7915 - Network as Code: DevOps Implications of Programmable Infrastructure | 80 |
| 3 | NET7858R - Reference Design for SDDC with NSX and vSphere: Part 2 | 50 |
| 4 | MGT8766 - How IT Can Enable DevOps and Development Teams to Rapidly Deliver and Iterate Robust Applications in a Multicloud Environment including VMware, AWS, Azure and Softlayer | 49 |
| 5 | DEVOP7674 - vRA, API, CI, Oh My! | 46 |
| 6 | MGT8831 - Digital Transformation Through VMware DevOps Code Stream | 46 |
| 7 | DEVOP7730 - DevOps Bootcamp Actual | 46 |
| 8 | MGT8499 - Moving to Infrastructure as Code: How Fannie Mae Is Managing the SDDC with the vRCS Management Pack (aka Project Houdini) | 40 |
| 9 | DEVOP8924 - Building an Actionable Strategy Around DevOps and Platform as a Service (PaaS) | 39 |
| 10 | DEVOP7859 - Real-World DevOps Customer Panel | 36 |

## End User Computing
|# |Session|Views|
|---|---|---|
| 1 | STO7443 - How did VMware IT Achieve a Non-Disruptive Disaster Recovery Test in 90 Minutes for 900 Terabytes of Storage and 2000 Production Virtual Machines? | 190 |
| 2 | EUC9391 - Managing Windows in a Modern Mobile-Cloud Framework | 145 |
| 3 | EUC7799 - Design Horizon the Easy Way with Help from the Horizon Sizing Estimator | 122 |
| 4 | EUC8243R - Troubleshooting 101 for Horizon | 111 |
| 5 | EUC9386 - What’s new with Workspace ONE: Identity meets Mobility | 110 |
| 6 | EUC7998 - The Latest in High-Performance Desktops and Applications with  Horizon 7, Blast Extreme Protocol,  and NVIDIA GRID vGPU | 108 |
| 7 | EUC8822 - Case Study: Large-Scale Deployment of VMware App Volumes and User Environment Manager for 10,000 Seats | 95 |
| 8 | EUC9139 - NSX and Horizon Reference Design: Secure End-User Computing | 75 |
| 9 | EUC8648R - Architecting VSAN for Horizon the VCDX Way | 74 |
| 10 | EUC8521 - The Future of VMware Fusion and Workstation | 74 |

## Hybrid Cloud vcloud Air
|# |Session|Views|
|---|---|---|
| 1 | HBC9092 - vCloud Air: Advanced Networking Concepts | 56 |
| 2 | HBC7948 - Extending Your Data Center to vCloud Air in Less than 60 Minutes | 44 |
| 3 | HBC9401 - Whats New with vCloud Air | 35 |
| 4 | HBC7646 - St. John's University Leverages vCloud Air Disaster Recovery for Its Critical ERP System, Banner | 30 |
| 5 | HBC10827-SPO - Ensure Success of Hybrid Cloud with Amazon Web Services | 29 |
| 6 | HBC8292 - vCloud Air Recovery as a Service (RaaS) Deep Dive | 29 |
| 7 | HBC8805 - Extend Your Data Center to the Cloud: A Real-World Example | 18 |
| 8 | HBC9111 - vRealize Operations and vCloud Air: Monitoring Your Cloud | 18 |
| 9 | HBC8295 - The VMware Journey to Cloud with vCloud Air | 17 |
| 10 | HBC9164 - Modernizing Healthcare IT with the Public Cloud, Your Way! | 13 |

## Hybrid Cloud vcloud Air Network
|# |Session|Views|
|---|---|---|
| 1 | HBC8474 - Making It Easy to Orchestrate and Automate Your Hybrid Cloud Environment | 123 |
| 2 | HBC7830 - Virtualize, Secure, and Extend Your Data Center to the Cloud Using NSX: A Perspective for Service Providers and End Users | 123 |
| 3 | HBC9463-SPO - Data Protection as a service for your vCloud Director environment with Veeam | 78 |
| 4 | HBC7602 - Build True Hybrid Clouds: See How Service Providers Can Use NSX to Extend Customer On-Premises Data Centers | 53 |
| 5 | HBC8491 - Deep Dive: VMware on IBM Cloud Validated Design | 47 |
| 6 | HBC9185 - How to Connect Your On-Premises Data Center to the Cloud | 37 |
| 7 | HBC9949-SPO - Hybrid Cloud: Automated and validated VMware deployments on IBM Cloud | 36 |
| 8 | HBC9171 - Intercontinental vMotion with Purpose | 34 |
| 9 | HBC8046-QT - Customer Onboarding with VMware NSX L2VPN Service for VMware vCloud Air Network | 31 |
| 10 | HBC8503 - Taking VDI and Published Application Environments to the Next Level with App Volumes | 27 |

## Hyper Converged Infrastructure and Storage
|# |Session|Views|
|---|---|---|
| 1 | STO7875 - A Day in the Life of a VSAN I/O | 506 |
| 2 | STO7534 - Virtual SAN - Day 2 Operations | 395 |
| 3 | STO7535 - Conducting a Successful Virtual SAN 6.2 Proof of Concept | 391 |
| 4 | STO7904 - Virtual SAN Management Current & Future | 293 |
| 5 | STO8246R - Virtual SAN Technical Deep Dive and What’s New | 174 |
| 6 | STO8159 - Snapshots Suck: How VSAN and VVol fix all your operational nightmares | 164 |
| 7 | STO9423 - File Services on Virtual SAN | 156 |
| 8 | STO8179R - Understanding the Availability Features of Virtual SAN | 142 |
| 9 | STO8422 - Virtual Volumes: Why? | 113 |
| 10 | STO7973 - Architecting Site Recovery Manager to Meet Your Recovery Goals | 106 |

## Most Popular Session
|# |Session|Views|
|---|---|---|
| 1 | INF9047 - Managing vSphere 6.0 Deployments and Upgrades | 1020 |
| 2 | INF8225 - The vCenter Server and Platform Services Controller Guide to the Galaxy | 916 |
| 3 | INF8430 - vSphere 6.x Host Resource Deep Dive | 600 |
| 4 | NET7907 - Advanced Network Services with NSX | 537 |
| 5 | MGT7924 - vRealize Operations Capacity Explained | 374 |
| 6 | INF7827 - vSphere DRS Deep Dive: Understanding the Best Practices, Advanced Concepts, and Future Direction of DRS | 364 |
| 7 | CTO9943 - VMware Chief Technology Officer Panel - Trends and Futures | 326 |
| 8 | INF8755R - Troubleshooting vSphere 6: Tips and Tricks for the Real World | 297 |
| 9 | CNA7522 - Containers for the vSphere Admin | 261 |
| 10 | VIRT8290R - Monster VMs (Database Virtualization) Doing IT Right | 252 |

## Networking and Security
|# |Session|Views|
|---|---|---|
| 1 | NET7514 - PowerNSX and PyNSXv: Using PowerShell and Python for Automation and Management of VMware NSX for vSphere | 585 |
| 2 | NET7861R - Multisite Networking and Security with Cross-vCenter NSX: Part 2 | 401 |
| 3 | NET8758 - vSphere Distributed Switch Deep Dive | 185 |
| 4 | NET8131R - NSX for vSphere Logical Routing Deep Dive | 184 |
| 5 | NET7854R - Multisite Networking and Security with Cross-vCenter NSX—Part 1 | 164 |
| 6 | NET8364R - How to Deploy VMware NSX with Cisco Infrastructure | 162 |
| 7 | NET8030 - NSX Performance Deep Dive | 130 |
| 8 | NET8194 - How VMware IT Implemented Microsegmentation and Deployed a Large-Scale Private Cloud Using NSX | 122 |
| 9 | NET8241 - Monitoring and Troubleshooting NSX with vRealize Network Insight (Arkin) | 112 |
| 10 | NET8337 - Leveraging NSX for Remote and Branch Offices | 112 |

## Software Defined Datacenter
|# |Session|Views|
|---|---|---|
| 1 | SDDC8621 - VMware Cloud Foundation: Technical Deep Dive | 252 |
| 2 | SDDC9456-SPO - Implementing Self-Service Storage Provisioning with vRealize Automation XaaS | 177 |
| 3 | SDDC8472 - An IT Architect's Guide to the Software-Defined Data Center | 120 |
| 4 | SDDC8414 - VMware Validated Design for SDDC: A Technical Deep Dive | 106 |
| 5 | SDDC8468R - A Beginner's Guide to the Software-Defined Data Center | 99 |
| 6 | SDDC9176 - How VMware Cloud Foundation powers the IBM Cloud | 90 |
| 7 | SDDC7780 - Agile: The Scrum Master for Your Software-Defined Data Center! | 55 |
| 8 | SDDC9404-SPO - Reinventing Disaster Recovery Leveraging Public Cloud Infrastructure | 51 |
| 9 | SDDC9181 - VMware Cloud Foundation Backup and Disaster Recovery | 42 |
| 10 | SDDC7692 - Tips for Realizing the Full Value of Your SDDC Transformation | 35 |

## Technology Futures
|# |Session|Views|
|---|---|---|
| 1 | CTO8519 - Best of Both Worlds: Achieving Ultra-Low VM Network Latencies and Extreme Bandwidth Without Compromise | 80 |
| 2 | CTO9018 - VMware Internet of Things Strategy; Unveiled | 63 |
| 3 | CTO8120 - Debunking the Myths about Virtualizing High Performance Computing | 61 |
| 4 | CTO9002-QT - Artificial Intelligence Is the Future of IT | 55 |
| 5 | CTO9471-SPO - New Capabilities in ONTAP 9 Optimized for All Flash Virtualized Workloads | 45 |
| 6 | CTO9951-SPO - What’s Old Is New Again: Next Generation Storage | 36 |
| 7 | CTO9032 - Is it Possible to Use NSX to Cut WAN Network Costs in Half? | 31 |
| 8 | CTO9996-SPO - Fortifying the Cloud: What the New Samsung-VMware Partnership Means | 28 |
| 9 | CTO9036 - Providing Management Tools for the Emerging IoT Infrastructure | 24 |
| 10 | CTO8995-QT - How Do You Manage Security Vs Privacy in IoT Beyond Device Management? | 23 |

## Virtualizing Applications
|# |Session|Views|
|---|---|---|
| 1 | VIRT8290R - Monster VMs (Database Virtualization) Doing IT Right | 251 |
| 2 | VIRT9009 - Licensing SQL Server and Oracle  on vSphere | 211 |
| 3 | VIRT9034 - Oracle Databases Licensing on a Hyper-Converged Platform | 149 |
| 4 | VIRT7620 - Successfully Virtualize and Operate Your Microsoft Skype for Business Infrastructure on the VMware vSphere Platform | 117 |
| 5 | VIRT7598 - Extreme Performance Series: Monster VM Database Performance | 113 |
| 6 | VIRT8530R - Deep Dive on pNUMA & vNUMA - Save Your SQL VMs from Certain DoomA! | 96 |
| 7 | VIRT7840 - VMware and Microsoft Present: Successfully Virtualizing Microsoft Exchange Server, the Right Way | 96 |
| 8 | VIRT7511 - Performance Tuning and Monitoring for Virtualized Database Servers | 90 |
| 9 | VIRT7654 - SQL Server on vSphere: A Panel with Some of the World's Most Renowned Experts | 87 |
| 10 | VIRT7941 - The Best of Both Words: Achieving SQL Server High Availability with VMware | 75 |
