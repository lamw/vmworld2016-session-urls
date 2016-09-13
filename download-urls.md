# VMworld US 2016 Breakout Sessions Download URLs

Here is a nice summary list of all VMworld US 2016 Breakout session with the respective video download URLs. You simply just need to right click on the link and "Save As" to download the mp4 file.

If you wish to download this in bulk, I have also published the "raw" download URLs [here](raw_download_urls.txt) which simply just has the VMworld Session Name and the download URL seperated by a "#" symbol (this is because a comma is used in several session titles) which should be easier to parse (sorry about that Athony).

Here's a quick script that you can use by passing in the **raw_download_urls.txt** or a subset of that list in a file you create yourself.

```console
IFS=$'\n'
for i in $(cat raw_download_urls.txt);
do
  LABEL=$(echo $i | awk -F '#' '{print $1}')
  URL=$(echo $i | awk -F '#' '{print $2}')
  curl -o "${LABEL}.mp4" "${URL}"
done
```

For those that want a simpler 1-liner that even fits in a tweet, have a look at:

```console
IFS=$'\n';for i in $(cat urls.txt);do;A=$(echo $i | awk -F '#' '{print $1}');B=$(echo $i | awk -F '#' '{print $2}');curl -o "${A}.mp4" "${B}";done
```

For those who prefer PowerShell (works on Windows/Mac and Linux Versions) use the following:
```console
$Filelocation = "C:\VMW2016Sessions\raw_download_urls.txt" #Mac/Linux example: "~/VMW2016Sessions/raw_download_urls.txt"
$SaveLocation = "C:\VMW2016Sessions\" #Mac/Linux example: "~/VMW2016Sessions/"
$List = Import-CSV $Filelocation -Header "ID", "Link" -Delimiter "#"
If (Get-Module BitsTransfer -ErrorAction SilentlyContinue) {
    $Bits=$true
    Write-Host "Using BITS transfer for faster more reliable downloads"
}

Foreach ($Session in $List) {
    if (Test-Path "$($Savelocation)$($Session.ID).mp4") {
        Write-Host "$($Session.ID) already downloaded... Skipping"
    } Else {
        Write-Host "Downloading Session $($Session.ID)"
        If ($Bits) {
            Start-BitsTransfer -Source $Session.Link -Destination "$($Savelocation)$($Session.ID).mp4"
        } Else {
            Invoke-WebRequest -Uri $Session.Link -OutFile "$($Savelocation)$($Session.ID).mp4"
        }
    }
}
```

Enjoy!

[CTO10624-S - Are you ahead of the IoT curve](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/01fae26b-4035-4dd8-b9b9-3fb18b2b49b9.mp4?playbackTicket=b0d81072769247eaa06870ca7b601c54&site=vmware.mediasite.com)

[SDDC7808-S - How I Learned to Stop Worrying and Love Consistency: Standardizing Datacenter Designs](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/dfafac9a-4f90-4087-8b0b-194c6b495851.mp4?playbackTicket=9fe3a89c3fa741dda00e505df4fb06e2&site=vmware.mediasite.com)

[HBC9363-S - Virtualization 2.0: How the Cloud Is Evolving the Modern Data Center](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/219e226b-a919-4eb1-8394-0983ca2f8f75.mp4?playbackTicket=f0ce4d0cf121432baa099a49aba44100&site=vmware.mediasite.com)

[EUC10682-S - Delivering the Digital Workspace: The Transformation of End-User Computing](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/7e7da282-3138-4332-97f6-3b842130fd37.mp4?playbackTicket=0c9fd099666c4634a806d06abba64ee5&site=vmware.mediasite.com)

[CNA9993-S - Cloud Native Applications, What it means & Why it matters](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/78332728-0f36-4ad3-a79d-f5af5f1e4904.mp4?playbackTicket=a3aa124ba5934ad0b0475cf03e418126&site=vmware.mediasite.com)

[VIRT8612-S - How Travis Credit Union Virtualized Their Systems and Significantly Improved Stability and Performance](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/2131953d-b383-4d2a-8328-16c1888f3f86.mp4?playbackTicket=709a640361e64fc5877e622d6ca76d25&site=vmware.mediasite.com)

[SDDC8618-S - Introducing VMware Cloud Foundation](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/e0912fd2-aa5a-4144-baf8-a4491af2bf13.mp4?playbackTicket=7ccf735158f2411999117214b4f229e5&site=vmware.mediasite.com)

[SEC9990-S - How Virtualization Will Transform Security](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/a327314e-d0b6-43d2-a3c7-c922e74502cd.mp4?playbackTicket=068f7eacdb0343b78620d85a0120edf8&site=vmware.mediasite.com)

[NET9989-S - NSX - The Network Bridge to the Multi-cloud Future](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/ce36b8bc-f2ef-405c-b575-266e141a413a.mp4?playbackTicket=6dd072bafe004178bfbf4a9d04ba047d&site=vmware.mediasite.com)

[CTO9978-S - Digital Transformation - Technology & Business Futures, A CTO's Perspective](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/b86cd48c-8ae4-47d9-ae22-9568e05e1450.mp4?playbackTicket=df62366bb8d44e97a8df6e858a96aab8&site=vmware.mediasite.com)

[INF9947-S - Spotlight on vSphere: Today, Tomorrow, and Beyond](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/5d6fa026-80f4-4879-ab77-b14866636186.mp4?playbackTicket=ea6aa158bfaf4bd78084a7aa445105c3&site=vmware.mediasite.com)

[SDDC9035-S - SDDC and Hyperconverged has Arrived – Get on Board!](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/16009f16-157c-494c-83db-c36344096943.mp4?playbackTicket=25516f42e83645ffae7c5e4b8b377005&site=vmware.mediasite.com)

[STO9424-S - Taking HCI Mainstream](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/192fe167-453f-4961-b241-df10a01f9202.mp4?playbackTicket=51861f197c2546a7b31b56a9ad204c2f&site=vmware.mediasite.com)

[INF8172 - vSphere Client Roadmap: Host Client, HTML5 Client, and Web Client](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/a899f127-1e55-4c07-be7b-be8bdf363a95.mp4?playbackTicket=8932ee57df4c4cc29e073f5747646768&site=vmware.mediasite.com)

[INF8396 - Winter Is Coming. Are You Dev/Ops Ready? Instant Clone Is!](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/1414f2a7-ffa3-41b5-bcd4-75c2af91c84c.mp4?playbackTicket=6e31c12bddff4eb1b8b3e083cdb26a69&site=vmware.mediasite.com)

[INF8755R - Troubleshooting vSphere 6: Tips and Tricks for the Real World](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/2e2bb9f5-1de5-4bf4-9489-d9d71cb49a83.mp4?playbackTicket=4a47c0c2e78a4c048ab228d2c6e8d936&site=vmware.mediasite.com)

[INF8383 - Maximizing Your Remote Site Infrastructure with vSphere and Virtual SAN](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/42cc8b37-b433-42b0-afd7-88fdbafdb6c4.mp4?playbackTicket=d12a79d385d84bf69f81b9de11d5343f&site=vmware.mediasite.com)

[MGT8040 - Turning Up the Noise: How VMware's Private Cloud Team Is Getting Closer to the Heartbeat of Its Infrastructure, Billions of Events at a Time](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/4e300c36-f458-4ffa-978d-fa17470b1857.mp4?playbackTicket=db381d468025411aa91f07d24feb2e1b&site=vmware.mediasite.com)

[INF8631 - VMware Certificate Management for Mere Mortals](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/0875c252-9193-4999-967a-b89d71ceafb8.mp4?playbackTicket=e80b8fa7432546ce97ed899e938241bc&site=vmware.mediasite.com)

[INF8374 - Zero Downtime, 20K+ VMware vSphere 6 Upgrade](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/32cdada2-55ef-403c-a276-52b0fd97b861.mp4?playbackTicket=499107270e5d47f2ab7b5174f687be96&site=vmware.mediasite.com)

[INF8845 - vSphere Logs Grow Up! Tech Preview of Actionable Logging with vRealize Log Insight](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/07b71600-0b14-42a3-a516-16704a61407e.mp4?playbackTicket=d1d433e464eb45a3ac758deba7fd86a5&site=vmware.mediasite.com)

[INF8038r - Getting Started with PowerShell and PowerCLI for Your VMware Environment (Copy)](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/1d06701d-6bd1-44c8-be5f-94b0ba8ab40f.mp4?playbackTicket=2eec4108d1a84bb386227710997bab95&site=vmware.mediasite.com)

[INF9128 - Day 2 Operations: A vCenter Server Administrator's Diary](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/bc1a52a2-03d8-4a60-ae1c-8eb8ed571d47.mp4?playbackTicket=ed6cac06c89b4a70a6cda0b59368eafa&site=vmware.mediasite.com)

[INF8693 - How to Get the Most out of Your VMware Investment: Leveraging vSphere to Reduce Total Cost of Ownership](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/61ece176-3888-4b04-993b-f33f4652a0e9.mp4?playbackTicket=a53091ee46e44a5493697dc38369ebac&site=vmware.mediasite.com)

[INF8251 - vSphere Host Fabric: Why It Matters to You?](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/80fa3989-6846-446a-89d6-4c29c49043be.mp4?playbackTicket=47d1c7429e9f485a853862a801e13236&site=vmware.mediasite.com)

[INF8108 - Extreme Performance Series: vCenter Performance Deep Dive](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/51ff8ada-1fd4-402c-8648-79c640e6c5cd.mp4?playbackTicket=ad93243c50de463a9ebf0851de26cd05&site=vmware.mediasite.com)

[INF8379 - Virtualization 101](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/93da5bc3-3dd3-443a-81f7-1d580b3d8c52.mp4?playbackTicket=ec395ecf76514e7baf909e4cf1deea3a&site=vmware.mediasite.com)

[INF8371 - How Did the Private Cloud Transform VMware IT?](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/130b3d4a-2847-43ef-a006-1cf2618c4f96.mp4?playbackTicket=6f46ae3935714c1c90e7b1102bc33cde&site=vmware.mediasite.com)

[INF8045 - vSphere High Availability Best Practices and Tech Preview](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/52a4b2b1-5c3b-4eec-89cf-2839cb1d1d5e.mp4?playbackTicket=d6bbfd110f544c1fb4bcf6354ec15406&site=vmware.mediasite.com)

[INF8375 - What's New with vSphere](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/80d4642c-9da5-45de-bc0d-414139f72c7a.mp4?playbackTicket=9e89f3bc6e2841f6a641c1b06e9f667f&site=vmware.mediasite.com)

[INF9144 - Through the Looking Glass:  An Overview of the vCenter Server Appliance Management Interface and API](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/849650f4-893a-44cb-8051-a65f02f5c892.mp4?playbackTicket=4cdd43b2b85f4c1e8d01b951784eb6c8&site=vmware.mediasite.com)

[MGT9997-SPO - How to Automate Cloud Operations with vRealize and NSX Featuring Lessons Learned from Deluxe Corp’s Transformation](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/6e8217e6-de61-4fe4-bab6-1173d531c231.mp4?playbackTicket=dbe79d1da4194f119b5df6e615eadbff&site=vmware.mediasite.com)

[INF8858 - vSphere Identity: Multifactor Authentication Deep Dive](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/fba352fa-976b-4391-a406-afb4e650932f.mp4?playbackTicket=ac5b27996cb4496e83d825320891cffb&site=vmware.mediasite.com)

[INF8683 - Understanding the Role SNMP Agents Play in a vSphere Stack](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/896be611-932c-46e2-a864-bab90d7908a2.mp4?playbackTicket=5f7267de8cfd4292aedd8beaff0be14a&site=vmware.mediasite.com)

[INF9048 - An Architect's Guide to Designing Risk: The VCDX Methodology](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/5cc8a552-e12b-4701-b52d-6b35dafc21ee.mp4?playbackTicket=f95b35decf864c8eb4b0fbad1e29e79f&site=vmware.mediasite.com)

[INF8469 - iSCSI/iSER: HW SAN Performance Over the Converged Data Center](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/1ac81c00-a233-479f-a457-b2d4330979a6.mp4?playbackTicket=28575c4c10b6496f8774e6e58b1e26cc&site=vmware.mediasite.com)

[INF8250 - Case Study: Using vCloud Suite to monitor Global operations](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/87e2cf5f-b458-4e41-91b9-980c6c8442b4.mp4?playbackTicket=1a23ec7fc1804edbb3ee1dabdf29ee27&site=vmware.mediasite.com)

[INF9089 - Managing vCenter Server at Scale? Here's What You Need to Know](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/1d92dafa-054d-44aa-8722-91749035c509.mp4?playbackTicket=113bb198595245a89a464e3140017251&site=vmware.mediasite.com)

[INF9608-SPO - How to Use Machine Learning to Increase Application Availability](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/3dce78c7-e4ff-40a2-b53c-5f5dfe3aee3d.mp4?playbackTicket=02c33c763d614c4ead86312346f5fda9&site=vmware.mediasite.com)

[MGT8884 - Our SDDC Journey - See how SDDC transformed IT in just 12 months and changed how we think about “automation” at Johnson & Johnson IT.](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/5cbf0bfd-4caa-49d3-8804-44eb61cf0d67.mp4?playbackTicket=a5acf05b8e0e4c589864157ccac930f5&site=vmware.mediasite.com)

[INF8939 - Virtual Machine and Application Protection Demystified](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/a47bb7b8-484f-4bdd-9115-9cb6bb86edb0.mp4?playbackTicket=8e546144d6614e94b12fe140360aaaa5&site=vmware.mediasite.com)

[INF9944R - What's New with vCenter Server](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/5b06226a-d1fc-475b-bf2a-d79edaa1fd77.mp4?playbackTicket=61af029292c44edb861b0938989e25bf&site=vmware.mediasite.com)

[INF9205R - Troubleshooting vSphere 6 Made Easy: Expert Talk](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/8a9b1309-a70b-4f1f-b87d-a58247c65bb1.mp4?playbackTicket=16f9a915cd084254a2ee1c196067c637&site=vmware.mediasite.com)

[INF8117 - Why Fiserv Deployed Auto Deploy and Why You Should as Well](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/bd847eff-60cf-44c3-aea9-ea05333ed432.mp4?playbackTicket=8ee001b3c54541e5bbcd78b765a2cb07&site=vmware.mediasite.com)

[INF8959 - Extreme Performance Series: DRS Performance Deep Dive—Bigger Clusters, Better Balancing, Lower Overhead](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/c1649510-b8f7-40c7-b9aa-df5ae530afa6.mp4?playbackTicket=2426244afc354f5bb988b1877d6ce3f0&site=vmware.mediasite.com)

[INF8701R - vSphere Core 4 Performance Troubleshooting and Root Cause Analysis, Part 2: Disk and Network](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/eadc091c-9868-4a5d-9975-bc56e5e25497.mp4?playbackTicket=78d79ac42295416a8483d3c6aecb91ba&site=vmware.mediasite.com)

[INF9950 - Storage at Memory Speed and the Amazing Future of Virtual Non-Volatile Memory](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/fc325f9c-3633-4715-a08b-dbb5e5db54e2.mp4?playbackTicket=0879db311d8e4d23b901c3af9bf2344f&site=vmware.mediasite.com)

[INF8856 - vSphere Encryption Deep Dive: Technology Preview](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/b59479d4-6fbc-41fc-a7a7-8de7bbb4dac5.mp4?playbackTicket=9d84b4c841a141db935fe993296c0e41&site=vmware.mediasite.com)

[INF8780R - vSphere Core 4 Performance Troubleshooting and Root Cause Analysis, Part 1: CPU and RAM](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/26a2ed3a-0923-4b30-86e7-2f2ff0d7a7d0.mp4?playbackTicket=57d0595e749d416280030b5b5067d893&site=vmware.mediasite.com)

[INF9205R - Troubleshooting vSphere 6 Made Easy: Expert Talk](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/c1e0bef8-9d01-4d01-8f77-d33d4e6acbc3.mp4?playbackTicket=2b400c6d7fae465d8629146143ae60e2&site=vmware.mediasite.com)

[MGT8714-SPO - Creating Automated Self-Service Data Protection with Rubrik and vRealize Automation](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/8fade289-f6b9-47ab-9dc8-a6b2d31f7fa5.mp4?playbackTicket=94f853d583564fd5aa125f70b6ceb734&site=vmware.mediasite.com)

[INF8020 - Tech Preview: Enhanced VM Availability Leveraging vCenter and Partner Hardware Integration](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/bb7f9158-0fcc-43b6-a276-24ff19c818a6.mp4?playbackTicket=fdefebc04c78406c84cca191b80f38e9&site=vmware.mediasite.com)

[INF8644 - Getting the Most out of vMotion: Architecture, Features, Performance and Debugging](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/7efd9285-c17e-4bad-8086-184e8f8a379d.mp4?playbackTicket=cc21ebf6777d433681836e0e817d3d88&site=vmware.mediasite.com)

[INF8097 - Production Is Down and So Are My Tools: Meeting Infrastructure High Availability by Deploying an Out-of-Band Management Cluster, A Customer Evolution](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/a782976f-139c-42b9-9eb4-764c5676fe23.mp4?playbackTicket=d007f58f124f4657a9a323c06fc4b53a&site=vmware.mediasite.com)

[INF8837 - How to Relocate Your Physical Data Center Without Downtime in a Few Clicks, Thanks to Automation](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/c9e95fed-4a3e-4037-bb72-39fd3a7baca0.mp4?playbackTicket=7668b9eb9cff434e804c36b91c504f55&site=vmware.mediasite.com)

[INF8122 - A Storage Story: Capacity Management and Performance Planning for Storage Systems in vRealize Operations](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/c0c3db6d-a0b6-4a93-8a36-0c2c1aaa19a0.mp4?playbackTicket=c99e415e1b18438ea1ebcbf581497146&site=vmware.mediasite.com)

[INF8914 - Mastering the VM Tools Lifecycle in your vSphere Data Center](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/8b388d81-86d9-4d76-a341-3efd33333a67.mp4?playbackTicket=b3df89b97c0a4d1eb5fbdf96a279d289&site=vmware.mediasite.com)

[INF8926 - Take Control of VMware vSphere Lifecycle Management in Your Software-Defined Data Center](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/1f37efa2-2b73-4e12-ace2-f1f69bce53c5.mp4?playbackTicket=fade57808cf84bd78f96feffde797c7f&site=vmware.mediasite.com)

[INF9119 - How to Manage Your Platform Services Controller Like Batman](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/8006f1d9-9f72-4673-a5aa-af5687badc33.mp4?playbackTicket=b987863885f144c3a351dd85ee717189&site=vmware.mediasite.com)

[INF8038r - Getting Started with PowerShell and PowerCLI for Your VMware Environment](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/3e0c884f-e6aa-4a0c-84f0-995603b60b53.mp4?playbackTicket=1d68cd1129e341de9050409af7aac88f&site=vmware.mediasite.com)

[INF8525-SPO - Enterprise-Class Cloud Stacks Power Mission-Critical Applications](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/cf060393-f5f9-45d5-ab34-78ba72453e27.mp4?playbackTicket=25b3688ceabd4ca0948ef25f02472e1c&site=vmware.mediasite.com)

[INF7818 - Take Virtualization to the Next Level](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/c3681486-24d1-4bd3-9fd3-2a0d54f2f8d4.mp4?playbackTicket=42dc54798f7c495287f9d890e58c6c82&site=vmware.mediasite.com)

[MGT7713 - Intelligent IT Operations Management from Infra to Apps, On-Premises and in The Cloud](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/ad09d498-3d1c-403c-8a99-030c80ce424d.mp4?playbackTicket=6ab6a6547b0d480bb26404d6c7966d7a&site=vmware.mediasite.com)

[INF7825 - vSphere DRS and vRealize Operations: Better Together](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/972faeb8-cae6-4cd4-85ae-8d5ddca1388e.mp4?playbackTicket=abb552999e4646c28ff609b7cc0ec27c&site=vmware.mediasite.com)

[INF8459 - VMware Security: How to Meet Your Compliance Objectives Using Cool Technology](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/97816611-dc29-4787-968f-0e02609bbaf9.mp4?playbackTicket=1bea3b9962c94831b875ce609eb4fe79&site=vmware.mediasite.com)

[INF9151 - Getting to Zero: Zero Downtime, Zero Data Loss with vSphere Fault Tolerance](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/10afe696-10aa-454a-a088-4549715fdbaf.mp4?playbackTicket=ab4e273aa9364b2090c91672aee82634&site=vmware.mediasite.com)

[INF8275R - How to Manage Health, Performance, and Capacity of Your Virtualized Data Center Using vSphere with Operations Management](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/c3b67aa0-0279-4f47-8368-ca559c477884.mp4?playbackTicket=2166385b069b47afbcb652d4de6ce028&site=vmware.mediasite.com)

[INF8701R - vSphere Core 4 Performance Troubleshooting and Root Cause Analysis, Part 2: Disk and Network](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/b1ad03eb-0653-4ad8-87bc-cb86cac49708.mp4?playbackTicket=495e4c798bb541d3ade51ff6385f1ec4&site=vmware.mediasite.com)

[MGT7878r - Using vRealize Suite for Endpoint Monitoring in a Multicloud Environment (Copy)](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/f59a5194-5d66-4e50-8aca-1464801e3ef8.mp4?playbackTicket=d2007add59614a66a470468358d4d4b4&site=vmware.mediasite.com)

[INF8465 - Extreme Performance Series: Power Management's Impact on Performance](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/c0ab1291-d2b5-4a8c-805c-034b99e12911.mp4?playbackTicket=e5e16d82003b4fe0b34b1906b5418c17&site=vmware.mediasite.com)

[INF8920 - Leveraging Stateless Compute Infrastructure for Centralized Control of the Software-Defined Data Center](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/786c91dc-f4bf-422d-b76b-540411d4e4b5.mp4?playbackTicket=dd6ec94757b14d0dafff305bec0da0b8&site=vmware.mediasite.com)

[INF9455-SPO - Best Practices for All-Flash Data Reduction Arrays with VMware vSphere](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/9f376add-dc21-4a54-bc33-677791e0484c.mp4?playbackTicket=125f56850aaa4410aaf87a544710bbff&site=vmware.mediasite.com)

[INF8275R - How to Manage Health, Performance, and Capacity of Your Virtualized Data Center Using vSphere with Operations Management](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/77da8677-e828-4330-a148-b536b3dc1038.mp4?playbackTicket=81c43f5c2ff346318adbb4644e80ade3&site=vmware.mediasite.com)

[INF8553 - The Nuts and Bolts of vSphere Resource Management](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/441d46cf-46a9-43e8-94ac-b43871205fbe.mp4?playbackTicket=9535d8d245954aa2b452b444965933de&site=vmware.mediasite.com)

[INF9205R - Troubleshooting vSphere 6 Made Easy: Expert Talk](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/c2161de5-790a-484f-a931-435ef9f33fe0.mp4?playbackTicket=10b52c5e5ed24c73a19b99827288e0ad&site=vmware.mediasite.com)

[INF7578 - A Cloud Service Provider's Success Story: Adoption of vSphere with Operations Management](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/ec08d346-515b-40dc-89d2-c6e22e94ad5d.mp4?playbackTicket=12be43883bbb4b6d9e85fadde6cdb7c2&site=vmware.mediasite.com)

[MGT7878 - Using vRealize Suite for Endpoint Monitoring in a Multicloud Environment](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/607168d1-d433-4bc2-9c56-65fdda283d92.mp4?playbackTicket=544c24355ea84a80ad714a24cd1d5297&site=vmware.mediasite.com)

[INF8663 - The Making of a Legend-Dairy Software-Defined Data Center](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/92835196-98e6-48c7-8c7c-189fc011ad7e.mp4?playbackTicket=45558955b1794fe5a8487a2e43b709b2&site=vmware.mediasite.com)

[INF8260 - Automated Deployment and Configuration of the vCenter Server Appliance](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/b5edbdd6-355e-410e-857a-c6aeb77772cf.mp4?playbackTicket=5f8cbe3eb539433aa23c843854453ccf&site=vmware.mediasite.com)

[INF8850 - vSphere Platform Security](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/248ea383-bc5e-4cf8-8ff1-0cb30f4700d7.mp4?playbackTicket=cbf78145b88c4926892b8517370fa6e8&site=vmware.mediasite.com)

[INF9944R - What's New with vCenter Server](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/b5b5b563-4599-4226-8216-dab3d82f8ad2.mp4?playbackTicket=90e6826ceef14f028a922809f3cdf0d1&site=vmware.mediasite.com)

[INF8780R - vSphere Core 4 Performance Troubleshooting and Root Cause Analysis, Part 1: CPU and RAM](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/0f7b9a5f-e1b6-419f-8478-20e17766eb9a.mp4?playbackTicket=45724c040f6b46db9435edf6789d65ae&site=vmware.mediasite.com)

[MGT8439 - Lessons Learned from EMC IT's Data Center Evolution](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/abdb85ef-c635-4d99-b99b-be0cc2470498.mp4?playbackTicket=b3931b2a2fac4917996952d4e8184433&site=vmware.mediasite.com)

[INF8277-QT - Dear IT, You Can Be a Strategic Partner to Your Business. Let me help. Yours Truly, vSphere with Operations Management.](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/242ae00e-ad21-46d2-b947-6a1d6a16f385.mp4?playbackTicket=2878db8b0bf0488b9e7ae93a0ab37ac6&site=vmware.mediasite.com)

[INF8558-QT - Business Value of Data Center Virtualization and Hybrid Cloud Extensibility](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/b8bfe039-3304-40ca-b321-b990d90b2a99.mp4?playbackTicket=7ddc65879b1843d9ad059c0943426ef7&site=vmware.mediasite.com)

[INF8516-QT - VMware Security: The Whole Is Greater than the Sum of Parts](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/a3d798c2-1e61-4d71-98bc-fe8715b37e95.mp4?playbackTicket=ae7d0898c72e40a5b63fd5f75c942443&site=vmware.mediasite.com)

[INF7764-QT - Has the Hypervisor Been Commoditized?](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/283e2135-71eb-4f53-a94e-619edfc346be.mp4?playbackTicket=28691253c8db4213a62cc0c61327c812&site=vmware.mediasite.com)

[MGT8543 - Simpler Extensibility in vRealize Automation 7.0 with the Event Broker](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/ccfa56d7-b98d-4904-b14d-70fdca584e6d.mp4?playbackTicket=8d594fc616d64fd3839d5a11ae4caf31&site=vmware.mediasite.com)

[MGT7770 - Virtual SAN Management – Time to Level Up Your Ops Game!](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/f8c014e7-debb-44d8-a257-fb6d3c14e4d8.mp4?playbackTicket=318f255eeb604d21b129e68a906a17d3&site=vmware.mediasite.com)

[MGT7751R - A Technical Deep Dive into VMware Integrated OpenStack](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/31a9a081-27ea-406b-b18d-795534077f0c.mp4?playbackTicket=b3e79b1269bf4f7aa5e9fd3c2eb3f869&site=vmware.mediasite.com)

[MGT8080 - vRealize Reference Architecture: Design, Deploy, and Realize Value at High Speed and Amaze Your Customers!](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/7bdbd96d-3bda-4c18-84aa-fdacd8feb6a7.mp4?playbackTicket=6ec9dcdad9074ec8bcd70f550a09c2ab&site=vmware.mediasite.com)

[MGT7751 - A Technical Deep Dive into VMware Integrated OpenStack](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/f412aace-2825-4442-8c32-1791f9a73372.mp4?playbackTicket=8ec822b49ae94375916d4c4daf53a6f7&site=vmware.mediasite.com)

[MGT7685R - Insight into the World of Logs with VMware vRealize Log Insight](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/25044a08-8221-4c08-b257-158ee0c8e9f2.mp4?playbackTicket=b880c665ead54c32a1b3c879bdc06b77&site=vmware.mediasite.com)

[MGT8770 - Managing Microsoft Azure with the vRealize Suite](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/e3475598-2380-4bde-9a5d-59b4e843902d.mp4?playbackTicket=1106b6d79b7a4e8a8849e0a1eb5f24e3&site=vmware.mediasite.com)

[MGT8641R - A Lot of Insight and No PowerPoint](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/96abe8b8-77dc-4dbd-8b56-e2b77711a6df.mp4?playbackTicket=308c551cb2e94b909bf8a46f7f33a75a&site=vmware.mediasite.com)

[MGT8085 - Save Time With Everything and Anything as a Service (XXXAAS) using vRealize Automation (vRA)](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/206c7998-f064-4fdb-8fca-26aa8ca5a0ec.mp4?playbackTicket=9a76e488e19440ad84ba4a3a1fcfd60c&site=vmware.mediasite.com)

[MGT9184 - Day 2 Automated Operations with vRealize Automation 7.0 and the Event Broker Service, a Deep Dive.](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/5bfd6c00-bba2-4096-91de-b0026d37b4fe.mp4?playbackTicket=632bc05022344e5c9d8c1298e32d4c8b&site=vmware.mediasite.com)

[MGT8641R - A Lot of Insight and No PowerPoint](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/c84773f2-c8df-45a4-ad6b-e5391348a700.mp4?playbackTicket=68a6388ad7ca4c7fa8049d873805fe84&site=vmware.mediasite.com)

[MGT9426-SPO - Best Practices for Cloud Service Data Security](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/c215056d-5fad-4b62-9cb4-60bc5a0ba66b.mp4?playbackTicket=9481d055fd33410d858343bc7fc44171&site=vmware.mediasite.com)

[MGT9948-SPO - It’s Time to expect more from your Virtual Environment](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/9cec6924-b24b-4ac8-8a29-b60ccb52f4dc.mp4?playbackTicket=a9e2a6b90a0b49978ae3f3d0531b6d1b&site=vmware.mediasite.com)

[MGT7759 - Early VVD Adopter Experience: Building a Secure and Automated Cloud](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/c228cd0b-85b7-4021-9228-93ef34d5311e.mp4?playbackTicket=15047210f7734b2db2d1d4898c9bb812&site=vmware.mediasite.com)

[MGT8332 - How I Learned to Stop Worrying and Love the vRealize Automation API](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/77be32ea-8175-4cb0-b638-4337b92868f4.mp4?playbackTicket=fa960e289d2c417191eab5aa907801e7&site=vmware.mediasite.com)

[MGT7685R - Insight into the World of Logs with VMware vRealize Log Insight](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/ef81101b-8ac3-432e-ac60-ef6b83a5b33b.mp4?playbackTicket=1592fb6858114e7ba5e7e6f781239ee2&site=vmware.mediasite.com)

[MGT7899 - Whose Hand Is in the Cookie Jar? Reducing the Mean Time to Innocence Using vRealize Operations](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/9aa1417e-fb35-4e49-a7fc-e49f736d6c24.mp4?playbackTicket=aeee3b1fd7cf43c4a798f673e7aac7fd&site=vmware.mediasite.com)

[MGT9457 - Understanding the Value of vRealize Network Insight](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/88c36b95-83b1-47c5-b923-de4d18d63147.mp4?playbackTicket=b7969b335c934576b6c422317ce9a2d0&site=vmware.mediasite.com)

[MGT8733R - Application Self-Service with On-Demand Networking & Security from vRealize Automation and NSX](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/e2c595c5-4ae1-4136-8860-b5f2c51ceb19.mp4?playbackTicket=3021c16b432a4ed29484d93621f83bcb&site=vmware.mediasite.com)

[MGT8486 - NSX Operations with vRealize Suite](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/a02aac83-8f99-46ee-b845-bc7ff2d9598b.mp4?playbackTicket=6745978fc4b4412e92dc96279d3bdf27&site=vmware.mediasite.com)

[MGT9615-SPO - vRealize the Possibilities:  Application Agility and Rapid Deployment with vRealize Automation, Orchestration, Operations and Log Insight](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/1770c354-0e4d-45d9-a6c0-fca5fde01633.mp4?playbackTicket=af067604fbca4d70bfc7a7439eea59fd&site=vmware.mediasite.com)

[MGT8984 - From Zero to SDDC at a Major Telco](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/4dea4ba0-e360-4ff9-bcbc-d240928cbf0f.mp4?playbackTicket=4d0e58de18d94f1289fca28b7b6b4c0c&site=vmware.mediasite.com)

[MGT7671 - What's New in VMware Integrated OpenStack Version 3.0!](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/57f8f101-cd2b-4052-9f8e-b310d94a0ea1.mp4?playbackTicket=13167889dde7482e8528ca01b7d07647&site=vmware.mediasite.com)

[MGT7752 - OpenStack in the Real World: VMware Integrated OpenStack Customer Panel](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/51c630c9-4528-4611-8841-6123e657ff4d.mp4?playbackTicket=a30da697d1cd45bb9028444fe1bb71b9&site=vmware.mediasite.com)

[MGT8763 - 3 Best Practices for IT to Enable Developers to Deploy on Amazon and Azure While Ensuring Security and Accountability](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/02a5f93e-1703-4dbb-9ecc-5a21a5acb411.mp4?playbackTicket=b25a0efe753b41528768e7d9d8b2c27c&site=vmware.mediasite.com)

[MGT8768 - How TIAA Uses an API-Centric Cloud Management Platform to Allow Applications to Be Easily Deployed and Managed on Both Public and Private Clouds](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/df16125c-cf55-4f70-b1f0-d34ec077ab71.mp4?playbackTicket=7ea8d0f0cb98470ca884b9f551dc0c32&site=vmware.mediasite.com)

[MGT7629R - 360-Degree Troubleshooting](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/1b18cd73-1a3a-4a40-904a-a38c318ee006.mp4?playbackTicket=ad74e37770fb451aa051aadf560dee01&site=vmware.mediasite.com)

[MGT9220 - vRealize Automation and NSX Design Experts Panel](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/32f50480-5374-402b-b3a9-10cfb7d15f51.mp4?playbackTicket=680a8293558e45c2aa030719b7c9bdbb&site=vmware.mediasite.com)

[MGT8762 - How to Set Up a Multicloud IT Portal to Deploy, Manage, and Control Applications on Private and Public Clouds](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/9e6ab72b-430d-4a3b-9468-27151330576e.mp4?playbackTicket=5677ba8b05dc4ff79864ca263f649e21&site=vmware.mediasite.com)

[MGT8807 - What's New in vRealize Code Stream](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/9002ce06-d69a-4dc3-bc32-648d1c0b9634.mp4?playbackTicket=e3b359d8220547fe91407b0dbc6fcea3&site=vmware.mediasite.com)

[MGT8733R - Application Self-Service with On-Demand Networking & Security from vRealize Automation and NSX](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/68f928aa-795e-4a40-a87c-c7c4cad4dc41.mp4?playbackTicket=0ec678db87b44f8bb5b63527b50ebc75&site=vmware.mediasite.com)

[MGT7737 - Intelligent Operations Management: A Customer Perspective](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/95268c27-2a95-4d78-b215-17e46517017a.mp4?playbackTicket=ae248889c41741ffac0b974cfdae7580&site=vmware.mediasite.com)

[MGT7629R - 360-Degree Troubleshooting](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/66c85e14-7271-4af5-97ae-c3b5723f4984.mp4?playbackTicket=25681354d1664ec69b36e24dc0b81a24&site=vmware.mediasite.com)

[MGT8902-QT - Process, Process, Process, And Then Tools](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/44974845-300c-4341-9dc8-6a8069bad800.mp4?playbackTicket=d6b0b92dd5244d48ba2d2accc963fa43&site=vmware.mediasite.com)

[MGT8751-QT - Be the IT Hero of Your Company and Discover How to Save Thousands of Dollars by Reclaiming Underutilized CPU, Memory, and Disk Resources](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/fb6cfd29-e101-47e6-8e7d-3c3f515b59e7.mp4?playbackTicket=41938125acb94d33a3e389ad57ebcf4b&site=vmware.mediasite.com)

[MGT7782-QT - Automating Resource Reclamation in the Modern Data Center](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/f32d79f9-5b42-4875-a1dd-e27fb913ab4e.mp4?playbackTicket=474a92e3516846fdb393eec971035006&site=vmware.mediasite.com)

[MGT8355-QT - Tutorial: Build a data-driven story around capacity planning using VMware vRealize® Operations™ and third-party Management Packs](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/f0b3de0f-fcc4-4b25-a595-479987b8df61.mp4?playbackTicket=ccbc66430a9a4e4a80431524710c759a&site=vmware.mediasite.com)

[CNA7806 - Pivotal and VMware: The Lowdown on the High Up](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/f6537dbb-31c9-480c-adce-6ceb68ed6289.mp4?playbackTicket=ef5251a212b6405f80a7963c99976cdd&site=vmware.mediasite.com)

[CNA7741 - From Zero to VMware Photon Platform](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/3c85b6b2-aefa-47c6-ba5c-e7a3e5298f2d.mp4?playbackTicket=7a9c5dee64c4484fa29e0eff620529ca&site=vmware.mediasite.com)

[CNA8986R - Running Docker on Your Existing Infrastructure with vSphere Integrated Containers](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/a459cc08-49fd-4487-8697-0a1351f1a054.mp4?playbackTicket=1a075e812157471eaddc6fba352bca92&site=vmware.mediasite.com)

[CNA8313 - Your Open-Source Data Center](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/1666c675-e776-4d67-82db-135c40e81c49.mp4?playbackTicket=1fdf290c4fcb4438882924cf2786f27e&site=vmware.mediasite.com)

[CNA7524 - Photon Platform, vSphere, or Both?](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/d2d40873-7ad0-4272-b43d-130cbed7587a.mp4?playbackTicket=aaca4b6719924fcf900e845419b3870b&site=vmware.mediasite.com)

[CNA8578 - VMware Private Cloud and Containers in Production: Lessons Learned from a Real-World Deployment at Retailer Otto](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/f3e7ddd3-9397-4bf0-846d-ce83323d80b7.mp4?playbackTicket=fe9fe84f140a41f09d6ab3ed5c89563f&site=vmware.mediasite.com)

[CNA8145 - From Today to ''CNA'': VMware Technologies and DevOps Frameworks as a Service](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/e4e498af-e8ce-49d3-8a00-4d205692d12b.mp4?playbackTicket=9023ba16a8094c37a2e7b64ab142b909&site=vmware.mediasite.com)

[CNA8717 - vSphere Integrated Containers – Learn how you can run Docker Containers, in Production, Today!](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/90bf852a-9035-4370-a948-d40b03b0b159.mp4?playbackTicket=7e5ef02fc4104c23ac35056ae1c6e90f&site=vmware.mediasite.com)

[CTO7964 - Cloud Native Buzzwords (Demystified) for Dummies](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/ecd734f3-6c76-4c6c-afbe-1613fca1a917.mp4?playbackTicket=6481eb3c492d48c68c3f71c6c854a4cf&site=vmware.mediasite.com)

[INF10869 - Accelerate Your Journey to Cloud with Accenture’s Private Cloud Blueprint](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/d6114ab5-5f54-4987-a5d1-26fb0ad92145.mp4?playbackTicket=e54b68915d6d42bab949385a8f4da948&site=vmware.mediasite.com)

[SDDC9462-SPO - The Edge is Still Bleeding: A face-melting technical smorgasbord of all things Converged, Hyper-Converged, Cloud Native & Software Defined](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/a18e8431-7d10-4c51-85ba-0470c76df70a.mp4?playbackTicket=ee3b972d8b9649639adfeafb18cd4578&site=vmware.mediasite.com)

[CNA8986 - Running Docker on Your Existing Infrastructure with vSphere Integrated Containers](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/0a23fdc4-ddbf-4e8b-adde-4668538a5c10.mp4?playbackTicket=a317894dc71b4de88a40b519448230c3&site=vmware.mediasite.com)

[MGT7804 - Container Management with vRealize Automation](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/53af543f-d537-42a2-ab25-44c520c412e3.mp4?playbackTicket=211b3422a8694d6cbd9393d7eed32c3b&site=vmware.mediasite.com)

[CNA8897 - Continuous Integration and Continuous Deployment for Containers: Confidently Promote Your Code into Production](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/6e8a6150-3771-428a-b01c-33c01f30366f.mp4?playbackTicket=7b78b6be0a3d4467b124de5881a385f7&site=vmware.mediasite.com)

[CNA7454 - Introduction to Containers as a Service](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/c00a93e3-64d8-4672-b049-cc47c9fd57c4.mp4?playbackTicket=60d1bab51f3e44b1a48b0225b6c17bab&site=vmware.mediasite.com)

[CNA9994-QT - VMware's Cloud Native Stack](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/0e51cd9b-cf8a-4a81-8a22-a9f7722aab57.mp4?playbackTicket=255ada04f1084f0b93a3d2534e9deadc&site=vmware.mediasite.com)

[STO9984-QT - Business-Critical Applications for Virtual SAN](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/81cbad16-bc19-43dd-91f1-fb985fc0c09e.mp4?playbackTicket=f788576e859245a3bec282bdeb45ccfd&site=vmware.mediasite.com)

[CNA7813-QT - Architecting Cloud-Native Systems with Photon and Pivotal Cloud Foundry](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/00253617-2ab9-48e2-aa0e-fa42d572ba8b.mp4?playbackTicket=8930f838615f4d28806f7e680a970563&site=vmware.mediasite.com)

[DEVOP7915 - Network as Code: DevOps Implications of Programmable Infrastructure](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/451f8d95-0e35-4d4a-9e06-c013217edc05.mp4?playbackTicket=1dd2a2917ccc4f4ca448539ebb86fcb3&site=vmware.mediasite.com)

[MGT8969 - Forrester Research POV on DevOps, Automation, and Virtualization Maturity Trends](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/c6d2d4f4-6465-4c3a-a9dc-5c878a50eda0.mp4?playbackTicket=a3122c32bead44eab024702cfc7bb4e0&site=vmware.mediasite.com)

[INF8255 - Evolving the vSphere API for the Modern Era](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/fa25d2c4-fc32-43b4-bb5c-c2767bf10b7c.mp4?playbackTicket=7e46e6866fcb48bbaaebe6f25221bafc&site=vmware.mediasite.com)

[MGT8499 - Moving to Infrastructure as Code: How Fannie Mae Is Managing the SDDC with the vRCS Management Pack (aka Project Houdini)](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/39c21296-ef06-400c-8d13-3ce4c0da8e2a.mp4?playbackTicket=763b398d10f346eaa79bd913959055c8&site=vmware.mediasite.com)

[DEVOP9093 - Unpanel: How I Survived the DevOps Transition](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/ac7e82bb-cd89-4d96-9efc-7d45960c4b62.mp4?playbackTicket=81e7043041ae468aac9014c13f2634d6&site=vmware.mediasite.com)

[DEVOP9403-SPO - Hacking Your Backups: Making Your Backup Data & Systems Work for You](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/52479be8-d8f4-4551-9d8e-0b40dd2a2922.mp4?playbackTicket=08ca2f7dad52447eb2a5073981025ec1&site=vmware.mediasite.com)

[DEVOP8924 - Building an Actionable Strategy Around DevOps and Platform as a Service (PaaS)](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/e3282a09-3b57-4119-a7a9-11d156262b62.mp4?playbackTicket=59d95cf888984e1792f8cb3769ee48e0&site=vmware.mediasite.com)

[NET7858R - Reference Design for SDDC with NSX and vSphere: Part 2](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/878a7c6a-c7e9-46c4-ba78-d91c10d868da.mp4?playbackTicket=e1a28bbcb3b3437db672d050c9229b52&site=vmware.mediasite.com)

[DEVOP8971 - Run a Hybrid Application Across VMware and Google Cloud Platform](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/1a9e5995-9f83-4164-8471-94f38d614dc9.mp4?playbackTicket=6767bc0249144b59a091e534f38b7afa&site=vmware.mediasite.com)

[MGT8831 - Digital Transformation Through VMware DevOps Code Stream](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/53468bae-c764-4a76-a765-7c975389a135.mp4?playbackTicket=c1e0cda08b2549849d31971febf7aca9&site=vmware.mediasite.com)

[INF8546 - Case Study: Extreme Dogfooding of SDDC for VMware R&D's Private Cloud](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/76012b3b-d9c0-4309-a87c-d45364e908ff.mp4?playbackTicket=194eb8fda962421b93eeb0b8b6e0b3dc&site=vmware.mediasite.com)

[DEVOP7859 - Real-World DevOps Customer Panel](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/26df095b-709e-4221-a6ca-4226bcdf3fb3.mp4?playbackTicket=bbfa9d087bb84cd5bdcc2e365a33ee97&site=vmware.mediasite.com)

[DEVOP7730 - DevOps Bootcamp Actual](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/dff45cf0-51e3-43af-afa0-d9810177f42e.mp4?playbackTicket=273e5f894f444d84b2e771b46212865e&site=vmware.mediasite.com)

[DEVOP9965-SPO - Implementing DevOps with VMware vRealize and Cisco UCS](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/725fe6a3-9cab-449c-afe3-560a589fd8b6.mp4?playbackTicket=380dcd46e84b4bdb9414dfcf34dcbd7d&site=vmware.mediasite.com)

[NET8368 - Network as a Service (NaaS) Transformation with NSX](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/212c06af-c61c-46e9-9424-18cb32fbc742.mp4?playbackTicket=4783d489d25a4d30a8ca7925fffab9ca&site=vmware.mediasite.com)

[INF8540-SPO - Say Yes to vRA and vRO in a Real-World Hybrid Cloud](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/485b49c9-7428-411f-bded-d80dee1739bc.mp4?playbackTicket=43a4e8d1447a4e63b011791ecd8a26d4&site=vmware.mediasite.com)

[INF8635 - vSphere Content Library: Organize, Distribute, and Utilize Your Content Effortlessly](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/6f7d580c-e67a-4839-a207-2fca37749af1.mp4?playbackTicket=30a502dfc18a4c319c21ce17177a411b&site=vmware.mediasite.com)

[NET7858R - Reference Design for SDDC with NSX and vSphere: Part 2](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/9e2db62c-0e26-4abe-8be8-47dbf9923a22.mp4?playbackTicket=1aa44d65eb1f4c38a53f27d8f0b53170&site=vmware.mediasite.com)

[DEVOP7788 - Industry Perspective: Enterprise Reality of Doing DevOps](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/602f7c97-9082-4bc4-ada1-6c6afb1f1361.mp4?playbackTicket=c2ab41f52ca54a8c99307479fb5ed038&site=vmware.mediasite.com)

[DEVOP7674 - vRA, API, CI, Oh My!](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/d6743640-1d0c-4ef0-849f-bab15f0268dc.mp4?playbackTicket=a38a3a1b17ed4345bacd3864ae9de94c&site=vmware.mediasite.com)

[MGT8766 - How IT Can Enable DevOps and Development Teams to Rapidly Deliver and Iterate Robust Applications in a Multicloud Environment including VMware, AWS, Azure and Softlayer](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/4eab316d-ace5-4486-a642-84e4c5811671.mp4?playbackTicket=8a1c9878f4ea446e85a986c32903b755&site=vmware.mediasite.com)

[DEVOP7447 - Redefining Enterprise Resource Planning Using vSphere 6 and Workspace ONE](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/b68e46cc-409c-44b5-958e-36175ff360b7.mp4?playbackTicket=351a6d6097694742a64507c934d0211e&site=vmware.mediasite.com)

[DEVOP8630 - Increased Employee Productivity with Enterprise-Grade Security Using VMware IT’s Managed Public Key Infrastructure Service and AirWatch](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/befc6a60-c561-4e7b-8e96-0fd3faa3064c.mp4?playbackTicket=45e7a074e74a437a8bb79ca224453acd&site=vmware.mediasite.com)

[EUC7799 - Design Horizon the Easy Way with Help from the Horizon Sizing Estimator](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/0751d0e8-46b0-472b-9c04-9ede3e382b87.mp4?playbackTicket=d3bf8603a9734ffd8544a531e478d9c4&site=vmware.mediasite.com)

[EUC7562 - Cloud-Hosted Virtual Desktops and Apps: A Technical Deep Dive into Horizon Air](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/3dc80c8a-0c33-45ec-b1b1-d0813053258c.mp4?playbackTicket=fad7bda2520d46c5854668ac28280393&site=vmware.mediasite.com)

[EUC7998 - The Latest in High-Performance Desktops and Applications with  Horizon 7, Blast Extreme Protocol,  and NVIDIA GRID vGPU](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/24ffd9ea-2f2b-482c-8950-d9a117c0a5c0.mp4?playbackTicket=95674226d9ae45fab2ccfa4c2ba8ec04&site=vmware.mediasite.com)

[EUC9392 - Expand Your Enterprise Mobility Strategy with VMware and the AirWatch Partners](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/3cdeaa04-4ff3-45aa-8aa7-f7d87786a5a4.mp4?playbackTicket=9b65d16692de4bdf8fce540471f1bc6a&site=vmware.mediasite.com)

[EUC8216 - Deep Dive: Deploying Office365 Applications on mobile devices with AirWatch](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/db7df503-595f-4100-ab82-b28996b4be6d.mp4?playbackTicket=eda895721fb7408aa1bbab180d8f74f3&site=vmware.mediasite.com)

[EUC8243R - Troubleshooting 101 for Horizon](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/f8a2493b-71cd-4671-9dca-bfd0807770f5.mp4?playbackTicket=a705ba4aba564167ad3a45e6d02d70b3&site=vmware.mediasite.com)

[EUC9386 - What’s new with Workspace ONE: Identity meets Mobility](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/0d8d5f67-6515-4e9c-aac3-6b2cc895f0f1.mp4?playbackTicket=e215a58b44aa4f88a51b1b276bcc7117&site=vmware.mediasite.com)

[EUC7870 - VMware's Solution Strategy on Mobility’s Evolution to Internet of Things into 2016 and Beyond](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/c87ab1e1-d61a-4953-8911-727c2b99c86c.mp4?playbackTicket=4384cf74e45f4966ae5a8bda88473a89&site=vmware.mediasite.com)

[EUC8938 - Limitless Learning: Leveraging VMware Technology to Provide a Digital Learning and Working Environment for Every Student and All Faculty and Staff](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/2c9d47f7-c4db-4509-b8f0-ddc90df7392c.mp4?playbackTicket=2ce3ea818cb44d9999a0be66e498e1d1&site=vmware.mediasite.com)

[EUC7644R - Unify Endpoint Management Across Mobile and Desktop](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/ff9b9d5c-3dca-41b2-ab2c-7c42ea7672d1.mp4?playbackTicket=c80b143dc7324ee9a84ece951b3dc0b7&site=vmware.mediasite.com)

[EUC8160r - Discover AirWatch: Enterprise Mobility Management](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/7cefde1a-fe78-46b5-9bf3-7d976f8fcc80.mp4?playbackTicket=d76ac6e6769c4334824aa8d70a14838a&site=vmware.mediasite.com)

[EUC9395 - How Horizon 7 and Horizon Air Are Changing the Cost Economics of Virtual Desktop Delivery](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/b1a82cb2-4e1c-41a6-ada7-56c0205d839a.mp4?playbackTicket=898c180356234a23a1f587631c77d365&site=vmware.mediasite.com)

[EUC8725 - Everything You Need to Know About Horizon Remote Desktop Services Hosted Applications (But Probably Do Not)](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/0d23d478-06ea-4e5b-b874-b01ccf6d5dfd.mp4?playbackTicket=3c41be3327f84f01ba03c57d45f952c7&site=vmware.mediasite.com)

[EUC8853 - Taking Back the Desktop](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/67a58451-7ada-4136-b115-c43e7db21415.mp4?playbackTicket=b58c16fd6169429db3c3c6e86b2491f4&site=vmware.mediasite.com)

[EUC8346 - Modernizing and Mobilizing Retail IT](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/d4bc8d91-2cd0-43f0-993d-769d62815ef3.mp4?playbackTicket=ff98efe42b5742298ad059c5287a27cd&site=vmware.mediasite.com)

[EUC8822 - Case Study: Large-Scale Deployment of VMware App Volumes and User Environment Manager for 10,000 Seats](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/333badbf-1f4c-4ebb-964b-cb49b90e6e3b.mp4?playbackTicket=fca0ccd8520f433eb6a891fac2396f13&site=vmware.mediasite.com)

[EUC8521 - The Future of VMware Fusion and Workstation](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/426732dd-6b9f-42b5-ace2-a480c6947905.mp4?playbackTicket=13d89199b79f4f43881fcb3aa9fa7043&site=vmware.mediasite.com)

[EUC7678 - Real-World Examples Using App Volumes, User Environment Manager, Mirage, and vRealize Operations to Deliver Complete Desktop, App, and User Management and Monitoring](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/551f1099-059e-40cc-9a54-23e515b78e1c.mp4?playbackTicket=4a0d0d24ac8f41e3b2f35d478825a0a1&site=vmware.mediasite.com)

[EUC8605 - Next-Generation Mobile Productivity with Workspace ONE Apps](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/302fee13-a6fa-4c47-ab0e-0deeb22c056f.mp4?playbackTicket=3b14ffc47ea6483e80088f2b19fd5842&site=vmware.mediasite.com)

[EUC7995 - Enterprise Mobility Automation using Software Defined Data Center (SDDC): Role-based Desktop and infrastructure provisioning](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/cac0cea1-25e9-43ee-a38a-535f585f3366.mp4?playbackTicket=74f1c28e16ba47d0afbfffe41f4e12be&site=vmware.mediasite.com)

[EUC9179 - Introducing Horizon Air Hybrid Mode: Low-Cost, Simplified Virtual Desktop and Application Deployment and Management](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/4a4e16fa-61bd-46b4-b451-f3db2851327c.mp4?playbackTicket=1d64ea7a67724ee587a9a0a6ef3061b5&site=vmware.mediasite.com)

[EUC8345 - Mobilizing and Modernizing Government IT to Advance Missions: The Secure Digital Workspace for Government](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/9968bd24-8546-482d-b9ba-2bc1990ece46.mp4?playbackTicket=8e5b7ecc598f4a748687b14042dbf8dd&site=vmware.mediasite.com)

[EUC9451-SPO - Preventing Attacks on Mobile Devices using AirWatch Integration with Palo Alto Networks](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/47bdb86a-ffb3-4698-bf1c-81c4d3de11ad.mp4?playbackTicket=ecb6d5f1a20a41b6a841ced732192e18&site=vmware.mediasite.com)

[EUC7797 - How to Manage Personal Settings with App Volumes and ThinApp](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/345bb591-6ea5-4abf-b74f-6326b60e96ab.mp4?playbackTicket=322c062425104145b534a2dc6f13b86d&site=vmware.mediasite.com)

[EUC8392 - Untethered Yet Secure: Technical Deep Dive on Using Horizon FLEX to Manage VMware Workstation Player and VMware Fusion Pro](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/9bce471a-b9fb-4ae6-a220-5e011b345662.mp4?playbackTicket=4899debdc14f4ce5b90216343c6b02ef&site=vmware.mediasite.com)

[EUC8648R - Architecting VSAN for Horizon the VCDX Way](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/889c34d2-5e13-464d-8c21-221d3d869f96.mp4?playbackTicket=dc5783626a01441cb1e4e3e8ff487c8c&site=vmware.mediasite.com)

[EUC8784-SPO - Architecting Highly Available, Scalabe and Resilient Enterprise Mobility & Desktop/Application Solutions](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/bfab2dd5-02ef-4ff4-8065-05cc2f14d541.mp4?playbackTicket=681dbfa9b0e84ceda4fd58bbc6f17270&site=vmware.mediasite.com)

[EUC8745 - Under the Hood with Identity Manager and Office 365](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/56941882-36db-4144-ba46-3ef6f9c471cd.mp4?playbackTicket=705195bf1594446ba5ae214fb24c7f33&site=vmware.mediasite.com)

[EUC7519 - Access Point: Advances in End-User Computing Remote Access](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/5801bd25-a7d3-4122-8aa6-91d609c00a8c.mp4?playbackTicket=a09ccfa213f84108a7054f0bce144076&site=vmware.mediasite.com)

[EUC9388 - Customer Panel: How Enterprises Are Using VMware Identity Manager to Enable Their Users to Be Productive on Any Device, Anywhere](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/d8f728a4-bfe8-4cbd-8c5c-784b6a74bc47.mp4?playbackTicket=0c30599ee5a340929054483ec9d7b011&site=vmware.mediasite.com)

[EUC9394 - Horizon Air and Interconnecting the Clouds](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/58c631da-fd14-41bd-bf09-522c23b6168d.mp4?playbackTicket=70fb97bc65e5482abc74d0261f1c0aad&site=vmware.mediasite.com)

[EUC9139 - NSX and Horizon Reference Design: Secure End-User Computing](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/3a14c5bf-dc3a-44eb-9128-5373d9cee5ee.mp4?playbackTicket=1182eeac517d47ba9fe531cb20925fbd&site=vmware.mediasite.com)

[EUC7864 - Protect the Edge: Secure IoT and Medical Devices](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/83b28d53-1ee1-4e0e-a43c-9201e35aea4d.mp4?playbackTicket=e29716fe28b74f569553e2fb0d06e88b&site=vmware.mediasite.com)

[EUC9391 - Managing Windows in a Modern Mobile-Cloud Framework](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/705317fd-7db1-4c27-942d-a50cceefa3ec.mp4?playbackTicket=8987f3c072f24aef989b4209bf64fb14&site=vmware.mediasite.com)

[STO7560 - Four Unique Enterprise Customers Deployment of VMware Virtual SAN](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/f9b56ed8-e637-4547-82f4-7ad1563fcbcc.mp4?playbackTicket=174a01ce29d740c98290f03c0323392f&site=vmware.mediasite.com)

[STO8754 - Virtual SAN and Horizon: Designed for Simple, Powerful Virtual Desktops](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/ae6ca51e-07e9-4a31-ba27-d33ed60ca211.mp4?playbackTicket=1486c55e05c844de9aef2b335d584839&site=vmware.mediasite.com)

[EUC7888 - Why Siemens Uses High-Performance Desktops with VMware Horizon and Nvidia GRID vGPU](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/e72851aa-58c4-4460-b904-68a539c6951d.mp4?playbackTicket=3b07074392884b5c8ce605cd1fd700ed&site=vmware.mediasite.com)

[EUC7613 - Ask the Expert: Everything You Want to Know About VMware End-User Computing](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/30c6553a-e7fe-44b5-b9c1-eeaa7162581f.mp4?playbackTicket=734b738b42ac4a539b399b350843fa83&site=vmware.mediasite.com)

[EUC9390 - Securing Against Cyber Attacks from Datacenter to Device](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/ca1ca96c-439e-4879-8cbe-2adba1a32723.mp4?playbackTicket=f870fd5eb25e4119a9474f19a13c18ac&site=vmware.mediasite.com)

[EUC8648R - Architecting VSAN for Horizon the VCDX Way](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/8511e61a-b3b4-48e5-a0fd-e3fa562a2417.mp4?playbackTicket=79fa67d6901d4bc69146b8104bc4b933&site=vmware.mediasite.com)

[EUC8603 - Support the Complete Mobile App Management (MAM) Lifecycle with AirWatch](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/a99f5a37-5d74-4b65-84cf-4a818c7bb190.mp4?playbackTicket=e077920e916442d5986e246146939c9c&site=vmware.mediasite.com)

[EUC9610-SPO - Optimize Storage Infrastructure for Horizon Performance](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/3b9e9aa7-9370-4154-93a3-6ebc250e4157.mp4?playbackTicket=a93347ab0103468484a5cea35e3374f3&site=vmware.mediasite.com)

[EUC7611 - User Environment Manager 9: Do It Fast, Do It Right, Do It Big!](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/465fdb6d-2db1-49c5-b21d-5761066447cc.mp4?playbackTicket=91d1e3c8ff7d4a9987bc1f68f9f8a7e4&site=vmware.mediasite.com)

[EUC8670 - Your Digital Workspace: How to Plan, How to Start](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/b451012c-7040-450f-b346-4731125316a1.mp4?playbackTicket=ef192ed4329c4ac697a6333e64e73e00&site=vmware.mediasite.com)

[EUC7453 - Horizon for Linux Technical Deep Dive](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/3e238fd9-4693-485e-b66a-c0a545377032.mp4?playbackTicket=cf1df8c008b64eb4b4fed9f01abb8d70&site=vmware.mediasite.com)

[EUC7644R - Unify Endpoint Management Across Mobile and Desktop](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/dba82114-36af-4b2a-95b8-180e151ade94.mp4?playbackTicket=336eae1b257a4b2491b4757ad2854c7b&site=vmware.mediasite.com)

[EUC8441 - End-to-End Security for End-User Computing](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/f972d8b3-6167-482f-82a9-72ea1107a807.mp4?playbackTicket=4630ffaa959545849ed50313bf7ba539&site=vmware.mediasite.com)

[EUC7856 - Solve Your Citrix Problems with VMware Technologies](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/920db7a3-ccba-44e7-87bd-12b1b93f569d.mp4?playbackTicket=e646afd915664cfa8f520d5b77d9c146&site=vmware.mediasite.com)

[EUC9992 - Ask the Experts: Practical Tips and Tricks to Help You Succeed in EUC](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/0332e1ad-b459-41e1-abf8-a25209832c01.mp4?playbackTicket=1d0b891f25004faba1e0afe1ffac2a4c&site=vmware.mediasite.com)

[EUC9922-SPO - Cisco HyperFlex Systems: Next Generation Hyperconvergence](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/9629f6e7-abb8-4e63-8d78-4405c808dd5a.mp4?playbackTicket=36cb0356480642f4bbc7001374f3e89a&site=vmware.mediasite.com)

[EUC8437 - Workspace ONE’s Secure App Token System (SATS) for Mobile Single Sign-On explained](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/aa848ed6-6904-404f-8cac-3350767eceba.mp4?playbackTicket=43358d1b3abf4c1280d588e95bdcbe0e&site=vmware.mediasite.com)

[EUC8589 - Best Practices for Effectively Planning and Implementing BYOD Programs](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/ae245971-c6a5-4e2d-a4f4-4f85831e3944.mp4?playbackTicket=a0e6ab23973d45eba83a4e257bfa0e44&site=vmware.mediasite.com)

[EUC9393 - Real-time Endpoint Visibility and Control with VMware TrustPoint](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/695a0ed4-494d-40db-b04f-70337e4c5f71.mp4?playbackTicket=bca95daf8cec4c6db7b05f76fa19caf2&site=vmware.mediasite.com)

[EUC9469-SPO - Scale, Efficiency and Data Management for EUC solutions with NetApp](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/0f441738-4956-4143-a512-5303f8ae6ca0.mp4?playbackTicket=1cb780a83a6d43eb81acc81774275fc3&site=vmware.mediasite.com)

[EUC9217 - On-Premises Workloads with Cloud-Based Management: Technical Deep Dive into Horizon Air Hybrid Mode](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/09a96be4-52a3-4e8b-b03e-15b93dc25c3f.mp4?playbackTicket=b30c1b6b5021473b886597e054017bbc&site=vmware.mediasite.com)

[STO7443r - How did VMware IT Achieve a Non-Disruptive Disaster Recovery Test in 90 Minutes for 900 Terabytes of Storage and 2000 Production Virtual Machines?](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/a04b4f51-dd0c-47e4-a2e8-4f9460a7ff14.mp4?playbackTicket=df6eabc78e394d1da4614d06432121df&site=vmware.mediasite.com)

[EUC9160 - Secure Digital Workspace of the Future: Embracing the Opportunities Presented by Enterprise Mobility in Financial Services](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/758a3a0b-2c40-4ba7-8bf4-a6e35056ba08.mp4?playbackTicket=8dfd7050ec684fd3903a6adf5d281dd2&site=vmware.mediasite.com)

[EUC8160 - Discover AirWatch: Enterprise Mobility Management](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/1ce83258-307d-4813-a9a4-4a1c47fb4b78.mp4?playbackTicket=e4c5bf7793b5478db75f56367b5bc254&site=vmware.mediasite.com)

[EUC9970-SPO - 0-70 with Horizon 7](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/0fbcf7e1-009d-4ffc-914f-886253b97157.mp4?playbackTicket=ed7d478ef47d4548bece7d5c79d93461&site=vmware.mediasite.com)

[EUC8990 - CSC Hyper-Productive Digital Workplace](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/42287088-fb98-46a8-97b2-6e02f72cdf1b.mp4?playbackTicket=47dbd45d4d32409b9c1441d9170a9631&site=vmware.mediasite.com)

[EUC7601R - Advances in Remote Display Protocol Technology with VMware Blast Extreme](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/1fff7498-1519-4a87-adc9-9eda2a63eda2.mp4?playbackTicket=d3304d2969ab46e1ad6ee6a64c3ef9e8&site=vmware.mediasite.com)

[EUC8584 - vRealize Operations: The Authoritative Source for Monitoring and Reporting for Horizon and Citrix XenApp Deployments on vSphere](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/c6bdf625-2bb7-42bc-a996-9a220a87af4e.mp4?playbackTicket=a9fa821a384243948f1b55c71297858e&site=vmware.mediasite.com)

[EUC9389 - What Is VMware Workspace ONE?](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/6980f296-5b3a-48ed-b653-211d9c56ac57.mp4?playbackTicket=a684d01386714253b851c1bd94767eaa&site=vmware.mediasite.com)

[EUC7800 - Deliver a Digital Clinical Workspace: Healthcare Customer Panel](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/d5d36426-3659-4354-8c36-13a78500b914.mp4?playbackTicket=3a40a63655714cedac282978b97735b5&site=vmware.mediasite.com)

[STO7443 - How did VMware IT Achieve a Non-Disruptive Disaster Recovery Test in 90 Minutes for 900 Terabytes of Storage and 2000 Production Virtual Machines?](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/356309a5-f740-4cda-bc4d-5bec22a96d82.mp4?playbackTicket=f1d48be256b84eb2aad78baf87475ef3&site=vmware.mediasite.com)

[EUC9387 - Deployment Best Practices for VMware Identity Manager](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/2b083f40-2cf1-477a-998c-7409584245e5.mp4?playbackTicket=a72dc258a0c048abbabb238d4829effb&site=vmware.mediasite.com)

[HBC7602 - Build True Hybrid Clouds: See How Service Providers Can Use NSX to Extend Customer On-Premises Data Centers](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/38d02c53-daf4-4e0c-bcbf-b66890345119.mp4?playbackTicket=1b021c5f1c7841ac86fcbb92aad958be&site=vmware.mediasite.com)

[HBC8474 - Making It Easy to Orchestrate and Automate Your Hybrid Cloud Environment](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/799aec9e-91f7-424e-bcd3-5292e896d295.mp4?playbackTicket=d99d9566f5e847c8bb9f8f4f3770f3f8&site=vmware.mediasite.com)

[HBC8503 - Taking VDI and Published Application Environments to the Next Level with App Volumes](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/3c07d192-efa6-41cf-8625-670210ef8037.mp4?playbackTicket=59a3ce3ce0064554bc61e4b69acb7689&site=vmware.mediasite.com)

[HBC9463-SPO - Data Protection as a service for your vCloud Director environment with Veeam](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/c1d161f6-d86c-4f51-bd4b-a0ac96dd163a.mp4?playbackTicket=dc40dfea43294b369db2229c2e716ab6&site=vmware.mediasite.com)

[HBC7943 - Designing a Data Center in the Cloud: A vCloud Air Perspective](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/12653315-3309-48f4-8e56-30767992e382.mp4?playbackTicket=72685977d1104e6d85e946b4f4a30fdf&site=vmware.mediasite.com)

[HBC8226 - Why Cloud Networking and Security Matter – A Primer for Choosing Your Ideal Cloud Provider](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/7cbf7cf6-1e27-41cd-a7ef-fd2b96e4a5b0.mp4?playbackTicket=b137b6f54b1f4f309e571d2e2dd2d135&site=vmware.mediasite.com)

[HBC8312 - Maintaining Regulatory Compliance in the Hybrid Cloud](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/06d347aa-aac9-4df8-a124-4544d9888e29.mp4?playbackTicket=84e5b86b036e4fb58c4051b5ea3b54f9&site=vmware.mediasite.com)

[HBC8799 - How OVH, vCloud Air Network Service Provider, Is Using NSX to Easily Onboard Workloads to the Cloud](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/91183f3f-781d-4c55-b60e-f0f5b55468a6.mp4?playbackTicket=9be6d640248742b0a880d2f1b339adb5&site=vmware.mediasite.com)

[HBC9171 - Intercontinental vMotion with Purpose](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/a2cbb462-5e27-4897-836d-0b3f009f2d59.mp4?playbackTicket=3881d35bdc20482d88e7c45f04666fe1&site=vmware.mediasite.com)

[HBC8484 - Data Sovereignty and Compliance Automation In The Cloud](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/4b42e505-08e0-4fec-b301-da013525f163.mp4?playbackTicket=74c6bde04b164ac3a992936f6cb7a454&site=vmware.mediasite.com)

[HBC7999 - VMware Availability for VCAN: Native vSphere Replication](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/025a6455-130f-4542-b0ca-3f9f3191c798.mp4?playbackTicket=ab74290f7ac94b7ea2f3f9f252417efd&site=vmware.mediasite.com)

[HBC8504 - Have It Your Way: Hybrid Cloud Management](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/1d006204-6f3e-44fe-b6c0-01dff52f1885.mp4?playbackTicket=47e0919be2a349cb92527a6766ae302a&site=vmware.mediasite.com)

[HBC7928 - Introduction to vCloud Air Networking and Security Portfolio: A Technical Deep Dive](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/72693426-caa8-4829-888e-eac837f33266.mp4?playbackTicket=aabbe13109734deebd160ba1dc285118&site=vmware.mediasite.com)

[MGT8084 - Hybrid Cloud Case study: City of New York Self-Provisioning Gateway 2.1](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/ed5da4fe-d8f5-4fd6-a5fa-923c04db8c4a.mp4?playbackTicket=e7df0e5336e34eb4a73d101d95acdd8b&site=vmware.mediasite.com)

[HBC8491 - Deep Dive: VMware on IBM Cloud Validated Design](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/2d098a0a-d6b4-43f1-b95f-e9011497d904.mp4?playbackTicket=a0be99aecbb64ad4a430769674854527&site=vmware.mediasite.com)

[HBC9453-SPO - Achieving New Levels of Cloud Efficiency over vSphere based Hyper-Converged Infrastructure](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/a59122b8-3952-4ee1-81a9-781184008646.mp4?playbackTicket=2058a803d49846259dc558bff2358a9b&site=vmware.mediasite.com)

[HBC7954 - Implementing Hybrid Cloud with VMware vCloud Air and NSX: A Closer Look](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/ebef739a-a48c-4c29-829e-08943179e525.mp4?playbackTicket=3a1322cceb9f46319387b9465b2453b1&site=vmware.mediasite.com)

[HBC9185 - How to Connect Your On-Premises Data Center to the Cloud](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/f6ee960d-55a7-4f01-8e70-0154aa64975f.mp4?playbackTicket=358b9deffbe14a0588deb5f5594b9730&site=vmware.mediasite.com)

[HBC8861 - Getting the Most Out of Your Hybrid Cloud Service Provider](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/8bb37f93-6ecb-4c56-b4ac-fd8ef1217b15.mp4?playbackTicket=d5a11e96b28143e99dcfc77cb43147a9&site=vmware.mediasite.com)

[HBC7830 - Virtualize, Secure, and Extend Your Data Center to the Cloud Using NSX: A Perspective for Service Providers and End Users](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/96ab1fa7-4fb1-432c-a333-6077482f653d.mp4?playbackTicket=f798e14e495a44419bcbdd906fafc751&site=vmware.mediasite.com)

[HBC7700 - Disaster Recovery in the Cloud with VMware vCloud Availability](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/75a2ecce-4bd4-4090-957f-be6fb1037bf7.mp4?playbackTicket=0028de5c8b9340cba29d94c69e92efcb&site=vmware.mediasite.com)

[HBC9949-SPO - Hybrid Cloud: Automated and validated VMware deployments on IBM Cloud](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/4797fd28-6cbe-4ba0-8f2f-04d837ff4a45.mp4?playbackTicket=1bf66f00ed2a4edc9f79012b03f28d71&site=vmware.mediasite.com)

[HBC9611-SPO - OnApp: your hybrid cloud delivered](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/0d345739-6ad9-46b1-a9c2-596f1935def3.mp4?playbackTicket=bddf446e47624882a76f51ab167c207f&site=vmware.mediasite.com)

[HBC8046-QT - Customer Onboarding with VMware NSX L2VPN Service for VMware vCloud Air Network](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/d632a06b-7662-4524-845f-4350274c1778.mp4?playbackTicket=772b02892f534058aa45e72ac4cdde6d&site=vmware.mediasite.com)

[HBC7661-QT - Generate Revenue with vSphere Optimization Assessment (VOA) for Service Providers](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/d2d85af5-7f02-408e-8222-f9ae4e5a46c6.mp4?playbackTicket=82275e417b384778b8e1eee686c09fef&site=vmware.mediasite.com)

[HBC8915 - SLED and Cloud: Is Cost Containment the Right Question?  Yes and No](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/79227b2a-7fd1-4bcc-80e7-b5879832f0d7.mp4?playbackTicket=c7955c432a274a4fbe46e0e6569bc4a5&site=vmware.mediasite.com)

[HBC8298 - Designing a Business Continuity Solution in the Cloud](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/9a1188a2-d2f0-4d36-b18b-52870eb5d4e5.mp4?playbackTicket=246198b145b6410f9498e55995f1cb66&site=vmware.mediasite.com)

[HBC7948 - Extending Your Data Center to vCloud Air in Less than 60 Minutes](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/a4ca518f-da7f-4103-a0c7-5efcfcd619b4.mp4?playbackTicket=a1310a72ffb14115ace48173bb5de42f&site=vmware.mediasite.com)

[HBC9111 - vRealize Operations and vCloud Air: Monitoring Your Cloud](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/f8c7643e-51a5-4c95-901f-00f21ef427df.mp4?playbackTicket=e6e07efe6fec427398041bffd36908d3&site=vmware.mediasite.com)

[HBC8805 - Extend Your Data Center to the Cloud: A Real-World Example](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/7106079c-72a7-4bc4-a587-b90f6651198a.mp4?playbackTicket=7b87dd2e41064f8781357a5da409b585&site=vmware.mediasite.com)

[HBC10827-SPO - Ensure Success of Hybrid Cloud with Amazon Web Services](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/a749a3ab-4c94-4f7b-abcb-f160de2023d2.mp4?playbackTicket=54cd8d6dbc274ed8939f286fd744a0ca&site=vmware.mediasite.com)

[HBC8295 - The VMware Journey to Cloud with vCloud Air](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/f9598f6b-9b50-4f5a-a4bb-ac2c5ed72d08.mp4?playbackTicket=726476cb3da34fd1939d6cafcd19e6d1&site=vmware.mediasite.com)

[HBC9401 - Whats New with vCloud Air](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/f53efd07-a26c-472d-bed0-ba09e4183c97.mp4?playbackTicket=7569e9e6262c4b23af719c2b4bec406d&site=vmware.mediasite.com)

[HBC9092 - vCloud Air: Advanced Networking Concepts](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/3a1f6d3d-9236-47fc-afd3-fdc163ece69a.mp4?playbackTicket=d9f345860695456f99e490663b959acf&site=vmware.mediasite.com)

[HBC9065 - Better Together: vRealize Automation and vCloud Air](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/5ce767de-b2df-44ab-bf07-1df96e80670e.mp4?playbackTicket=c022070b1a6f42cb811595d898d2bfb0&site=vmware.mediasite.com)

[HBC8292 - vCloud Air Recovery as a Service (RaaS) Deep Dive](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/75913957-404b-4b52-a877-1a224fac9ed4.mp4?playbackTicket=292d7612e85341579aff85a3c519cbb0&site=vmware.mediasite.com)

[HBC8617 - Seamless Security and Compliance in a Hybrid Cloud Architecture](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/4668f565-aa7c-4d04-9219-fa3f2011ea13.mp4?playbackTicket=e1906260a2e74aad98542f9bb4e7c01f&site=vmware.mediasite.com)

[HBC8563 - VMs and Containers: Extending Docker to vCloud Air](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/153f03e4-85b8-4164-b07b-577694bb4a5b.mp4?playbackTicket=6ab3ab0286dd424aa7c6d79132f77452&site=vmware.mediasite.com)

[MGT8767 - How Zebra IT transformed to become a cloud broker running global virtual infrastructure in multiple public and private clouds](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/0d2ddac4-f879-46f4-bc9f-0c90928be87f.mp4?playbackTicket=4ae8e120ab8441baa280d8fd104493eb&site=vmware.mediasite.com)

[HBC9164 - Modernizing Healthcare IT with the Public Cloud, Your Way!](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/aa5252bd-f68e-479d-ba82-511a81ad36c2.mp4?playbackTicket=7b82dd36660e44939adbe6815045194b&site=vmware.mediasite.com)

[HBC8952 - vCloud Air Design Patterns for Design, Implementation, and Operations](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/0d6a0dad-c682-4206-b611-ecd00d37e0ed.mp4?playbackTicket=2e9942aca491427c9788616cff48e4a5&site=vmware.mediasite.com)

[HBC7646 - St. John's University Leverages vCloud Air Disaster Recovery for Its Critical ERP System, Banner](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/9931795e-75c4-4278-844a-4e81e1589523.mp4?playbackTicket=7ec7ce717c434d5dbcd94e6ac9c2d79d&site=vmware.mediasite.com)

[STO8164 - Benchmarking VAIO-Integrated Caching. Is it Really Faster? How Much, and Why?](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/946b3b60-7277-4823-8a43-8e657619c1e2.mp4?playbackTicket=1d6e4bd119fe485a81a5af0da8423a02&site=vmware.mediasite.com)

[STO7973 - Architecting Site Recovery Manager to Meet Your Recovery Goals](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/145853e6-414b-40d3-9064-3c6258b2c562.mp4?playbackTicket=b9710667eccd4af0a87d6c1e930eb1f4&site=vmware.mediasite.com)

[STO8422 - Virtual Volumes: Why?](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/c7322870-0548-49d7-8898-70fa369c71dd.mp4?playbackTicket=2ec1cde1e80b46459ae185aa2b4bebd7&site=vmware.mediasite.com)

[STO7848 - Virtual SAN Storage Efficiency Technologies](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/51d8e968-a14a-4fd6-9a70-78eea373aa51.mp4?playbackTicket=c44ac6f4047c4792a28622861bfc8a32&site=vmware.mediasite.com)

[STO7549 - Achieving Agility, Flexibility , Scalability and Performance with VMware Software Defined Storage (SDS) and Virtual Volumes for Business critical databases](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/5d219294-dd04-4027-b8d3-e1d97bc4c07f.mp4?playbackTicket=0ff3c98e1b14466781ec9ef7137088d8&site=vmware.mediasite.com)

[STO8246R - Virtual SAN Technical Deep Dive and What’s New](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/6bc53227-80fd-40bf-9fa2-72f6dec72e4a.mp4?playbackTicket=d86bbd45ece540129bb1f9a17cacefbc&site=vmware.mediasite.com)

[STO8619 - Transitioning to VVols: Partner Panel](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/3bbc94f5-0e4d-4eb1-b446-22846fc5fd8d.mp4?playbackTicket=3d1ddacf682d4f5fb320917c85a18e02&site=vmware.mediasite.com)

[STO9925 - Enterprise-grade data protection for Virtual SAN with EMC Recoverpoint for VMs](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/cd4506da-6b6d-4fda-ac49-d32df4784c4d.mp4?playbackTicket=1ad5f7337de6479bbad43da663166e4b&site=vmware.mediasite.com)

[STO7903 - An Industry Roadmap: From storage to data management](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/d39a396e-cc32-4821-ba43-67ccd49d41bc.mp4?playbackTicket=259cbb81fa5b4d2bbea4085340e8e4d5&site=vmware.mediasite.com)

[STO9014 - Deploying HCI at datacenter scale](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/02d2d30f-5cfa-41a3-a59b-a339bf394a61.mp4?playbackTicket=de52ad1f5f2c44f3b53a060de22aa2de&site=vmware.mediasite.com)

[STO9157R - Achieving Unprecedented Availability, Security, & Cost Savings with VMware Virtual SAN and NSX](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/ffbe6fc0-a23d-434d-90f7-2c569a28943e.mp4?playbackTicket=d0f89466277d405bb0dc95835f33bad8&site=vmware.mediasite.com)

[STO8880 - Successful ROBO Design with vSphere & Virtual SAN](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/7fd88b7f-ac04-4d07-acd3-9729fc7e6182.mp4?playbackTicket=08329b36a4614692856832f26e2127b2&site=vmware.mediasite.com)

[STO8562 - Deployable and Tactical Hyper-Converged Software (HCS) for the Battlefield](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/7dca7dbc-89a1-495b-a2be-d76e6620f8c1.mp4?playbackTicket=2c6891221fe04b4d8348c07ba583eb03&site=vmware.mediasite.com)

[STO8795 - Ushering in a New Era of Hyperconverged Big Data - Hadoop over VSAN](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/c9068a08-c05b-4ad7-81eb-c44b2b26bbf2.mp4?playbackTicket=fc8ba667216749768de300dcab70b10d&site=vmware.mediasite.com)

[STO8750 - Troubleshooting Virtual SAN 6.2: Tips & Tricks for the Real World](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/95b66ec6-541c-4fab-a042-61481853b9cd.mp4?playbackTicket=03b6e6c6781b4488a13529ca478d89f3&site=vmware.mediasite.com)

[STO8718-SPO - Building Next-Gen Data Protection for VMware Environments with Rubrik](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/87aa3401-c537-46b4-934c-5e4c098e5b1c.mp4?playbackTicket=2b45ae9d7a2747f08cfc4696ebc53cfa&site=vmware.mediasite.com)

[STO9423 - File Services on Virtual SAN](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/55454cf3-9e48-47a2-a9a3-2f10341456f6.mp4?playbackTicket=9aefd024a8eb4f719d97a5d25bf1d5af&site=vmware.mediasite.com)

[STO8246R - Virtual SAN Technical Deep Dive and What’s New](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/f2db2653-853b-47eb-9953-57f83aec95ae.mp4?playbackTicket=4370e076a35d400cbe35d3b389a50a85&site=vmware.mediasite.com)

[STO9981-SPO - The Irrational Data Growth Problem at Scale: How do I make the leap from data to information and gain insight?](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/d4053a63-f439-4537-b1ef-7073e794bf89.mp4?playbackTicket=0f2a32ecae8b4dcbb42e2b621d54c0bd&site=vmware.mediasite.com)

[STO8699 - Building a Business Case for VMware Hyper-Converged Software with Virtual SAN](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/b73c509d-4ed1-44d8-9c09-c2deef21b7ba.mp4?playbackTicket=feaac8c9e6094277a069faa2d0d96206&site=vmware.mediasite.com)

[STO8204 - Cohesity & VMware: Simplifying data protection for Vsphere and Virtual SAN](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/2f498060-c1c2-485c-9ec5-b606dc5c8ae1.mp4?playbackTicket=02134bffab6f4ce981c4623d88c3cca2&site=vmware.mediasite.com)

[STO7645r - Virtual Volumes Technical Deep Dive](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/9aef4a6b-ab4a-414f-abfd-784e217e73e9.mp4?playbackTicket=37e574059af04ace865821d6227fe941&site=vmware.mediasite.com)

[STO9157R - Achieving Unprecedented Availability, Security, & Cost Savings with VMware Virtual SAN and NSX](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/84b62518-6e36-4c1f-b353-15e795338039.mp4?playbackTicket=459e6761e874465492517f7be592ba4f&site=vmware.mediasite.com)

[STO7791-SPO - Insights to success: Capitalizing on the software-defined data center with the right management and storage](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/a0db9b50-7680-4818-bf9c-2bdd5a94619c.mp4?playbackTicket=e71cd968fd564242b82bfdd7c23022b0&site=vmware.mediasite.com)

[STO8344 - SRM with vRA 7: Automating Disaster Recovery Operations](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/e51b5f6e-6dc8-44d8-b67d-5ad975ecb652.mp4?playbackTicket=80a1c5cad89e41438536bf28d4c7eb67&site=vmware.mediasite.com)

[STO8159 - Snapshots Suck: How VSAN and VVol fix all your operational nightmares](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/617fe527-34bc-43e8-91bd-2dbba4ed701b.mp4?playbackTicket=6c918e2811fd43c2815da205d2b48b4e&site=vmware.mediasite.com)

[STO9969-SPO - How Did Designer Shoe Warehouse Lace up Success With Flash-Optimized Storage From INFINIDAT?](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/0c14365f-1922-4589-974a-62c23ea6fb38.mp4?playbackTicket=8934d622f69a47c7add84681f25ff5fe&site=vmware.mediasite.com)

[STO7831 - Storage for Cloud Native Applications](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/3a7c36a0-bfed-43a7-a2ab-9f9c6dec42a1.mp4?playbackTicket=945808624a2a40ba9fb9e880adba2106&site=vmware.mediasite.com)

[STO9422 - Essential Virtual SAN Management](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/404c7a76-5b45-4133-b851-438c9926afa9.mp4?playbackTicket=e87b2ae5f79a4a21a2496b5f58198192&site=vmware.mediasite.com)

[STO9449-SPO - Journey to the SDDC: The Who, What, Why and Oh No of Moving to a Modern Data Center Platform](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/abbe1b58-7dcf-46c7-a5b9-3742bb96f635.mp4?playbackTicket=c58e8633ae414297ac9c07c25802dd3d&site=vmware.mediasite.com)

[STO7965 - VMware Site Recovery Manager: Technical Walkthrough and Best Practices](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/817de0e2-acb3-4bdf-bd12-0108388bca94.mp4?playbackTicket=86fcf5c72b004ffd916d739ca4cb4d43&site=vmware.mediasite.com)

[STO7535 - Conducting a Successful Virtual SAN 6.2 Proof of Concept](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/c65a5a6b-2419-41cd-8a3f-496bdb9e15d9.mp4?playbackTicket=94dbc1bda4b8489bbf7dbcc2cd282e9a&site=vmware.mediasite.com)

[STO9079 - Virtual SAN for VMware Service Providers](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/d0cd2969-d32f-4035-abc8-c53743c95145.mp4?playbackTicket=919201f7a1dd48d698e846a731c5cc2f&site=vmware.mediasite.com)

[STO10801-SPO - Modernizing with Private and Hybrid Cloud: How CSC & VMware move enterprise clients to next-generation infrastructures](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/27af5e3c-a248-42e5-82cd-a273d89782d3.mp4?playbackTicket=6700dc25fec041e49f20c5e070d6022b&site=vmware.mediasite.com)

[STO7904 - Virtual SAN Management Current & Future](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/3feebb4d-de31-40c9-8d97-42bde26aacfd.mp4?playbackTicket=d3841be4444745aa9c64fc201f847816&site=vmware.mediasite.com)

[STO8165R - VSAN Networking Deep Dive and Best Practices](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/fa572d71-aa51-4b77-a402-0c3f7de77cdd.mp4?playbackTicket=7f17f883ff834e66adf856a5b4609e9d&site=vmware.mediasite.com)

[STO8694 - High-Speed Heroics: Array-based Replication and Recovery for VMware Virtual Volumes](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/7c7abe95-e28b-48d4-8a41-d94e53ad738b.mp4?playbackTicket=f78a339503c945afaf3eaa42da991b3f&site=vmware.mediasite.com)

[STO8923 - PowerShelling Storage to the extreme](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/10b3cc7e-cfe1-427a-a39e-ea368f3e6b99.mp4?playbackTicket=a2cad37966ec4092b4573230abaa7d9e&site=vmware.mediasite.com)

[STO8179R - Understanding the Availability Features of Virtual SAN](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/e6bb9492-8265-4a30-8b9e-e8c7179c5380.mp4?playbackTicket=6381cde541284939b02033d2e9977e6e&site=vmware.mediasite.com)

[STO7802 - Simplifying Disaster Recovery in 2016 using VSAN, NSX and SRM](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/8cd391ca-2d58-47b6-bf48-6c0aba6ca278.mp4?playbackTicket=51415f050db8450aa80b65eda66b9c15&site=vmware.mediasite.com)

[STO8144 - VMware vSphere Virtual Volumes in a NetApp Environment](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/c709554e-e853-45f6-a587-868b0cae18c5.mp4?playbackTicket=a2cba49a8c8347cabd7f48885b47b5cc&site=vmware.mediasite.com)

[STO8689 - Virtual SAN Primer and What?s New](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/c5e87fd7-fcdc-4849-8a95-50218ef2e2f1.mp4?playbackTicket=1325a54031ef41c5b58ece0c38a665b6&site=vmware.mediasite.com)

[STO7650 - Software-Defined Storage at VMware Primer](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/ff8fe8c5-04c7-4929-a042-76938a923ae5.mp4?playbackTicket=9f9097beb18f427eb78804ab899a698c&site=vmware.mediasite.com)

[STO8279 - Deploying Virtual SAN with VMware Private Cloud](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/d7c8cb0b-a057-4cab-8e3d-ce105b8c7c5a.mp4?playbackTicket=9251dff3494c4017a510dd55a28da3f8&site=vmware.mediasite.com)

[STO7552r - Architecting High Availability and Workload Balancing for Tier 1 Mission Critical workloads using VMware Software Defined Storage and Extended Oracle RAC](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/4bb00508-f028-4529-8d7a-1dca8a59a57a.mp4?playbackTicket=514bce1da1ed465ea525273b1a8ea233&site=vmware.mediasite.com)

[STO8840 - Deploy Scalable Private Cloud with vSphere Virtual Volumes](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/4866bb37-d7a1-425a-b4c0-e91e38953280.mp4?playbackTicket=26ead8b3226d43e28b695403d37e7020&site=vmware.mediasite.com)

[STO7557 - Successful Virtual SAN 6 Stretched Clusters](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/cac28377-f056-43e3-8e55-269a901c428f.mp4?playbackTicket=268c96d7ae6844c688d447e8f694faaa&site=vmware.mediasite.com)

[STO7953 - The Future is Here:  Turbocharge All Flash Virtual SAN with Next Generation Hardware](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/81287ef0-2e1b-4129-bc3d-5de1d9edf72a.mp4?playbackTicket=1404c5d68a1d483aba5c469ae462b442&site=vmware.mediasite.com)

[STO8179R - Understanding the Availability Features of Virtual SAN](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/ca6f06cd-41c0-4d87-af99-4b825c5d54d9.mp4?playbackTicket=4dc4ff1ad62b4588a073c27998bd216e&site=vmware.mediasite.com)

[STO9058 - Evolution of VMware Virtual SAN](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/67b74fb0-c717-4502-ab2d-844253ca0639.mp4?playbackTicket=479bfd13a8b44c7d8065b21d18b330cb&site=vmware.mediasite.com)

[STO7534 - Virtual SAN - Day 2 Operations](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/f760bfc2-3bf7-43be-9392-f9b4cd4b70a3.mp4?playbackTicket=043145f2a2dc4666bdd48965e31129eb&site=vmware.mediasite.com)

[STO9607-SPO - Running Business Critical Applications and the Software Defined Data Center on Hyper-Converged Infrastructure at the Speed of Flash](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/9229c783-b259-47fc-90e9-589761e12cd4.mp4?playbackTicket=08b2458cdf0e4f90834c81b1f7a602ae&site=vmware.mediasite.com)

[STO7902 - VMware Virtual SAN: Enterprise-Grade Storage For Hyper-Converged Infrastructures](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/2fd3564e-d721-4a9a-9906-807fd296097d.mp4?playbackTicket=e80910f0f68149c6add3449c4676d6f5&site=vmware.mediasite.com)

[STO7875 - A Day in the Life of a VSAN I/O](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/e04d9a51-2380-4ed0-af3e-54857741cfd1.mp4?playbackTicket=2f8864c028ae49d0bc74ca1c5c4a76d0&site=vmware.mediasite.com)

[STO8904 - Hardware Choices in the Software Defined World – Tips on Choosing Hardware for Virtual SAN Deployment](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/9f297417-ea36-49c4-a00d-e64e946c22dd.mp4?playbackTicket=7b5f68e118ba494cbe445c7792e0d3f4&site=vmware.mediasite.com)

[STO9614-SPO - You have an all-flash Virtual SAN - what's next?](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/7a94fdf7-79a3-4b0f-974d-d0e2bac674a2.mp4?playbackTicket=eaf590d6e6d04a27880710d09413563e&site=vmware.mediasite.com)

[STO9054 - VVol and Storage Policy-Based Management ? Is It Everything They Said It Would Be?](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/4d7ec3ff-fe19-4773-a6c6-293a09d3b7e0.mp4?playbackTicket=0bbb84f7c711424685f1ddf541fe88dd&site=vmware.mediasite.com)

[STO7755 - Storage for Virtual Environments - What's new and What's next for vSphere Storage](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/bca09538-0b41-47c3-9e34-9b9b4f4ec6cf.mp4?playbackTicket=fe4545746c994b99a01a95fe2c25818b&site=vmware.mediasite.com)

[STO8568 - Virtual SAN with just 2 Failure Domains](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/cceb944d-d62c-4868-9705-4a60d8e0e718.mp4?playbackTicket=2a488d4a6edf4e5283e07153b131eafc&site=vmware.mediasite.com)

[STO8743 - Extreme Performance Series: Virtual SAN Performance Troubeshooting](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/0e19ef18-865b-4eba-bd76-d5aae334b7c0.mp4?playbackTicket=c27bb55a0f1742598691029b9f331b7d&site=vmware.mediasite.com)

[STO9967-SPO - Rethinking Data Protection:  The Rise of Hyperconverged Infrastructure and Built-in Backup and Disaster Recovery](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/9fcc4072-3062-4ca9-86f8-3002c6f9e568.mp4?playbackTicket=44a5410900744e99b27a3b370eadbbe8&site=vmware.mediasite.com)

[STO9396-SPO - Real World Guidance for Implementing VMware Virtual SAN from Ready Nodes to Build Your Own](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/f340d793-566e-494e-a74e-2dc27c0ac97b.mp4?playbackTicket=68374c46d5c74f28b673dc9aa728167c&site=vmware.mediasite.com)

[STO8165R - VSAN Networking Deep Dive and Best Practices](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/29ff33bf-9d87-41db-87a4-1727893b65d3.mp4?playbackTicket=4f55ae77b7f74692bfab212760078498&site=vmware.mediasite.com)

[STO7977 - SRM with NSX: Simplifying Disaster Recovery Operations & Reducing RTO](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/e500d561-47df-46ec-bed3-4cc833eb23ba.mp4?playbackTicket=8d6c8bed0504446f933c163f8f5a0d90&site=vmware.mediasite.com)

[STO7552 - Architecting High Availability and Workload Balancing for Tier 1 Mission Critical workloads using VMware Software Defined Storage and Extended Oracle RAC](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/9f2e5ecb-df45-4088-95df-2346c6737be2.mp4?playbackTicket=fb4836869fb34f1a9394233d5f62546f&site=vmware.mediasite.com)

[STO8488 - Hyperconvergence Panel Discussion: Exploring the ?Reality? of Hyper-Converged Infrastructure and Virtual SAN](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/0808114d-638e-4a5b-a77a-b090539d58cb.mp4?playbackTicket=3d91e9c78edc4f0f995cc512d8899e6e&site=vmware.mediasite.com)

[STO7914 - Revamped vSphere Storage DRS and SIOC for automating the Data Centers](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/0c379cbf-2658-498d-aca2-4c747d200731.mp4?playbackTicket=b45f3a28b13543d28f3c655712040338&site=vmware.mediasite.com)

[HBC10704-QT - Backups to the cloud - Leverage the cloud for Business Continuity](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/0d373172-3f12-4322-ad14-453619b57d9c.mp4?playbackTicket=37c9fe57b2cf41ae948781cef6371fd7&site=vmware.mediasite.com)

[STO9988-QT - Running Epic with VSAN – Modern Architecture for Healthcare](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/5bf7cd9b-79aa-41e1-88c3-23c20319fd94.mp4?playbackTicket=61a30c567bbb4f6ba2fb4759772ebbca&site=vmware.mediasite.com)

[STO9987-QT - Hardware Procurement Guide for Virtual SAN](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/f6be281a-a26c-4e6d-a6ed-10ca4905a4b4.mp4?playbackTicket=fbf8f7f5c66445bda4c65be3231b076c&site=vmware.mediasite.com)

[HBC10703-QT - Top Tips for Moving to the Cloud](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/753561a7-293f-4b03-937e-62d8fef159a3.mp4?playbackTicket=c32b2270f4a34916a755174608f52313&site=vmware.mediasite.com)

[STO9977-QT - 5 Tips for Getting The Most From Virtual Volumes and vSphere Storage Policy-Based Management](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/e06cf55d-e91f-4afc-8e5d-ca3b6c1acf83.mp4?playbackTicket=c779304ce6e5495eae56885775ac2c8b&site=vmware.mediasite.com)

[INF9991-QT - vSphere Web Client Plug-in Certification Program](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/1af38b2f-cf0d-45c4-8d59-a440142856a5.mp4?playbackTicket=087fb77a757c43c6a6eff49100416bf3&site=vmware.mediasite.com)

[STO8267 - Hours to Minutes: Automated Provisioning and Deployment Using PowerCLI, vRealize Automation and vRealize Orchestrator](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/698493fe-181f-4997-b23d-87b3cf22cae2.mp4?playbackTicket=2795fdb71ebe42bdb4da7dfc1c001f1f&site=vmware.mediasite.com)

[INF9047 - Managing vSphere 6.0 Deployments and Upgrades](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/b4060695-2e20-4abe-a638-a97a2fffebfb.mp4?playbackTicket=2fa56c8ed5d04f3bb547350e4d7a968f&site=vmware.mediasite.com)

[INF8225 - The vCenter Server and Platform Services Controller Guide to the Galaxy](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/3fc56ead-c735-436b-9f49-de699335b666.mp4?playbackTicket=244b6e8412274704846d3d86d1abe40b&site=vmware.mediasite.com)

[INF9044 - Journey to the vCenter Server Appliance: A Migration Story](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/ececaec3-6872-4066-b5fa-8d701dfb11de.mp4?playbackTicket=fc6ced2e77bb43a1aef269d08824a076&site=vmware.mediasite.com)

[MGT7924 - vRealize Operations Capacity Explained](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/8df89b89-613d-4ecf-b105-0f5548b4995c.mp4?playbackTicket=de9b60d15d314bc3b8620d54b44540f7&site=vmware.mediasite.com)

[CTO9943 - VMware Chief Technology Officer Panel - Trends and Futures](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/089b2b2c-abb9-4b89-802f-1ae5feafbed5.mp4?playbackTicket=a8c8db5fb0fd45cea66b8d3adba7c903&site=vmware.mediasite.com)

[CTO7516 - Ask the Experts - Titans of Tech](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/5a6e8319-01e7-4e34-b2fa-8fdfcab5a9f3.mp4?playbackTicket=be6cf3720ca6410b9d4d93971b9dd7f1&site=vmware.mediasite.com)

[INF7827 - vSphere DRS Deep Dive: Understanding the Best Practices, Advanced Concepts, and Future Direction of DRS](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/9e665824-de61-4007-80c0-6752f6e1f626.mp4?playbackTicket=bba75249951546c88b7bbd5e1bca866d&site=vmware.mediasite.com)

[SDDC8468 - A Beginner's Guide to the Software-Defined Data Center](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/d00dc0a3-1dbf-4ae5-8b5e-d0e64645fadb.mp4?playbackTicket=435d11dd97a04da98da2cc324cac82c9&site=vmware.mediasite.com)

[EUC8203 - Beyond the Marketing: Horizon Instant Clones Deep Dive](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/9b6f6f52-5dfa-4fa3-8dc8-f6d51e98f586.mp4?playbackTicket=62731bf348754cf8855953afcb536bff&site=vmware.mediasite.com)

[INF8755R - Troubleshooting vSphere 6: Tips and Tricks for the Real World](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/f91f2373-4041-464f-a6d3-c8e5fd14be8f.mp4?playbackTicket=af8753825ed549dfb71109677d00f12b&site=vmware.mediasite.com)

[INF8089 - Extreme Performance Series: vSphere Compute and Memory](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/7ecb27d4-9fe7-44b6-9bc2-8b96206693fb.mp4?playbackTicket=41d26c88f5f44a2a8e311bc6901297c0&site=vmware.mediasite.com)

[CNA7522 - Containers for the vSphere Admin](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/a30fe5bb-d60b-4f33-bd10-3defe6afda99.mp4?playbackTicket=d1b2f21a0dc44caabdd0cab9b36a12d1&site=vmware.mediasite.com)

[INF8430 - vSphere 6.x Host Resource Deep Dive](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/1eb2cc67-845c-4e0f-a99b-a48e2838c638.mp4?playbackTicket=64c78bf4511547a685010d05faaa9157&site=vmware.mediasite.com)

[EUC8243R - Troubleshooting 101 for Horizon](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/a1effcaa-ae5e-481f-9d06-58d29be1928d.mp4?playbackTicket=0b9c5502ed0c48b19beb60857ba3a273&site=vmware.mediasite.com)

[SDDC9461-SPO - Veeam Availability Suite 9.5 Deep Dive](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/def6d256-6f54-48b2-a316-f2a0f299c085.mp4?playbackTicket=4765a4abc82345df9a380ab91ed1bfc0&site=vmware.mediasite.com)

[NET7907 - Advanced Network Services with NSX](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/43d2278c-15ff-43a4-8b17-6d6051eb449a.mp4?playbackTicket=5f40c91c23614d719fd6ed8ba4d5c9bf&site=vmware.mediasite.com)

[NET8364R - How to Deploy VMware NSX with Cisco Infrastructure](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/61104286-525e-4c3a-bb62-05b0e4adcf09.mp4?playbackTicket=12d5e2e014eb43bb8d262c574c14361d&site=vmware.mediasite.com)

[INF8092 - The Power Hour: Deep Dive, DevOps, and New Features of PowerCLI](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/4022bd26-efd7-4db0-a63e-9d62dfd006f8.mp4?playbackTicket=219fc964d49d46fc85eadd06285fc30d&site=vmware.mediasite.com)

[STO9617-SPO - Containers & VVols - a technical deep dive on new technologies that revolutionize storage for vSphere](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/5b3b9ade-a3c6-4714-9186-a573d8523b7b.mp4?playbackTicket=8bc4e0bfec704fae932729e243f86e06&site=vmware.mediasite.com)

[VIRT8290R - Monster VMs (Database Virtualization) Doing IT Right](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/23e6a4d1-84d5-488a-ad38-b86ebf82b5c9.mp4?playbackTicket=af09c7eeeb964babbf128f4d47e09f73&site=vmware.mediasite.com)

[EUC8404 - What's New with Horizon 7](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/a23fe748-0d10-43c4-aa4e-32a754dd94a6.mp4?playbackTicket=4da7645367bf403b98a2ad4f532c6e0f&site=vmware.mediasite.com)

[MGT7718 - The KISS of vRealize Operations!](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/57b0df04-2a8f-4d72-b468-1f553af4a721.mp4?playbackTicket=437d0d13d90f4bd98243ae636290e468&site=vmware.mediasite.com)

[VIRT7621 - Virtualize Active Directory, the Right Way!](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/06fefe16-b378-4167-9022-ea6d1d0c7f64.mp4?playbackTicket=4bc83d64876e496bbef365aa463d6ac2&site=vmware.mediasite.com)

[NET9989-S - NSX - The Network Bridge to the Multi-cloud Future](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/ce36b8bc-f2ef-405c-b575-266e141a413a.mp4?playbackTicket=ae04c12f02574ec6bb4743175f69f048&site=vmware.mediasite.com)

[INF8036 - Enforcing a vSphere Cluster Design with PowerCLI Automation](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/6ba959a6-9220-4524-b886-4a48df46d36d.mp4?playbackTicket=80710c840305457cbf7ccd25a9d0a7e0&site=vmware.mediasite.com)

[INF9083 - Ask the vCenter Server Experts Panel](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/cfecf036-2439-43e9-962e-837f194aea55.mp4?playbackTicket=dc89d8a9cc3f4f8b99ac567acf655c59&site=vmware.mediasite.com)

[STO7645 - Virtual Volumes Technical Deep Dive](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/abe4594f-f57d-4939-9fcf-10b1d0b81683.mp4?playbackTicket=7926113ebc454aca8144ecb8f28f3815&site=vmware.mediasite.com)

[INF8038 - Getting Started with PowerShell and PowerCLI for Your VMware Environment](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/6c26b53f-53b8-45d5-8215-395edf199814.mp4?playbackTicket=c6758a3c6d1641989baae93eee945599&site=vmware.mediasite.com)

[STO9424-S - Taking HCI Mainstream](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/192fe167-453f-4961-b241-df10a01f9202.mp4?playbackTicket=d955147c0b274776a34ba15e5a38e80e&site=vmware.mediasite.com)

[EUC7601 - Advances in Remote Display Protocol Technology with VMware Blast Extreme](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/c6dbb3b5-ff86-4071-b6f6-2796cee9af27.mp4?playbackTicket=b9766099718a4329adb900f2b1fb3713&site=vmware.mediasite.com)

[NET9094 - Customer Case Study on American Tire Distributor (ATD): Migrating to the Software-Defined Data Center with Arista Networks and VMware NSX](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/bc209b25-f681-4f21-92ce-2f4e70f2b23f.mp4?playbackTicket=ce4a4549a14a4020ab294fc762be2877&site=vmware.mediasite.com)

[NET9069 - Automating Traffic Visibility for the Software-Defined Data Center](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/c2ff1815-4b3d-4547-a8dc-6995a89605c6.mp4?playbackTicket=860e7f7cd4cd497391ec7a83f69416d0&site=vmware.mediasite.com)

[SEC8081 - Healthcare: The Security Awakens](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/e2ad5f1a-0538-4caa-89b2-77e5e6c3b915.mp4?playbackTicket=78fc0880d39a40049b3aa9f93f87e6a6&site=vmware.mediasite.com)

[SEC8667 - Deep Dive into Real-Life Data-Center Breaches and How They Could Have Been Avoided](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/f5d438ba-393a-42a9-bc1c-068778d3f801.mp4?playbackTicket=68d5c90e3e5743fcb141ba816d86cdee&site=vmware.mediasite.com)

[NET8832 - The Role of VIO and NSX in Virtualizing the Telecoms Infrastructure](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/96f95edc-f786-4735-9f08-b496b9da41b6.mp4?playbackTicket=65ee7ac7df014cce92215f8786f5ed62&site=vmware.mediasite.com)

[NET8189 - VMware NSX and Pivotal Cloud Foundry](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/c53b02ad-491a-4410-a4da-c4b8bf85e72b.mp4?playbackTicket=f591219d53c74d3ebb85c90cee8b3222&site=vmware.mediasite.com)

[NET8194 - How VMware IT Implemented Microsegmentation and Deployed a Large-Scale Private Cloud Using NSX](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/eb172374-d40c-45ad-bf73-338bf6c8ad29.mp4?playbackTicket=a9946ea4636e4fa8ad4abbde33e8e6f7&site=vmware.mediasite.com)

[NET8131R - NSX for vSphere Logical Routing Deep Dive](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/85057bc4-c329-4d80-9999-647a30321478.mp4?playbackTicket=cee1f147cd8746d1b49518236791f306&site=vmware.mediasite.com)

[NET7861R - Multisite Networking and Security with Cross-vCenter NSX: Part 2](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/7c1e5950-7fc5-4b87-ba2e-8434c024c294.mp4?playbackTicket=a00e2b69c1474825ac4eccb46dba3087&site=vmware.mediasite.com)

[NET8758 - vSphere Distributed Switch Deep Dive](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/a448b565-4b05-408f-b97c-3c5755b09c08.mp4?playbackTicket=a1c518e9f1014518a199b85d8690ffe2&site=vmware.mediasite.com)

[SEC7593 - NSX Security for Horizon View 7—Deep Dive](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/e59158e7-78cb-49b8-b062-82399b2a59cf.mp4?playbackTicket=07e98b841b324ddfa5433252b137ce24&site=vmware.mediasite.com)

[NET9447-SPO - Extensible Solution for Software Driven Data Centers (SDDC) with VMware and Arista](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/e80bc914-96f0-4601-8e5e-73b7bfb83e1a.mp4?playbackTicket=57df1237cb654a20a7950956e4aef259&site=vmware.mediasite.com)

[NET7854R - Multisite Networking and Security with Cross-vCenter NSX—Part 1](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/0b746cbd-40f0-453e-87a1-9604db71e55c.mp4?playbackTicket=c702e4efab634b808be4730447aec01a&site=vmware.mediasite.com)

[NET8030 - NSX Performance Deep Dive](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/5cef4d73-dccb-47b1-a93e-7290facffc8e.mp4?playbackTicket=d31fcc66909f4aa9b33fb4fece898eb5&site=vmware.mediasite.com)

[SEC9450-SPO - Bridging the Gap between Infrastructure and Security Operations](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/7257c5fc-70e3-40bf-bed3-bdf86a570535.mp4?playbackTicket=f27dd483341040ada9e3752dd822ac0a&site=vmware.mediasite.com)

[NET8109 - Amadeus's Journey Building a Software-Defined Data Center with VMware Integrated OpenStack and NSX](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/fdae400c-842c-4a3d-97db-588cd7a65163.mp4?playbackTicket=721ead420ac04e249ea7f1baecfecc04&site=vmware.mediasite.com)

[NET7701 - How to Easily Become a Cool Automation NSX Cloud Network Engineer](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/3d21f392-4660-427c-84d8-ee526fc2193d.mp4?playbackTicket=faff1212ff184c62a810c5507bab55c1&site=vmware.mediasite.com)

[NET7514 - PowerNSX and PyNSXv: Using PowerShell and Python for Automation and Management of VMware NSX for vSphere](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/b0e89702-2a4b-4461-bd52-2263ccc14860.mp4?playbackTicket=40b806b5e39841e78b8b4db2792897f4&site=vmware.mediasite.com)

[SEC10020 - Managing Cybersecurity Risks Within SDDC: VMware and Palo Alto Networks Customers Discuss Their Perspectives and Experiences with NSX and VM-Series Deployments](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/abe989c5-749c-4893-8754-a8f5b30e954e.mp4?playbackTicket=d9b700dd33c148319e78648a0dcb612c&site=vmware.mediasite.com)

[SEC9619-SPO - Scale and Segment the Agile Data Center with Software-Defined Security and NSX](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/28217635-14e9-4f98-8c66-fbe1f0c7c7a8.mp4?playbackTicket=97146e1d487b422abaabad269e15441f&site=vmware.mediasite.com)

[SEC9177 - A Real World Deployment of VMware NSX in the DMZ](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/d416db3c-1c15-409b-ae01-9401caac27e6.mp4?playbackTicket=a0ad7fe99d8b41618070c80fd95783e3&site=vmware.mediasite.com)

[NET7648 - How PG&E is Automating Secure Environments with NSX, vRealize Automation, and vRealize Orchestrator](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/c2382388-36a9-4bb1-8657-53ad88850699.mp4?playbackTicket=85ac81b856124c2e87af77ad543495b3&site=vmware.mediasite.com)

[NET9155 - NSX Policy, Visibility, and Intelligence](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/b7882556-0a6d-42e3-8023-9ae2a2a00ab1.mp4?playbackTicket=13d66d01d95c4a6a8546d99946bf05bc&site=vmware.mediasite.com)

[NET8082 - NSX Operationalization: Monitoring and Troubleshooting Your NSX  Software Defined Data Center](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/fbf63ab7-991f-48fa-9de9-14de326b6342.mp4?playbackTicket=54180bcefb6648c5abd64feede7b22ed&site=vmware.mediasite.com)

[NET9029 - NSX Logical Load Balancing: From Basics to Fine Art](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/174213fc-dfdb-4671-82a2-901fcfd10cb2.mp4?playbackTicket=5327adced3af40e1a92a63575ea76b88&site=vmware.mediasite.com)

[NET8337 - Leveraging NSX for Remote and Branch Offices](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/64a2941c-824f-473b-b48f-fa3a98f4ef4d.mp4?playbackTicket=a23ddbc40dae4762a445b871e0ec6199&site=vmware.mediasite.com)

[NET8343 - OpenStack Networking in the Enterprise: Real-Life Use Cases](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/f3145cd4-2077-4022-9130-06d4ef8cd34f.mp4?playbackTicket=cc7c871426fe4cd7b610a568671cf0e2&site=vmware.mediasite.com)

[SEC8022 - Implementing Agentless AV and IPS/IDS Security Solutions with NSX](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/e6f36b5a-37e2-4c2d-b70e-8e1afecfd771.mp4?playbackTicket=0d3edb74b22c4a65a6fc09ab6ea2b958&site=vmware.mediasite.com)

[STO9886-SPO - Modernize Remote/Branch Office (ROBO) Operations with Software-Defined Edge](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/747af7fa-7640-4384-835a-d19dce0f0c24.mp4?playbackTicket=cb765543c7c541b894db50aefa437230&site=vmware.mediasite.com)

[SEC9446-SPO - Integrating a Threat Defense Lifecycle Security Approach with VMware NSX](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/450ea122-fdae-4dd0-88bb-3b8f367184cd.mp4?playbackTicket=92edb61547eb45898171d751440bca20&site=vmware.mediasite.com)

[SEC8348 - Deploying Security in a Brownfield Environment](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/ea40cabc-8cee-40a6-ac8f-301f6868d355.mp4?playbackTicket=c7276c4917e54c53a5395310f11fbaf5&site=vmware.mediasite.com)

[NET7956 - vRealize Automation and NSX Design Best Practices](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/9a06725d-9812-4a63-aaa8-5b715a253d09.mp4?playbackTicket=869272396bf94f388bd245397812cfbd&site=vmware.mediasite.com)

[NET8680R - Advanced NSX Troubleshooting: Tips & Tricks for Experienced Users](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/51edbe55-f33b-4f22-aa4a-25ecf7b25d36.mp4?playbackTicket=197cc58064b1495995eae9864dabd653&site=vmware.mediasite.com)

[NET7865 - Operational Best Practices for VMware NSX](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/edd17c7a-726c-4791-91bb-1e691464fc2f.mp4?playbackTicket=0e9f0d681fee432cb7406d15ab82f93b&site=vmware.mediasite.com)

[NET8364R - How to Deploy VMware NSX with Cisco Infrastructure](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/314f9ab0-80f3-4239-b193-c2b408632b0f.mp4?playbackTicket=fc142721a37845f5883051e81b37fd8b&site=vmware.mediasite.com)

[NET7514R - PowerNSX and PyNSXv: Using PowerShell and Python for Automation and Management of VMware NSX for vSphere](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/c9187dbd-bdef-4aa3-8e51-ca14876bab14.mp4?playbackTicket=5081951af5f34e2b80d3098112a6e9a9&site=vmware.mediasite.com)

[SEC7836R - Introduction to Security with VMware NSX](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/fb585051-36f5-4258-929a-af2fbfa265a8.mp4?playbackTicket=623f0d4aa45f4a9eb012c50be421bf47&site=vmware.mediasite.com)

[NET8193R - The Architectural Future of Network Virtualization](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/e9ec6df8-d6c4-49a8-96fa-004d3a4fa4e0.mp4?playbackTicket=54c8da81086d4c948e64b38ef342ff45&site=vmware.mediasite.com)

[NET8039 - Bridging Virtual and Physical in NSX with Open vSwitch Database Management Protocol-Based Hardware VXLAN Tunnel Endpoint Integration](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/ef55ee7e-01bc-4a98-a255-71d584b66d97.mp4?playbackTicket=3dff6f0669a345b5986bbc782ae091ed&site=vmware.mediasite.com)

[NET8935 - NSX for Small Data Centers—Breaking Boundaries](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/9c338b26-d1c9-48ec-bc0a-d0e4d0a5c1a0.mp4?playbackTicket=64c287bd0891415d8858b037221f6c03&site=vmware.mediasite.com)

[SEC7628 - Use NSX to Automate Your Security Incident Response so You Can Stay Above Water](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/80b1a787-3cea-46f0-8a62-11a313cc2b32.mp4?playbackTicket=20344bb3d366472288ad2954139297a3&site=vmware.mediasite.com)

[NET7857R - Reference Design for SDDC with NSX and vSphere: Part 1](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/39c4ae41-ad86-4156-a203-2b198c9b0bf7.mp4?playbackTicket=b4b99bee0da046eeac7b20ba916c9016&site=vmware.mediasite.com)

[NET8675r - The Practical Path to NSX](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/12b342ab-5b04-4fd5-a56f-9e6056891529.mp4?playbackTicket=3ea6a2c5b77f41c7881b02631d55426f&site=vmware.mediasite.com)

[SEC9609-SPO - Trusted Security in the Software Defined Data Center: Real-World Use Cases Across VMware Platforms, including NSX](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/4f21e3d9-6da0-4e87-b5e0-4bda79132447.mp4?playbackTicket=33431ed4cca1488b9b1411874550cdd4&site=vmware.mediasite.com)

[NET8734 - Automating Networking and Security Operations with NSX Customer Panel](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/fbe6a4a7-b9cd-47d1-b176-55696b43f392.mp4?playbackTicket=ca820f96e01245e99b70e8e699d212d9&site=vmware.mediasite.com)

[NET9156 - Customer Case Study: Journey to Automate Security As a Part Of Service Delivery](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/66cb8812-67f5-4f3d-ad06-5f92a6e11018.mp4?playbackTicket=8aba1f8447c14b9e88f3e29ebfe25b85&site=vmware.mediasite.com)

[NET7861R - Multisite Networking and Security with Cross-vCenter NSX: Part 2](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/19986278-3ecb-455c-94de-d9c6aa3595be.mp4?playbackTicket=b7774fce04264d3fb74aae38fa503477&site=vmware.mediasite.com)

[NET7760 - Enhanced Disaster Recovery with NSX](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/00980cda-d66c-4b24-aa16-5b7e1fed8d56.mp4?playbackTicket=09c66ae8445d4eb4b945b09cf583ee9f&site=vmware.mediasite.com)

[NET7854R - Multisite Networking and Security with Cross-vCenter NSX—Part 1](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/72adacde-1d18-415a-9b1b-037e6073be50.mp4?playbackTicket=48e8b60222904fc19f3e83911097424f&site=vmware.mediasite.com)

[NET8903 - Stories from the Alexandria SDN Zone](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/f150a565-74b3-4bf3-aecb-d89af91590a7.mp4?playbackTicket=480beafc5c464201b89436c90717d4bc&site=vmware.mediasite.com)

[NET8680R - Advanced NSX Troubleshooting: Tips & Tricks for Experienced Users](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/c7b8ab46-fbea-490e-99ae-70b98808152e.mp4?playbackTicket=f99b0756e7844feebb60837c014b8a35&site=vmware.mediasite.com)

[SEC9976-SPO - Extending security beyond the SDDC with VMware NSX and Palo Alto Networks VM-Series Virtualized Next-Generation Firewall](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/99f1a482-e8af-4218-9afc-8a1ac3177fdf.mp4?playbackTicket=4b2a84bf7f704d36aceb16831bf996e3&site=vmware.mediasite.com)

[NET8131R - NSX for vSphere Logical Routing Deep Dive](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/7b9b1d75-dbcc-44d9-8d6a-be1123570aac.mp4?playbackTicket=2724033bcace402f96aa076e83fb5b4e&site=vmware.mediasite.com)

[SEC8730 - NSX Security and Micro-segmentation Customer Panel](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/969b9b2b-2fca-4983-aa6d-4a4f81ccc526.mp4?playbackTicket=083aa85c8bea49f396e58523e742f258&site=vmware.mediasite.com)

[NET8241 - Monitoring and Troubleshooting NSX with vRealize Network Insight (Arkin)](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/fcbe5ea9-3927-4534-a2bf-f1860015e74e.mp4?playbackTicket=75681a4b6c484c5abb3f57ba92b91f33&site=vmware.mediasite.com)

[NET7834r - Introduction to VMware NSX](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/2006587c-d420-47fa-9812-69df4e0ee2ef.mp4?playbackTicket=9be3d084bb104e8a8dea8e767aabcc89&site=vmware.mediasite.com)

[NET7944 - NSX Brownfield Deployment Best Practices](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/0a6d7f57-a1ba-4a11-9290-889f4f6dd39c.mp4?playbackTicket=a0796167c147497e95a78d2223519714&site=vmware.mediasite.com)

[SEC7568 - Practical NSX Distributed Firewall Policy Creation](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/f247242f-0ec7-4bdb-b6fa-375075834e3e.mp4?playbackTicket=aca11dd0405d465f96c3615560ac0fbc&site=vmware.mediasite.com)

[NET8731 - IT Automation with NSX Network Virtualization and Security](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/3f16f5fc-8a2b-40d9-9181-934b82253229.mp4?playbackTicket=0178ad45d02d43bca41c38800ae829e9&site=vmware.mediasite.com)

[SEC9968-SPO - Automate Check Point vSEC Advanced Security with NSX](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/038e1c96-3e9b-4461-89d7-669504d3f6b6.mp4?playbackTicket=2cd78eed7e1648ee97bec102c7ca3ac3&site=vmware.mediasite.com)

[SEC9618-SPO - Deep Dive:  Extending L4-L7 Security Controls for VMware NSX and VMware Integrated OpenStack (VIO) Environments with Fortinet Next Generation Security](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/a7dec1a2-2f6f-4384-a5e6-5d8acef8f14e.mp4?playbackTicket=4c9469eb910c4d0c85e42bc5b6a42bef&site=vmware.mediasite.com)

[SEC9972-SPO - Deep Dive: Secure your multi-tenant cloud with Palo Alto Networks VM-Series and VMware NSX](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/b16415ad-38c1-472c-b253-8ea09f848221.mp4?playbackTicket=3713175c4d0b4a54ab9dce5068d83008&site=vmware.mediasite.com)

[NET8729 - NSX on Cisco ACI Customer Panel](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/68087b20-37f4-4d82-b067-dfe0efe595e6.mp4?playbackTicket=daa2d3c453594f88acf8f07b4667896c&site=vmware.mediasite.com)

[NET7837 - Introduction to Application Continuity with VMware NSX](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/0bb6466d-f47f-4b33-bb19-c2b690f89554.mp4?playbackTicket=499ee5dc6bb84c26b0af8afe740ad110&site=vmware.mediasite.com)

[NET7935 - Container Orchestration and Network Virtualization](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/9ebc72ed-5e25-4230-ab48-1e6ca316da3e.mp4?playbackTicket=a9425dcbbf89498b9af033e5ff10b98f&site=vmware.mediasite.com)

[NET7656-SPO - Accelerating SDDC through mainstream adoption of network virtualization](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/bf1f215e-1855-452b-8ce9-597a9085da5f.mp4?playbackTicket=7e281274e324416aab4af056f9917652&site=vmware.mediasite.com)

[NET8193R - The Architectural Future of Network Virtualization](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/651d9fdd-2b97-45df-89c3-46e2c2ae640e.mp4?playbackTicket=0aef3a50875640f1b6a012be62f67e83&site=vmware.mediasite.com)

[SEC7836R - Introduction to Security with VMware NSX](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/be6cab8f-3195-4d85-8f7e-ad065bc32c78.mp4?playbackTicket=69a217de1c8d430c88284884aae4ece7&site=vmware.mediasite.com)

[NET7834 - Introduction to VMware NSX](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/294283c8-dfcb-4231-8b6d-c65ce9170db7.mp4?playbackTicket=f3604b018da547f793663063849bf2f9&site=vmware.mediasite.com)

[NET7857R - Reference Design for SDDC with NSX and vSphere: Part 1](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/0c01d09c-da0c-402c-a89d-971bd9a0ae1a.mp4?playbackTicket=f263fd57a7fb4ffaa7ca3421150460e0&site=vmware.mediasite.com)

[NET8675 - The Practical Path to NSX](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/5f26a99e-1a15-46a5-a9db-1f4635b5ce5f.mp4?playbackTicket=0fbb5dc518ec4eff8b2b80cf9f4bc8a9&site=vmware.mediasite.com)

[NET9381 - Operationalizing NSX Customer Panel](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/be7b7c37-fd03-4d31-a4b7-e578b5b26e02.mp4?playbackTicket=28e8595675bd457b95eb942517ffc179&site=vmware.mediasite.com)

[SEC10019 - VMware NSX Micro-segmentation – Definition & Benchmark Deep-Dive](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/fc19c529-a917-4251-8af0-623ef49562a6.mp4?playbackTicket=a31f5b423c1b469a8f91c9abb8e45710&site=vmware.mediasite.com)

[NET9152 - VMware NSX—Deep Dive](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/db352180-d08a-459f-8f0e-c14df9536c58.mp4?playbackTicket=9e497a3812b94dc48cbcdf901d1784ab&site=vmware.mediasite.com)

[NET10884 - Moving to the next level of the SDDC - a Public Agency introduces VMware NSX, AirWatch, and Palo Alto Networks integration](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/ff96e2fd-c27c-4303-8911-14120e947a00.mp4?playbackTicket=479cc7d6e3984f458ce230eafce71841&site=vmware.mediasite.com)

[NET9004-QT - Virtually Unstoppable: Scaling NSX to Bridge the Gap between Security & Cloud Automation](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/c8282e8c-bb18-4a2a-b711-f36c5636faeb.mp4?playbackTicket=14389ce740ca4cd784c1b9217890cc84&site=vmware.mediasite.com)

[NET8769-QT - Hyper-convergence in Healthcare:  The Key to Doing More with Less](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/f24888cd-2591-4edc-af87-c4295f15c0d4.mp4?playbackTicket=02ed06977f28451e81d9cce34c007dc2&site=vmware.mediasite.com)

[NET9382-QT - A Software-Defined Data Center in Overseas Bases and Military Operations](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/843ed907-b0cd-4392-86cd-1c55dc4140b1.mp4?playbackTicket=42d68570675d454f91771702760d5c53&site=vmware.mediasite.com)

[NET7774 - Day Two NSX Operations in VMware's Private Cloud](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/c990199b-c895-4922-a378-ad5128590c58.mp4?playbackTicket=55f57a4584d0410ebd2963d92da92381&site=vmware.mediasite.com)

[SDDC8621 - VMware Cloud Foundation: Technical Deep Dive](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/145115e1-24d9-4ee7-acf2-137b00cfdd9a.mp4?playbackTicket=4be320cc6b704fc39878667c5cb08798&site=vmware.mediasite.com)

[SDDC8472 - An IT Architect's Guide to the Software-Defined Data Center](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/b32b5eb9-e753-4b65-a9c7-8512c0025cd9.mp4?playbackTicket=cf409804b4084cd7aa36dc6bbb246986&site=vmware.mediasite.com)

[SDDC7780 - Agile: The Scrum Master for Your Software-Defined Data Center!](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/c544030e-0807-45d7-b0e9-6c19ffc73da8.mp4?playbackTicket=2c58ffe9d8f04f18b0f9c69049ebdd2c&site=vmware.mediasite.com)

[SDDC8468R - A Beginner's Guide to the Software-Defined Data Center](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/ca166216-ef18-489e-981e-dee260e77115.mp4?playbackTicket=78de5c1a8f71439cbf428e408504a3ce&site=vmware.mediasite.com)

[SDDC7886 - Implementing An Operating Model for Agility: A Customer Success Story](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/52ceb29a-7e09-404c-b281-d4cd3080cb6a.mp4?playbackTicket=bc39a3b513b34212a2ecc22b03f98c10&site=vmware.mediasite.com)

[SDDC9971 - Experience the Business Impact of IT Innovation & Transformation in this Live Interactive Simulation](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/f62de2b4-4429-47c4-b4dd-20f5a14a8207.mp4?playbackTicket=c11634c427714911b5ccc91e1eb9c6eb&site=vmware.mediasite.com)

[SDDC8414 - VMware Validated Design for SDDC: A Technical Deep Dive](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/d37cf776-1e24-4b30-a723-d9bb1a386209.mp4?playbackTicket=53b53ea046194fc28995e56f45e98c58&site=vmware.mediasite.com)

[SDDC7502 - On the Front Line: A VCDX Perspective Working in VMware Global Support Services](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/2dd8fd5b-d366-48d6-a6f1-1621acaae98f.mp4?playbackTicket=d36f8256aa744d748e75d3389d536eab&site=vmware.mediasite.com)

[SDDC9456-SPO - Implementing Self-Service Storage Provisioning with vRealize Automation XaaS](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/7f338d41-d20f-436e-8541-c769183a10ac.mp4?playbackTicket=a4dd99e701624fe19103973046c43bab&site=vmware.mediasite.com)

[SDDC8615 - vRealize Automation 7 in VMware Cloud Foundation](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/44ddb3c5-fd34-4ed5-95e7-715ffa4894a6.mp4?playbackTicket=04f1d070799f49a5b05c1037b1a066e8&site=vmware.mediasite.com)

[SDDC10623-SPO - The private cloud is dead. Long live the private cloud!](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/d57b5c93-333a-4d68-9816-d8f2abb4b576.mp4?playbackTicket=55a32f877ca048518feb010cd4a0cd49&site=vmware.mediasite.com)

[SDDC8748 - Building a Successful Business Case for VMware Cloud Foundation](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/b265578c-561f-43c3-8138-8cfb68d690de.mp4?playbackTicket=d3f9a49b958e4a31a1b36c958c793b15&site=vmware.mediasite.com)

[SDDC7692 - Tips for Realizing the Full Value of Your SDDC Transformation](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/85b5628a-d8d9-43e1-91a1-7c57d848709d.mp4?playbackTicket=3e5957f539024fc0b314e1dba28aa0d4&site=vmware.mediasite.com)

[SDDC9726-SPO - Making SolidFire Invisible in your VMware Environment](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/6629b6cd-d700-47ba-9676-23c41b4c5fd2.mp4?playbackTicket=be7b073f375049d685f5e071466282cf&site=vmware.mediasite.com)

[SDDC9612-SPO - How to design and implement VMware’s vCloud in production](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/4f441c47-1bb9-448e-8961-d14350103470.mp4?playbackTicket=4c1e9b0501b046e6a2676e9b699b1592&site=vmware.mediasite.com)

[SDDC8154 - Building the Integrated Software Stack](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/71d42022-17bf-47f4-a5bb-ab2387d35be1.mp4?playbackTicket=633a35ec98664ee7baa3ae25b423bc42&site=vmware.mediasite.com)

[STO9405-SPO - Stopping Global Threats with Converged Infrastructure for the US DoD Cyber Range](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/634f6b69-587c-4eb1-a9ab-589084e3522e.mp4?playbackTicket=7524dded73bb431e8eed720d3549b685&site=vmware.mediasite.com)

[SDDC9108 - VMware Cloud Foundation – Future Innovations](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/9339d1db-891e-442f-9791-6de66e2ee81d.mp4?playbackTicket=4356974a464147d8acbe410aa51eb841&site=vmware.mediasite.com)

[SDDC9181 - VMware Cloud Foundation Backup and Disaster Recovery](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/59c88da0-75a7-435b-88fa-289317d89211.mp4?playbackTicket=7f139bd922014fd4893eac700ab56c5c&site=vmware.mediasite.com)

[SDDC8614 - NSX in VMware Cloud Foundation](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/ad9332ff-7442-4713-90fc-d196c8b98ca6.mp4?playbackTicket=63921daea8ae4c778a82c3fcbf233398&site=vmware.mediasite.com)

[SDDC9995-SPO - HPE Hyper Converged – path to composable infrastructure](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/eb227f29-de4d-4005-a19e-ca1ea827ce1b.mp4?playbackTicket=6cf44d58ae234a2a927003e78efb2182&site=vmware.mediasite.com)

[SDDC9465-SPO - Level Up to IT as a Service with Hyper-Converged](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/70383486-f4fd-4e5c-b797-d6ce7a1d2729.mp4?playbackTicket=c83a3cd36c3d4eb2b2a9cac74468c744&site=vmware.mediasite.com)

[SDDC8357 - If They Come - Are You Ready?](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/d45d7d81-cfb4-41e4-ac2c-f2421ecce646.mp4?playbackTicket=2526ba0ad2094ec29ce0449a8a70174a&site=vmware.mediasite.com)

[SDDC9428-SPO - Practical Strategies for SDI and Security](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/bc29d651-6b57-4ac5-8053-3ced1695bfdb.mp4?playbackTicket=727f19ab97af43e28ac0ffd8adc39a29&site=vmware.mediasite.com)

[SDDC8445 - VMware Validated Design for Microsegmentation Deepdive](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/a06343f5-12d6-4d01-b902-d19021a126ab.mp4?playbackTicket=2ca6256279f447ab85edbdb2e26966ab&site=vmware.mediasite.com)

[SDDC8946 - Deep Dive into Deploying the vRealize Cloud Management Platform the VMware Validated Designs Way!](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/5f3e1ad2-e8f3-4cfd-80f4-3115a6d6b2a1.mp4?playbackTicket=d1fbe1f507fa49c9b7e83a9b65830825&site=vmware.mediasite.com)

[SDDC8628 - Automating Virtual Desktop Deployments with VMware Cloud Foundation](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/fe609247-bc9e-4f36-925f-3c299f32b8e9.mp4?playbackTicket=5a5428aa2176430487b5d3f8674e9494&site=vmware.mediasite.com)

[SDDC8150 - Rack Scale Architecture (RSA) and Software Defined Data Center (SDDC) Innovations](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/7a6acdf2-3436-4ca3-a683-1a73a55d4895.mp4?playbackTicket=2f1e1012a83142a5a268b36eefc5acc0&site=vmware.mediasite.com)

[SDDC7587r - Software-Defined Networking in VMware Validated Designs](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/5697883d-eee6-4893-afdf-b75890f2059f.mp4?playbackTicket=71a873d0c58d40419222dcfaeae8a7c1&site=vmware.mediasite.com)

[SDDC9613-SPO - Building the Future Data Center with Province of Nova Scotia](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/1a43a8d3-456c-44a8-aeab-73030eeb2057.mp4?playbackTicket=bd303a0aa773484d8a642bb9195a51aa&site=vmware.mediasite.com)

[SDDC9921-SPO - Evaluating Tradeoffs in Reducing and Eliminating Downtime Inside and Outside of the Software Defined Data Center](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/c57b7ae0-9841-450b-b245-9caf50e72ece.mp4?playbackTicket=39e4bd1d6a9a4f5e8391bf1a879be545&site=vmware.mediasite.com)

[SDDC8520 - No IT Left Behind: Connecting the Software-Defined Data Center to Multi-Modal IT](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/29c4377d-360b-4300-b41d-7a4fa5c37f78.mp4?playbackTicket=399529648faa4609a2d03daba0e47fc1&site=vmware.mediasite.com)

[SDDC8423 - VMware Validated Design for SDDC – Operations Architecture Technical Deepdive](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/807002c7-14ae-432c-b9b3-907903612542.mp4?playbackTicket=9e2c09b0a9d744b184d1a74c1acb2f78&site=vmware.mediasite.com)

[SDDC8214 - Case Study: VMware's Private Cloud Journey to Over 100K Virtual Machines](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/fcb8f3cf-d3ee-412d-a74c-0f1988d84686.mp4?playbackTicket=30dd26252c184fa0a373bfcf4139c590&site=vmware.mediasite.com)

[SDDC8975 - SunTrust's Cloud Journey](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/7a869c4d-1e9c-4c2b-b26a-86f2abcbd3c2.mp4?playbackTicket=d46b44a0a24d45b1b05453e38666375d&site=vmware.mediasite.com)

[SDDC9025 - VVD 101: Build Your Cloud the Right Way, First Time](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/e793f827-95d9-42f7-adc1-cc4cf1ff48be.mp4?playbackTicket=70715e5693d145d7ac8c1a5319aa56c8&site=vmware.mediasite.com)

[SDDC9605-SPO - Using Hyper-intelligence to build next generation storage platforms](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/fcd52ca6-4cc9-4a21-a789-fd1210aedfb2.mp4?playbackTicket=82027d0a997f48f192a14161f2b4688f&site=vmware.mediasite.com)

[SDDC8930 - American Tire Distributors: Our Journey to a Modern Private Cloud](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/e508be8c-02e7-4bf7-9424-4bc65b53f4e8.mp4?playbackTicket=a79fdba84f7e40fdabf41d21387623c3&site=vmware.mediasite.com)

[SDDC9176 - How VMware Cloud Foundation powers the IBM Cloud](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/f1afa7a1-e475-413f-8c1c-52c2226037e6.mp4?playbackTicket=1312bd94aad04b4da549212063662708&site=vmware.mediasite.com)

[SDDC8994 - Taming the Hydra: IT in a Multi-Cloud World](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/da8988b5-8811-4a9a-b79e-4085cba95b90.mp4?playbackTicket=d661f8a2d77d4540b859a75e52f1f4b8&site=vmware.mediasite.com)

[SDDC9448-SPO - Don’t Let Data Protection Drag Down Your Business Transformation](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/3ecf84e5-ded5-4007-95cf-6800c838e8f4.mp4?playbackTicket=02db999f50024e86b40b6fa6e4b59d8c&site=vmware.mediasite.com)

[NET9460-SPO - Use Cases for Software Defined Data Center with NSX: Transform to Digital Business by deploying multi-tenant agile network in SDDC environment](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/850ba54b-4941-486f-b9dd-e226a6520564.mp4?playbackTicket=f731b6d02c1945ec8ee5c37c4268a035&site=vmware.mediasite.com)

[SDDC7819-SPO - Lessons learned to provide secure service assurance for your VMware investments](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/9e01af4c-85d6-4d61-8593-216926fe9b94.mp4?playbackTicket=2d2e565249d44e1e97b0239a4957cd6a&site=vmware.mediasite.com)

[SDDC9023 - Hyperconverged Infrastructure at Scale with VxRack 1000 SDDC](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/19a8c25d-b824-4b5a-94cb-79d90951be6e.mp4?playbackTicket=a2af7e4883354f9087da2f450f02c694&site=vmware.mediasite.com)

[SDDC8351 - How VMware Cloud Foundation Makes Your Private Cloud Operation More Efficient](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/1d4654db-b109-4de9-aaf6-6eb791482258.mp4?playbackTicket=ee3ec3eb8ced4b92b2483a7d5e43e4f5&site=vmware.mediasite.com)

[SDDC9404-SPO - Reinventing Disaster Recovery Leveraging Public Cloud Infrastructure](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/5e2e320e-9f3a-4f65-8712-7456268d8b73.mp4?playbackTicket=040b5a92dc504cdd8f68ee43070c9cc1&site=vmware.mediasite.com)

[SDDC7616 - Strategizing Cloud Business Management Using vRealize Business](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/dbfd0a69-0569-42a5-80eb-70e995c17217.mp4?playbackTicket=2908cb7dd413409987f7a61de0bea1ee&site=vmware.mediasite.com)

[SDDC7587 - Software-Defined Networking in VMware Validated Designs](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/91dbf951-2178-452a-bd80-f4e7e27a4878.mp4?playbackTicket=adf0083a9e1347e89cb53b12977f1b7b&site=vmware.mediasite.com)

[SDDC8475-QT - A Manager's Guide to the Software-Defined Data Center](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/4505b802-2ff3-4dde-9e4d-68b7e023ff46.mp4?playbackTicket=16492614f4074a038d7af493b5969674&site=vmware.mediasite.com)

[SDDC7609-QT - How to Respond to the &quot;Bring Your Own Data Center&quot; Trend](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/82391ced-f3bb-41e4-9754-9d048fd69637.mp4?playbackTicket=1dfa529265374782a32e459ed7242e0c&site=vmware.mediasite.com)

[SDDC7881-QT - Cloud Service Lifecycle in a DevOps-Focused Delivery Model](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/0e76123d-776c-4f84-ba61-657bcc3aeacc.mp4?playbackTicket=b0caee27c9c246bf91d3114acbb818d1&site=vmware.mediasite.com)

[SDDC8945-QT - Learning in the Cloud: VMware Education's New Enterprise Learning Subscription](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/1cb8ea0a-f38d-4742-b703-4712b1a5ff86.mp4?playbackTicket=f20efa603bb945489c6cb2798b9d50cc&site=vmware.mediasite.com)

[SDDC7876-QT - Service Automation Roadmap: Approach and Samples](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/8c3f94e1-e968-4172-9d02-3187e08faf2b.mp4?playbackTicket=9d81cbdf00ca4f3b8f8202ff9af70136&site=vmware.mediasite.com)

[SDDC8024 - VMWorld Hands on Labs Architecture Design](http:)

[CTO8519 - Best of Both Worlds: Achieving Ultra-Low VM Network Latencies and Extreme Bandwidth Without Compromise](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/6486a7e1-de71-437e-a245-7aa3a8ca69a6.mp4?playbackTicket=6a6164a19df545e59fb9dca0c5dcf552&site=vmware.mediasite.com)

[CTO9606 - Open Source as Critical Ingredient in Enterprise Computing](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/ec63056a-7995-42a7-a8d3-a339a0c0ec6b.mp4?playbackTicket=c54f9628afbd4643a2fe071ac2e14293&site=vmware.mediasite.com)

[CTO8120 - Debunking the Myths about Virtualizing High Performance Computing](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/7addbc86-091d-49b7-bce1-4b82f4d2300b.mp4?playbackTicket=6e30625e0f8547fea9e35e6d895ac82f&site=vmware.mediasite.com)

[CTO9942 - Multi-Cloud Mania: Practical Operations in a Multi-Cloud World](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/84262670-fe66-4260-9ad2-9588ab010fac.mp4?playbackTicket=e32ad3cda1804f13ab96be99f55b80fb&site=vmware.mediasite.com)

[CTO9471-SPO - New Capabilities in ONTAP 9 Optimized for All Flash Virtualized Workloads](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/b0a4825f-5c93-4b0f-a434-bfc1c47da3f4.mp4?playbackTicket=1a32549e301c4891b9abe989a0912a58&site=vmware.mediasite.com)

[CTO9036 - Providing Management Tools for the Emerging IoT Infrastructure](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/5239219a-9e26-43f2-afb3-f292203de50f.mp4?playbackTicket=c8f0b97ef4b14861893fc05806d02a14&site=vmware.mediasite.com)

[CTO9951-SPO - What’s Old Is New Again: Next Generation Storage](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/d52773e8-b6c5-4523-9113-643a24a4d5b9.mp4?playbackTicket=958de6c1991e4048aa5c57691e38f1aa&site=vmware.mediasite.com)

[CTO9018 - VMware Internet of Things Strategy; Unveiled](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/a36f731f-0772-41cb-87ce-c97451f20aba.mp4?playbackTicket=9acea271fc2841918e6f47319295161c&site=vmware.mediasite.com)

[CTO9032 - Is it Possible to Use NSX to Cut WAN Network Costs in Half?](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/a9038d55-f8bb-40cc-b70d-ebca41e83845.mp4?playbackTicket=f2401123eafd466c863175eb79906043&site=vmware.mediasite.com)

[CTO7942 - Unik: A Platform for Automating Unikernels Compilation and Deployment](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/e77b2fd4-110f-4db9-a816-ed7acb8ba825.mp4?playbackTicket=e81c098720b54aa692b17bca9b82d06b&site=vmware.mediasite.com)

[CTO9996-SPO - Fortifying the Cloud: What the New Samsung-VMware Partnership Means](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/ef193cad-b079-4716-882c-bab49e29c035.mp4?playbackTicket=984825c64f0e44db81b69da51ecd6a33&site=vmware.mediasite.com)

[CTO8995-QT - How Do You Manage Security Vs Privacy in IoT Beyond Device Management?](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/ab81a983-a114-4f53-9a10-1172d4f95007.mp4?playbackTicket=b17a5b037d904d2cb3912e767d567062&site=vmware.mediasite.com)

[CTO9002-QT - Artificial Intelligence Is the Future of IT](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/a657dff9-c9e6-42de-9feb-d7655a146def.mp4?playbackTicket=5e94a5ef767340f898733f83e806fe43&site=vmware.mediasite.com)

[VIRT9034 - Oracle Databases Licensing on a Hyper-Converged Platform](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/b541aeb8-6944-4707-aa8a-bdb73d5e1df2.mp4?playbackTicket=3360e2568bf745a4abd5c4bb82d13c46&site=vmware.mediasite.com)

[VIRT8443 - Extreme Performance Series: Evaluate the Performance of Your Cloud with Weathervane and VMware vRealize Operations](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/de2b1eb5-c391-4b99-993b-f7fd7aaf0b2c.mp4?playbackTicket=031b858ff9b2457a901399055dbacc47&site=vmware.mediasite.com)

[VIRT7620 - Successfully Virtualize and Operate Your Microsoft Skype for Business Infrastructure on the VMware vSphere Platform](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/b6d1bf35-22fd-4dcc-b8a2-ad792d73b7e0.mp4?playbackTicket=80a782298f194f6ca097d64307f77159&site=vmware.mediasite.com)

[VIRT7941 - The Best of Both Words: Achieving SQL Server High Availability with VMware](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/308e14df-2601-4c42-8cf0-1ce2bdc581b2.mp4?playbackTicket=df771930cc05420a91400b59f788338c&site=vmware.mediasite.com)

[VIRT8290R - Monster VMs (Database Virtualization) Doing IT Right](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/68f7bf93-4794-49e9-805e-0c50cd4edb28.mp4?playbackTicket=4452d858614349c0ae08e35c3ef5fc22&site=vmware.mediasite.com)

[VIRT7699 - Use Cases in Performance Root Cause Resolution for SQL Server: How to Use vRealize Operations Manager, SIOS iQ Machine Learning Analytics, and SQL Sentry Performance Advisor](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/74740c5a-9b34-4048-9287-dd04e09cb974.mp4?playbackTicket=aedca9711cce4398b59d7cc8d4c39632&site=vmware.mediasite.com)

[VIRT8182 - Virtualizing Internet of Things with SAP HANA in a Flash](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/ae1514fc-a72d-4b88-836c-17d523abf8d1.mp4?playbackTicket=8b9509ffcc5b48eda7b749e8a24f01ec&site=vmware.mediasite.com)

[VIRT9009 - Licensing SQL Server and Oracle  on vSphere](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/38993112-12c8-41ef-8d15-40dbbec89d9d.mp4?playbackTicket=0e4b8bee21e643788d9f3dd01c294c63&site=vmware.mediasite.com)

[VIRT7598 - Extreme Performance Series: Monster VM Database Performance](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/703a6607-5dd8-4c20-811a-3c0eb0c16a09.mp4?playbackTicket=1274dc2cbfc643bfba5844e28560235b&site=vmware.mediasite.com)

[VIRT7840 - VMware and Microsoft Present: Successfully Virtualizing Microsoft Exchange Server, the Right Way](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/74a36563-6d67-48ea-a05a-df447b25295a.mp4?playbackTicket=5f57c71a02ce4413a517b51e2a37c5c5&site=vmware.mediasite.com)

[VIRT9402-SPO - Modern Storage Strategies for On-Demand Applications](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/8735e1f6-3ccf-4846-9765-3112f6f3e635.mp4?playbackTicket=19ede559b5c44c35a29c5a4441517eee&site=vmware.mediasite.com)

[VIRT8074 - The SDDC: Full Stack on vSphere 6.0 SAP Business Warehouse Powered By HANA, NSX,  vRealize Operations, SDS-Virtual Volumes on Hitachi Unified Platform](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/1cd2489d-727d-46eb-a12f-98b2afc9eac4.mp4?playbackTicket=80ca3a262e914cd6bb7addc6a8cbbd82&site=vmware.mediasite.com)

[VIRT9435-SPO - Accelerate, Simplify and Control: Add Data Virtualization to Your Enterprise](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/90c84369-5407-463a-bcba-00f55e4c7df1.mp4?playbackTicket=121ac345fe3c4f52a6cf4cc96d688fe1&site=vmware.mediasite.com)

[VIRT7511 - Performance Tuning and Monitoring for Virtualized Database Servers](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/e5735769-400e-4f2a-baa0-475b5917c98e.mp4?playbackTicket=cf73a2f6f254483c856a6f9b05f4aec4&site=vmware.mediasite.com)

[VIRT8738 - Extreme Performance Series: Virtualized Big Data Performance Best Practices](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/e0b656c2-2c61-4071-90bf-067ba8023943.mp4?playbackTicket=d12b020f803a490d891b691704c90624&site=vmware.mediasite.com)

[VIRT7575 - Architecting NSX with Business Critical Applications for Security, Automation and Business Continuity](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/077cfabe-994f-4021-b2bb-11fa359fee83.mp4?playbackTicket=f19e863d222a43cc932cd77bee6713d2&site=vmware.mediasite.com)

[VIRT8278 - Snapshots and SQL Server - Technical Deep Dive and Detailed Lab Findings](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/c4e34999-0ac0-49cc-962a-fa2e40c3e2fb.mp4?playbackTicket=da05a75a0c014f7587c5f377876052a4&site=vmware.mediasite.com)

[VIRT9459-SPO - High Performance Software Defined Data Center for Business Critical Applications](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/24956ef0-3277-484d-8367-930c7000e3ba.mp4?playbackTicket=642fa73a248e4d7aae841292e53f9505&site=vmware.mediasite.com)

[VIRT7684 - SAP on Virtual SAN](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/938dc975-ecd1-43e4-aac2-7511f9db36ea.mp4?playbackTicket=0476818e9da64906a3efb058f2e725fa&site=vmware.mediasite.com)

[VIRT8530R - Deep Dive on pNUMA & vNUMA - Save Your SQL VMs from Certain DoomA!](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/3dbfa642-cf54-41ad-8035-9d610e15fb44.mp4?playbackTicket=f4c6b5adfb2445f994f9d7276a84aac0&site=vmware.mediasite.com)

[VIRT7550 - Providing HA and DR to Mission Critical Oracle Databases using vSphere Metro Storage Cluster and VMware Software defined Storage and Networking](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/7e847d8c-32e4-48b3-8a2c-381905c66afc.mp4?playbackTicket=ce13f7d113a849329952c86b6e4558ec&site=vmware.mediasite.com)

[VIRT8708 - Understanding Difficult Applications that Require Extra TLC for Better Performance](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/f62f836c-6ef5-4987-ba1c-da31ceb91d90.mp4?playbackTicket=d2f499ca0f3c4ceb8da7565b17723a87&site=vmware.mediasite.com)

[VIRT7709 - Innovations from Cloudera and VMware for Virtualizing Hadoop](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/fd4c7cb4-17dc-4496-862c-8004b4b6450b.mp4?playbackTicket=48597cacd21c418d8fa2038114dc39f8&site=vmware.mediasite.com)

[VIRT8071 - Making Virtualized Hadoop Deployments Successful](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/79e99643-7392-4679-a2d0-c1146683aeb5.mp4?playbackTicket=d665f7f33206455196a9a8f8a0f26482&site=vmware.mediasite.com)

[VIRT7654 - SQL Server on vSphere: A Panel with Some of the World's Most Renowned Experts](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/b2d1c69a-d1aa-4562-b7d1-6b480a0a8944.mp4?playbackTicket=633a899cbe4e4c1c85e8efd88f5efc29&site=vmware.mediasite.com)

[VIRT9923-SPO - Virtual SQL Server for the Non-DBA](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/2a387a56-0346-464b-8046-2e77ce8d0d57.mp4?playbackTicket=b9d559430f2f48e28686f13caee82831&site=vmware.mediasite.com)

[VIRT8530R - Deep Dive on pNUMA & vNUMA - Save Your SQL VMs from Certain DoomA!](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/5d968302-43ce-4c00-99ce-892ca3ccd0cc.mp4?playbackTicket=7cf44a171ad74f0f955507feca34167d&site=vmware.mediasite.com)

[VIRT7931 - SAP on SDDC: Business Benefits of SAP Automation with SDDC](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/539bf66d-4f9f-48ef-8fe9-731b28d6b896.mp4?playbackTicket=f5d2530d821044a8a482aeff755a09d1&site=vmware.mediasite.com)

[VIRT9132 - Virtualized Extended Distance RAC on Hyperconverged Infrastructure in a Private Cloud - The Perfect Marriage of Availability and On-demand Scalability](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/b9de61bb-a773-45b6-87d1-e137aebb5bb8.mp4?playbackTicket=b1f61d7f0b2045c59a8b280451c97807&site=vmware.mediasite.com)

[VIRT8198 - Automating Deployments of Mission-Critical Applications - in a Flash!](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/23bb5813-7124-4ecf-82ec-f719203666b9.mp4?playbackTicket=ddf873153460417f9ce301e90f9f8018&site=vmware.mediasite.com)

[VIRT7632 - SQL Server On-Premises in the Cloud](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/701a8981-3b63-4f20-86ff-3e8cb7c24503.mp4?playbackTicket=08f518008bad44a59aab99d47500b746&site=vmware.mediasite.com)

[VIRT7507 - How to Design and Tune Virtualized Trading Platforms](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/f548e5c6-fde3-4f6f-8b30-b41b647cf8c4.mp4?playbackTicket=ce7f489818a84f65a48ea18ec1d44f37&site=vmware.mediasite.com)

[VIRT8530R - Deep Dive on pNUMA & vNUMA - Save Your SQL VMs from Certain DoomA!](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/9f4373e0-8868-4282-984e-5b8328e3e044.mp4?playbackTicket=dca31eba965747b4b2024c79e4e14a96&site=vmware.mediasite.com)

[VIRT9366-QT - Business Critical Applications at VMware and DBaaS with the Hybrid Cloud](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/117befe9-72c9-401e-ac7c-34e909352c5f.mp4?playbackTicket=ea818c02b76b4b0b903c3d733502c73d&site=vmware.mediasite.com)

[VIRT8239-QT - Things You Should Know about Big Data](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/745b7d28-7e3d-4aa4-b711-68beefdb2b5f.mp4?playbackTicket=2bade7d9cfe04520a24dcd7deb89d331&site=vmware.mediasite.com)

[VIRT7504-QT - Deploying SAP Netweaver and HANA with vSphere 6 and Latest Solutions in the VMware SDDC](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/26f7e7dd-9245-4ef1-9876-95b268b38cda.mp4?playbackTicket=3dda00b0f96248aea84bc04f4b8bad4d&site=vmware.mediasite.com)
