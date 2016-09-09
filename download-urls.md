# VMworld US 2016 Breakout Sessions Download URLs

Here is a nice summary list of all VMworld US 2016 Breakout session with the respective video download URLs. You simply just need to right click on the link and "Save As" to download the mp4 file.

If you wish to download this in bulk, I have also published the "raw" download URLs [here](raw_download_urls.txt) which simply just has the VMworld Session ID and the download URL seperate by a comma which should be easier to parse (sorry about that Athony).

Here's a quick script that you can use by passing in the **raw_download_urls.txt** or a subset of that list in a file you create yourself.

```console
for i in $(cat raw_download_urls.txt);
do
  LABEL=$(echo $i | awk -F ',' '{print $1}')
  URL=$(echo $i | awk -F ',' '{print $2}')
  curl -o "${LABEL}.mp4" "${URL}"
done
```

For those that want a simpler 1-liner that even fits in a tweet, have a look at:

```console
for i in $(cat urls.txt);do;A=$(echo $i | awk -F ',' '{print $1}');B=$(echo $i | awk -F ',' '{print $2}');curl -o "${A}.mp4" "${B}";done
```

Enjoy! 

[INF9047 - Managing vSphere 6.0 Deployments and Upgrades](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/b4060695-2e20-4abe-a638-a97a2fffebfb.mp4?playbackTicket=2fa56c8ed5d04f3bb547350e4d7a968f&site=vmware.mediasite.com)

[INF8225 - The vCenter Server and Platform Services Controller Guide to the Galaxy](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/3fc56ead-c735-436b-9f49-de699335b666.mp4?playbackTicket=244b6e8412274704846d3d86d1abe40b&site=vmware.mediasite.com)

[INF9044 - Journey to the vCenter Server Appliance: A Migration Story](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/ececaec3-6872-4066-b5fa-8d701dfb11de.mp4?playbackTicket=fc6ced2e77bb43a1aef269d08824a076&site=vmware.mediasite.com)

[MGT7924 - vRealize Operations Capacity Explained](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/8df89b89-613d-4ecf-b105-0f5548b4995c.mp4?playbackTicket=de9b60d15d314bc3b8620d54b44540f7&site=vmware.mediasite.com)

[CTO9943 - VMware Chief Technology Officer Panel - Trends and Futures](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/089b2b2c-abb9-4b89-802f-1ae5feafbed5.mp4?playbackTicket=cec9a4f0a8a5449aa13ed9013ed5f602&site=vmware.mediasite.com)

[CTO7516 - Ask the Experts - Titans of Tech](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/5a6e8319-01e7-4e34-b2fa-8fdfcab5a9f3.mp4?playbackTicket=be6cf3720ca6410b9d4d93971b9dd7f1&site=vmware.mediasite.com)

[INF7827 - vSphere DRS Deep Dive: Understanding the Best Practices, Advanced Concepts, and Future Direction of DRS](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/9e665824-de61-4007-80c0-6752f6e1f626.mp4?playbackTicket=bba75249951546c88b7bbd5e1bca866d&site=vmware.mediasite.com)

[SDDC8468 - A Beginner's Guide to the Software-Defined Data Center](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/d00dc0a3-1dbf-4ae5-8b5e-d0e64645fadb.mp4?playbackTicket=2074776b88524cf59efd103acb60de89&site=vmware.mediasite.com)

[EUC8203 - Beyond the Marketing: Horizon Instant Clones Deep Dive](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/9b6f6f52-5dfa-4fa3-8dc8-f6d51e98f586.mp4?playbackTicket=15dfe634995842ac9b6e700131c34bd8&site=vmware.mediasite.com)

[INF8755R - Troubleshooting vSphere 6: Tips and Tricks for the Real World](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/f91f2373-4041-464f-a6d3-c8e5fd14be8f.mp4?playbackTicket=7f11214c0bdb4d069dcc4cb35a0648b6&site=vmware.mediasite.com)

[INF8089 - Extreme Performance Series: vSphere Compute and Memory](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/7ecb27d4-9fe7-44b6-9bc2-8b96206693fb.mp4?playbackTicket=42a189c7598c464ab028f0164b5db1ab&site=vmware.mediasite.com)

[CNA7522 - Containers for the vSphere Admin](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/a30fe5bb-d60b-4f33-bd10-3defe6afda99.mp4?playbackTicket=d1b2f21a0dc44caabdd0cab9b36a12d1&site=vmware.mediasite.com)

[INF8430 - vSphere 6.x Host Resource Deep Dive](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/1eb2cc67-845c-4e0f-a99b-a48e2838c638.mp4?playbackTicket=64c78bf4511547a685010d05faaa9157&site=vmware.mediasite.com)

[EUC8243R - Troubleshooting 101 for Horizon](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/a1effcaa-ae5e-481f-9d06-58d29be1928d.mp4?playbackTicket=9d41c0a92e6a4ba18eb5ab248fe5fc80&site=vmware.mediasite.com)

[SDDC9461-SPO - Veeam Availability Suite 9.5 Deep Dive](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/def6d256-6f54-48b2-a316-f2a0f299c085.mp4?playbackTicket=79191a4e2dab47dbaa5ceb1a7985cdfe&site=vmware.mediasite.com)

[NET7907 - Advanced Network Services with NSX](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/43d2278c-15ff-43a4-8b17-6d6051eb449a.mp4?playbackTicket=5f40c91c23614d719fd6ed8ba4d5c9bf&site=vmware.mediasite.com)

[NET8364R - How to Deploy VMware NSX with Cisco Infrastructure](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/61104286-525e-4c3a-bb62-05b0e4adcf09.mp4?playbackTicket=12d5e2e014eb43bb8d262c574c14361d&site=vmware.mediasite.com)

[INF8092 - The Power Hour: Deep Dive, DevOps, and New Features of PowerCLI](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/4022bd26-efd7-4db0-a63e-9d62dfd006f8.mp4?playbackTicket=219fc964d49d46fc85eadd06285fc30d&site=vmware.mediasite.com)

[STO9617-SPO - Containers & VVols - a technical deep dive on new technologies that revolutionize storage for vSphere](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/5b3b9ade-a3c6-4714-9186-a573d8523b7b.mp4?playbackTicket=f7145116b7024213b9127a8a061f42e9&site=vmware.mediasite.com)

[VIRT8290R - Monster VMs (Database Virtualization) Doing IT Right](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/23e6a4d1-84d5-488a-ad38-b86ebf82b5c9.mp4?playbackTicket=d9de207f10434d648676deb246920906&site=vmware.mediasite.com)

[EUC8404 - What's New with Horizon 7](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/a23fe748-0d10-43c4-aa4e-32a754dd94a6.mp4?playbackTicket=a8df07008e4f4a1c801964679ae74391&site=vmware.mediasite.com)

[MGT7718 - The KISS of vRealize Operations!](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/57b0df04-2a8f-4d72-b468-1f553af4a721.mp4?playbackTicket=8e6128a13c4848a1811981772257025c&site=vmware.mediasite.com)

[VIRT7621 - Virtualize Active Directory, the Right Way!](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/06fefe16-b378-4167-9022-ea6d1d0c7f64.mp4?playbackTicket=353d04cce0e644f8ae0b1c64a2b138d6&site=vmware.mediasite.com)

[NET9989-S - NSX - The Network Bridge to the Multi-cloud Future](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/ce36b8bc-f2ef-405c-b575-266e141a413a.mp4?playbackTicket=dcfe6c5d1298468abeefec65c68f4a1c&site=vmware.mediasite.com)

[INF8036 - Enforcing a vSphere Cluster Design with PowerCLI Automation](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/6ba959a6-9220-4524-b886-4a48df46d36d.mp4?playbackTicket=ba5025d7e93246b1a8822e02fe7a7893&site=vmware.mediasite.com)

[INF9083 - Ask the vCenter Server Experts Panel](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/cfecf036-2439-43e9-962e-837f194aea55.mp4?playbackTicket=2671aa7ddac84d69b5617d8487ccec50&site=vmware.mediasite.com)

[STO7645 - Virtual Volumes Technical Deep Dive](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/abe4594f-f57d-4939-9fcf-10b1d0b81683.mp4?playbackTicket=7926113ebc454aca8144ecb8f28f3815&site=vmware.mediasite.com)

[INF8038 - Getting Started with PowerShell and PowerCLI for Your VMware Environment](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/6c26b53f-53b8-45d5-8215-395edf199814.mp4?playbackTicket=bde5442e5513447db3bbd6a3a87b680e&site=vmware.mediasite.com)

[STO9424-S - Taking HCI Mainstream](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/192fe167-453f-4961-b241-df10a01f9202.mp4?playbackTicket=42e36b589fa64defbcae01a1d90045ed&site=vmware.mediasite.com)

[EUC7601 - Advances in Remote Display Protocol Technology with VMware Blast Extreme](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/c6dbb3b5-ff86-4071-b6f6-2796cee9af27.mp4?playbackTicket=ad83c075109446e0805bec9ae34182f9&site=vmware.mediasite.com)

[Tuesday, August 30 - Competitive Advantage in the Multi-Cloud Era](http:)

[Monday, August 29 - Competitive Advantage in the Multi-Cloud Era](http:)

[CTO10624-S - Are you ahead of the IoT curve](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/01fae26b-4035-4dd8-b9b9-3fb18b2b49b9.mp4?playbackTicket=639e463242b8454eb91fe0c83e3ad42f&site=vmware.mediasite.com)

[SDDC7808-S - How I Learned to Stop Worrying and Love Consistency: Standardizing Datacenter Designs](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/dfafac9a-4f90-4087-8b0b-194c6b495851.mp4?playbackTicket=9fe3a89c3fa741dda00e505df4fb06e2&site=vmware.mediasite.com)

[HBC9363-S - Virtualization 2.0: How the Cloud Is Evolving the Modern Data Center](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/219e226b-a919-4eb1-8394-0983ca2f8f75.mp4?playbackTicket=94957390f2954501a076d4abff632eef&site=vmware.mediasite.com)

[EUC10682-S - Delivering the Digital Workspace: The Transformation of End-User Computing](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/7e7da282-3138-4332-97f6-3b842130fd37.mp4?playbackTicket=0c9fd099666c4634a806d06abba64ee5&site=vmware.mediasite.com)

[CNA9993-S - Cloud Native Applications, What it means & Why it matters](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/78332728-0f36-4ad3-a79d-f5af5f1e4904.mp4?playbackTicket=c75ea3b0ee1a43dab90bffb8e7c7ca44&site=vmware.mediasite.com)

[VIRT8612-S - How Travis Credit Union Virtualized Their Systems and Significantly Improved Stability and Performance](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/2131953d-b383-4d2a-8328-16c1888f3f86.mp4?playbackTicket=fa7db8f3dda34923ac0a7257ad749eba&site=vmware.mediasite.com)

[SDDC8618-S - Introducing VMware Cloud Foundation](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/e0912fd2-aa5a-4144-baf8-a4491af2bf13.mp4?playbackTicket=022bc7b5a780475994bf51d12ae8f799&site=vmware.mediasite.com)

[SEC9990-S - How Virtualization Will Transform Security](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/a327314e-d0b6-43d2-a3c7-c922e74502cd.mp4?playbackTicket=cec07ff02e74407a923d15ede1da100b&site=vmware.mediasite.com)

[NET9989-S - NSX - The Network Bridge to the Multi-cloud Future](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/ce36b8bc-f2ef-405c-b575-266e141a413a.mp4?playbackTicket=76902dc7caf144218d031f04fe9ff09f&site=vmware.mediasite.com)

[CTO9978-S - Digital Transformation - Technology & Business Futures, A CTO's Perspective](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/b86cd48c-8ae4-47d9-ae22-9568e05e1450.mp4?playbackTicket=dfcf9e27638a440b8f58ac463952b76e&site=vmware.mediasite.com)

[INF9947-S - Spotlight on vSphere: Today, Tomorrow, and Beyond](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/5d6fa026-80f4-4879-ab77-b14866636186.mp4?playbackTicket=213301a108114a3e9a8a3263e9a616bf&site=vmware.mediasite.com)

[SDDC9035-S - SDDC and Hyperconverged has Arrived â€“ Get on Board!](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/16009f16-157c-494c-83db-c36344096943.mp4?playbackTicket=481b2f62432e4607accea6d4bedc20d9&site=vmware.mediasite.com)

[STO9424-S - Taking HCI Mainstream](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/192fe167-453f-4961-b241-df10a01f9202.mp4?playbackTicket=50696ea6576c4fef8e1e4f4ad7260900&site=vmware.mediasite.com)

[INF8172 - vSphere Client Roadmap: Host Client, HTML5 Client, and Web Client](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/a899f127-1e55-4c07-be7b-be8bdf363a95.mp4?playbackTicket=23b69655314e45e39753727901f9672d&site=vmware.mediasite.com)

[INF8396 - Winter Is Coming. Are You Dev/Ops Ready? Instant Clone Is!](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/1414f2a7-ffa3-41b5-bcd4-75c2af91c84c.mp4?playbackTicket=5f63e87028804d978fced3bf154afc68&site=vmware.mediasite.com)

[INF8755R - Troubleshooting vSphere 6: Tips and Tricks for the Real World](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/2e2bb9f5-1de5-4bf4-9489-d9d71cb49a83.mp4?playbackTicket=5ec9f25f60304d4a89bd3034a306d09c&site=vmware.mediasite.com)

[INF8383 - Maximizing Your Remote Site Infrastructure with vSphere and Virtual SAN](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/42cc8b37-b433-42b0-afd7-88fdbafdb6c4.mp4?playbackTicket=dd3797cbdc5c473e8df444a3b914caf4&site=vmware.mediasite.com)

[MGT8040 - Turning Up the Noise: How VMware's Private Cloud Team Is Getting Closer to the Heartbeat of Its Infrastructure, Billions of Events at a Time](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/4e300c36-f458-4ffa-978d-fa17470b1857.mp4?playbackTicket=2f5e390dbfbb4b2cb837e3a270a21c90&site=vmware.mediasite.com)

[INF8631 - VMware Certificate Management for Mere Mortals](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/0875c252-9193-4999-967a-b89d71ceafb8.mp4?playbackTicket=e80b8fa7432546ce97ed899e938241bc&site=vmware.mediasite.com)

[INF8374 - Zero Downtime, 20K+ VMware vSphere 6 Upgrade](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/32cdada2-55ef-403c-a276-52b0fd97b861.mp4?playbackTicket=504d7a872c674bf4930527ed7f1d2abf&site=vmware.mediasite.com)

[INF8845 - vSphere Logs Grow Up! Tech Preview of Actionable Logging with vRealize Log Insight](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/07b71600-0b14-42a3-a516-16704a61407e.mp4?playbackTicket=8c2b255bdcae4ea882b643df721d865b&site=vmware.mediasite.com)

[INF8038r - Getting Started with PowerShell and PowerCLI for Your VMware Environment (Copy)](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/1d06701d-6bd1-44c8-be5f-94b0ba8ab40f.mp4?playbackTicket=6de3643a79b849ae87c1ba2482349696&site=vmware.mediasite.com)

[INF9128 - Day 2 Operations: A vCenter Server Administrator's Diary](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/bc1a52a2-03d8-4a60-ae1c-8eb8ed571d47.mp4?playbackTicket=0ebf483fbc2a4a748c8d5a6f200999d1&site=vmware.mediasite.com)

[INF8693 - How to Get the Most out of Your VMware Investment: Leveraging vSphere to Reduce Total Cost of Ownership](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/61ece176-3888-4b04-993b-f33f4652a0e9.mp4?playbackTicket=afa5c04ffe714bb5a4bfd3486baa7c50&site=vmware.mediasite.com)

[INF8251 - vSphere Host Fabric: Why It Matters to You?](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/80fa3989-6846-446a-89d6-4c29c49043be.mp4?playbackTicket=a6371f9879bc41c7b58f118f94017368&site=vmware.mediasite.com)

[INF8108 - Extreme Performance Series: vCenter Performance Deep Dive](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/51ff8ada-1fd4-402c-8648-79c640e6c5cd.mp4?playbackTicket=ad93243c50de463a9ebf0851de26cd05&site=vmware.mediasite.com)

[INF8371 - How Did the Private Cloud Transform VMware IT?](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/130b3d4a-2847-43ef-a006-1cf2618c4f96.mp4?playbackTicket=67da2e748a3f42c6adf4e4a9dc67bc87&site=vmware.mediasite.com)

[INF8045 - vSphere High Availability Best Practices and Tech Preview](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/52a4b2b1-5c3b-4eec-89cf-2839cb1d1d5e.mp4?playbackTicket=f1ef27f4d2924005b0eb5c1d4fbe929f&site=vmware.mediasite.com)

[INF8375 - What's New with vSphere](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/80d4642c-9da5-45de-bc0d-414139f72c7a.mp4?playbackTicket=9e89f3bc6e2841f6a641c1b06e9f667f&site=vmware.mediasite.com)

[INF9144 - Through the Looking Glass:  An Overview of the vCenter Server Appliance Management Interface and API](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/849650f4-893a-44cb-8051-a65f02f5c892.mp4?playbackTicket=6134758866f84d7b80d288755ac4ebbe&site=vmware.mediasite.com)

[MGT9997-SPO - How to Automate Cloud Operations with vRealize and NSX Featuring Lessons Learned from Deluxe Corpâ€™s Transformation](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/6e8217e6-de61-4fe4-bab6-1173d531c231.mp4?playbackTicket=e81188b83f5d46818fcd610b67ff266f&site=vmware.mediasite.com)

[INF8858 - vSphere Identity: Multifactor Authentication Deep Dive](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/fba352fa-976b-4391-a406-afb4e650932f.mp4?playbackTicket=1cf679ebd3ae41f7a7ab1c30835c3de9&site=vmware.mediasite.com)

[INF8683 - Understanding the Role SNMP Agents Play in a vSphere Stack](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/896be611-932c-46e2-a864-bab90d7908a2.mp4?playbackTicket=2806646447864a64bd082f64b9267b41&site=vmware.mediasite.com)

[INF9048 - An Architect's Guide to Designing Risk: The VCDX Methodology](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/5cc8a552-e12b-4701-b52d-6b35dafc21ee.mp4?playbackTicket=a8275ffd5b454009926b0385813aae4e&site=vmware.mediasite.com)

[INF8469 - iSCSI/iSER: HW SAN Performance Over the Converged Data Center](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/1ac81c00-a233-479f-a457-b2d4330979a6.mp4?playbackTicket=5552747fb3694a808b5eb4a4b5cb3aeb&site=vmware.mediasite.com)

[INF8250 - Case Study: Using vCloud Suite to monitor Global operations](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/87e2cf5f-b458-4e41-91b9-980c6c8442b4.mp4?playbackTicket=36bd360b75924ee0bf38758acbfa316d&site=vmware.mediasite.com)

[INF9089 - Managing vCenter Server at Scale? Here's What You Need to Know](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/1d92dafa-054d-44aa-8722-91749035c509.mp4?playbackTicket=c981e363032945d7af57f567c51aa319&site=vmware.mediasite.com)

[INF9608-SPO - How to Use Machine Learning to Increase Application Availability](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/3dce78c7-e4ff-40a2-b53c-5f5dfe3aee3d.mp4?playbackTicket=7f777e702e49487a8b2afbe09e5e0d5d&site=vmware.mediasite.com)

[MGT8884 - Our SDDC Journey - See how SDDC transformed IT in just 12 months and changed how we think about â€œautomationâ€ at Johnson & Johnson IT.](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/5cbf0bfd-4caa-49d3-8804-44eb61cf0d67.mp4?playbackTicket=a4999fcb6602456f9bd71f9ed060750f&site=vmware.mediasite.com)

[INF8939 - Virtual Machine and Application Protection Demystified](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/a47bb7b8-484f-4bdd-9115-9cb6bb86edb0.mp4?playbackTicket=9ffb28b46a6944239ee32612222206fd&site=vmware.mediasite.com)

[INF9944R - What's New with vCenter Server](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/5b06226a-d1fc-475b-bf2a-d79edaa1fd77.mp4?playbackTicket=df94b80708eb465281d4f8bba705b927&site=vmware.mediasite.com)

[INF9205R - Troubleshooting vSphere 6 Made Easy: Expert Talk](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/8a9b1309-a70b-4f1f-b87d-a58247c65bb1.mp4?playbackTicket=cbc442e8dd68440cb4fdb9199bde04d6&site=vmware.mediasite.com)

[INF8117 - Why Fiserv Deployed Auto Deploy and Why You Should as Well](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/bd847eff-60cf-44c3-aea9-ea05333ed432.mp4?playbackTicket=c1f9f52a810b4f01a48b20556deba10c&site=vmware.mediasite.com)

[INF8959 - Extreme Performance Series: DRS Performance Deep Diveâ€”Bigger Clusters, Better Balancing, Lower Overhead](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/c1649510-b8f7-40c7-b9aa-df5ae530afa6.mp4?playbackTicket=d784aef3400d4d6fb72dc837144e801e&site=vmware.mediasite.com)

[INF8701R - vSphere Core 4 Performance Troubleshooting and Root Cause Analysis, Part 2: Disk and Network](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/eadc091c-9868-4a5d-9975-bc56e5e25497.mp4?playbackTicket=0a7a5274ac174aa18ef9f75a25400774&site=vmware.mediasite.com)

[INF9950 - Storage at Memory Speed and the Amazing Future of Virtual Non-Volatile Memory](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/fc325f9c-3633-4715-a08b-dbb5e5db54e2.mp4?playbackTicket=53b035f40a314386a4d9718d086cbc91&site=vmware.mediasite.com)

[INF8856 - vSphere Encryption Deep Dive: Technology Preview](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/b59479d4-6fbc-41fc-a7a7-8de7bbb4dac5.mp4?playbackTicket=a560a72cdf61461f8e7c220425243dca&site=vmware.mediasite.com)

[INF8780R - vSphere Core 4 Performance Troubleshooting and Root Cause Analysis, Part 1: CPU and RAM](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/26a2ed3a-0923-4b30-86e7-2f2ff0d7a7d0.mp4?playbackTicket=89dc95e851d54570bc99bbdbea686713&site=vmware.mediasite.com)

[INF9205R - Troubleshooting vSphere 6 Made Easy: Expert Talk](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/c1e0bef8-9d01-4d01-8f77-d33d4e6acbc3.mp4?playbackTicket=f5ee8d6299e84834af5a94acfc928bc7&site=vmware.mediasite.com)

[MGT8714-SPO - Creating Automated Self-Service Data Protection with Rubrik and vRealize Automation](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/8fade289-f6b9-47ab-9dc8-a6b2d31f7fa5.mp4?playbackTicket=251d8d431ff543f495c2f9c2f2ec5974&site=vmware.mediasite.com)

[INF8020 - Tech Preview: Enhanced VM Availability Leveraging vCenter and Partner Hardware Integration](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/bb7f9158-0fcc-43b6-a276-24ff19c818a6.mp4?playbackTicket=bfc9bffe1a4f4c11bb4c47197ce0b113&site=vmware.mediasite.com)

[INF8644 - Getting the Most out of vMotion: Architecture, Features, Performance and Debugging](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/7efd9285-c17e-4bad-8086-184e8f8a379d.mp4?playbackTicket=fa93dc6d79af4b15862c8bc8e33d970e&site=vmware.mediasite.com)

[INF8097 - Production Is Down and So Are My Tools: Meeting Infrastructure High Availability by Deploying an Out-of-Band Management Cluster, A Customer Evolution](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/a782976f-139c-42b9-9eb4-764c5676fe23.mp4?playbackTicket=730646be6ae846f9a31bc8b442214e22&site=vmware.mediasite.com)

[INF8837 - How to Relocate Your Physical Data Center Without Downtime in a Few Clicks, Thanks to Automation](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/c9e95fed-4a3e-4037-bb72-39fd3a7baca0.mp4?playbackTicket=bbe9b9ff363f49bf890ccc8ef6324520&site=vmware.mediasite.com)

[INF8122 - A Storage Story: Capacity Management and Performance Planning for Storage Systems in vRealize Operations](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/c0c3db6d-a0b6-4a93-8a36-0c2c1aaa19a0.mp4?playbackTicket=2aae0991b8cd4eddb7f47417c488f9b1&site=vmware.mediasite.com)

[INF8914 - Mastering the VM Tools Lifecycle in your vSphere Data Center](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/8b388d81-86d9-4d76-a341-3efd33333a67.mp4?playbackTicket=801289dab31e4762ba91acf7e5f8f623&site=vmware.mediasite.com)

[INF8926 - Take Control of VMware vSphere Lifecycle Management in Your Software-Defined Data Center](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/1f37efa2-2b73-4e12-ace2-f1f69bce53c5.mp4?playbackTicket=6a7af02230e04282821bd8fcef7ec43a&site=vmware.mediasite.com)

[INF9119 - How to Manage Your Platform Services Controller Like Batman](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/8006f1d9-9f72-4673-a5aa-af5687badc33.mp4?playbackTicket=d1958e6f33ea4ae4ba16cd45f9a4fc7f&site=vmware.mediasite.com)

[INF8038r - Getting Started with PowerShell and PowerCLI for Your VMware Environment](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/3e0c884f-e6aa-4a0c-84f0-995603b60b53.mp4?playbackTicket=dab8b793a64a46ada92fc6be15434b5f&site=vmware.mediasite.com)

[INF8525-SPO - Enterprise-Class Cloud Stacks Power Mission-Critical Applications](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/cf060393-f5f9-45d5-ab34-78ba72453e27.mp4?playbackTicket=a9ff5889c6be48b7b22c37ef835dc073&site=vmware.mediasite.com)

[INF7818 - Take Virtualization to the Next Level](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/c3681486-24d1-4bd3-9fd3-2a0d54f2f8d4.mp4?playbackTicket=08a01c39a10c4aa4aeb66e4b05993903&site=vmware.mediasite.com)

[MGT7713 - Intelligent IT Operations Management from Infra to Apps, On-Premises and in The Cloud](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/ad09d498-3d1c-403c-8a99-030c80ce424d.mp4?playbackTicket=b1349c02cd0d444e9c52c1873d71c09a&site=vmware.mediasite.com)

[INF7825 - vSphere DRS and vRealize Operations: Better Together](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/972faeb8-cae6-4cd4-85ae-8d5ddca1388e.mp4?playbackTicket=9f8217ba212148b9b23903266b7b754f&site=vmware.mediasite.com)

[INF8459 - VMware Security: How to Meet Your Compliance Objectives Using Cool Technology](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/97816611-dc29-4787-968f-0e02609bbaf9.mp4?playbackTicket=9ba13ea264364e92b52a00f6bd11ad24&site=vmware.mediasite.com)

[INF9151 - Getting to Zero: Zero Downtime, Zero Data Loss with vSphere Fault Tolerance](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/10afe696-10aa-454a-a088-4549715fdbaf.mp4?playbackTicket=8ba655c437114cea80087297c4a42851&site=vmware.mediasite.com)

[INF8275R - How to Manage Health, Performance, and Capacity of Your Virtualized Data Center Using vSphere with Operations Management](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/c3b67aa0-0279-4f47-8368-ca559c477884.mp4?playbackTicket=5ac7ff200cde41f2aca0163c69134df5&site=vmware.mediasite.com)

[INF8701R - vSphere Core 4 Performance Troubleshooting and Root Cause Analysis, Part 2: Disk and Network](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/b1ad03eb-0653-4ad8-87bc-cb86cac49708.mp4?playbackTicket=5a8e123e6db94a3a8bbb44ef5cfb9adb&site=vmware.mediasite.com)

[MGT7878r - Using vRealize Suite for Endpoint Monitoring in a Multicloud Environment (Copy)](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/f59a5194-5d66-4e50-8aca-1464801e3ef8.mp4?playbackTicket=7ab83aed84ca4741b1185607a7eebdea&site=vmware.mediasite.com)

[INF8465 - Extreme Performance Series: Power Management's Impact on Performance](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/c0ab1291-d2b5-4a8c-805c-034b99e12911.mp4?playbackTicket=f34645038f354715b15598e736c66ef8&site=vmware.mediasite.com)

[INF8920 - Leveraging Stateless Compute Infrastructure for Centralized Control of the Software-Defined Data Center](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/786c91dc-f4bf-422d-b76b-540411d4e4b5.mp4?playbackTicket=5c2d20c940f4479ea695076502ae66e6&site=vmware.mediasite.com)

[INF9455-SPO - Best Practices for All-Flash Data Reduction Arrays with VMware vSphere](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/9f376add-dc21-4a54-bc33-677791e0484c.mp4?playbackTicket=c1c7814562304900a424aeac94bcab73&site=vmware.mediasite.com)

[INF8275R - How to Manage Health, Performance, and Capacity of Your Virtualized Data Center Using vSphere with Operations Management](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/77da8677-e828-4330-a148-b536b3dc1038.mp4?playbackTicket=fac143bb96ab4af792f11685ee585f03&site=vmware.mediasite.com)

[INF8553 - The Nuts and Bolts of vSphere Resource Management](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/441d46cf-46a9-43e8-94ac-b43871205fbe.mp4?playbackTicket=e97a6f33aeda4406a66623419778cf88&site=vmware.mediasite.com)

[INF9205R - Troubleshooting vSphere 6 Made Easy: Expert Talk](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/c2161de5-790a-484f-a931-435ef9f33fe0.mp4?playbackTicket=75d912e12a404b18b88d5e26fe0216ef&site=vmware.mediasite.com)

[INF7578 - A Cloud Service Provider's Success Story: Adoption of vSphere with Operations Management](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/ec08d346-515b-40dc-89d2-c6e22e94ad5d.mp4?playbackTicket=d9eb296aab00491996445ccb61c5eca3&site=vmware.mediasite.com)

[MGT7878 - Using vRealize Suite for Endpoint Monitoring in a Multicloud Environment](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/607168d1-d433-4bc2-9c56-65fdda283d92.mp4?playbackTicket=fc53908e542642d783a5848d3cc9093b&site=vmware.mediasite.com)

[INF8663 - The Making of a Legend-Dairy Software-Defined Data Center](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/92835196-98e6-48c7-8c7c-189fc011ad7e.mp4?playbackTicket=e020aa8f31724d4b9d6b02362c5ba9d9&site=vmware.mediasite.com)

[INF8260 - Automated Deployment and Configuration of the vCenter Server Appliance](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/b5edbdd6-355e-410e-857a-c6aeb77772cf.mp4?playbackTicket=5f8cbe3eb539433aa23c843854453ccf&site=vmware.mediasite.com)

[INF8850 - vSphere Platform Security](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/248ea383-bc5e-4cf8-8ff1-0cb30f4700d7.mp4?playbackTicket=e502c84a91084a498c850eb9642fc26e&site=vmware.mediasite.com)

[INF9944R - What's New with vCenter Server](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/b5b5b563-4599-4226-8216-dab3d82f8ad2.mp4?playbackTicket=089ab2685df44c34b9b7f63f65481a1f&site=vmware.mediasite.com)

[INF8780R - vSphere Core 4 Performance Troubleshooting and Root Cause Analysis, Part 1: CPU and RAM](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/0f7b9a5f-e1b6-419f-8478-20e17766eb9a.mp4?playbackTicket=105a76dfc3344969b625a13d91464787&site=vmware.mediasite.com)

[MGT8439 - Lessons Learned from EMC IT's Data Center Evolution](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/abdb85ef-c635-4d99-b99b-be0cc2470498.mp4?playbackTicket=a9561b7d42c84bc6a71a67ca54f1da46&site=vmware.mediasite.com)

[INF8277-QT - Dear IT, You Can Be a Strategic Partner to Your Business. Let me help. Yours Truly, vSphere with Operations Management.](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/242ae00e-ad21-46d2-b947-6a1d6a16f385.mp4?playbackTicket=a035c98066da4d138c8ac2b20e681655&site=vmware.mediasite.com)

[INF8558-QT - Business Value of Data Center Virtualization and Hybrid Cloud Extensibility](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/b8bfe039-3304-40ca-b321-b990d90b2a99.mp4?playbackTicket=2fb82c85979e4934a23b95ee986f9b6f&site=vmware.mediasite.com)

[INF8516-QT - VMware Security: The Whole Is Greater than the Sum of Parts](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/a3d798c2-1e61-4d71-98bc-fe8715b37e95.mp4?playbackTicket=91e0345e38be44fb9dd207f2ff7c4bf4&site=vmware.mediasite.com)

[INF7764-QT - Has the Hypervisor Been Commoditized?](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/283e2135-71eb-4f53-a94e-619edfc346be.mp4?playbackTicket=40f44176b2414af497f7ba9d56b66367&site=vmware.mediasite.com)

[MGT8543 - Simpler Extensibility in vRealize Automation 7.0 with the Event Broker](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/ccfa56d7-b98d-4904-b14d-70fdca584e6d.mp4?playbackTicket=992b8c75d8f4476d9468a0abebf5248b&site=vmware.mediasite.com)

[MGT7770 - Virtual SAN Management â€“ Time to Level Up Your Ops Game!](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/f8c014e7-debb-44d8-a257-fb6d3c14e4d8.mp4?playbackTicket=faee7fdbbc60463697920d9748b8a827&site=vmware.mediasite.com)

[MGT7751R - A Technical Deep Dive into VMware Integrated OpenStack](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/31a9a081-27ea-406b-b18d-795534077f0c.mp4?playbackTicket=c09b437380714bbfa4b5031a02002f94&site=vmware.mediasite.com)

[MGT8080 - vRealize Reference Architecture: Design, Deploy, and Realize Value at High Speed and Amaze Your Customers!](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/7bdbd96d-3bda-4c18-84aa-fdacd8feb6a7.mp4?playbackTicket=b62e476637a94555b23d90f0b464d455&site=vmware.mediasite.com)

[MGT7751 - A Technical Deep Dive into VMware Integrated OpenStack](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/f412aace-2825-4442-8c32-1791f9a73372.mp4?playbackTicket=41060c622a054d2f8f05944e4d2daa53&site=vmware.mediasite.com)

[MGT7685R - Insight into the World of Logs with VMware vRealize Log Insight](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/25044a08-8221-4c08-b257-158ee0c8e9f2.mp4?playbackTicket=1fdb65a53e02420d89c912f6369eccc8&site=vmware.mediasite.com)

[MGT8770 - Managing Microsoft Azure with the vRealize Suite](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/e3475598-2380-4bde-9a5d-59b4e843902d.mp4?playbackTicket=35249c854d1a4b90a829e04606c8859d&site=vmware.mediasite.com)

[MGT8641R - A Lot of Insight and No PowerPoint](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/96abe8b8-77dc-4dbd-8b56-e2b77711a6df.mp4?playbackTicket=2dd38d344cba4494b06705933aa95b62&site=vmware.mediasite.com)

[MGT8085 - Save Time With Everything and Anything as a Service (XXXAAS) using vRealize Automation (vRA)](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/206c7998-f064-4fdb-8fca-26aa8ca5a0ec.mp4?playbackTicket=e7eca37a35304c9288016ca16ab653c6&site=vmware.mediasite.com)

[MGT9184 - Day 2 Automated Operations with vRealize Automation 7.0 and the Event Broker Service, a Deep Dive.](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/5bfd6c00-bba2-4096-91de-b0026d37b4fe.mp4?playbackTicket=62098799b0324f3ebc2f82ee7f42f746&site=vmware.mediasite.com)

[MGT8641R - A Lot of Insight and No PowerPoint](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/c84773f2-c8df-45a4-ad6b-e5391348a700.mp4?playbackTicket=e70dc10e46d74b5491d6fd966d4886de&site=vmware.mediasite.com)

[MGT9426-SPO - Best Practices for Cloud Service Data Security](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/c215056d-5fad-4b62-9cb4-60bc5a0ba66b.mp4?playbackTicket=60589346c06e49abb8063145d0e8bfef&site=vmware.mediasite.com)

[MGT9948-SPO - Itâ€™s Time to expect more from your Virtual Environment](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/9cec6924-b24b-4ac8-8a29-b60ccb52f4dc.mp4?playbackTicket=666a95dafe70466bb00f52e58427d18b&site=vmware.mediasite.com)

[MGT7759 - Early VVD Adopter Experience: Building a Secure and Automated Cloud](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/c228cd0b-85b7-4021-9228-93ef34d5311e.mp4?playbackTicket=d0b9bd67ba2a480080c547b922e0d98e&site=vmware.mediasite.com)

[MGT8332 - How I Learned to Stop Worrying and Love the vRealize Automation API](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/77be32ea-8175-4cb0-b638-4337b92868f4.mp4?playbackTicket=06249ef3aeb24bc29191e7117807930b&site=vmware.mediasite.com)

[MGT7685R - Insight into the World of Logs with VMware vRealize Log Insight](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/ef81101b-8ac3-432e-ac60-ef6b83a5b33b.mp4?playbackTicket=0a75666c2edf4916867b19157fb4a532&site=vmware.mediasite.com)

[MGT7899 - Whose Hand Is in the Cookie Jar? Reducing the Mean Time to Innocence Using vRealize Operations](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/9aa1417e-fb35-4e49-a7fc-e49f736d6c24.mp4?playbackTicket=2e637384debd456cb91dc994b36c29a8&site=vmware.mediasite.com)

[MGT9457 - Understanding the Value of vRealize Network Insight](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/88c36b95-83b1-47c5-b923-de4d18d63147.mp4?playbackTicket=7a3abea916884ece969bbf1fba01b288&site=vmware.mediasite.com)

[MGT8733R - Application Self-Service with On-Demand Networking & Security from vRealize Automation and NSX](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/e2c595c5-4ae1-4136-8860-b5f2c51ceb19.mp4?playbackTicket=ef59ac3ef69540a798db7faddc4e36bd&site=vmware.mediasite.com)

[MGT8486 - NSX Operations with vRealize Suite](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/a02aac83-8f99-46ee-b845-bc7ff2d9598b.mp4?playbackTicket=20d7140606b1462ab15afcb0f53cefad&site=vmware.mediasite.com)

[MGT9615-SPO - vRealize the Possibilities:  Application Agility and Rapid Deployment with vRealize Automation, Orchestration, Operations and Log Insight](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/1770c354-0e4d-45d9-a6c0-fca5fde01633.mp4?playbackTicket=8a80f65170454cb7b3e798ae99159b1d&site=vmware.mediasite.com)

[MGT8984 - From Zero to SDDC at a Major Telco](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/4dea4ba0-e360-4ff9-bcbc-d240928cbf0f.mp4?playbackTicket=5a92aca6e1bc4b75ab7656f2c96ea367&site=vmware.mediasite.com)

[MGT7671 - What's New in VMware Integrated OpenStack Version 3.0!](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/57f8f101-cd2b-4052-9f8e-b310d94a0ea1.mp4?playbackTicket=4f977850b47a48639114468a837b32d9&site=vmware.mediasite.com)

[MGT7752 - OpenStack in the Real World: VMware Integrated OpenStack Customer Panel](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/51c630c9-4528-4611-8841-6123e657ff4d.mp4?playbackTicket=a037663395c148378724121151d3e11b&site=vmware.mediasite.com)

[MGT8763 - 3 Best Practices for IT to Enable Developers to Deploy on Amazon and Azure While Ensuring Security and Accountability](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/02a5f93e-1703-4dbb-9ecc-5a21a5acb411.mp4?playbackTicket=afa410b7159c49c38504071cee0dd97f&site=vmware.mediasite.com)

[MGT8768 - How TIAA Uses an API-Centric Cloud Management Platform to Allow Applications to Be Easily Deployed and Managed on Both Public and Private Clouds](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/df16125c-cf55-4f70-b1f0-d34ec077ab71.mp4?playbackTicket=415c8d2231c049c7a82b1931bd87822a&site=vmware.mediasite.com)

[MGT7629R - 360-Degree Troubleshooting](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/1b18cd73-1a3a-4a40-904a-a38c318ee006.mp4?playbackTicket=a90cc027cb62493fa53c219403e5e2bf&site=vmware.mediasite.com)

[MGT9220 - vRealize Automation and NSX Design Experts Panel](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/32f50480-5374-402b-b3a9-10cfb7d15f51.mp4?playbackTicket=47d12315e2344b748032f2d15554f4b1&site=vmware.mediasite.com)

[MGT8762 - How to Set Up a Multicloud IT Portal to Deploy, Manage, and Control Applications on Private and Public Clouds](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/9e6ab72b-430d-4a3b-9468-27151330576e.mp4?playbackTicket=82d46762165e415898e5fdd695896c52&site=vmware.mediasite.com)

[MGT8807 - What's New in vRealize Code Stream](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/9002ce06-d69a-4dc3-bc32-648d1c0b9634.mp4?playbackTicket=a792c65d279348dc9ff73014dd53ca16&site=vmware.mediasite.com)

[MGT8733R - Application Self-Service with On-Demand Networking & Security from vRealize Automation and NSX](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/68f928aa-795e-4a40-a87c-c7c4cad4dc41.mp4?playbackTicket=ec299702c5f347e29aefb6fe56eb5f9f&site=vmware.mediasite.com)

[MGT7737 - Intelligent Operations Management: A Customer Perspective](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/95268c27-2a95-4d78-b215-17e46517017a.mp4?playbackTicket=61fe4006feab4c87b5e4f8b5b587f278&site=vmware.mediasite.com)

[MGT7629R - 360-Degree Troubleshooting](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/66c85e14-7271-4af5-97ae-c3b5723f4984.mp4?playbackTicket=9f9926fe5b3d48bb9bbd98660fb3d15a&site=vmware.mediasite.com)

[MGT8902-QT - Process, Process, Process, And Then Tools](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/44974845-300c-4341-9dc8-6a8069bad800.mp4?playbackTicket=44d9d8aaaeea41d2ae313fceff8dd4e3&site=vmware.mediasite.com)

[MGT8751-QT - Be the IT Hero of Your Company and Discover How to Save Thousands of Dollars by Reclaiming Underutilized CPU, Memory, and Disk Resources](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/fb6cfd29-e101-47e6-8e7d-3c3f515b59e7.mp4?playbackTicket=24cf4062d20648f79673b9bec9a24aba&site=vmware.mediasite.com)

[MGT7782-QT - Automating Resource Reclamation in the Modern Data Center](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/f32d79f9-5b42-4875-a1dd-e27fb913ab4e.mp4?playbackTicket=e91cb53b4ef14898a81db62ca1164c0a&site=vmware.mediasite.com)

[MGT8355-QT - Tutorial: Build a data-driven story around capacity planning using VMware vRealizeÂ® Operationsâ„¢ and third-party Management Packs](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/f0b3de0f-fcc4-4b25-a595-479987b8df61.mp4?playbackTicket=a8b05bb4d1214394b550e15e2180aa88&site=vmware.mediasite.com)

[CNA7806 - Pivotal and VMware: The Lowdown on the High Up](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/f6537dbb-31c9-480c-adce-6ceb68ed6289.mp4?playbackTicket=98488704cebf4c6c86bdccbf23ca4d6a&site=vmware.mediasite.com)

[CNA7741 - From Zero to VMware Photon Platform](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/3c85b6b2-aefa-47c6-ba5c-e7a3e5298f2d.mp4?playbackTicket=7a9c5dee64c4484fa29e0eff620529ca&site=vmware.mediasite.com)

[CNA8986R - Running Docker on Your Existing Infrastructure with vSphere Integrated Containers](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/a459cc08-49fd-4487-8697-0a1351f1a054.mp4?playbackTicket=f632da63ee2a44d582dba9bddd9f4c3c&site=vmware.mediasite.com)

[CNA8313 - Your Open-Source Data Center](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/1666c675-e776-4d67-82db-135c40e81c49.mp4?playbackTicket=1fdf290c4fcb4438882924cf2786f27e&site=vmware.mediasite.com)

[CNA7524 - Photon Platform, vSphere, or Both?](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/d2d40873-7ad0-4272-b43d-130cbed7587a.mp4?playbackTicket=aaca4b6719924fcf900e845419b3870b&site=vmware.mediasite.com)

[CNA8145 - From Today to ''CNA'': VMware Technologies and DevOps Frameworks as a Service](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/e4e498af-e8ce-49d3-8a00-4d205692d12b.mp4?playbackTicket=9023ba16a8094c37a2e7b64ab142b909&site=vmware.mediasite.com)

[CTO7964 - Cloud Native Buzzwords (Demystified) for Dummies](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/ecd734f3-6c76-4c6c-afbe-1613fca1a917.mp4?playbackTicket=63b2e8ef787f462c8c7d1ac7f26fc0d9&site=vmware.mediasite.com)

[CNA8717 - vSphere Integrated Containers â€“ Learn how you can run Docker Containers, in Production, Today!](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/90bf852a-9035-4370-a948-d40b03b0b159.mp4?playbackTicket=e9020f829f3c48739ec67de7781f48a8&site=vmware.mediasite.com)

[INF10869 - Accelerate Your Journey to Cloud with Accentureâ€™s Private Cloud Blueprint](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/d6114ab5-5f54-4987-a5d1-26fb0ad92145.mp4?playbackTicket=48ab0319dfd34f208a28e0c64bbe8f73&site=vmware.mediasite.com)

[SDDC9462-SPO - The Edge is Still Bleeding: A face-melting technical smorgasbord of all things Converged, Hyper-Converged, Cloud Native & Software Defined](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/a18e8431-7d10-4c51-85ba-0470c76df70a.mp4?playbackTicket=ce64f6e3aea8462dac179ead5ceacd65&site=vmware.mediasite.com)

[CNA8986 - Running Docker on Your Existing Infrastructure with vSphere Integrated Containers](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/0a23fdc4-ddbf-4e8b-adde-4668538a5c10.mp4?playbackTicket=a317894dc71b4de88a40b519448230c3&site=vmware.mediasite.com)

[MGT7804 - Container Management with vRealize Automation](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/53af543f-d537-42a2-ab25-44c520c412e3.mp4?playbackTicket=86f42bf032104912a0c4c367d26a4810&site=vmware.mediasite.com)

[CNA8897 - Continuous Integration and Continuous Deployment for Containers: Confidently Promote Your Code into Production](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/6e8a6150-3771-428a-b01c-33c01f30366f.mp4?playbackTicket=b513913263544dc886b8841e675b76be&site=vmware.mediasite.com)

[CNA7454 - Introduction to Containers as a Service](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/c00a93e3-64d8-4672-b049-cc47c9fd57c4.mp4?playbackTicket=8ad0ca1d01c94a95b2e78c94b3e064a4&site=vmware.mediasite.com)

[CNA9994-QT - VMware's Cloud Native Stack](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/0e51cd9b-cf8a-4a81-8a22-a9f7722aab57.mp4?playbackTicket=0c03d7c0c85044819b6a79995801294c&site=vmware.mediasite.com)

[STO9984-QT - Business-Critical Applications for Virtual SAN](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/81cbad16-bc19-43dd-91f1-fb985fc0c09e.mp4?playbackTicket=e739b5a86feb4fa491b427c8e1792997&site=vmware.mediasite.com)

[CNA7813-QT - Architecting Cloud-Native Systems with Photon and Pivotal Cloud Foundry](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/00253617-2ab9-48e2-aa0e-fa42d572ba8b.mp4?playbackTicket=d27799adff314861b7813a5b666def81&site=vmware.mediasite.com)

[DEVOP7915 - Network as Code: DevOps Implications of Programmable Infrastructure](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/451f8d95-0e35-4d4a-9e06-c013217edc05.mp4?playbackTicket=ec24a213710841af983b232fb170ac53&site=vmware.mediasite.com)

[MGT8969 - Forrester Research POV on DevOps, Automation, and Virtualization Maturity Trends](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/c6d2d4f4-6465-4c3a-a9dc-5c878a50eda0.mp4?playbackTicket=9a993b7f850745e581a9efa04836542b&site=vmware.mediasite.com)

[INF8255 - Evolving the vSphere API for the Modern Era](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/fa25d2c4-fc32-43b4-bb5c-c2767bf10b7c.mp4?playbackTicket=7e46e6866fcb48bbaaebe6f25221bafc&site=vmware.mediasite.com)

[MGT8499 - Moving to Infrastructure as Code: How Fannie Mae Is Managing the SDDC with the vRCS Management Pack (aka Project Houdini)](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/39c21296-ef06-400c-8d13-3ce4c0da8e2a.mp4?playbackTicket=9b36558afa184416a6b94b55972486b4&site=vmware.mediasite.com)

[DEVOP9093 - Unpanel: How I Survived the DevOps Transition](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/ac7e82bb-cd89-4d96-9efc-7d45960c4b62.mp4?playbackTicket=bff7d89540d148bdadb922ccc9a1f902&site=vmware.mediasite.com)

[DEVOP9403-SPO - Hacking Your Backups: Making Your Backup Data & Systems Work for You](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/52479be8-d8f4-4551-9d8e-0b40dd2a2922.mp4?playbackTicket=b71665eb05354293a3da00217dc8e770&site=vmware.mediasite.com)

[DEVOP8924 - Building an Actionable Strategy Around DevOps and Platform as a Service (PaaS)](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/e3282a09-3b57-4119-a7a9-11d156262b62.mp4?playbackTicket=2b327bfff71c47b4a7be05fca2d57db1&site=vmware.mediasite.com)

[NET7858R - Reference Design for SDDC with NSX and vSphere: Part 2](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/878a7c6a-c7e9-46c4-ba78-d91c10d868da.mp4?playbackTicket=57aa895a99d7422981cc424295bc8cae&site=vmware.mediasite.com)

[DEVOP8971 - Run a Hybrid Application Across VMware and Google Cloud Platform](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/1a9e5995-9f83-4164-8471-94f38d614dc9.mp4?playbackTicket=09de6e9885b441f29d412a28df6a9746&site=vmware.mediasite.com)

[MGT8831 - Digital Transformation Through VMware DevOps Code Stream](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/53468bae-c764-4a76-a765-7c975389a135.mp4?playbackTicket=96bcb7b6d1c24630b358183dfc3164ec&site=vmware.mediasite.com)

[INF8546 - Case Study: Extreme Dogfooding of SDDC for VMware R&D's Private Cloud](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/76012b3b-d9c0-4309-a87c-d45364e908ff.mp4?playbackTicket=72dc153640134031b02c4d9d67973f0c&site=vmware.mediasite.com)

[DEVOP7859 - Real-World DevOps Customer Panel](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/26df095b-709e-4221-a6ca-4226bcdf3fb3.mp4?playbackTicket=1221ecb55bbf42db8556af80fbde8c54&site=vmware.mediasite.com)

[DEVOP7730 - DevOps Bootcamp Actual](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/dff45cf0-51e3-43af-afa0-d9810177f42e.mp4?playbackTicket=90873d94c3fe4cc69a544b64dd6d579b&site=vmware.mediasite.com)

[DEVOP9965-SPO - Implementing DevOps with VMware vRealize and Cisco UCS](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/725fe6a3-9cab-449c-afe3-560a589fd8b6.mp4?playbackTicket=07c6444d467843fd80ce00860b122d13&site=vmware.mediasite.com)

[NET8368 - Network as a Service (NaaS) Transformation with NSX](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/212c06af-c61c-46e9-9424-18cb32fbc742.mp4?playbackTicket=bd6975d2e2974e2f96e9018b29e2dcfb&site=vmware.mediasite.com)

[INF8540-SPO - Say Yes to vRA and vRO in a Real-World Hybrid Cloud](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/485b49c9-7428-411f-bded-d80dee1739bc.mp4?playbackTicket=7baac13a1e8441f9b366dcd95bc4ac93&site=vmware.mediasite.com)

[INF8635 - vSphere Content Library: Organize, Distribute, and Utilize Your Content Effortlessly](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/6f7d580c-e67a-4839-a207-2fca37749af1.mp4?playbackTicket=374d27ab755a4d7a82d1c515bb7eca80&site=vmware.mediasite.com)

[NET7858R - Reference Design for SDDC with NSX and vSphere: Part 2](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/9e2db62c-0e26-4abe-8be8-47dbf9923a22.mp4?playbackTicket=05b78ec0c2534eceb5939ab8b3fa94ec&site=vmware.mediasite.com)

[DEVOP7788 - Industry Perspective: Enterprise Reality of Doing DevOps](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/602f7c97-9082-4bc4-ada1-6c6afb1f1361.mp4?playbackTicket=11dd53e787d44b9d8516139b4006768f&site=vmware.mediasite.com)

[DEVOP7674 - vRA, API, CI, Oh My!](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/d6743640-1d0c-4ef0-849f-bab15f0268dc.mp4?playbackTicket=9598c7472aa04a58a60acd870afb95a4&site=vmware.mediasite.com)

[MGT8766 - How IT Can Enable DevOps and Development Teams to Rapidly Deliver and Iterate Robust Applications in a Multicloud Environment including VMware, AWS, Azure and Softlayer](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/4eab316d-ace5-4486-a642-84e4c5811671.mp4?playbackTicket=ee17071a03b3419598bb927c3dffa0f4&site=vmware.mediasite.com)

[DEVOP7447 - Redefining Enterprise Resource Planning Using vSphere 6 and Workspace ONE](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/b68e46cc-409c-44b5-958e-36175ff360b7.mp4?playbackTicket=0f53b2b4e3674f208ad968e29166bfd8&site=vmware.mediasite.com)

[DEVOP8630 - Increased Employee Productivity with Enterprise-Grade Security Using VMware ITâ€™s Managed Public Key Infrastructure Service and AirWatch](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/befc6a60-c561-4e7b-8e96-0fd3faa3064c.mp4?playbackTicket=5f3b5a4a957142b3bd496cb936383a50&site=vmware.mediasite.com)

[EUC7799 - Design Horizon the Easy Way with Help from the Horizon Sizing Estimator](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/0751d0e8-46b0-472b-9c04-9ede3e382b87.mp4?playbackTicket=d3bf8603a9734ffd8544a531e478d9c4&site=vmware.mediasite.com)

[EUC7562 - Cloud-Hosted Virtual Desktops and Apps: A Technical Deep Dive into Horizon Air](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/3dc80c8a-0c33-45ec-b1b1-d0813053258c.mp4?playbackTicket=4ae7dcc7ed5440d094e1033bf8000f2c&site=vmware.mediasite.com)

[EUC7998 - The Latest in High-Performance Desktops and Applications with  Horizon 7, Blast Extreme Protocol,  and NVIDIA GRID vGPU](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/24ffd9ea-2f2b-482c-8950-d9a117c0a5c0.mp4?playbackTicket=1eee7886ebf9418e85f81e232f018927&site=vmware.mediasite.com)

[EUC9392 - Expand Your Enterprise Mobility Strategy with VMware and the AirWatch Partners](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/3cdeaa04-4ff3-45aa-8aa7-f7d87786a5a4.mp4?playbackTicket=ebf3308441e840c3be2c036c720c3020&site=vmware.mediasite.com)

[EUC8216 - Deep Dive: Deploying Office365 Applications on mobile devices with AirWatch](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/db7df503-595f-4100-ab82-b28996b4be6d.mp4?playbackTicket=c5176709fca34bdea736d8f11eb1c890&site=vmware.mediasite.com)

[EUC7644R - Unify Endpoint Management Across Mobile and Desktop](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/ff9b9d5c-3dca-41b2-ab2c-7c42ea7672d1.mp4?playbackTicket=8049c31d7ddf4c9fb7195d60f859374b&site=vmware.mediasite.com)

[EUC8243R - Troubleshooting 101 for Horizon](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/f8a2493b-71cd-4671-9dca-bfd0807770f5.mp4?playbackTicket=9d510aa7d0b642a482bd5465d3573d92&site=vmware.mediasite.com)

[EUC9386 - Whatâ€™s new with Workspace ONE: Identity meets Mobility](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/0d8d5f67-6515-4e9c-aac3-6b2cc895f0f1.mp4?playbackTicket=e59d70d612054612a30088218314eafb&site=vmware.mediasite.com)

[EUC7870 - VMware's Solution Strategy on Mobilityâ€™s Evolution to Internet of Things into 2016 and Beyond](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/c87ab1e1-d61a-4953-8911-727c2b99c86c.mp4?playbackTicket=4384cf74e45f4966ae5a8bda88473a89&site=vmware.mediasite.com)

[EUC8938 - Limitless Learning: Leveraging VMware Technology to Provide a Digital Learning and Working Environment for Every Student and All Faculty and Staff](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/2c9d47f7-c4db-4509-b8f0-ddc90df7392c.mp4?playbackTicket=606a79808bc9450b89eed235333e22d1&site=vmware.mediasite.com)

[EUC8160r - Discover AirWatch: Enterprise Mobility Management](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/7cefde1a-fe78-46b5-9bf3-7d976f8fcc80.mp4?playbackTicket=9c3d06f0600a4332ac70cec5d183f144&site=vmware.mediasite.com)

[EUC9395 - How Horizon 7 and Horizon Air Are Changing the Cost Economics of Virtual Desktop Delivery](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/b1a82cb2-4e1c-41a6-ada7-56c0205d839a.mp4?playbackTicket=22c90f8c6d734b88b098a65ce5ff1b32&site=vmware.mediasite.com)

[EUC8725 - Everything You Need to Know About Horizon Remote Desktop Services Hosted Applications (But Probably Do Not)](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/0d23d478-06ea-4e5b-b874-b01ccf6d5dfd.mp4?playbackTicket=8935b2c0152b4bd8a8a6f521b3f61f65&site=vmware.mediasite.com)

[EUC8853 - Taking Back the Desktop](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/67a58451-7ada-4136-b115-c43e7db21415.mp4?playbackTicket=b05a5d64ed9f46b2931a2e5cde00fc0f&site=vmware.mediasite.com)

[EUC8346 - Modernizing and Mobilizing Retail IT](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/d4bc8d91-2cd0-43f0-993d-769d62815ef3.mp4?playbackTicket=b5c7dd335d504c198198ab8f74dcb1b4&site=vmware.mediasite.com)

[EUC8822 - Case Study: Large-Scale Deployment of VMware App Volumes and User Environment Manager for 10,000 Seats](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/333badbf-1f4c-4ebb-964b-cb49b90e6e3b.mp4?playbackTicket=9f423610102347d4bdfaf95951def308&site=vmware.mediasite.com)

[EUC8521 - The Future of VMware Fusion and Workstation](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/426732dd-6b9f-42b5-ace2-a480c6947905.mp4?playbackTicket=83e731ec9f1f4d7d8c8a43208aa59f74&site=vmware.mediasite.com)

[EUC8605 - Next-Generation Mobile Productivity with Workspace ONE Apps](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/302fee13-a6fa-4c47-ab0e-0deeb22c056f.mp4?playbackTicket=27976a3da77f402b8d3664e467149ed0&site=vmware.mediasite.com)

[EUC7995 - Enterprise Mobility Automation using Software Defined Data Center (SDDC): Role-based Desktop and infrastructure provisioning](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/cac0cea1-25e9-43ee-a38a-535f585f3366.mp4?playbackTicket=bb59997842554ccdae3807e98ed13c2c&site=vmware.mediasite.com)

[EUC9179 - Introducing Horizon Air Hybrid Mode: Low-Cost, Simplified Virtual Desktop and Application Deployment and Management](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/4a4e16fa-61bd-46b4-b451-f3db2851327c.mp4?playbackTicket=fde35c09474c4f75b3791b608ac85c85&site=vmware.mediasite.com)

[EUC8345 - Mobilizing and Modernizing Government IT to Advance Missions: The Secure Digital Workspace for Government](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/9968bd24-8546-482d-b9ba-2bc1990ece46.mp4?playbackTicket=c97b335979b7416f9df02aad104bca91&site=vmware.mediasite.com)

[EUC9451-SPO - Preventing Attacks on Mobile Devices using AirWatch Integration with Palo Alto Networks](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/47bdb86a-ffb3-4698-bf1c-81c4d3de11ad.mp4?playbackTicket=97729d54fa524229a85a54e7750d85d8&site=vmware.mediasite.com)

[EUC7797 - How to Manage Personal Settings with App Volumes and ThinApp](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/345bb591-6ea5-4abf-b74f-6326b60e96ab.mp4?playbackTicket=ae4d5a9173c54a59830ceba7ecf09cc1&site=vmware.mediasite.com)

[EUC8392 - Untethered Yet Secure: Technical Deep Dive on Using Horizon FLEX to Manage VMware Workstation Player and VMware Fusion Pro](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/9bce471a-b9fb-4ae6-a220-5e011b345662.mp4?playbackTicket=e724933dde7b4659b600d07bfd83acdb&site=vmware.mediasite.com)

[EUC8648R - Architecting VSAN for Horizon the VCDX Way](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/889c34d2-5e13-464d-8c21-221d3d869f96.mp4?playbackTicket=b1eb6903f45e44bca1e91b9a8cc8c6ea&site=vmware.mediasite.com)

[EUC8784-SPO - Architecting Highly Available, Scalabe and Resilient Enterprise Mobility & Desktop/Application Solutions](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/bfab2dd5-02ef-4ff4-8065-05cc2f14d541.mp4?playbackTicket=f7df806097994231b217e52069929118&site=vmware.mediasite.com)

[EUC7519 - Access Point: Advances in End-User Computing Remote Access](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/5801bd25-a7d3-4122-8aa6-91d609c00a8c.mp4?playbackTicket=695c23456a1a4f8db07f8c3beffe1f0c&site=vmware.mediasite.com)

[EUC8745 - Under the Hood with Identity Manager and Office 365](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/56941882-36db-4144-ba46-3ef6f9c471cd.mp4?playbackTicket=198b1e642f224222874a65b1d700f9a7&site=vmware.mediasite.com)

[EUC9388 - Customer Panel: How Enterprises Are Using VMware Identity Manager to Enable Their Users to Be Productive on Any Device, Anywhere](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/d8f728a4-bfe8-4cbd-8c5c-784b6a74bc47.mp4?playbackTicket=8f2ac968cf7e4f2d9e851c26884fa23e&site=vmware.mediasite.com)

[EUC9394 - Horizon Air and Interconnecting the Clouds](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/58c631da-fd14-41bd-bf09-522c23b6168d.mp4?playbackTicket=72f803b61da9457a86d23993c4eb81ff&site=vmware.mediasite.com)

[EUC9139 - NSX and Horizon Reference Design: Secure End-User Computing](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/3a14c5bf-dc3a-44eb-9128-5373d9cee5ee.mp4?playbackTicket=d94d056e8e684c338e553a4d21cf7ca5&site=vmware.mediasite.com)

[EUC7864 - Protect the Edge: Secure IoT and Medical Devices](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/83b28d53-1ee1-4e0e-a43c-9201e35aea4d.mp4?playbackTicket=28f77742217d4d23adfadeb7f0617a1d&site=vmware.mediasite.com)

[EUC9391 - Managing Windows in a Modern Mobile-Cloud Framework](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/705317fd-7db1-4c27-942d-a50cceefa3ec.mp4?playbackTicket=37cfe76c3ca54ef3a52c12361f38dbc8&site=vmware.mediasite.com)

[STO7560 - Four Unique Enterprise Customers Deployment of VMware Virtual SAN](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/f9b56ed8-e637-4547-82f4-7ad1563fcbcc.mp4?playbackTicket=fd87d6b2b7274a41ab99ad8c96ca269c&site=vmware.mediasite.com)

[STO8754 - Virtual SAN and Horizon: Designed for Simple, Powerful Virtual Desktops](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/ae6ca51e-07e9-4a31-ba27-d33ed60ca211.mp4?playbackTicket=3104be6023a448d190639ce863626031&site=vmware.mediasite.com)

[EUC7613 - Ask the Expert: Everything You Want to Know About VMware End-User Computing](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/30c6553a-e7fe-44b5-b9c1-eeaa7162581f.mp4?playbackTicket=ffbcb3fd886d4e06b652bfc655ad954e&site=vmware.mediasite.com)

[EUC9390 - Securing Against Cyber Attacks from Datacenter to Device](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/ca1ca96c-439e-4879-8cbe-2adba1a32723.mp4?playbackTicket=04a9cf40b3bd4e809883169cb3b224e7&site=vmware.mediasite.com)

[EUC7888 - Why Siemens Uses High-Performance Desktops with VMware Horizon and Nvidia GRID vGPU](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/e72851aa-58c4-4460-b904-68a539c6951d.mp4?playbackTicket=80422d115c574be286950daacb7199f1&site=vmware.mediasite.com)

[EUC8603 - Support the Complete Mobile App Management (MAM) Lifecycle with AirWatch](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/a99f5a37-5d74-4b65-84cf-4a818c7bb190.mp4?playbackTicket=009a41d75bc2468585cccfaff06d75f9&site=vmware.mediasite.com)

[EUC8648R - Architecting VSAN for Horizon the VCDX Way](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/8511e61a-b3b4-48e5-a0fd-e3fa562a2417.mp4?playbackTicket=da05248f7c4c4e37bdfea81b5203fa09&site=vmware.mediasite.com)

[EUC7611 - User Environment Manager 9: Do It Fast, Do It Right, Do It Big!](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/465fdb6d-2db1-49c5-b21d-5761066447cc.mp4?playbackTicket=5cd8b1fe4cec43b1894ec00336de8f08&site=vmware.mediasite.com)

[EUC8670 - Your Digital Workspace: How to Plan, How to Start](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/b451012c-7040-450f-b346-4731125316a1.mp4?playbackTicket=f7c2fdff7a8c4fe698ec2680dea92370&site=vmware.mediasite.com)

[EUC9610-SPO - Optimize Storage Infrastructure for Horizon Performance](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/3b9e9aa7-9370-4154-93a3-6ebc250e4157.mp4?playbackTicket=408e7ce04de84b8aabfc4404524bdb4f&site=vmware.mediasite.com)

[EUC7644R - Unify Endpoint Management Across Mobile and Desktop](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/dba82114-36af-4b2a-95b8-180e151ade94.mp4?playbackTicket=8cdada6a5b80439eb52e0ab22a375a01&site=vmware.mediasite.com)

[EUC7453 - Horizon for Linux Technical Deep Dive](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/3e238fd9-4693-485e-b66a-c0a545377032.mp4?playbackTicket=48c9c39ecbc54b73b1241823408b4bc1&site=vmware.mediasite.com)

[EUC8441 - End-to-End Security for End-User Computing](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/f972d8b3-6167-482f-82a9-72ea1107a807.mp4?playbackTicket=81ff91189754444c869405c68206e221&site=vmware.mediasite.com)

[EUC7856 - Solve Your Citrix Problems with VMware Technologies](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/920db7a3-ccba-44e7-87bd-12b1b93f569d.mp4?playbackTicket=67ccdad6b228470c8f8f85107876a96d&site=vmware.mediasite.com)

[EUC9922-SPO - Cisco HyperFlex Systems: Next Generation Hyperconvergence](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/9629f6e7-abb8-4e63-8d78-4405c808dd5a.mp4?playbackTicket=85c6ee1de75442798cc4989480fac8db&site=vmware.mediasite.com)

[EUC9992 - Ask the Experts: Practical Tips and Tricks to Help You Succeed in EUC](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/0332e1ad-b459-41e1-abf8-a25209832c01.mp4?playbackTicket=aff4360b1e10468f9ca0abe03e96f6f0&site=vmware.mediasite.com)

[EUC8437 - Workspace ONEâ€™s Secure App Token System (SATS) for Mobile Single Sign-On explained](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/aa848ed6-6904-404f-8cac-3350767eceba.mp4?playbackTicket=adc9db80c2334188964b356fdbb1d2b9&site=vmware.mediasite.com)

[EUC8589 - Best Practices for Effectively Planning and Implementing BYOD Programs](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/ae245971-c6a5-4e2d-a4f4-4f85831e3944.mp4?playbackTicket=0c19858e825a4716b8f0f5ac4960e6f8&site=vmware.mediasite.com)

[EUC9393 - Real-time Endpoint Visibility and Control with VMware TrustPoint](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/695a0ed4-494d-40db-b04f-70337e4c5f71.mp4?playbackTicket=c69ed5ff977c4b89bba68dc4cdf4c5ab&site=vmware.mediasite.com)

[EUC9469-SPO - Scale, Efficiency and Data Management for EUC solutions with NetApp](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/0f441738-4956-4143-a512-5303f8ae6ca0.mp4?playbackTicket=76077ffe0841407b9c573bcba4d52abe&site=vmware.mediasite.com)

[EUC9217 - On-Premises Workloads with Cloud-Based Management: Technical Deep Dive into Horizon Air Hybrid Mode](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/09a96be4-52a3-4e8b-b03e-15b93dc25c3f.mp4?playbackTicket=ad6aac39896c442ba8f74d4733abed9a&site=vmware.mediasite.com)

[STO7443r - How did VMware IT Achieve a Non-Disruptive Disaster Recovery Test in 90 Minutes for 900 Terabytes of Storage and 2000 Production Virtual Machines?](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/a04b4f51-dd0c-47e4-a2e8-4f9460a7ff14.mp4?playbackTicket=e726eead5790453a8a6cb1a4890edbe4&site=vmware.mediasite.com)

[EUC9160 - Secure Digital Workspace of the Future: Embracing the Opportunities Presented by Enterprise Mobility in Financial Services](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/758a3a0b-2c40-4ba7-8bf4-a6e35056ba08.mp4?playbackTicket=4ccbf8c70994434e96934a2f62bdd551&site=vmware.mediasite.com)

[EUC8160 - Discover AirWatch: Enterprise Mobility Management](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/1ce83258-307d-4813-a9a4-4a1c47fb4b78.mp4?playbackTicket=572cc64cda9c4e60aced4234a11a705d&site=vmware.mediasite.com)

[EUC9970-SPO - 0-70 with Horizon 7](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/0fbcf7e1-009d-4ffc-914f-886253b97157.mp4?playbackTicket=74e78c6603d84f4bb64eb612880c37b9&site=vmware.mediasite.com)

[EUC8990 - CSC Hyper-Productive Digital Workplace](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/42287088-fb98-46a8-97b2-6e02f72cdf1b.mp4?playbackTicket=e120c8870ef64631a05d95f6d6a38d18&site=vmware.mediasite.com)

[EUC7601R - Advances in Remote Display Protocol Technology with VMware Blast Extreme](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/1fff7498-1519-4a87-adc9-9eda2a63eda2.mp4?playbackTicket=66f751b062814a74b97797dfdb9354b2&site=vmware.mediasite.com)

[EUC8584 - vRealize Operations: The Authoritative Source for Monitoring and Reporting for Horizon and Citrix XenApp Deployments on vSphere](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/c6bdf625-2bb7-42bc-a996-9a220a87af4e.mp4?playbackTicket=8358e683a92b41b399e41f3c6250d5d9&site=vmware.mediasite.com)

[EUC9389 - What Is VMware Workspace ONE?](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/6980f296-5b3a-48ed-b653-211d9c56ac57.mp4?playbackTicket=39aefbc7dde14efd8c7a70173a4d685a&site=vmware.mediasite.com)

[EUC7800 - Deliver a Digital Clinical Workspace: Healthcare Customer Panel](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/d5d36426-3659-4354-8c36-13a78500b914.mp4?playbackTicket=2c029fdd42994ae9977486b86349459e&site=vmware.mediasite.com)

[STO7443 - How did VMware IT Achieve a Non-Disruptive Disaster Recovery Test in 90 Minutes for 900 Terabytes of Storage and 2000 Production Virtual Machines?](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/356309a5-f740-4cda-bc4d-5bec22a96d82.mp4?playbackTicket=573c66010c2a4b0a8809651a248a5c9b&site=vmware.mediasite.com)

[EUC9387 - Deployment Best Practices for VMware Identity Manager](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/2b083f40-2cf1-477a-998c-7409584245e5.mp4?playbackTicket=e2843ed530684df1be335d83d80ee7aa&site=vmware.mediasite.com)

[HBC8915 - SLED and Cloud: Is Cost Containment the Right Question?  Yes and No](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/79227b2a-7fd1-4bcc-80e7-b5879832f0d7.mp4?playbackTicket=1b9f88ed450f4f3f8812f2881c605bbe&site=vmware.mediasite.com)

[HBC8298 - Designing a Business Continuity Solution in the Cloud](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/9a1188a2-d2f0-4d36-b18b-52870eb5d4e5.mp4?playbackTicket=7915b37be5e847f7970a260c79cdb48b&site=vmware.mediasite.com)

[HBC7948 - Extending Your Data Center to vCloud Air in Less than 60 Minutes](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/a4ca518f-da7f-4103-a0c7-5efcfcd619b4.mp4?playbackTicket=44585a059f7d4df68a68d8f6d8d7eb99&site=vmware.mediasite.com)

[HBC9111 - vRealize Operations and vCloud Air: Monitoring Your Cloud](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/f8c7643e-51a5-4c95-901f-00f21ef427df.mp4?playbackTicket=6f05d9559ab94c2186cf8c14a7f250ba&site=vmware.mediasite.com)

[HBC8805 - Extend Your Data Center to the Cloud: A Real-World Example](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/7106079c-72a7-4bc4-a587-b90f6651198a.mp4?playbackTicket=264bcdc2e7a048b0a0f33691971b50e1&site=vmware.mediasite.com)

[HBC10827-SPO - Ensure Success of Hybrid Cloud with Amazon Web Services](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/a749a3ab-4c94-4f7b-abcb-f160de2023d2.mp4?playbackTicket=cebcb8d7984e42abbaf624cdc40187f5&site=vmware.mediasite.com)

[HBC8295 - The VMware Journey to Cloud with vCloud Air](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/f9598f6b-9b50-4f5a-a4bb-ac2c5ed72d08.mp4?playbackTicket=7f52eba54d4b46ccae0d8f06a6c5b30b&site=vmware.mediasite.com)

[HBC9401 - Whats New with vCloud Air](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/f53efd07-a26c-472d-bed0-ba09e4183c97.mp4?playbackTicket=65b5449ceccb4180b39d68ce84ca19fb&site=vmware.mediasite.com)

[HBC9092 - vCloud Air: Advanced Networking Concepts](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/3a1f6d3d-9236-47fc-afd3-fdc163ece69a.mp4?playbackTicket=26dbe4591aca481e98f83b81961c9051&site=vmware.mediasite.com)

[HBC9065 - Better Together: vRealize Automation and vCloud Air](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/5ce767de-b2df-44ab-bf07-1df96e80670e.mp4?playbackTicket=2f661ac191b84efeab558f407343c657&site=vmware.mediasite.com)

[HBC8292 - vCloud Air Recovery as a Service (RaaS) Deep Dive](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/75913957-404b-4b52-a877-1a224fac9ed4.mp4?playbackTicket=2952e454e05a46d4a74ecf86c6fe5a3c&site=vmware.mediasite.com)

[HBC8617 - Seamless Security and Compliance in a Hybrid Cloud Architecture](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/4668f565-aa7c-4d04-9219-fa3f2011ea13.mp4?playbackTicket=3d5d58e86f79402fbc6d76dea2b80777&site=vmware.mediasite.com)

[HBC8563 - VMs and Containers: Extending Docker to vCloud Air](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/153f03e4-85b8-4164-b07b-577694bb4a5b.mp4?playbackTicket=ed043bb531f14c1a91be38be6340565d&site=vmware.mediasite.com)

[MGT8767 - How Zebra IT transformed to become a cloud broker running global virtual infrastructure in multiple public and private clouds](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/0d2ddac4-f879-46f4-bc9f-0c90928be87f.mp4?playbackTicket=01c8ad5b0bfe40798f16bd36aeaa7fb9&site=vmware.mediasite.com)

[HBC9164 - Modernizing Healthcare IT with the Public Cloud, Your Way!](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/aa5252bd-f68e-479d-ba82-511a81ad36c2.mp4?playbackTicket=a2fa058fc51845ad9066a85d3a2bc2dc&site=vmware.mediasite.com)

[HBC8952 - vCloud Air Design Patterns for Design, Implementation, and Operations](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/0d6a0dad-c682-4206-b611-ecd00d37e0ed.mp4?playbackTicket=57c4a6d77f2246488e8d49e31ddec329&site=vmware.mediasite.com)

[HBC7646 - St. John's University Leverages vCloud Air Disaster Recovery for Its Critical ERP System, Banner](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/9931795e-75c4-4278-844a-4e81e1589523.mp4?playbackTicket=8f36a8b1ff404286afe1fca09fb45e2b&site=vmware.mediasite.com)

[HBC7602 - Build True Hybrid Clouds: See How Service Providers Can Use NSX to Extend Customer On-Premises Data Centers](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/38d02c53-daf4-4e0c-bcbf-b66890345119.mp4?playbackTicket=1aa7d1a11a4a4b3ea043b0eb1743cd61&site=vmware.mediasite.com)

[HBC8474 - Making It Easy to Orchestrate and Automate Your Hybrid Cloud Environment](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/799aec9e-91f7-424e-bcd3-5292e896d295.mp4?playbackTicket=99b2eadc3bfd402baf143dc2b9768ca5&site=vmware.mediasite.com)

[HBC8503 - Taking VDI and Published Application Environments to the Next Level with App Volumes](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/3c07d192-efa6-41cf-8625-670210ef8037.mp4?playbackTicket=60d89373eb7242e59f224ecfced183a2&site=vmware.mediasite.com)

[HBC9463-SPO - Data Protection as a service for your vCloud Director environment with Veeam](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/c1d161f6-d86c-4f51-bd4b-a0ac96dd163a.mp4?playbackTicket=686df661268641bb8cc368063748f167&site=vmware.mediasite.com)

[HBC7943 - Designing a Data Center in the Cloud: A vCloud Air Perspective](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/12653315-3309-48f4-8e56-30767992e382.mp4?playbackTicket=d7c26969e577402da10c6e6ca6dfc85b&site=vmware.mediasite.com)

[HBC8226 - Why Cloud Networking and Security Matter â€“ A Primer for Choosing Your Ideal Cloud Provider](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/7cbf7cf6-1e27-41cd-a7ef-fd2b96e4a5b0.mp4?playbackTicket=d041df4307c0402c95d91d55ddd04912&site=vmware.mediasite.com)

[HBC8312 - Maintaining Regulatory Compliance in the Hybrid Cloud](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/06d347aa-aac9-4df8-a124-4544d9888e29.mp4?playbackTicket=985c16a72513402d94ad9474a0a90be2&site=vmware.mediasite.com)

[HBC8799 - How OVH, vCloud Air Network Service Provider, Is Using NSX to Easily Onboard Workloads to the Cloud](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/91183f3f-781d-4c55-b60e-f0f5b55468a6.mp4?playbackTicket=00dfe4bd9cd1429d93dfa925707eef71&site=vmware.mediasite.com)

[HBC9171 - Intercontinental vMotion with Purpose](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/a2cbb462-5e27-4897-836d-0b3f009f2d59.mp4?playbackTicket=9831b2d593864190beeed0fcdeece851&site=vmware.mediasite.com)

[HBC8484 - Data Sovereignty and Compliance Automation In The Cloud](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/4b42e505-08e0-4fec-b301-da013525f163.mp4?playbackTicket=68d5af75978e405cbc50dd958c3d76df&site=vmware.mediasite.com)

[HBC7999 - VMware Availability for VCAN: Native vSphere Replication](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/025a6455-130f-4542-b0ca-3f9f3191c798.mp4?playbackTicket=53865952c2ad492e8a3c62daeedd9891&site=vmware.mediasite.com)

[HBC8504 - Have It Your Way: Hybrid Cloud Management](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/1d006204-6f3e-44fe-b6c0-01dff52f1885.mp4?playbackTicket=2042f5e5ab0c4b0e8ca01c3a67e1b9b7&site=vmware.mediasite.com)

[HBC7928 - Introduction to vCloud Air Networking and Security Portfolio: A Technical Deep Dive](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/72693426-caa8-4829-888e-eac837f33266.mp4?playbackTicket=31601b70809f4b80ac4263763b14530c&site=vmware.mediasite.com)

[MGT8084 - Hybrid Cloud Case study: City of New York Self-Provisioning Gateway 2.1](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/ed5da4fe-d8f5-4fd6-a5fa-923c04db8c4a.mp4?playbackTicket=cba31972674e4807a9e65607253c0b51&site=vmware.mediasite.com)

[HBC8491 - Deep Dive: VMware on IBM Cloud Validated Design](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/2d098a0a-d6b4-43f1-b95f-e9011497d904.mp4?playbackTicket=3511334826a9452bbc5feca866e17ba0&site=vmware.mediasite.com)

[HBC9453-SPO - Achieving New Levels of Cloud Efficiency over vSphere based Hyper-Converged Infrastructure](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/a59122b8-3952-4ee1-81a9-781184008646.mp4?playbackTicket=9a0ee597938b4e3a8ab66c35f468d5b7&site=vmware.mediasite.com)

[HBC7954 - Implementing Hybrid Cloud with VMware vCloud Air and NSX: A Closer Look](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/ebef739a-a48c-4c29-829e-08943179e525.mp4?playbackTicket=4765fa51249e483c9331a81609ab7105&site=vmware.mediasite.com)

[HBC9185 - How to Connect Your On-Premises Data Center to the Cloud](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/f6ee960d-55a7-4f01-8e70-0154aa64975f.mp4?playbackTicket=c36d3cb9e8ce4582963513d8df1f0a02&site=vmware.mediasite.com)

[HBC8861 - Getting the Most Out of Your Hybrid Cloud Service Provider](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/8bb37f93-6ecb-4c56-b4ac-fd8ef1217b15.mp4?playbackTicket=3a2fbafaf8c447c2b38c5016806d975d&site=vmware.mediasite.com)

[HBC7830 - Virtualize, Secure, and Extend Your Data Center to the Cloud Using NSX: A Perspective for Service Providers and End Users](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/96ab1fa7-4fb1-432c-a333-6077482f653d.mp4?playbackTicket=f798e14e495a44419bcbdd906fafc751&site=vmware.mediasite.com)

[HBC7700 - Disaster Recovery in the Cloud with VMware vCloud Availability](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/75a2ecce-4bd4-4090-957f-be6fb1037bf7.mp4?playbackTicket=3fd0022f5d904c74bda32b4f915e0af1&site=vmware.mediasite.com)

[HBC9949-SPO - Hybrid Cloud: Automated and validated VMware deployments on IBM Cloud](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/4797fd28-6cbe-4ba0-8f2f-04d837ff4a45.mp4?playbackTicket=84806418ce534ed3930d964422880f7e&site=vmware.mediasite.com)

[HBC9611-SPO - OnApp: your hybrid cloud delivered](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/0d345739-6ad9-46b1-a9c2-596f1935def3.mp4?playbackTicket=f792a73f5f724b5ea09e811ef9fda05e&site=vmware.mediasite.com)

[HBC8046-QT - Customer Onboarding with VMware NSX L2VPN Service for VMware vCloud Air Network](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/d632a06b-7662-4524-845f-4350274c1778.mp4?playbackTicket=63b57f92e1fd476dbc99c6b17435f81d&site=vmware.mediasite.com)

[HBC7661-QT - Generate Revenue with vSphere Optimization Assessment (VOA) for Service Providers](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/d2d85af5-7f02-408e-8222-f9ae4e5a46c6.mp4?playbackTicket=faa92294134a4292ad2b9569bcb8c587&site=vmware.mediasite.com)

[STO8164 - Benchmarking VAIO-Integrated Caching. Is it Really Faster? How Much, and Why?](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/946b3b60-7277-4823-8a43-8e657619c1e2.mp4?playbackTicket=d8c94c93f2e54e41898865f331491116&site=vmware.mediasite.com)

[STO7973 - Architecting Site Recovery Manager to Meet Your Recovery Goals](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/145853e6-414b-40d3-9064-3c6258b2c562.mp4?playbackTicket=12d37a8b794747f4abb46bbf2a2c341d&site=vmware.mediasite.com)

[STO8422 - Virtual Volumes: Why?](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/c7322870-0548-49d7-8898-70fa369c71dd.mp4?playbackTicket=2ec1cde1e80b46459ae185aa2b4bebd7&site=vmware.mediasite.com)

[STO7848 - Virtual SAN Storage Efficiency Technologies](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/51d8e968-a14a-4fd6-9a70-78eea373aa51.mp4?playbackTicket=fe8ffe8be7204377b7813aa5edf99eb1&site=vmware.mediasite.com)

[STO7549 - Achieving Agility, Flexibility , Scalability and Performance with VMware Software Defined Storage (SDS) and Virtual Volumes for Business critical databases](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/5d219294-dd04-4027-b8d3-e1d97bc4c07f.mp4?playbackTicket=22d38b0c8e0c4be6935255efc1a817db&site=vmware.mediasite.com)

[STO8246R - Virtual SAN Technical Deep Dive and Whatâ€™s New](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/6bc53227-80fd-40bf-9fa2-72f6dec72e4a.mp4?playbackTicket=d86bbd45ece540129bb1f9a17cacefbc&site=vmware.mediasite.com)

[STO8619 - Transitioning to VVols: Partner Panel](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/3bbc94f5-0e4d-4eb1-b446-22846fc5fd8d.mp4?playbackTicket=dacc61cc741441a3848bf2cffd5d9c67&site=vmware.mediasite.com)

[STO9925 - Enterprise-grade data protection for Virtual SAN with EMC Recoverpoint for VMs](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/29f55542-3995-4122-a239-060e5e83c345.mp4?playbackTicket=1c0460bda8f6488aa3a010bb682de766&site=vmware.mediasite.com)

[STO7903 - An Industry Roadmap: From storage to data management](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/d39a396e-cc32-4821-ba43-67ccd49d41bc.mp4?playbackTicket=259cbb81fa5b4d2bbea4085340e8e4d5&site=vmware.mediasite.com)

[STO9014 - Deploying HCI at datacenter scale](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/02d2d30f-5cfa-41a3-a59b-a339bf394a61.mp4?playbackTicket=e9a0f0da8cfe4e4db3dabe6723b0cdc9&site=vmware.mediasite.com)

[STO9157R - Achieving Unprecedented Availability, Security, & Cost Savings with VMware Virtual SAN and NSX](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/ffbe6fc0-a23d-434d-90f7-2c569a28943e.mp4?playbackTicket=e59b8000dac14c2cb405b92cf4e4126f&site=vmware.mediasite.com)

[STO8880 - Successful ROBO Design with vSphere & Virtual SAN](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/7fd88b7f-ac04-4d07-acd3-9729fc7e6182.mp4?playbackTicket=6c6134161e01464595c21ecae7802c12&site=vmware.mediasite.com)

[STO8562 - Deployable and Tactical Hyper-Converged Software (HCS) for the Battlefield](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/7dca7dbc-89a1-495b-a2be-d76e6620f8c1.mp4?playbackTicket=7368badda56d474ab218795b2f6bc25e&site=vmware.mediasite.com)

[STO8795 - Ushering in a New Era of Hyperconverged Big Data - Hadoop over VSAN](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/c9068a08-c05b-4ad7-81eb-c44b2b26bbf2.mp4?playbackTicket=dc646a3dcf344f7f89c5e7e880737e60&site=vmware.mediasite.com)

[STO8750 - Troubleshooting Virtual SAN 6.2: Tips & Tricks for the Real World](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/95b66ec6-541c-4fab-a042-61481853b9cd.mp4?playbackTicket=03b6e6c6781b4488a13529ca478d89f3&site=vmware.mediasite.com)

[STO8718-SPO - Building Next-Gen Data Protection for VMware Environments with Rubrik](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/87aa3401-c537-46b4-934c-5e4c098e5b1c.mp4?playbackTicket=1f18da2d16c9421ab7f156eec5b05a37&site=vmware.mediasite.com)

[STO9423 - File Services on Virtual SAN](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/55454cf3-9e48-47a2-a9a3-2f10341456f6.mp4?playbackTicket=9aefd024a8eb4f719d97a5d25bf1d5af&site=vmware.mediasite.com)

[STO8246R - Virtual SAN Technical Deep Dive and Whatâ€™s New](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/f2db2653-853b-47eb-9953-57f83aec95ae.mp4?playbackTicket=9a053c5a8ccd4286a1f89bffbe00d553&site=vmware.mediasite.com)

[STO9981-SPO - The Irrational Data Growth Problem at Scale: How do I make the leap from data to information and gain insight?](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/d4053a63-f439-4537-b1ef-7073e794bf89.mp4?playbackTicket=6793b83367464a53af802bfb6f303a1c&site=vmware.mediasite.com)

[STO8699 - Building a Business Case for VMware Hyper-Converged Software with Virtual SAN](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/b73c509d-4ed1-44d8-9c09-c2deef21b7ba.mp4?playbackTicket=4bbb725971b849a78d7497257a9aa025&site=vmware.mediasite.com)

[STO8204 - Cohesity & VMware: Simplifying data protection for Vsphere and Virtual SAN](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/2f498060-c1c2-485c-9ec5-b606dc5c8ae1.mp4?playbackTicket=73fa15da43b04a16ad2a65d2b8105e6a&site=vmware.mediasite.com)

[STO7645r - Virtual Volumes Technical Deep Dive](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/9aef4a6b-ab4a-414f-abfd-784e217e73e9.mp4?playbackTicket=66129c40dd4047d092a8dffa82bc25a6&site=vmware.mediasite.com)

[STO9157R - Achieving Unprecedented Availability, Security, & Cost Savings with VMware Virtual SAN and NSX](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/84b62518-6e36-4c1f-b353-15e795338039.mp4?playbackTicket=9f36b3217917451284f5a2c6b2a957fb&site=vmware.mediasite.com)

[STO7791-SPO - Insights to success: Capitalizing on the software-defined data center with the right management and storage](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/a0db9b50-7680-4818-bf9c-2bdd5a94619c.mp4?playbackTicket=d1cb5429378d4d0892cdcfa495f8c633&site=vmware.mediasite.com)

[STO8344 - SRM with vRA 7: Automating Disaster Recovery Operations](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/e51b5f6e-6dc8-44d8-b67d-5ad975ecb652.mp4?playbackTicket=f9ee827dd6164801b2f7640b45bb169a&site=vmware.mediasite.com)

[STO8159 - Snapshots Suck: How VSAN and VVol fix all your operational nightmares](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/617fe527-34bc-43e8-91bd-2dbba4ed701b.mp4?playbackTicket=47f433cd73f24a4f8ee50bb52d7c1679&site=vmware.mediasite.com)

[STO9969-SPO - How Did Designer Shoe Warehouse Lace up Success With Flash-Optimized Storage From INFINIDAT?](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/0c14365f-1922-4589-974a-62c23ea6fb38.mp4?playbackTicket=6fd8865e94474c2e8c318fc65a63cb6d&site=vmware.mediasite.com)

[STO7831 - Storage for Cloud Native Applications](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/3a7c36a0-bfed-43a7-a2ab-9f9c6dec42a1.mp4?playbackTicket=8c6a614123f4433ea91db72260e2a140&site=vmware.mediasite.com)

[STO9422 - Essential Virtual SAN Management](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/404c7a76-5b45-4133-b851-438c9926afa9.mp4?playbackTicket=142b200deaf5400ba146f0b5de6ac11f&site=vmware.mediasite.com)

[STO9449-SPO - Journey to the SDDC: The Who, What, Why and Oh No of Moving to a Modern Data Center Platform](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/abbe1b58-7dcf-46c7-a5b9-3742bb96f635.mp4?playbackTicket=10d403be78534ec7a968261d00e2cc82&site=vmware.mediasite.com)

[STO7965 - VMware Site Recovery Manager: Technical Walkthrough and Best Practices](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/817de0e2-acb3-4bdf-bd12-0108388bca94.mp4?playbackTicket=5c2b2f7e26c746b89939c137c7d91f3d&site=vmware.mediasite.com)

[STO7535 - Conducting a Successful Virtual SAN 6.2 Proof of Concept](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/c65a5a6b-2419-41cd-8a3f-496bdb9e15d9.mp4?playbackTicket=94dbc1bda4b8489bbf7dbcc2cd282e9a&site=vmware.mediasite.com)

[STO9079 - Virtual SAN for VMware Service Providers](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/d0cd2969-d32f-4035-abc8-c53743c95145.mp4?playbackTicket=d2722b5af3664e29b7aad4aeab48b05e&site=vmware.mediasite.com)

[STO10801-SPO - Modernizing with Private and Hybrid Cloud: How CSC & VMware move enterprise clients to next-generation infrastructures](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/27af5e3c-a248-42e5-82cd-a273d89782d3.mp4?playbackTicket=50d3d4032d144f08950ccc63a2cbf007&site=vmware.mediasite.com)

[STO7904 - Virtual SAN Management Current & Future](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/3feebb4d-de31-40c9-8d97-42bde26aacfd.mp4?playbackTicket=198f94de8fdc4fbaac1cbd1f794045fb&site=vmware.mediasite.com)

[STO8165R - VSAN Networking Deep Dive and Best Practices](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/fa572d71-aa51-4b77-a402-0c3f7de77cdd.mp4?playbackTicket=6912073e2ddf4bc08c90bffacef562a6&site=vmware.mediasite.com)

[STO8694 - High-Speed Heroics: Array-based Replication and Recovery for VMware Virtual Volumes](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/7c7abe95-e28b-48d4-8a41-d94e53ad738b.mp4?playbackTicket=95834c963d224fd783f75c730fc02970&site=vmware.mediasite.com)

[STO8923 - PowerShelling Storage to the extreme](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/10b3cc7e-cfe1-427a-a39e-ea368f3e6b99.mp4?playbackTicket=e096f85f70f34391b1a1c65ef5544296&site=vmware.mediasite.com)

[STO8179R - Understanding the Availability Features of Virtual SAN](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/e6bb9492-8265-4a30-8b9e-e8c7179c5380.mp4?playbackTicket=cb2f4073adef436bb00a38d0a106247b&site=vmware.mediasite.com)

[STO7802 - Simplifying Disaster Recovery in 2016 using VSAN, NSX and SRM](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/8cd391ca-2d58-47b6-bf48-6c0aba6ca278.mp4?playbackTicket=5fd5637d055e44698e9005c2a4961246&site=vmware.mediasite.com)

[STO8144 - VMware vSphere Virtual Volumes in a NetApp Environment](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/c709554e-e853-45f6-a587-868b0cae18c5.mp4?playbackTicket=a9804a01b70447efb265b58f38362b2d&site=vmware.mediasite.com)

[STO8689 - Virtual SAN Primer and What?s New](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/c5e87fd7-fcdc-4849-8a95-50218ef2e2f1.mp4?playbackTicket=93a040eca51947e4af4bb5dd6b3f4481&site=vmware.mediasite.com)

[STO7650 - Software-Defined Storage at VMware Primer](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/ff8fe8c5-04c7-4929-a042-76938a923ae5.mp4?playbackTicket=941e9f619ed84295ab1539ca1f526cba&site=vmware.mediasite.com)

[STO8279 - Deploying Virtual SAN with VMware Private Cloud](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/d7c8cb0b-a057-4cab-8e3d-ce105b8c7c5a.mp4?playbackTicket=658f9685101d4c1b890b0dc164671cb5&site=vmware.mediasite.com)

[STO7552r - Architecting High Availability and Workload Balancing for Tier 1 Mission Critical workloads using VMware Software Defined Storage and Extended Oracle RAC](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/4bb00508-f028-4529-8d7a-1dca8a59a57a.mp4?playbackTicket=292efd035f764daea06109e980f5f039&site=vmware.mediasite.com)

[STO8840 - Deploy Scalable Private Cloud with vSphere Virtual Volumes](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/4866bb37-d7a1-425a-b4c0-e91e38953280.mp4?playbackTicket=1d954dd9d166454e9dae4d4925cdd1dd&site=vmware.mediasite.com)

[STO7557 - Successful Virtual SAN 6 Stretched Clusters](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/cac28377-f056-43e3-8e55-269a901c428f.mp4?playbackTicket=82a0cfbc54dd46c29eb86c9913af3637&site=vmware.mediasite.com)

[STO7953 - The Future is Here:  Turbocharge All Flash Virtual SAN with Next Generation Hardware](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/81287ef0-2e1b-4129-bc3d-5de1d9edf72a.mp4?playbackTicket=33e3e0c78dc644f6a2e81a42a79b466a&site=vmware.mediasite.com)

[STO8179R - Understanding the Availability Features of Virtual SAN](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/ca6f06cd-41c0-4d87-af99-4b825c5d54d9.mp4?playbackTicket=1d588417754b47268c08543c052bc9b8&site=vmware.mediasite.com)

[STO9058 - Evolution of VMware Virtual SAN](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/67b74fb0-c717-4502-ab2d-844253ca0639.mp4?playbackTicket=ccf740d8a40d444b80af03f70e491969&site=vmware.mediasite.com)

[STO7534 - Virtual SAN - Day 2 Operations](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/f760bfc2-3bf7-43be-9392-f9b4cd4b70a3.mp4?playbackTicket=043145f2a2dc4666bdd48965e31129eb&site=vmware.mediasite.com)

[STO9607-SPO - Running Business Critical Applications and the Software Defined Data Center on Hyper-Converged Infrastructure at the Speed of Flash](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/9229c783-b259-47fc-90e9-589761e12cd4.mp4?playbackTicket=e2d0417055af4173b5b1579a050fe60e&site=vmware.mediasite.com)

[STO7902 - VMware Virtual SAN: Enterprise-Grade Storage For Hyper-Converged Infrastructures](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/2fd3564e-d721-4a9a-9906-807fd296097d.mp4?playbackTicket=13685bcfb6f14316b4d891c22a8e08d4&site=vmware.mediasite.com)

[STO7875 - A Day in the Life of a VSAN I/O](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/e04d9a51-2380-4ed0-af3e-54857741cfd1.mp4?playbackTicket=2f8864c028ae49d0bc74ca1c5c4a76d0&site=vmware.mediasite.com)

[STO8904 - Hardware Choices in the Software Defined World â€“ Tips on Choosing Hardware for Virtual SAN Deployment](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/9f297417-ea36-49c4-a00d-e64e946c22dd.mp4?playbackTicket=e93a2fbb7c8e4819887602738367215b&site=vmware.mediasite.com)

[STO9614-SPO - You have an all-flash Virtual SAN - what's next?](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/7a94fdf7-79a3-4b0f-974d-d0e2bac674a2.mp4?playbackTicket=28acce300b154cbcabbca551598381e6&site=vmware.mediasite.com)

[STO9054 - VVol and Storage Policy-Based Management ? Is It Everything They Said It Would Be?](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/4d7ec3ff-fe19-4773-a6c6-293a09d3b7e0.mp4?playbackTicket=33a73e043c7e4bf9b824d114bd3d7d54&site=vmware.mediasite.com)

[STO7755 - Storage for Virtual Environments - What's new and What's next for vSphere Storage](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/bca09538-0b41-47c3-9e34-9b9b4f4ec6cf.mp4?playbackTicket=89c017030d084cf0b89bf16479d9599c&site=vmware.mediasite.com)

[STO8568 - Virtual SAN with just 2 Failure Domains](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/cceb944d-d62c-4868-9705-4a60d8e0e718.mp4?playbackTicket=489e89cc36064848bdcfdd6e67962ff7&site=vmware.mediasite.com)

[STO8743 - Extreme Performance Series: Virtual SAN Performance Troubeshooting](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/0e19ef18-865b-4eba-bd76-d5aae334b7c0.mp4?playbackTicket=c9d1380a33ea4b72a332a3484b38ae20&site=vmware.mediasite.com)

[STO9967-SPO - Rethinking Data Protection:  The Rise of Hyperconverged Infrastructure and Built-in Backup and Disaster Recovery](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/9fcc4072-3062-4ca9-86f8-3002c6f9e568.mp4?playbackTicket=58e46b10036641c0bc81321c84fd0869&site=vmware.mediasite.com)

[STO9396-SPO - Real World Guidance for Implementing VMware Virtual SAN from Ready Nodes to Build Your Own](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/f340d793-566e-494e-a74e-2dc27c0ac97b.mp4?playbackTicket=c0f6153358d9497c8a26a209cc9a8664&site=vmware.mediasite.com)

[STO8165R - VSAN Networking Deep Dive and Best Practices](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/29ff33bf-9d87-41db-87a4-1727893b65d3.mp4?playbackTicket=7cf1ff59c89b48328a9346ca4551c35b&site=vmware.mediasite.com)

[STO7977 - SRM with NSX: Simplifying Disaster Recovery Operations & Reducing RTO](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/e500d561-47df-46ec-bed3-4cc833eb23ba.mp4?playbackTicket=5f5090b618074be9bf5a553afd1a4f9f&site=vmware.mediasite.com)

[STO7552 - Architecting High Availability and Workload Balancing for Tier 1 Mission Critical workloads using VMware Software Defined Storage and Extended Oracle RAC](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/9f2e5ecb-df45-4088-95df-2346c6737be2.mp4?playbackTicket=2dbbed9a921541249ed6719d82f3e3d4&site=vmware.mediasite.com)

[STO8488 - Hyperconvergence Panel Discussion: Exploring the ?Reality? of Hyper-Converged Infrastructure and Virtual SAN](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/0808114d-638e-4a5b-a77a-b090539d58cb.mp4?playbackTicket=4feefa39bc774b96b7be1d86410457a9&site=vmware.mediasite.com)

[STO7914 - Revamped vSphere Storage DRS and SIOC for automating the Data Centers](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/0c379cbf-2658-498d-aca2-4c747d200731.mp4?playbackTicket=2c8bd8315b88478d8af3c997f7ca56eb&site=vmware.mediasite.com)

[HBC10704-QT - Backups to the cloud - Leverage the cloud for Business Continuity](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/0d373172-3f12-4322-ad14-453619b57d9c.mp4?playbackTicket=61c8f6319ae84ff2848a0cfbbb88c556&site=vmware.mediasite.com)

[STO9988-QT - Running Epic with VSAN â€“ Modern Architecture for Healthcare](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/5bf7cd9b-79aa-41e1-88c3-23c20319fd94.mp4?playbackTicket=486b94f3cd2244c691fc8f1210deb1d7&site=vmware.mediasite.com)

[STO9987-QT - Hardware Procurement Guide for Virtual SAN](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/f6be281a-a26c-4e6d-a6ed-10ca4905a4b4.mp4?playbackTicket=ecd847885abe47a2a3a45eac0db063da&site=vmware.mediasite.com)

[HBC10703-QT - Top Tips for Moving to the Cloud](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/753561a7-293f-4b03-937e-62d8fef159a3.mp4?playbackTicket=83efc6244b9e4cb89c853f0d5e427b1e&site=vmware.mediasite.com)

[STO9977-QT - 5 Tips for Getting The Most From Virtual Volumes and vSphere Storage Policy-Based Management](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/e06cf55d-e91f-4afc-8e5d-ca3b6c1acf83.mp4?playbackTicket=2d4de11bb31e41438ae5ddb243e7d863&site=vmware.mediasite.com)

[INF9991-QT - vSphere Web Client Plug-in Certification Program](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/1af38b2f-cf0d-45c4-8d59-a440142856a5.mp4?playbackTicket=c7d0efba9a0d401a98eecdc84e70ae89&site=vmware.mediasite.com)

[STO8267 - Hours to Minutes: Automated Provisioning and Deployment Using PowerCLI, vRealize Automation and vRealize Orchestrator](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/698493fe-181f-4997-b23d-87b3cf22cae2.mp4?playbackTicket=c9a25bbb88754ad49cb78e0314e2cfec&site=vmware.mediasite.com)

[NET9094 - Customer Case Study on American Tire Distributor (ATD): Migrating to the Software-Defined Data Center with Arista Networks and VMware NSX](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/bc209b25-f681-4f21-92ce-2f4e70f2b23f.mp4?playbackTicket=539253d7db554cb9a90ba9b84644ad08&site=vmware.mediasite.com)

[NET9069 - Automating Traffic Visibility for the Software-Defined Data Center](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/c2ff1815-4b3d-4547-a8dc-6995a89605c6.mp4?playbackTicket=8806864d96b445b0a87cd43505775f60&site=vmware.mediasite.com)

[SEC8081 - Healthcare: The Security Awakens](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/e2ad5f1a-0538-4caa-89b2-77e5e6c3b915.mp4?playbackTicket=ee21637d7ea448398935f34627d0665a&site=vmware.mediasite.com)

[SEC8667 - Deep Dive into Real-Life Data-Center Breaches and How They Could Have Been Avoided](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/f5d438ba-393a-42a9-bc1c-068778d3f801.mp4?playbackTicket=a62271e436564a91af3232c1cdacebe7&site=vmware.mediasite.com)

[NET8832 - The Role of VIO and NSX in Virtualizing the Telecoms Infrastructure](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/96f95edc-f786-4735-9f08-b496b9da41b6.mp4?playbackTicket=5e1c966a52bd4a9283631bb1faa5b63c&site=vmware.mediasite.com)

[NET8189 - VMware NSX and Pivotal Cloud Foundry](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/c53b02ad-491a-4410-a4da-c4b8bf85e72b.mp4?playbackTicket=d7589133fdd14b93bc6771535ee5dc01&site=vmware.mediasite.com)

[NET8194 - How VMware IT Implemented Microsegmentation and Deployed a Large-Scale Private Cloud Using NSX](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/eb172374-d40c-45ad-bf73-338bf6c8ad29.mp4?playbackTicket=becd669a03e8436792415bb6e6fb078f&site=vmware.mediasite.com)

[NET8131R - NSX for vSphere Logical Routing Deep Dive](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/85057bc4-c329-4d80-9999-647a30321478.mp4?playbackTicket=9a29c9d565d245a3953b9f114f89ad21&site=vmware.mediasite.com)

[NET7861R - Multisite Networking and Security with Cross-vCenter NSX: Part 2](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/7c1e5950-7fc5-4b87-ba2e-8434c024c294.mp4?playbackTicket=a00e2b69c1474825ac4eccb46dba3087&site=vmware.mediasite.com)

[NET8758 - vSphere Distributed Switch Deep Dive](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/a448b565-4b05-408f-b97c-3c5755b09c08.mp4?playbackTicket=12ac6572215942e684229c4c22c22faa&site=vmware.mediasite.com)

[SEC7593 - NSX Security for Horizon View 7â€”Deep Dive](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/e59158e7-78cb-49b8-b062-82399b2a59cf.mp4?playbackTicket=a86439e767fc47638a1b191881fb766e&site=vmware.mediasite.com)

[NET9447-SPO - Extensible Solution for Software Driven Data Centers (SDDC) with VMware and Arista](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/e80bc914-96f0-4601-8e5e-73b7bfb83e1a.mp4?playbackTicket=332c23afe2b74afcb5a52f43804d8e2d&site=vmware.mediasite.com)

[NET7854R - Multisite Networking and Security with Cross-vCenter NSXâ€”Part 1](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/0b746cbd-40f0-453e-87a1-9604db71e55c.mp4?playbackTicket=c702e4efab634b808be4730447aec01a&site=vmware.mediasite.com)

[NET8030 - NSX Performance Deep Dive](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/5cef4d73-dccb-47b1-a93e-7290facffc8e.mp4?playbackTicket=2bacaf2140f94a1f87376dffd63cda83&site=vmware.mediasite.com)

[SEC9450-SPO - Bridging the Gap between Infrastructure and Security Operations](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/7257c5fc-70e3-40bf-bed3-bdf86a570535.mp4?playbackTicket=fbca1317158f47f2afc7e277457e7f4d&site=vmware.mediasite.com)

[NET8109 - Amadeus's Journey Building a Software-Defined Data Center with VMware Integrated OpenStack and NSX](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/fdae400c-842c-4a3d-97db-588cd7a65163.mp4?playbackTicket=513124aeccc24f24848c98c265c6acc0&site=vmware.mediasite.com)

[NET7701 - How to Easily Become a Cool Automation NSX Cloud Network Engineer](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/3d21f392-4660-427c-84d8-ee526fc2193d.mp4?playbackTicket=faff1212ff184c62a810c5507bab55c1&site=vmware.mediasite.com)

[NET7514 - PowerNSX and PyNSXv: Using PowerShell and Python for Automation and Management of VMware NSX for vSphere](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/b0e89702-2a4b-4461-bd52-2263ccc14860.mp4?playbackTicket=40b806b5e39841e78b8b4db2792897f4&site=vmware.mediasite.com)

[SEC10020 - Managing Cybersecurity Risks Within SDDC: VMware and Palo Alto Networks Customers Discuss Their Perspectives and Experiences with NSX and VM-Series Deployments](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/abe989c5-749c-4893-8754-a8f5b30e954e.mp4?playbackTicket=9cc88c8f5e9a482ab74238030914583f&site=vmware.mediasite.com)

[SEC9619-SPO - Scale and Segment the Agile Data Center with Software-Defined Security and NSX](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/28217635-14e9-4f98-8c66-fbe1f0c7c7a8.mp4?playbackTicket=a669d9f382184f52af6b86e4ed1ae1ed&site=vmware.mediasite.com)

[SEC9177 - A Real World Deployment of VMware NSX in the DMZ](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/d416db3c-1c15-409b-ae01-9401caac27e6.mp4?playbackTicket=ff42b1b6938542aba2786cd18994fcb2&site=vmware.mediasite.com)

[NET7648 - How PG&E is Automating Secure Environments with NSX, vRealize Automation, and vRealize Orchestrator](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/c2382388-36a9-4bb1-8657-53ad88850699.mp4?playbackTicket=1e005c6d003a4722988070a410ebc5d4&site=vmware.mediasite.com)

[NET9155 - NSX Policy, Visibility, and Intelligence](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/b7882556-0a6d-42e3-8023-9ae2a2a00ab1.mp4?playbackTicket=2582ed0ef3a348a486d324c5cde26c36&site=vmware.mediasite.com)

[NET8082 - NSX Operationalization: Monitoring and Troubleshooting Your NSX  Software Defined Data Center](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/fbf63ab7-991f-48fa-9de9-14de326b6342.mp4?playbackTicket=54180bcefb6648c5abd64feede7b22ed&site=vmware.mediasite.com)

[NET9029 - NSX Logical Load Balancing: From Basics to Fine Art](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/174213fc-dfdb-4671-82a2-901fcfd10cb2.mp4?playbackTicket=dcc9d2f4dbbb498ab5d67ea4dbf4a0b6&site=vmware.mediasite.com)

[NET8337 - Leveraging NSX for Remote and Branch Offices](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/64a2941c-824f-473b-b48f-fa3a98f4ef4d.mp4?playbackTicket=5093fa9111d44e71a96735db630117b2&site=vmware.mediasite.com)

[NET8343 - OpenStack Networking in the Enterprise: Real-Life Use Cases](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/f3145cd4-2077-4022-9130-06d4ef8cd34f.mp4?playbackTicket=8c85b3626ae3409989420db70c1077a2&site=vmware.mediasite.com)

[SEC8022 - Implementing Agentless AV and IPS/IDS Security Solutions with NSX](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/e6f36b5a-37e2-4c2d-b70e-8e1afecfd771.mp4?playbackTicket=0d3edb74b22c4a65a6fc09ab6ea2b958&site=vmware.mediasite.com)

[STO9886-SPO - Modernize Remote/Branch Office (ROBO) Operations with Software-Defined Edge](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/747af7fa-7640-4384-835a-d19dce0f0c24.mp4?playbackTicket=f3a80ab32d164026bce500e8d5e60d4d&site=vmware.mediasite.com)

[SEC9446-SPO - Integrating a Threat Defense Lifecycle Security Approach with VMware NSX](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/450ea122-fdae-4dd0-88bb-3b8f367184cd.mp4?playbackTicket=10bc2f76064c481884dbcccde5cc42f8&site=vmware.mediasite.com)

[SEC8348 - Deploying Security in a Brownfield Environment](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/ea40cabc-8cee-40a6-ac8f-301f6868d355.mp4?playbackTicket=a2526c356b1c4d87bd27de8e9da25b17&site=vmware.mediasite.com)

[NET7956 - vRealize Automation and NSX Design Best Practices](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/9a06725d-9812-4a63-aaa8-5b715a253d09.mp4?playbackTicket=8f080477a32147859381c8a7cab5dede&site=vmware.mediasite.com)

[NET8680R - Advanced NSX Troubleshooting: Tips & Tricks for Experienced Users](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/51edbe55-f33b-4f22-aa4a-25ecf7b25d36.mp4?playbackTicket=18b68919fb6549b5aca1671a99bbcf58&site=vmware.mediasite.com)

[NET7865 - Operational Best Practices for VMware NSX](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/edd17c7a-726c-4791-91bb-1e691464fc2f.mp4?playbackTicket=0eccb3d9c33a4edea3df41213583c7d0&site=vmware.mediasite.com)

[NET8364R - How to Deploy VMware NSX with Cisco Infrastructure](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/314f9ab0-80f3-4239-b193-c2b408632b0f.mp4?playbackTicket=ca48ae087d5149b8bd0e0d0fe2fc4d88&site=vmware.mediasite.com)

[NET7514R - PowerNSX and PyNSXv: Using PowerShell and Python for Automation and Management of VMware NSX for vSphere](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/c9187dbd-bdef-4aa3-8e51-ca14876bab14.mp4?playbackTicket=610f61c1e8084bdcb8cbf8a8478d7a15&site=vmware.mediasite.com)

[SEC7836R - Introduction to Security with VMware NSX](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/fb585051-36f5-4258-929a-af2fbfa265a8.mp4?playbackTicket=802e2ef8d7b044b6afcef337140dae5c&site=vmware.mediasite.com)

[NET8193R - The Architectural Future of Network Virtualization](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/e9ec6df8-d6c4-49a8-96fa-004d3a4fa4e0.mp4?playbackTicket=6511ef932d7e4452a0fca01909f5cb23&site=vmware.mediasite.com)

[NET8039 - Bridging Virtual and Physical in NSX with Open vSwitch Database Management Protocol-Based Hardware VXLAN Tunnel Endpoint Integration](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/ef55ee7e-01bc-4a98-a255-71d584b66d97.mp4?playbackTicket=f030978316ab4905986e919e84ad1d34&site=vmware.mediasite.com)

[NET8935 - NSX for Small Data Centersâ€”Breaking Boundaries](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/9c338b26-d1c9-48ec-bc0a-d0e4d0a5c1a0.mp4?playbackTicket=e589ccd1199e497f8bccc2e5c1dae072&site=vmware.mediasite.com)

[SEC7628 - Use NSX to Automate Your Security Incident Response so You Can Stay Above Water](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/80b1a787-3cea-46f0-8a62-11a313cc2b32.mp4?playbackTicket=fcd870f200a845e9a538d872c07a39df&site=vmware.mediasite.com)

[NET7857R - Reference Design for SDDC with NSX and vSphere: Part 1](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/39c4ae41-ad86-4156-a203-2b198c9b0bf7.mp4?playbackTicket=7c47b967117c492bb7097919b5328243&site=vmware.mediasite.com)

[NET8675r - The Practical Path to NSX](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/12b342ab-5b04-4fd5-a56f-9e6056891529.mp4?playbackTicket=b05dd05c2dc64915b82d2013911bbba6&site=vmware.mediasite.com)

[SEC9609-SPO - Trusted Security in the Software Defined Data Center: Real-World Use Cases Across VMware Platforms, including NSX](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/4f21e3d9-6da0-4e87-b5e0-4bda79132447.mp4?playbackTicket=f5fe985af3f74ee1aa7836056ce64fae&site=vmware.mediasite.com)

[NET8734 - Automating Networking and Security Operations with NSX Customer Panel](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/fbe6a4a7-b9cd-47d1-b176-55696b43f392.mp4?playbackTicket=eee47fa76c4b457091af5eddc2978ebb&site=vmware.mediasite.com)

[NET9156 - Customer Case Study: Journey to Automate Security As a Part Of Service Delivery](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/66cb8812-67f5-4f3d-ad06-5f92a6e11018.mp4?playbackTicket=decbac3bbe3e49f2bd4897f2f5702b6e&site=vmware.mediasite.com)

[NET7861R - Multisite Networking and Security with Cross-vCenter NSX: Part 2](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/19986278-3ecb-455c-94de-d9c6aa3595be.mp4?playbackTicket=24cb81e0c39943109d93d372b4c5e420&site=vmware.mediasite.com)

[NET7760 - Enhanced Disaster Recovery with NSX](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/00980cda-d66c-4b24-aa16-5b7e1fed8d56.mp4?playbackTicket=afa10f50a3604b0bb163f0caf9785e61&site=vmware.mediasite.com)

[NET7854R - Multisite Networking and Security with Cross-vCenter NSXâ€”Part 1](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/72adacde-1d18-415a-9b1b-037e6073be50.mp4?playbackTicket=9963c63747564220851258d68be1e0ce&site=vmware.mediasite.com)

[NET8903 - Stories from the Alexandria SDN Zone](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/f150a565-74b3-4bf3-aecb-d89af91590a7.mp4?playbackTicket=d1c833a974dd4e329235fcc214e4bf21&site=vmware.mediasite.com)

[NET8680R - Advanced NSX Troubleshooting: Tips & Tricks for Experienced Users](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/c7b8ab46-fbea-490e-99ae-70b98808152e.mp4?playbackTicket=54d63f7825b746f89ab7f5596295560d&site=vmware.mediasite.com)

[SEC9976-SPO - Extending security beyond the SDDC with VMware NSX and Palo Alto Networks VM-Series Virtualized Next-Generation Firewall](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/99f1a482-e8af-4218-9afc-8a1ac3177fdf.mp4?playbackTicket=dddfb18d14d44b8c8421cda6dd589c90&site=vmware.mediasite.com)

[NET8131R - NSX for vSphere Logical Routing Deep Dive](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/7b9b1d75-dbcc-44d9-8d6a-be1123570aac.mp4?playbackTicket=e4542441e0f149658b4ba4ac09238604&site=vmware.mediasite.com)

[SEC8730 - NSX Security and Micro-segmentation Customer Panel](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/969b9b2b-2fca-4983-aa6d-4a4f81ccc526.mp4?playbackTicket=82a28445797644b5a7571227793f9ec9&site=vmware.mediasite.com)

[NET8241 - Monitoring and Troubleshooting NSX with vRealize Network Insight (Arkin)](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/fcbe5ea9-3927-4534-a2bf-f1860015e74e.mp4?playbackTicket=b0a107f641054f89a926a4873d3ca4bd&site=vmware.mediasite.com)

[NET7834r - Introduction to VMware NSX](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/2006587c-d420-47fa-9812-69df4e0ee2ef.mp4?playbackTicket=b0fb65ed85234cc69e71a8f43b4ab771&site=vmware.mediasite.com)

[NET7944 - NSX Brownfield Deployment Best Practices](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/0a6d7f57-a1ba-4a11-9290-889f4f6dd39c.mp4?playbackTicket=ea064587d00144cc84bb3a1874bbd63a&site=vmware.mediasite.com)

[SEC7568 - Practical NSX Distributed Firewall Policy Creation](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/f247242f-0ec7-4bdb-b6fa-375075834e3e.mp4?playbackTicket=05d0af90da9b479086ec9e4989d400a6&site=vmware.mediasite.com)

[NET8731 - IT Automation with NSX Network Virtualization and Security](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/3f16f5fc-8a2b-40d9-9181-934b82253229.mp4?playbackTicket=ffe662ca97014e119ef65ff6b2741ea7&site=vmware.mediasite.com)

[SEC9968-SPO - Automate Check Point vSEC Advanced Security with NSX](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/038e1c96-3e9b-4461-89d7-669504d3f6b6.mp4?playbackTicket=b6f0a76dc8874965ab2dffccabf7a236&site=vmware.mediasite.com)

[SEC9618-SPO - Deep Dive:  Extending L4-L7 Security Controls for VMware NSX and VMware Integrated OpenStack (VIO) Environments with Fortinet Next Generation Security](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/a7dec1a2-2f6f-4384-a5e6-5d8acef8f14e.mp4?playbackTicket=7402699c678c4875a015fdf3b5febb8b&site=vmware.mediasite.com)

[SEC9972-SPO - Deep Dive: Secure your multi-tenant cloud with Palo Alto Networks VM-Series and VMware NSX](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/b16415ad-38c1-472c-b253-8ea09f848221.mp4?playbackTicket=e0f4df515ffc45d9baaea534481402cc&site=vmware.mediasite.com)

[NET8729 - NSX on Cisco ACI Customer Panel](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/68087b20-37f4-4d82-b067-dfe0efe595e6.mp4?playbackTicket=eb277380454b47e79234823987da15c8&site=vmware.mediasite.com)

[NET7837 - Introduction to Application Continuity with VMware NSX](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/0bb6466d-f47f-4b33-bb19-c2b690f89554.mp4?playbackTicket=89800f44e9b842639c9a1c9c30c06ae8&site=vmware.mediasite.com)

[NET7935 - Container Orchestration and Network Virtualization](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/9ebc72ed-5e25-4230-ab48-1e6ca316da3e.mp4?playbackTicket=f5dca01e4f124bc7bde4968be4a2f31e&site=vmware.mediasite.com)

[NET7656-SPO - Accelerating SDDC through mainstream adoption of network virtualization](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/bf1f215e-1855-452b-8ce9-597a9085da5f.mp4?playbackTicket=f255617a4b6247539163628db24ad793&site=vmware.mediasite.com)

[NET8193R - The Architectural Future of Network Virtualization](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/651d9fdd-2b97-45df-89c3-46e2c2ae640e.mp4?playbackTicket=0aef3a50875640f1b6a012be62f67e83&site=vmware.mediasite.com)

[SEC7836R - Introduction to Security with VMware NSX](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/be6cab8f-3195-4d85-8f7e-ad065bc32c78.mp4?playbackTicket=e5c0f5987fd845a69f5381a62c31a563&site=vmware.mediasite.com)

[NET7834 - Introduction to VMware NSX](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/294283c8-dfcb-4231-8b6d-c65ce9170db7.mp4?playbackTicket=fdb6d7cccf0044f495c475bd0465ac68&site=vmware.mediasite.com)

[NET7857R - Reference Design for SDDC with NSX and vSphere: Part 1](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/0c01d09c-da0c-402c-a89d-971bd9a0ae1a.mp4?playbackTicket=f7621d6f3088449786a03ca9e4c52737&site=vmware.mediasite.com)

[NET8675 - The Practical Path to NSX](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/5f26a99e-1a15-46a5-a9db-1f4635b5ce5f.mp4?playbackTicket=e4d4559587a74fdabfa2d3ab0df1263e&site=vmware.mediasite.com)

[NET9381 - Operationalizing NSX Customer Panel](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/be7b7c37-fd03-4d31-a4b7-e578b5b26e02.mp4?playbackTicket=827020b9f30f40caa89b010a35443a48&site=vmware.mediasite.com)

[SEC10019 - VMware NSX Micro-segmentation â€“ Definition & Benchmark Deep-Dive](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/fc19c529-a917-4251-8af0-623ef49562a6.mp4?playbackTicket=af71686c56ce4408872518a5e014a5cf&site=vmware.mediasite.com)

[NET9152 - VMware NSXâ€”Deep Dive](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/db352180-d08a-459f-8f0e-c14df9536c58.mp4?playbackTicket=47673977e6f64645b291e26cf5fbd742&site=vmware.mediasite.com)

[NET10884 - Moving to the next level of the SDDC - a Public Agency introduces VMware NSX, AirWatch, and Palo Alto Networks integration](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/ff96e2fd-c27c-4303-8911-14120e947a00.mp4?playbackTicket=e2ce57ca6f444d10bfc3afaa022e9920&site=vmware.mediasite.com)

[NET9004-QT - Virtually Unstoppable: Scaling NSX to Bridge the Gap between Security & Cloud Automation](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/c8282e8c-bb18-4a2a-b711-f36c5636faeb.mp4?playbackTicket=ab32d3b1c3a644ffa739cbaba0ee98b5&site=vmware.mediasite.com)

[NET8769-QT - Hyper-convergence in Healthcare:  The Key to Doing More with Less](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/f24888cd-2591-4edc-af87-c4295f15c0d4.mp4?playbackTicket=74ab0de401ab4ab29fe1b2ffdcdf5c63&site=vmware.mediasite.com)

[NET9382-QT - A Software-Defined Data Center in Overseas Bases and Military Operations](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/843ed907-b0cd-4392-86cd-1c55dc4140b1.mp4?playbackTicket=c62ef81e80f7427ca74e2ff79ed14dcc&site=vmware.mediasite.com)

[NET7774 - Day Two NSX Operations in VMware's Private Cloud](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/c990199b-c895-4922-a378-ad5128590c58.mp4?playbackTicket=a610e47a2de64155b91b0bf57e9834c3&site=vmware.mediasite.com)

[SDDC8621 - VMware Cloud Foundation: Technical Deep Dive](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/145115e1-24d9-4ee7-acf2-137b00cfdd9a.mp4?playbackTicket=4be320cc6b704fc39878667c5cb08798&site=vmware.mediasite.com)

[SDDC8472 - An IT Architect's Guide to the Software-Defined Data Center](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/b32b5eb9-e753-4b65-a9c7-8512c0025cd9.mp4?playbackTicket=33f35929ebbe48b49162296c3e13078c&site=vmware.mediasite.com)

[SDDC7780 - Agile: The Scrum Master for Your Software-Defined Data Center!](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/c544030e-0807-45d7-b0e9-6c19ffc73da8.mp4?playbackTicket=8d4a025b75824fbcbc20e5ecdb3ce28e&site=vmware.mediasite.com)

[SDDC8468R - A Beginner's Guide to the Software-Defined Data Center](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/ca166216-ef18-489e-981e-dee260e77115.mp4?playbackTicket=a0311e7e39f34866a4b5b24856c6b042&site=vmware.mediasite.com)

[SDDC7886 - Implementing An Operating Model for Agility: A Customer Success Story](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/52ceb29a-7e09-404c-b281-d4cd3080cb6a.mp4?playbackTicket=ec3668e06f4a4c6bbc8596682c736365&site=vmware.mediasite.com)

[SDDC9971 - Experience the Business Impact of IT Innovation & Transformation in this Live Interactive Simulation](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/f62de2b4-4429-47c4-b4dd-20f5a14a8207.mp4?playbackTicket=1aff559061034793b47d23dc8bab0265&site=vmware.mediasite.com)

[SDDC8414 - VMware Validated Design for SDDC: A Technical Deep Dive](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/d37cf776-1e24-4b30-a723-d9bb1a386209.mp4?playbackTicket=cdd0cbc182e944adb36dde1aad3263dc&site=vmware.mediasite.com)

[SDDC7502 - On the Front Line: A VCDX Perspective Working in VMware Global Support Services](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/2dd8fd5b-d366-48d6-a6f1-1621acaae98f.mp4?playbackTicket=a1aa81f27e694b3da294c01192d99ce4&site=vmware.mediasite.com)

[SDDC9456-SPO - Implementing Self-Service Storage Provisioning with vRealize Automation XaaS](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/7f338d41-d20f-436e-8541-c769183a10ac.mp4?playbackTicket=a4dd99e701624fe19103973046c43bab&site=vmware.mediasite.com)

[SDDC8615 - vRealize Automation 7 in VMware Cloud Foundation](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/44ddb3c5-fd34-4ed5-95e7-715ffa4894a6.mp4?playbackTicket=73c699ee9c534cad892b9fb837a5d1de&site=vmware.mediasite.com)

[SDDC10623-SPO - The private cloud is dead. Long live the private cloud!](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/d57b5c93-333a-4d68-9816-d8f2abb4b576.mp4?playbackTicket=a8f7ef43d3ed41ee94daafc014252991&site=vmware.mediasite.com)

[SDDC8748 - Building a Successful Business Case for VMware Cloud Foundation](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/b265578c-561f-43c3-8138-8cfb68d690de.mp4?playbackTicket=a657e5c386de450989ec6b46300345ff&site=vmware.mediasite.com)

[SDDC7692 - Tips for Realizing the Full Value of Your SDDC Transformation](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/85b5628a-d8d9-43e1-91a1-7c57d848709d.mp4?playbackTicket=c1b49d00631646928552fa4710c33feb&site=vmware.mediasite.com)

[SDDC9726-SPO - Making SolidFire Invisible in your VMware Environment](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/6629b6cd-d700-47ba-9676-23c41b4c5fd2.mp4?playbackTicket=f564b5786ca54f42bd54a1be07ce98e5&site=vmware.mediasite.com)

[SDDC9612-SPO - How to design and implement VMwareâ€™s vCloud in production](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/4f441c47-1bb9-448e-8961-d14350103470.mp4?playbackTicket=413f2957ea244eb9a3f4e2207d1c4d0e&site=vmware.mediasite.com)

[SDDC8154 - Building the Integrated Software Stack](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/71d42022-17bf-47f4-a5bb-ab2387d35be1.mp4?playbackTicket=1e71bd0c329049318494462c99150774&site=vmware.mediasite.com)

[STO9405-SPO - Stopping Global Threats with Converged Infrastructure for the US DoD Cyber Range](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/634f6b69-587c-4eb1-a9ab-589084e3522e.mp4?playbackTicket=7424af49271b40799b843c6f150ca101&site=vmware.mediasite.com)

[SDDC9108 - VMware Cloud Foundation â€“ Future Innovations](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/9339d1db-891e-442f-9791-6de66e2ee81d.mp4?playbackTicket=97b0ff00f3514f0ea194cec0e5da92ce&site=vmware.mediasite.com)

[SDDC9181 - VMware Cloud Foundation Backup and Disaster Recovery](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/59c88da0-75a7-435b-88fa-289317d89211.mp4?playbackTicket=abd561bea00945b3bcef541eae396a42&site=vmware.mediasite.com)

[SDDC8614 - NSX in VMware Cloud Foundation](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/ad9332ff-7442-4713-90fc-d196c8b98ca6.mp4?playbackTicket=01fe6a3a9bfb4a8cabcf2037a1d0c230&site=vmware.mediasite.com)

[SDDC9995-SPO - HPE Hyper Converged â€“ path to composable infrastructure](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/eb227f29-de4d-4005-a19e-ca1ea827ce1b.mp4?playbackTicket=b16090089ec549f081f208644b60f540&site=vmware.mediasite.com)

[SDDC9465-SPO - Level Up to IT as a Service with Hyper-Converged](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/70383486-f4fd-4e5c-b797-d6ce7a1d2729.mp4?playbackTicket=993f3830b10b4cb7b83df4375a9db9ba&site=vmware.mediasite.com)

[SDDC8357 - If They Come - Are You Ready?](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/d45d7d81-cfb4-41e4-ac2c-f2421ecce646.mp4?playbackTicket=d9e81cabe8c645a494212c985cb23fd6&site=vmware.mediasite.com)

[SDDC9428-SPO - Practical Strategies for SDI and Security](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/bc29d651-6b57-4ac5-8053-3ced1695bfdb.mp4?playbackTicket=2c2ae5d7aeca4025879bcbdffd765959&site=vmware.mediasite.com)

[SDDC8445 - VMware Validated Design for Microsegmentation Deepdive](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/a06343f5-12d6-4d01-b902-d19021a126ab.mp4?playbackTicket=526ca044cc1541e8913089f9134993f6&site=vmware.mediasite.com)

[SDDC8946 - Deep Dive into Deploying the vRealize Cloud Management Platform the VMware Validated Designs Way!](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/5f3e1ad2-e8f3-4cfd-80f4-3115a6d6b2a1.mp4?playbackTicket=2c96358650cb48618f5db6995da670da&site=vmware.mediasite.com)

[SDDC8628 - Automating Virtual Desktop Deployments with VMware Cloud Foundation](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/fe609247-bc9e-4f36-925f-3c299f32b8e9.mp4?playbackTicket=42786fe4323d48858be1e3d410a3bfcd&site=vmware.mediasite.com)

[SDDC8150 - Rack Scale Architecture (RSA) and Software Defined Data Center (SDDC) Innovations](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/7a6acdf2-3436-4ca3-a683-1a73a55d4895.mp4?playbackTicket=604b3dd859fd4facac2586e58a684f12&site=vmware.mediasite.com)

[SDDC7587r - Software-Defined Networking in VMware Validated Designs](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/5697883d-eee6-4893-afdf-b75890f2059f.mp4?playbackTicket=da035ef975f14cb18bb0f4c8da72126d&site=vmware.mediasite.com)

[SDDC9613-SPO - Building the Future Data Center with Province of Nova Scotia](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/1a43a8d3-456c-44a8-aeab-73030eeb2057.mp4?playbackTicket=04b30fd3cd3644d0a77bdd1dfaf306e9&site=vmware.mediasite.com)

[SDDC9921-SPO - Evaluating Tradeoffs in Reducing and Eliminating Downtime Inside and Outside of the Software Defined Data Center](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/c57b7ae0-9841-450b-b245-9caf50e72ece.mp4?playbackTicket=06ec996b9cfe4397a42a50938096623d&site=vmware.mediasite.com)

[SDDC8520 - No IT Left Behind: Connecting the Software-Defined Data Center to Multi-Modal IT](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/29c4377d-360b-4300-b41d-7a4fa5c37f78.mp4?playbackTicket=70ed3eac6b6a43eab41723987f061076&site=vmware.mediasite.com)

[SDDC8423 - VMware Validated Design for SDDC â€“ Operations Architecture Technical Deepdive](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/807002c7-14ae-432c-b9b3-907903612542.mp4?playbackTicket=fb069a4cdb8f44c88084657fd53f6eb8&site=vmware.mediasite.com)

[SDDC8214 - Case Study: VMware's Private Cloud Journey to Over 100K Virtual Machines](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/fcb8f3cf-d3ee-412d-a74c-0f1988d84686.mp4?playbackTicket=26577eaae34e49dc896a45b870a4beb0&site=vmware.mediasite.com)

[SDDC8975 - SunTrust's Cloud Journey](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/7a869c4d-1e9c-4c2b-b26a-86f2abcbd3c2.mp4?playbackTicket=b36f63e8d1844adfb617a8419dc44a83&site=vmware.mediasite.com)

[SDDC9025 - VVD 101: Build Your Cloud the Right Way, First Time](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/e793f827-95d9-42f7-adc1-cc4cf1ff48be.mp4?playbackTicket=6ad482b338e14cf0868651ef8e953de0&site=vmware.mediasite.com)

[SDDC9605-SPO - Using Hyper-intelligence to build next generation storage platforms](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/fcd52ca6-4cc9-4a21-a789-fd1210aedfb2.mp4?playbackTicket=995920a6f12f481381f0809e587de279&site=vmware.mediasite.com)

[SDDC8930 - American Tire Distributors: Our Journey to a Modern Private Cloud](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/e508be8c-02e7-4bf7-9424-4bc65b53f4e8.mp4?playbackTicket=6263148623e84d388c2fd118b140be54&site=vmware.mediasite.com)

[SDDC9176 - How VMware Cloud Foundation powers the IBM Cloud](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/f1afa7a1-e475-413f-8c1c-52c2226037e6.mp4?playbackTicket=830c0a967f194930977f14fca3df9ce6&site=vmware.mediasite.com)

[SDDC8994 - Taming the Hydra: IT in a Multi-Cloud World](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/da8988b5-8811-4a9a-b79e-4085cba95b90.mp4?playbackTicket=75570d80946d4262b31edde5354a9686&site=vmware.mediasite.com)

[SDDC9448-SPO - Donâ€™t Let Data Protection Drag Down Your Business Transformation](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/3ecf84e5-ded5-4007-95cf-6800c838e8f4.mp4?playbackTicket=18ae95b3882e458f8f56024ec76665ba&site=vmware.mediasite.com)

[NET9460-SPO - Use Cases for Software Defined Data Center with NSX: Transform to Digital Business by deploying multi-tenant agile network in SDDC environment](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/850ba54b-4941-486f-b9dd-e226a6520564.mp4?playbackTicket=da1c475665b444b69c79d9c1eedfce38&site=vmware.mediasite.com)

[SDDC7819-SPO - Lessons learned to provide secure service assurance for your VMware investments](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/9e01af4c-85d6-4d61-8593-216926fe9b94.mp4?playbackTicket=c4185926868541feb67918fca9f598a7&site=vmware.mediasite.com)

[SDDC9023 - Hyperconverged Infrastructure at Scale with VxRack 1000 SDDC](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/19a8c25d-b824-4b5a-94cb-79d90951be6e.mp4?playbackTicket=aa3f5bf51c6241b685b82819d7b5a531&site=vmware.mediasite.com)

[SDDC8351 - How VMware Cloud Foundation Makes Your Private Cloud Operation More Efficient](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/1d4654db-b109-4de9-aaf6-6eb791482258.mp4?playbackTicket=d193800891b24002a1338b1f1cc1a2c3&site=vmware.mediasite.com)

[SDDC9404-SPO - Reinventing Disaster Recovery Leveraging Public Cloud Infrastructure](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/5e2e320e-9f3a-4f65-8712-7456268d8b73.mp4?playbackTicket=920b3cbfcd834901abb617468f1919bb&site=vmware.mediasite.com)

[SDDC7616 - Strategizing Cloud Business Management Using vRealize Business](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/dbfd0a69-0569-42a5-80eb-70e995c17217.mp4?playbackTicket=b85c7738a3664ab6b7c70293b853c269&site=vmware.mediasite.com)

[SDDC7587 - Software-Defined Networking in VMware Validated Designs](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/91dbf951-2178-452a-bd80-f4e7e27a4878.mp4?playbackTicket=066cf6f995104079a0acc91dd2c6ddf6&site=vmware.mediasite.com)

[SDDC8475-QT - A Manager's Guide to the Software-Defined Data Center](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/4505b802-2ff3-4dde-9e4d-68b7e023ff46.mp4?playbackTicket=d86d241749c745d9a204a173f1d22508&site=vmware.mediasite.com)

[SDDC7609-QT - How to Respond to the &quot;Bring Your Own Data Center&quot; Trend](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/82391ced-f3bb-41e4-9754-9d048fd69637.mp4?playbackTicket=8e28398bea0b4e938ea372485fcb35e3&site=vmware.mediasite.com)

[SDDC7881-QT - Cloud Service Lifecycle in a DevOps-Focused Delivery Model](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/0e76123d-776c-4f84-ba61-657bcc3aeacc.mp4?playbackTicket=2d20833ae1e3438e9a10f217631c5144&site=vmware.mediasite.com)

[SDDC8945-QT - Learning in the Cloud: VMware Education's New Enterprise Learning Subscription](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/1cb8ea0a-f38d-4742-b703-4712b1a5ff86.mp4?playbackTicket=04dd5478a2f34d548f3e8d4e95475616&site=vmware.mediasite.com)

[SDDC7876-QT - Service Automation Roadmap: Approach and Samples](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/8c3f94e1-e968-4172-9d02-3187e08faf2b.mp4?playbackTicket=bc2509e3759642c0905df3b58f71fd1b&site=vmware.mediasite.com)

[SDDC8024 - VMWorld Hands on Labs Architecture Design](http:)

[CTO8519 - Best of Both Worlds: Achieving Ultra-Low VM Network Latencies and Extreme Bandwidth Without Compromise](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/6486a7e1-de71-437e-a245-7aa3a8ca69a6.mp4?playbackTicket=6a6164a19df545e59fb9dca0c5dcf552&site=vmware.mediasite.com)

[CTO8120 - Debunking the Myths about Virtualizing High Performance Computing](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/7addbc86-091d-49b7-bce1-4b82f4d2300b.mp4?playbackTicket=235f192d3fdc419ebd694585e5adef52&site=vmware.mediasite.com)

[CTO9942 - Multi-Cloud Mania: Practical Operations in a Multi-Cloud World](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/84262670-fe66-4260-9ad2-9588ab010fac.mp4?playbackTicket=09b902bc393d45bc8a73ddc506587689&site=vmware.mediasite.com)

[CTO9471-SPO - New Capabilities in ONTAP 9 Optimized for All Flash Virtualized Workloads](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/b0a4825f-5c93-4b0f-a434-bfc1c47da3f4.mp4?playbackTicket=e1c8dbf116e0455e85dfe806f34701ec&site=vmware.mediasite.com)

[CTO9036 - Providing Management Tools for the Emerging IoT Infrastructure](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/5239219a-9e26-43f2-afb3-f292203de50f.mp4?playbackTicket=b7461f3a58b14ba4991451393fc31bfa&site=vmware.mediasite.com)

[CTO9951-SPO - Whatâ€™s Old Is New Again: Next Generation Storage](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/d52773e8-b6c5-4523-9113-643a24a4d5b9.mp4?playbackTicket=15678dae556341deb9e4fa4df3e19ec0&site=vmware.mediasite.com)

[CTO9018 - VMware Internet of Things Strategy; Unveiled](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/a36f731f-0772-41cb-87ce-c97451f20aba.mp4?playbackTicket=46823c1c98e54158825323c5b5d63e0e&site=vmware.mediasite.com)

[CTO9032 - Is it Possible to Use NSX to Cut WAN Network Costs in Half?](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/a9038d55-f8bb-40cc-b70d-ebca41e83845.mp4?playbackTicket=ad528081b15a4ebcba30c288f62dd3a8&site=vmware.mediasite.com)

[CTO7942 - Unik: A Platform for Automating Unikernels Compilation and Deployment](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/e77b2fd4-110f-4db9-a816-ed7acb8ba825.mp4?playbackTicket=8cf31a76bc08497b98fa9a36c24b18e4&site=vmware.mediasite.com)

[CTO9996-SPO - Fortifying the Cloud: What the New Samsung-VMware Partnership Means](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/ef193cad-b079-4716-882c-bab49e29c035.mp4?playbackTicket=96ef77bc95e94d37a5248587f5091234&site=vmware.mediasite.com)

[CTO8995-QT - How Do You Manage Security Vs Privacy in IoT Beyond Device Management?](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/ab81a983-a114-4f53-9a10-1172d4f95007.mp4?playbackTicket=3ae1ac6b8f974d5d8d969a8dd92d9b6c&site=vmware.mediasite.com)

[CTO9002-QT - Artificial Intelligence Is the Future of IT](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/a657dff9-c9e6-42de-9feb-d7655a146def.mp4?playbackTicket=56ec89da7b5b4520ab2d8eed3dc791cb&site=vmware.mediasite.com)

[VIRT9034 - Oracle Databases Licensing on a Hyper-Converged Platform](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/b541aeb8-6944-4707-aa8a-bdb73d5e1df2.mp4?playbackTicket=abd0990d487c423abba87ca53118c6e4&site=vmware.mediasite.com)

[VIRT8443 - Extreme Performance Series: Evaluate the Performance of Your Cloud with Weathervane and VMware vRealize Operations](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/de2b1eb5-c391-4b99-993b-f7fd7aaf0b2c.mp4?playbackTicket=01a13497dd1e4b95ac7b163806c3901e&site=vmware.mediasite.com)

[VIRT7620 - Successfully Virtualize and Operate Your Microsoft Skype for Business Infrastructure on the VMware vSphere Platform](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/b6d1bf35-22fd-4dcc-b8a2-ad792d73b7e0.mp4?playbackTicket=f7baf9883bd943d899f0d6dca4384850&site=vmware.mediasite.com)

[VIRT7941 - The Best of Both Words: Achieving SQL Server High Availability with VMware](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/308e14df-2601-4c42-8cf0-1ce2bdc581b2.mp4?playbackTicket=390a4a945f0b4d47bf6f922ac90b9334&site=vmware.mediasite.com)

[VIRT8290R - Monster VMs (Database Virtualization) Doing IT Right](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/68f7bf93-4794-49e9-805e-0c50cd4edb28.mp4?playbackTicket=191c82921e2748f0b5c4b04725bf8e09&site=vmware.mediasite.com)

[VIRT7699 - Use Cases in Performance Root Cause Resolution for SQL Server: How to Use vRealize Operations Manager, SIOS iQ Machine Learning Analytics, and SQL Sentry Performance Advisor](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/74740c5a-9b34-4048-9287-dd04e09cb974.mp4?playbackTicket=603b53e6428349cda311c9fe2e490a26&site=vmware.mediasite.com)

[VIRT8182 - Virtualizing Internet of Things with SAP HANA in a Flash](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/ae1514fc-a72d-4b88-836c-17d523abf8d1.mp4?playbackTicket=09b9d738ef244f23a43e6a0fa2f83ad4&site=vmware.mediasite.com)

[VIRT9009 - Licensing SQL Server and Oracle  on vSphere](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/38993112-12c8-41ef-8d15-40dbbec89d9d.mp4?playbackTicket=ef6a6c9c7e4c427da9ededc9947d60ac&site=vmware.mediasite.com)

[VIRT7598 - Extreme Performance Series: Monster VM Database Performance](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/703a6607-5dd8-4c20-811a-3c0eb0c16a09.mp4?playbackTicket=3bc6ff44878a42c4b13710fb6c757e4b&site=vmware.mediasite.com)

[VIRT7840 - VMware and Microsoft Present: Successfully Virtualizing Microsoft Exchange Server, the Right Way](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/74a36563-6d67-48ea-a05a-df447b25295a.mp4?playbackTicket=33c16223429249cc985639d98f027ab7&site=vmware.mediasite.com)

[VIRT9402-SPO - Modern Storage Strategies for On-Demand Applications](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/8735e1f6-3ccf-4846-9765-3112f6f3e635.mp4?playbackTicket=387eeff95949452d91550212526b6cfa&site=vmware.mediasite.com)

[VIRT8074 - The SDDC: Full Stack on vSphere 6.0 SAP Business Warehouse Powered By HANA, NSX,  vRealize Operations, SDS-Virtual Volumes on Hitachi Unified Platform](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/1cd2489d-727d-46eb-a12f-98b2afc9eac4.mp4?playbackTicket=cdaffe9d777a48c288f422001f28a053&site=vmware.mediasite.com)

[VIRT9435-SPO - Accelerate, Simplify and Control: Add Data Virtualization to Your Enterprise](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/90c84369-5407-463a-bcba-00f55e4c7df1.mp4?playbackTicket=ec7a7cba65ce4d1cb873c4d371340871&site=vmware.mediasite.com)

[VIRT7511 - Performance Tuning and Monitoring for Virtualized Database Servers](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/e5735769-400e-4f2a-baa0-475b5917c98e.mp4?playbackTicket=6bdb121655224baeaf57b9f5e0791161&site=vmware.mediasite.com)

[VIRT8738 - Extreme Performance Series: Virtualized Big Data Performance Best Practices](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/e0b656c2-2c61-4071-90bf-067ba8023943.mp4?playbackTicket=272e058b6a4742d5a09bebc7e4f499d7&site=vmware.mediasite.com)

[VIRT7575 - Architecting NSX with Business Critical Applications for Security, Automation and Business Continuity](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/077cfabe-994f-4021-b2bb-11fa359fee83.mp4?playbackTicket=6d193bca56c74102a122844f0362f2b6&site=vmware.mediasite.com)

[VIRT8278 - Snapshots and SQL Server - Technical Deep Dive and Detailed Lab Findings](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/c4e34999-0ac0-49cc-962a-fa2e40c3e2fb.mp4?playbackTicket=8791cac147fb45a2a5a44520cfabdbfa&site=vmware.mediasite.com)

[VIRT9459-SPO - High Performance Software Defined Data Center for Business Critical Applications](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/24956ef0-3277-484d-8367-930c7000e3ba.mp4?playbackTicket=eb6a61524624437286ce25bd84e407de&site=vmware.mediasite.com)

[VIRT7684 - SAP on Virtual SAN](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/938dc975-ecd1-43e4-aac2-7511f9db36ea.mp4?playbackTicket=230f9f4a86ba464b8b3a8f2fa9faa976&site=vmware.mediasite.com)

[VIRT8530R - Deep Dive on pNUMA & vNUMA - Save Your SQL VMs from Certain DoomA!](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/3dbfa642-cf54-41ad-8035-9d610e15fb44.mp4?playbackTicket=7a5cd57f5a3844b0a04fb5828bd78e34&site=vmware.mediasite.com)

[VIRT7550 - Providing HA and DR to Mission Critical Oracle Databases using vSphere Metro Storage Cluster and VMware Software defined Storage and Networking](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/7e847d8c-32e4-48b3-8a2c-381905c66afc.mp4?playbackTicket=f4072d7502bf4922822f3d02e6e79983&site=vmware.mediasite.com)

[VIRT8708 - Understanding Difficult Applications that Require Extra TLC for Better Performance](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/f62f836c-6ef5-4987-ba1c-da31ceb91d90.mp4?playbackTicket=691928fe43b24508988a1dfeb8f389a0&site=vmware.mediasite.com)

[VIRT7709 - Innovations from Cloudera and VMware for Virtualizing Hadoop](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/fd4c7cb4-17dc-4496-862c-8004b4b6450b.mp4?playbackTicket=51c883b6f3c44c5b8d1e782b7d29c630&site=vmware.mediasite.com)

[VIRT8071 - Making Virtualized Hadoop Deployments Successful](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/79e99643-7392-4679-a2d0-c1146683aeb5.mp4?playbackTicket=c126e4b138a14fd3abb1383a2925f1ec&site=vmware.mediasite.com)

[VIRT7654 - SQL Server on vSphere: A Panel with Some of the World's Most Renowned Experts](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/b2d1c69a-d1aa-4562-b7d1-6b480a0a8944.mp4?playbackTicket=fad992f6ab5f48a9b8a4d3320d40fa03&site=vmware.mediasite.com)

[VIRT9923-SPO - Virtual SQL Server for the Non-DBA](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/2a387a56-0346-464b-8046-2e77ce8d0d57.mp4?playbackTicket=dd6976fca61a45c992e946a28959f7b4&site=vmware.mediasite.com)

[VIRT8530R - Deep Dive on pNUMA & vNUMA - Save Your SQL VMs from Certain DoomA!](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/5d968302-43ce-4c00-99ce-892ca3ccd0cc.mp4?playbackTicket=7dc77969eb4f4bd996e40178ae5c4308&site=vmware.mediasite.com)

[VIRT7931 - SAP on SDDC: Business Benefits of SAP Automation with SDDC](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/539bf66d-4f9f-48ef-8fe9-731b28d6b896.mp4?playbackTicket=669cabeb44224c3dab485197637c35ce&site=vmware.mediasite.com)

[VIRT9132 - Virtualized Extended Distance RAC on Hyperconverged Infrastructure in a Private Cloud - The Perfect Marriage of Availability and On-demand Scalability](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/b9de61bb-a773-45b6-87d1-e137aebb5bb8.mp4?playbackTicket=db3e3d2c27de4529a8d70b066bfb913c&site=vmware.mediasite.com)

[VIRT8198 - Automating Deployments of Mission-Critical Applications - in a Flash!](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/23bb5813-7124-4ecf-82ec-f719203666b9.mp4?playbackTicket=2c559deb9a9b43e394f0b85f30cbbb7b&site=vmware.mediasite.com)

[VIRT7632 - SQL Server On-Premises in the Cloud](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/701a8981-3b63-4f20-86ff-3e8cb7c24503.mp4?playbackTicket=98f93f668f254aa1b8cd6b18eaa82b21&site=vmware.mediasite.com)

[VIRT7507 - How to Design and Tune Virtualized Trading Platforms](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/f548e5c6-fde3-4f6f-8b30-b41b647cf8c4.mp4?playbackTicket=cc7cf05dfbdc41f7b20f5da684f03ada&site=vmware.mediasite.com)

[VIRT8530R - Deep Dive on pNUMA & vNUMA - Save Your SQL VMs from Certain DoomA!](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/9f4373e0-8868-4282-984e-5b8328e3e044.mp4?playbackTicket=d877c96863454877aa31d6c45f74f3a8&site=vmware.mediasite.com)

[VIRT9366-QT - Business Critical Applications at VMware and DBaaS with the Hybrid Cloud](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/117befe9-72c9-401e-ac7c-34e909352c5f.mp4?playbackTicket=6e79adb6cb4c4196b3035551c3f69f98&site=vmware.mediasite.com)

[VIRT8239-QT - Things You Should Know about Big Data](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/745b7d28-7e3d-4aa4-b711-68beefdb2b5f.mp4?playbackTicket=1803ec117cac4526ba9e1b95bcca44ec&site=vmware.mediasite.com)

[VIRT7504-QT - Deploying SAP Netweaver and HANA with vSphere 6 and Latest Solutions in the VMware SDDC](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/26f7e7dd-9245-4ef1-9876-95b268b38cda.mp4?playbackTicket=555351c557a24c27954e87c02ff65e3b&site=vmware.mediasite.com)
