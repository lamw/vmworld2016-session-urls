# VMworld US 2016 Breakout Sessions

Below you will find two lists which contains all VMworld US 2016 Break sessions organized by either online playback URL or if you wish to download the videos for offline viewing. Enjoy!

## Session Playback URLs
For complete list of all session playback URLs, please see **[playback-urls.md](playback-urls.md)**

## Session Download URLs
For complete list of all session download URLs, please see **[download-urls.md](download-urls.md)**

## Session JSON Files
For those interested in extracting more infromation from the raw data, I have also published a snapshot of the VMworld sessions in JSON.

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

**Last Updated: 09/26/16**

## Top VMworld US 2016 Sessions
|# |Session|Views|
|---|---|---|
| 1 | INF9047 - Managing vSphere 6.0 Deployments and Upgrades | 794 |
| 2 | INF8225 - The vCenter Server and Platform Services Controller Guide to the Galaxy | 633 |
| 3 | NET7514 - PowerNSX and PyNSXv: Using PowerShell and Python for Automation and Management of VMware NSX for vSphere | 534 |
| 4 | INF8255 - Evolving the vSphere API for the Modern Era | 485 |
| 5 | INF8430 - vSphere 6.x Host Resource Deep Dive | 480 |
| 6 | NET7907 - Advanced Network Services with NSX | 457 |
| 7 | STO7875 - A Day in the Life of a VSAN I/O | 422 |
| 8 | INF8108 - Extreme Performance Series: vCenter Performance Deep Dive | 372 |
| 9 | STO7534 - Virtual SAN - Day 2 Operations | 355 |
| 10 | STO7535 - Conducting a Successful Virtual SAN 6.2 Proof of Concept | 341 |

## All General Session
|# |Session|Views|
|---|---|---|
| 1 | Monday, August 29 - Competitive Advantage in the Multi-Cloud Era | 207 |
| 2 | Tuesday, August 30 - Competitive Advantage in the Multi-Cloud Era | 179 |

## All Spotlight Session
|# |Session|Views|
|---|---|---|
| 1 | EUC10682-S - Delivering the Digital Workspace: The Transformation of End-User Computing | 256 |
| 2 | SDDC8618-S - Introducing VMware Cloud Foundation | 151 |
| 3 | SDDC7808-S - How I Learned to Stop Worrying and Love Consistency: Standardizing Datacenter Designs | 105 |
| 4 | CTO10624-S - Are you ahead of the IoT curve | 96 |
| 5 | CNA9993-S - Cloud Native Applications, What it means & Why it matters | 68 |
| 6 | INF9947-S - Spotlight on vSphere: Today, Tomorrow, and Beyond | 60 |
| 7 | HBC9363-S - Virtualization 2.0: How the Cloud Is Evolving the Modern Data Center | 48 |
| 8 | CTO9978-S - Digital Transformation - Technology & Business Futures, A CTO's Perspective | 35 |
| 9 | SDDC9035-S - SDDC and Hyperconverged has Arrived – Get on Board! | 34 |
| 10 | STO9424-S - Taking HCI Mainstream | 21 |

## Cloud Infrastructure
|# |Session|Views|
|---|---|---|
| 1 | INF8108 - Extreme Performance Series: vCenter Performance Deep Dive | 372 |
| 2 | INF9151 - Getting to Zero: Zero Downtime, Zero Data Loss with vSphere Fault Tolerance | 134 |
| 3 | INF9944R - What's New with vCenter Server | 122 |
| 4 | INF8755R - Troubleshooting vSphere 6: Tips and Tricks for the Real World | 118 |
| 5 | INF8845 - vSphere Logs Grow Up! Tech Preview of Actionable Logging with vRealize Log Insight | 108 |
| 6 | INF8375 - What's New with vSphere | 85 |
| 7 | INF8850 - vSphere Platform Security | 83 |
| 8 | INF8038r - Getting Started with PowerShell and PowerCLI for Your VMware Environment (Copy) | 81 |
| 9 | INF8260 - Automated Deployment and Configuration of the vCenter Server Appliance | 78 |
| 10 | INF8780R - vSphere Core 4 Performance Troubleshooting and Root Cause Analysis, Part 1: CPU and RAM | 77 |

## Cloud Management
|# |Session|Views|
|---|---|---|
| 1 | MGT8770 - Managing Microsoft Azure with the vRealize Suite | 97 |
| 2 | MGT8543 - Simpler Extensibility in vRealize Automation 7.0 with the Event Broker | 82 |
| 3 | MGT9457 - Understanding the Value of vRealize Network Insight | 76 |
| 4 | MGT8080 - vRealize Reference Architecture: Design, Deploy, and Realize Value at High Speed and Amaze Your Customers! | 69 |
| 5 | MGT7685R - Insight into the World of Logs with VMware vRealize Log Insight | 60 |
| 6 | MGT7671 - What's New in VMware Integrated OpenStack Version 3.0! | 52 |
| 7 | MGT8085 - Save Time With Everything and Anything as a Service (XXXAAS) using vRealize Automation (vRA) | 46 |
| 8 | MGT9184 - Day 2 Automated Operations with vRealize Automation 7.0 and the Event Broker Service, a Deep Dive. | 43 |
| 9 | MGT9220 - vRealize Automation and NSX Design Experts Panel | 41 |
| 10 | MGT7751R - A Technical Deep Dive into VMware Integrated OpenStack | 36 |

## Cloud Native Apps
|# |Session|Views|
|---|---|---|
| 1 | CNA7741 - From Zero to VMware Photon Platform | 333 |
| 2 | CNA8986 - Running Docker on Your Existing Infrastructure with vSphere Integrated Containers | 289 |
| 3 | CNA7454 - Introduction to Containers as a Service | 86 |
| 4 | CNA7524 - Photon Platform, vSphere, or Both? | 80 |
| 5 | CNA8986R - Running Docker on Your Existing Infrastructure with vSphere Integrated Containers | 72 |
| 6 | CTO7964 - Cloud Native Buzzwords (Demystified) for Dummies | 65 |
| 7 | MGT7804 - Container Management with vRealize Automation | 60 |
| 8 | CNA8897 - Continuous Integration and Continuous Deployment for Containers: Confidently Promote Your Code into Production | 38 |
| 9 | CNA8145 - From Today to ''CNA'': VMware Technologies and DevOps Frameworks as a Service | 33 |
| 10 | CNA9994-QT - VMware's Cloud Native Stack | 28 |

## DevOps
|# |Session|Views|
|---|---|---|
| 1 | INF8255 - Evolving the vSphere API for the Modern Era | 485 |
| 2 | DEVOP7915 - Network as Code: DevOps Implications of Programmable Infrastructure | 62 |
| 3 | DEVOP7730 - DevOps Bootcamp Actual | 32 |
| 4 | DEVOP7674 - vRA, API, CI, Oh My! | 30 |
| 5 | MGT8766 - How IT Can Enable DevOps and Development Teams to Rapidly Deliver and Iterate Robust Applications in a Multicloud Environment including VMware, AWS, Azure and Softlayer | 29 |
| 6 | DEVOP8924 - Building an Actionable Strategy Around DevOps and Platform as a Service (PaaS) | 28 |
| 7 | MGT8831 - Digital Transformation Through VMware DevOps Code Stream | 26 |
| 8 | DEVOP7859 - Real-World DevOps Customer Panel | 25 |
| 9 | DEVOP9403-SPO - Hacking Your Backups: Making Your Backup Data & Systems Work for You | 22 |
| 10 | MGT8969 - Forrester Research POV on DevOps, Automation, and Virtualization Maturity Trends | 21 |

## End User Computing
|# |Session|Views|
|---|---|---|
| 1 | STO7443 - How did VMware IT Achieve a Non-Disruptive Disaster Recovery Test in 90 Minutes for 900 Terabytes of Storage and 2000 Production Virtual Machines? | 175 |
| 2 | EUC7799 - Design Horizon the Easy Way with Help from the Horizon Sizing Estimator | 88 |
| 3 | EUC8243R - Troubleshooting 101 for Horizon | 81 |
| 4 | EUC9386 - What’s new with Workspace ONE: Identity meets Mobility | 76 |
| 5 | EUC8822 - Case Study: Large-Scale Deployment of VMware App Volumes and User Environment Manager for 10,000 Seats | 73 |
| 6 | EUC7998 - The Latest in High-Performance Desktops and Applications with  Horizon 7, Blast Extreme Protocol,  and NVIDIA GRID vGPU | 72 |
| 7 | EUC8521 - The Future of VMware Fusion and Workstation | 61 |
| 8 | EUC8648R - Architecting VSAN for Horizon the VCDX Way | 51 |
| 9 | EUC7888 - Why Siemens Uses High-Performance Desktops with VMware Horizon and Nvidia GRID vGPU | 47 |
| 10 | EUC8725 - Everything You Need to Know About Horizon Remote Desktop Services Hosted Applications (But Probably Do Not) | 45 |

## Hybrid Cloud vcloud Air
|# |Session|Views|
|---|---|---|
| 1 | HBC9092 - vCloud Air: Advanced Networking Concepts | 42 |
| 2 | HBC9401 - Whats New with vCloud Air | 27 |
| 3 | HBC7948 - Extending Your Data Center to vCloud Air in Less than 60 Minutes | 26 |
| 4 | HBC7646 - St. John's University Leverages vCloud Air Disaster Recovery for Its Critical ERP System, Banner | 21 |
| 5 | HBC8292 - vCloud Air Recovery as a Service (RaaS) Deep Dive | 15 |
| 6 | HBC8295 - The VMware Journey to Cloud with vCloud Air | 14 |
| 7 | HBC9111 - vRealize Operations and vCloud Air: Monitoring Your Cloud | 12 |
| 8 | HBC10827-SPO - Ensure Success of Hybrid Cloud with Amazon Web Services | 11 |
| 9 | HBC8952 - vCloud Air Design Patterns for Design, Implementation, and Operations | 9 |
| 10 | HBC8915 - SLED and Cloud: Is Cost Containment the Right Question?  Yes and No | 8 |

## Hybrid Cloud vcloud Air Network
|# |Session|Views|
|---|---|---|
| 1 | HBC7830 - Virtualize, Secure, and Extend Your Data Center to the Cloud Using NSX: A Perspective for Service Providers and End Users | 91 |
| 2 | HBC9463-SPO - Data Protection as a service for your vCloud Director environment with Veeam | 62 |
| 3 | HBC7602 - Build True Hybrid Clouds: See How Service Providers Can Use NSX to Extend Customer On-Premises Data Centers | 38 |
| 4 | HBC8474 - Making It Easy to Orchestrate and Automate Your Hybrid Cloud Environment | 36 |
| 5 | HBC8312 - Maintaining Regulatory Compliance in the Hybrid Cloud | 22 |
| 6 | HBC8503 - Taking VDI and Published Application Environments to the Next Level with App Volumes | 19 |
| 7 | HBC8861 - Getting the Most Out of Your Hybrid Cloud Service Provider | 18 |
| 8 | HBC7954 - Implementing Hybrid Cloud with VMware vCloud Air and NSX: A Closer Look | 16 |
| 9 | HBC8491 - Deep Dive: VMware on IBM Cloud Validated Design | 15 |
| 10 | HBC9185 - How to Connect Your On-Premises Data Center to the Cloud | 14 |

## Hyper Converged Infrastructure and Storage
|# |Session|Views|
|---|---|---|
| 1 | STO7875 - A Day in the Life of a VSAN I/O | 422 |
| 2 | STO7534 - Virtual SAN - Day 2 Operations | 355 |
| 3 | STO7535 - Conducting a Successful Virtual SAN 6.2 Proof of Concept | 341 |
| 4 | STO7904 - Virtual SAN Management Current & Future | 176 |
| 5 | STO8246R - Virtual SAN Technical Deep Dive and What’s New | 119 |
| 6 | STO8159 - Snapshots Suck: How VSAN and VVol fix all your operational nightmares | 113 |
| 7 | STO8179R - Understanding the Availability Features of Virtual SAN | 101 |
| 8 | STO9423 - File Services on Virtual SAN | 85 |
| 9 | STO8422 - Virtual Volumes: Why? | 80 |
| 10 | STO9988-QT - Running Epic with VSAN – Modern Architecture for Healthcare | 73 |

## Most Popular Session
|# |Session|Views|
|---|---|---|
| 1 | INF9047 - Managing vSphere 6.0 Deployments and Upgrades | 794 |
| 2 | INF8225 - The vCenter Server and Platform Services Controller Guide to the Galaxy | 633 |
| 3 | INF8430 - vSphere 6.x Host Resource Deep Dive | 480 |
| 4 | NET7907 - Advanced Network Services with NSX | 457 |
| 5 | CTO9943 - VMware Chief Technology Officer Panel - Trends and Futures | 274 |
| 6 | MGT7924 - vRealize Operations Capacity Explained | 258 |
| 7 | INF7827 - vSphere DRS Deep Dive: Understanding the Best Practices, Advanced Concepts, and Future Direction of DRS | 244 |
| 8 | INF8755R - Troubleshooting vSphere 6: Tips and Tricks for the Real World | 205 |
| 9 | VIRT8290R - Monster VMs (Database Virtualization) Doing IT Right | 187 |
| 10 | CNA7522 - Containers for the vSphere Admin | 173 |

## Networking and Security
|# |Session|Views|
|---|---|---|
| 1 | NET7514 - PowerNSX and PyNSXv: Using PowerShell and Python for Automation and Management of VMware NSX for vSphere | 534 |
| 2 | NET7861R - Multisite Networking and Security with Cross-vCenter NSX: Part 2 | 332 |
| 3 | NET8758 - vSphere Distributed Switch Deep Dive | 124 |
| 4 | NET8131R - NSX for vSphere Logical Routing Deep Dive | 115 |
| 5 | NET8364R - How to Deploy VMware NSX with Cisco Infrastructure | 84 |
| 6 | NET7854R - Multisite Networking and Security with Cross-vCenter NSX—Part 1 | 75 |
| 7 | NET8194 - How VMware IT Implemented Microsegmentation and Deployed a Large-Scale Private Cloud Using NSX | 71 |
| 8 | NET8030 - NSX Performance Deep Dive | 70 |
| 9 | NET8337 - Leveraging NSX for Remote and Branch Offices | 70 |
| 10 | NET8193R - The Architectural Future of Network Virtualization | 68 |

## Software Defined Datacenter
|# |Session|Views|
|---|---|---|
| 1 | SDDC8621 - VMware Cloud Foundation: Technical Deep Dive | 179 |
| 2 | SDDC9456-SPO - Implementing Self-Service Storage Provisioning with vRealize Automation XaaS | 159 |
| 3 | SDDC8472 - An IT Architect's Guide to the Software-Defined Data Center | 89 |
| 4 | SDDC8468R - A Beginner's Guide to the Software-Defined Data Center | 67 |
| 5 | SDDC8414 - VMware Validated Design for SDDC: A Technical Deep Dive | 52 |
| 6 | SDDC9404-SPO - Reinventing Disaster Recovery Leveraging Public Cloud Infrastructure | 47 |
| 7 | SDDC7780 - Agile: The Scrum Master for Your Software-Defined Data Center! | 43 |
| 8 | SDDC9176 - How VMware Cloud Foundation powers the IBM Cloud | 42 |
| 9 | SDDC8748 - Building a Successful Business Case for VMware Cloud Foundation | 30 |
| 10 | SDDC7692 - Tips for Realizing the Full Value of Your SDDC Transformation | 25 |

## Technology Futures
|# |Session|Views|
|---|---|---|
| 1 | CTO8519 - Best of Both Worlds: Achieving Ultra-Low VM Network Latencies and Extreme Bandwidth Without Compromise | 57 |
| 2 | CTO9018 - VMware Internet of Things Strategy; Unveiled | 44 |
| 3 | CTO9002-QT - Artificial Intelligence Is the Future of IT | 43 |
| 4 | CTO8120 - Debunking the Myths about Virtualizing High Performance Computing | 36 |
| 5 | CTO9471-SPO - New Capabilities in ONTAP 9 Optimized for All Flash Virtualized Workloads | 36 |
| 6 | CTO9951-SPO - What’s Old Is New Again: Next Generation Storage | 28 |
| 7 | CTO9996-SPO - Fortifying the Cloud: What the New Samsung-VMware Partnership Means | 28 |
| 8 | CTO9032 - Is it Possible to Use NSX to Cut WAN Network Costs in Half? | 21 |
| 9 | CTO7942 - Unik: A Platform for Automating Unikernels Compilation and Deployment | 15 |
| 10 | CTO8995-QT - How Do You Manage Security Vs Privacy in IoT Beyond Device Management? | 13 |

## Virtualizing Applications
|# |Session|Views|
|---|---|---|
| 1 | VIRT8290R - Monster VMs (Database Virtualization) Doing IT Right | 205 |
| 2 | VIRT9009 - Licensing SQL Server and Oracle  on vSphere | 108 |
| 3 | VIRT7620 - Successfully Virtualize and Operate Your Microsoft Skype for Business Infrastructure on the VMware vSphere Platform | 101 |
| 4 | VIRT9034 - Oracle Databases Licensing on a Hyper-Converged Platform | 97 |
| 5 | VIRT7598 - Extreme Performance Series: Monster VM Database Performance | 89 |
| 6 | VIRT8530R - Deep Dive on pNUMA & vNUMA - Save Your SQL VMs from Certain DoomA! | 64 |
| 7 | VIRT7941 - The Best of Both Words: Achieving SQL Server High Availability with VMware | 48 |
| 8 | VIRT7840 - VMware and Microsoft Present: Successfully Virtualizing Microsoft Exchange Server, the Right Way | 47 |
| 9 | VIRT7654 - SQL Server on vSphere: A Panel with Some of the World's Most Renowned Experts | 44 |
| 10 | VIRT7511 - Performance Tuning and Monitoring for Virtualized Database Servers | 43 |
