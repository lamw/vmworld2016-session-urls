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

[CTO10624-S - Are you ahead of the IoT curve](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/01fae26b-4035-4dd8-b9b9-3fb18b2b49b9.mp4?playbackTicket=820f3e40d42c4091aca826a6351168d8&site=vmware.mediasite.com)

[SDDC7808-S - How I Learned to Stop Worrying and Love Consistency: Standardizing Datacenter Designs](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/dfafac9a-4f90-4087-8b0b-194c6b495851.mp4?playbackTicket=634a26f821f843d29f3c7d426a5a2b1f&site=vmware.mediasite.com)

[HBC9363-S - Virtualization 2.0: How the Cloud Is Evolving the Modern Data Center](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/219e226b-a919-4eb1-8394-0983ca2f8f75.mp4?playbackTicket=42c63a0c9da2484da4e3a4c7eb895346&site=vmware.mediasite.com)

[EUC10682-S - Delivering the Digital Workspace: The Transformation of End-User Computing](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/7e7da282-3138-4332-97f6-3b842130fd37.mp4?playbackTicket=a0f8c38e5ed84bd085b088230f577985&site=vmware.mediasite.com)

[CNA9993-S - Cloud Native Applications, What it means & Why it matters](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/78332728-0f36-4ad3-a79d-f5af5f1e4904.mp4?playbackTicket=83425caecb1843d8af723909be86fa6f&site=vmware.mediasite.com)

[VIRT8612-S - How Travis Credit Union Virtualized Their Systems and Significantly Improved Stability and Performance](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/2131953d-b383-4d2a-8328-16c1888f3f86.mp4?playbackTicket=2099022eeeb54534a0cfc8688c84345c&site=vmware.mediasite.com)

[SDDC8618-S - Introducing VMware Cloud Foundation](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/e0912fd2-aa5a-4144-baf8-a4491af2bf13.mp4?playbackTicket=7e5db5d184f64e55891a2b951e92a08d&site=vmware.mediasite.com)

[CTO9978-S - Digital Transformation - Technology & Business Futures, A CTO's Perspective](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/b86cd48c-8ae4-47d9-ae22-9568e05e1450.mp4?playbackTicket=76f130ecbb074ce08cd516710211ddd8&site=vmware.mediasite.com)

[INF9947-S - Spotlight on vSphere: Today, Tomorrow, and Beyond](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/5d6fa026-80f4-4879-ab77-b14866636186.mp4?playbackTicket=54eec78309e04d48b3a7bdd78c7c4278&site=vmware.mediasite.com)

[SDDC9035-S - SDDC and Hyperconverged has Arrived â Get on Board!](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/16009f16-157c-494c-83db-c36344096943.mp4?playbackTicket=3ac1b2063cf942d290aae162ad681b47&site=vmware.mediasite.com)

[STO9424-S - Taking HCI Mainstream](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/192fe167-453f-4961-b241-df10a01f9202.mp4?playbackTicket=ae1b42ff2aa948589c5df7654ea990b9&site=vmware.mediasite.com)

[INF8396 - Winter Is Coming. Are You Dev/Ops Ready? Instant Clone Is!](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/1414f2a7-ffa3-41b5-bcd4-75c2af91c84c.mp4?playbackTicket=63d38bc99adc4979881b927bf8452536&site=vmware.mediasite.com)

[INF8755R - Troubleshooting vSphere 6: Tips and Tricks for the Real World](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/2e2bb9f5-1de5-4bf4-9489-d9d71cb49a83.mp4?playbackTicket=e9d7f684ba2f495b96d52acca0424d1e&site=vmware.mediasite.com)

[INF8845 - vSphere Logs Grow Up! Tech Preview of Actionable Logging with vRealize Log Insight](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/07b71600-0b14-42a3-a516-16704a61407e.mp4?playbackTicket=0f0c208ff0894abd9dd65850ac86b7f5&site=vmware.mediasite.com)

[INF8038r - Getting Started with PowerShell and PowerCLI for Your VMware Environment (Copy)](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/1d06701d-6bd1-44c8-be5f-94b0ba8ab40f.mp4?playbackTicket=80e737550d1d432fb47689c3bc2aeecc&site=vmware.mediasite.com)

[INF8631 - VMware Certificate Management for Mere Mortals](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/0875c252-9193-4999-967a-b89d71ceafb8.mp4?playbackTicket=8b004d517c324f878821e3d2be4ec612&site=vmware.mediasite.com)

[INF8374 - Zero Downtime, 20K+ VMware vSphere 6 Upgrade](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/32cdada2-55ef-403c-a276-52b0fd97b861.mp4?playbackTicket=af7c5f948fdd4c2a92f1433428b31a3b&site=vmware.mediasite.com)

[MGT8040 - Turning Up the Noise: How VMware's Private Cloud Team Is Getting Closer to the Heartbeat of Its Infrastructure, Billions of Events at a Time](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/4e300c36-f458-4ffa-978d-fa17470b1857.mp4?playbackTicket=bf13f9c1427c4c7290e73d4baf04ff40&site=vmware.mediasite.com)

[INF8379 - Virtualization 101](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/93da5bc3-3dd3-443a-81f7-1d580b3d8c52.mp4?playbackTicket=cb057b2acb514d4a961b6ef9d95ccdbb&site=vmware.mediasite.com)

[INF8251 - vSphere Host Fabric: Why It Matters to You?](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/80fa3989-6846-446a-89d6-4c29c49043be.mp4?playbackTicket=df7e5c2e9d834da8818dd360d77976dd&site=vmware.mediasite.com)

[INF8108 - Extreme Performance Series: vCenter Performance Deep Dive](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/51ff8ada-1fd4-402c-8648-79c640e6c5cd.mp4?playbackTicket=a1515917368e4f7296d4aa3fc34fa4df&site=vmware.mediasite.com)

[INF8045 - vSphere High Availability Best Practices and Tech Preview](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/52a4b2b1-5c3b-4eec-89cf-2839cb1d1d5e.mp4?playbackTicket=c5d66e2f695748cbacf762f10e7215bf&site=vmware.mediasite.com)

[INF8375 - What's New with vSphere](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/80d4642c-9da5-45de-bc0d-414139f72c7a.mp4?playbackTicket=c2bbc5a6642c4420be705aba6dbfe7e7&site=vmware.mediasite.com)

[INF8371 - How Did the Private Cloud Transform VMware IT?](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/130b3d4a-2847-43ef-a006-1cf2618c4f96.mp4?playbackTicket=f005fb8bdbb54075a56207548a4a3d38&site=vmware.mediasite.com)

[INF9144 - Through the Looking Glass:  An Overview of the vCenter Server Appliance Management Interface and API](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/849650f4-893a-44cb-8051-a65f02f5c892.mp4?playbackTicket=cefa45f4c1484efd9289bc594a26f415&site=vmware.mediasite.com)

[MGT9997-SPO - How to Automate Cloud Operations with vRealize and NSX Featuring Lessons Learned from Deluxe Corpâs Transformation](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/6e8217e6-de61-4fe4-bab6-1173d531c231.mp4?playbackTicket=b181a5d1ccfc4e80876f758ade1dc84e&site=vmware.mediasite.com)

[INF8858 - vSphere Identity: Multifactor Authentication Deep Dive](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/fba352fa-976b-4391-a406-afb4e650932f.mp4?playbackTicket=d2a48b25f1b7457493eda230bd971732&site=vmware.mediasite.com)

[INF8683 - Understanding the Role SNMP Agents Play in a vSphere Stack](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/896be611-932c-46e2-a864-bab90d7908a2.mp4?playbackTicket=91a3d5e7bc584ff896eb1c10f18b7b6f&site=vmware.mediasite.com)

[INF9048 - An Architect's Guide to Designing Risk: The VCDX Methodology](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/5cc8a552-e12b-4701-b52d-6b35dafc21ee.mp4?playbackTicket=5c7429a557344bf483ff4a2babd1d25b&site=vmware.mediasite.com)

[INF8469 - iSCSI/iSER: HW SAN Performance Over the Converged Data Center](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/1ac81c00-a233-479f-a457-b2d4330979a6.mp4?playbackTicket=d6e8bd5007904264b49385349d8d8a57&site=vmware.mediasite.com)

[INF9089 - Managing vCenter Server at Scale? Here's What You Need to Know](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/1d92dafa-054d-44aa-8722-91749035c509.mp4?playbackTicket=e902de8f222f4f77b0f887df5b6ba371&site=vmware.mediasite.com)

[INF8250 - Case Study: Using vCloud Suite to monitor Global operations](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/87e2cf5f-b458-4e41-91b9-980c6c8442b4.mp4?playbackTicket=c18dbe031b43410a80e4f9d61b54c0dd&site=vmware.mediasite.com)

[INF9608-SPO - How to Use Machine Learning to Increase Application Availability](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/3dce78c7-e4ff-40a2-b53c-5f5dfe3aee3d.mp4?playbackTicket=c5ed50cecf7b4a96a1fcf4a88037b7f0&site=vmware.mediasite.com)

[MGT8884 - Our SDDC Journey - See how SDDC transformed IT in just 12 months and changed how we think about âautomationâ at Johnson & Johnson IT.](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/5cbf0bfd-4caa-49d3-8804-44eb61cf0d67.mp4?playbackTicket=620a0ccf440543b5b2b816a74cc7a8c4&site=vmware.mediasite.com)

[INF9944R - What's New with vCenter Server](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/5b06226a-d1fc-475b-bf2a-d79edaa1fd77.mp4?playbackTicket=76b2d62920664398857e535617e1e536&site=vmware.mediasite.com)

[INF8939 - Virtual Machine and Application Protection Demystified](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/a47bb7b8-484f-4bdd-9115-9cb6bb86edb0.mp4?playbackTicket=b134113fff8d4d50817fe8852cab1026&site=vmware.mediasite.com)

[INF9205R - Troubleshooting vSphere 6 Made Easy: Expert Talk](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/8a9b1309-a70b-4f1f-b87d-a58247c65bb1.mp4?playbackTicket=1dfd5bcf2f4542cab164571ed0b142fe&site=vmware.mediasite.com)

[INF8117 - Why Fiserv Deployed Auto Deploy and Why You Should as Well](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/bd847eff-60cf-44c3-aea9-ea05333ed432.mp4?playbackTicket=4e58590f3dc04d1089e2dfe5c1c2a4a7&site=vmware.mediasite.com)

[INF8959 - Extreme Performance Series: DRS Performance Deep DiveâBigger Clusters, Better Balancing, Lower Overhead](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/c1649510-b8f7-40c7-b9aa-df5ae530afa6.mp4?playbackTicket=f698506bf4cf48ac866841f53750bf23&site=vmware.mediasite.com)

[INF9205R - Troubleshooting vSphere 6 Made Easy: Expert Talk](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/c1e0bef8-9d01-4d01-8f77-d33d4e6acbc3.mp4?playbackTicket=40bcbe9e721545bf947895c07330ed6a&site=vmware.mediasite.com)

[INF8780R - vSphere Core 4 Performance Troubleshooting and Root Cause Analysis, Part 1: CPU and RAM](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/26a2ed3a-0923-4b30-86e7-2f2ff0d7a7d0.mp4?playbackTicket=d3891dc62a824b8989bb97bab9585fbe&site=vmware.mediasite.com)

[MGT8714-SPO - Creating Automated Self-Service Data Protection with Rubrik and vRealize Automation](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/8fade289-f6b9-47ab-9dc8-a6b2d31f7fa5.mp4?playbackTicket=71a9dacdb68f498b85adf965f4151780&site=vmware.mediasite.com)

[INF8644 - Getting the Most out of vMotion: Architecture, Features, Performance and Debugging](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/7efd9285-c17e-4bad-8086-184e8f8a379d.mp4?playbackTicket=1f7f3399b90a49489eb25812e774fdd8&site=vmware.mediasite.com)

[INF8097 - Production Is Down and So Are My Tools: Meeting Infrastructure High Availability by Deploying an Out-of-Band Management Cluster, A Customer Evolution](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/a782976f-139c-42b9-9eb4-764c5676fe23.mp4?playbackTicket=c78dc606fe934d7d9c10636c3aac47f4&site=vmware.mediasite.com)

[INF8122 - A Storage Story: Capacity Management and Performance Planning for Storage Systems in vRealize Operations](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/c0c3db6d-a0b6-4a93-8a36-0c2c1aaa19a0.mp4?playbackTicket=3fe766932b454aad80308abad8b2f9e1&site=vmware.mediasite.com)

[INF8038r - Getting Started with PowerShell and PowerCLI for Your VMware Environment](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/3e0c884f-e6aa-4a0c-84f0-995603b60b53.mp4?playbackTicket=e3fca3b47fde47d28b6159833ac60897&site=vmware.mediasite.com)

[INF7818 - Take Virtualization to the Next Level](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/c3681486-24d1-4bd3-9fd3-2a0d54f2f8d4.mp4?playbackTicket=b38a385fcd664487982fab5648924db9&site=vmware.mediasite.com)

[INF7825 - vSphere DRS and vRealize Operations: Better Together](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/972faeb8-cae6-4cd4-85ae-8d5ddca1388e.mp4?playbackTicket=6e494ba25e27474b9933f95f24d0d724&site=vmware.mediasite.com)

[MGT7713 - Intelligent IT Operations Management from Infra to Apps, On-Premises and in The Cloud](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/ad09d498-3d1c-403c-8a99-030c80ce424d.mp4?playbackTicket=a92f02d630d647479bd43ce8d5457bbd&site=vmware.mediasite.com)

[INF8459 - VMware Security: How to Meet Your Compliance Objectives Using Cool Technology](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/97816611-dc29-4787-968f-0e02609bbaf9.mp4?playbackTicket=89fb86af79464e658c7b703d7934d5ab&site=vmware.mediasite.com)

[INF9151 - Getting to Zero: Zero Downtime, Zero Data Loss with vSphere Fault Tolerance](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/10afe696-10aa-454a-a088-4549715fdbaf.mp4?playbackTicket=62b84f4fa03f4a0a9f55e27f87b52b6f&site=vmware.mediasite.com)

[INF8275R - How to Manage Health, Performance, and Capacity of Your Virtualized Data Center Using vSphere with Operations Management](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/c3b67aa0-0279-4f47-8368-ca559c477884.mp4?playbackTicket=5bb00bc9183a410f89794aa149d95e8a&site=vmware.mediasite.com)

[MGT7878r - Using vRealize Suite for Endpoint Monitoring in a Multicloud Environment (Copy)](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/f59a5194-5d66-4e50-8aca-1464801e3ef8.mp4?playbackTicket=ea1f7cfc60a64b4a8254369f192a3b69&site=vmware.mediasite.com)

[INF8465 - Extreme Performance Series: Power Management's Impact on Performance](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/c0ab1291-d2b5-4a8c-805c-034b99e12911.mp4?playbackTicket=9838d9f2368a45c1b760c1165c01e1dc&site=vmware.mediasite.com)

[INF9455-SPO - Best Practices for All-Flash Data Reduction Arrays with VMware vSphere](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/9f376add-dc21-4a54-bc33-677791e0484c.mp4?playbackTicket=354f22b9c64b499db475cab563be7fb6&site=vmware.mediasite.com)

[INF8275R - How to Manage Health, Performance, and Capacity of Your Virtualized Data Center Using vSphere with Operations Management](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/77da8677-e828-4330-a148-b536b3dc1038.mp4?playbackTicket=97f2f0b20653444cbaecaeb099fd10b3&site=vmware.mediasite.com)

[INF8553 - The Nuts and Bolts of vSphere Resource Management](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/441d46cf-46a9-43e8-94ac-b43871205fbe.mp4?playbackTicket=9f7c02efcb244b84a96687f568ad5947&site=vmware.mediasite.com)

[INF9205R - Troubleshooting vSphere 6 Made Easy: Expert Talk](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/c2161de5-790a-484f-a931-435ef9f33fe0.mp4?playbackTicket=6bb0f6840c9944ee895b6c42922f0c87&site=vmware.mediasite.com)

[INF7578 - A Cloud Service Provider's Success Story: Adoption of vSphere with Operations Management](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/ec08d346-515b-40dc-89d2-c6e22e94ad5d.mp4?playbackTicket=ffb2a986c99244c4adce2b230f13be34&site=vmware.mediasite.com)

[INF8663 - The Making of a Legend-Dairy Software-Defined Data Center](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/92835196-98e6-48c7-8c7c-189fc011ad7e.mp4?playbackTicket=b6121fcdd1734cce8d6b0919c4259e2e&site=vmware.mediasite.com)

[INF8260 - Automated Deployment and Configuration of the vCenter Server Appliance](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/b5edbdd6-355e-410e-857a-c6aeb77772cf.mp4?playbackTicket=6a90094eb273422ca5632babc8a617a7&site=vmware.mediasite.com)

[MGT7878 - Using vRealize Suite for Endpoint Monitoring in a Multicloud Environment](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/607168d1-d433-4bc2-9c56-65fdda283d92.mp4?playbackTicket=215b699d543044b2a0b0451d315fc943&site=vmware.mediasite.com)

[INF9944R - What's New with vCenter Server](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/b5b5b563-4599-4226-8216-dab3d82f8ad2.mp4?playbackTicket=61702a5be5854703999716ccce36101f&site=vmware.mediasite.com)

[INF8850 - vSphere Platform Security](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/248ea383-bc5e-4cf8-8ff1-0cb30f4700d7.mp4?playbackTicket=86d9cff28f9d411fbdc21dbb017ea4c9&site=vmware.mediasite.com)

[INF8780R - vSphere Core 4 Performance Troubleshooting and Root Cause Analysis, Part 1: CPU and RAM](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/0f7b9a5f-e1b6-419f-8478-20e17766eb9a.mp4?playbackTicket=560f2af1cbb8487fb56c0e97a5afa2f7&site=vmware.mediasite.com)

[MGT8439 - Lessons Learned from EMC IT's Data Center Evolution](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/abdb85ef-c635-4d99-b99b-be0cc2470498.mp4?playbackTicket=2d5c1a8a4b954ab7ba43efd5741163ff&site=vmware.mediasite.com)

[INF8277-QT - Dear IT, You Can Be a Strategic Partner to Your Business. Let me help. Yours Truly, vSphere with Operations Management.](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/242ae00e-ad21-46d2-b947-6a1d6a16f385.mp4?playbackTicket=85ca6ba13f6d4be784e8f6485efc9f3b&site=vmware.mediasite.com)

[INF8516-QT - VMware Security: The Whole Is Greater than the Sum of Parts](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/a3d798c2-1e61-4d71-98bc-fe8715b37e95.mp4?playbackTicket=a1f0a79cd31541028f6f915188e4c852&site=vmware.mediasite.com)

[MGT8543 - Simpler Extensibility in vRealize Automation 7.0 with the Event Broker](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/ccfa56d7-b98d-4904-b14d-70fdca584e6d.mp4?playbackTicket=1cede7bc9b5840d9b7f38fdf7c1f2e05&site=vmware.mediasite.com)

[MGT7770 - Virtual SAN Management â Time to Level Up Your Ops Game!](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/f8c014e7-debb-44d8-a257-fb6d3c14e4d8.mp4?playbackTicket=95f9b4f919fc4198b4da1948830cae4a&site=vmware.mediasite.com)

[MGT7751R - A Technical Deep Dive into VMware Integrated OpenStack](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/31a9a081-27ea-406b-b18d-795534077f0c.mp4?playbackTicket=dde3b2b7acdd460ab8fc6dc7222ae252&site=vmware.mediasite.com)

[MGT8080 - vRealize Reference Architecture: Design, Deploy, and Realize Value at High Speed and Amaze Your Customers!](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/7bdbd96d-3bda-4c18-84aa-fdacd8feb6a7.mp4?playbackTicket=19f95b352c6042d98cc393c4ad2203e1&site=vmware.mediasite.com)

[MGT7751 - A Technical Deep Dive into VMware Integrated OpenStack](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/f412aace-2825-4442-8c32-1791f9a73372.mp4?playbackTicket=fa77115d227d4d6089873fba1e6e8c14&site=vmware.mediasite.com)

[MGT7685R - Insight into the World of Logs with VMware vRealize Log Insight](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/25044a08-8221-4c08-b257-158ee0c8e9f2.mp4?playbackTicket=4010baa2764743529d1e2e01171dbd39&site=vmware.mediasite.com)

[MGT8770 - Managing Microsoft Azure with the vRealize Suite](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/e3475598-2380-4bde-9a5d-59b4e843902d.mp4?playbackTicket=a4ed8e374254417e80b2b9472654eed0&site=vmware.mediasite.com)

[MGT8641R - A Lot of Insight and No PowerPoint](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/96abe8b8-77dc-4dbd-8b56-e2b77711a6df.mp4?playbackTicket=5ea78eac0dfd47158f6adbe18dcde210&site=vmware.mediasite.com)

[MGT8085 - Save Time With Everything and Anything as a Service (XXXAAS) using vRealize Automation (vRA)](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/206c7998-f064-4fdb-8fca-26aa8ca5a0ec.mp4?playbackTicket=c893bb38f7154a9fab8da5b48fd92d00&site=vmware.mediasite.com)

[MGT9184 - Day 2 Automated Operations with vRealize Automation 7.0 and the Event Broker Service, a Deep Dive.](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/5bfd6c00-bba2-4096-91de-b0026d37b4fe.mp4?playbackTicket=2ed232ecaf1641d2a2d657244339e2d0&site=vmware.mediasite.com)

[MGT8641R - A Lot of Insight and No PowerPoint](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/c84773f2-c8df-45a4-ad6b-e5391348a700.mp4?playbackTicket=c6c05798a1c3475d8a6c9624a45d7ef0&site=vmware.mediasite.com)

[MGT9948-SPO - Itâs Time to expect more from your Virtual Environment](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/9cec6924-b24b-4ac8-8a29-b60ccb52f4dc.mp4?playbackTicket=a975d0dc916a44cf8d15a0e47ff5b4b6&site=vmware.mediasite.com)

[MGT9426-SPO - Best Practices for Cloud Service Data Security](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/c215056d-5fad-4b62-9cb4-60bc5a0ba66b.mp4?playbackTicket=ef339cb3d51f4b2f92373ec2f464ee06&site=vmware.mediasite.com)

[MGT8332 - How I Learned to Stop Worrying and Love the vRealize Automation API](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/77be32ea-8175-4cb0-b638-4337b92868f4.mp4?playbackTicket=95acc808bef84879bd93419fa8f5b035&site=vmware.mediasite.com)

[MGT7685R - Insight into the World of Logs with VMware vRealize Log Insight](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/ef81101b-8ac3-432e-ac60-ef6b83a5b33b.mp4?playbackTicket=7ff77667bca14af8a6473cdfc03edcce&site=vmware.mediasite.com)

[MGT9457 - Understanding the Value of vRealize Network Insight](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/88c36b95-83b1-47c5-b923-de4d18d63147.mp4?playbackTicket=be543f0f6a6147688b5b947e36966f33&site=vmware.mediasite.com)

[MGT7899 - Whose Hand Is in the Cookie Jar? Reducing the Mean Time to Innocence Using vRealize Operations](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/9aa1417e-fb35-4e49-a7fc-e49f736d6c24.mp4?playbackTicket=2b018aafb9384d49a119269bfb55a12d&site=vmware.mediasite.com)

[MGT8733R - Application Self-Service with On-Demand Networking & Security from vRealize Automation and NSX](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/e2c595c5-4ae1-4136-8860-b5f2c51ceb19.mp4?playbackTicket=b3a50dedb192478b877b4a2e6cbb1e3c&site=vmware.mediasite.com)

[MGT8486 - NSX Operations with vRealize Suite](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/a02aac83-8f99-46ee-b845-bc7ff2d9598b.mp4?playbackTicket=99421123a0fd4e60a046d56ff0c94807&site=vmware.mediasite.com)

[MGT9615-SPO - vRealize the Possibilities:  Application Agility and Rapid Deployment with vRealize Automation, Orchestration, Operations and Log Insight](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/1770c354-0e4d-45d9-a6c0-fca5fde01633.mp4?playbackTicket=e11cabf8695f45d9bd18496ff34eef28&site=vmware.mediasite.com)

[MGT7671 - What's New in VMware Integrated OpenStack Version 3.0!](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/57f8f101-cd2b-4052-9f8e-b310d94a0ea1.mp4?playbackTicket=43219944ccb2437e89f3613c4bd6c353&site=vmware.mediasite.com)

[MGT8763 - 3 Best Practices for IT to Enable Developers to Deploy on Amazon and Azure While Ensuring Security and Accountability](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/02a5f93e-1703-4dbb-9ecc-5a21a5acb411.mp4?playbackTicket=b7f60a934b7845c1948bc3721ba42532&site=vmware.mediasite.com)

[MGT8768 - How TIAA Uses an API-Centric Cloud Management Platform to Allow Applications to Be Easily Deployed and Managed on Both Public and Private Clouds](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/df16125c-cf55-4f70-b1f0-d34ec077ab71.mp4?playbackTicket=b70a361f87a841c38d116b87778ab331&site=vmware.mediasite.com)

[MGT7629R - 360-Degree Troubleshooting](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/1b18cd73-1a3a-4a40-904a-a38c318ee006.mp4?playbackTicket=25b6a3defff041339b9f1e21f2a656d0&site=vmware.mediasite.com)

[MGT9220 - vRealize Automation and NSX Design Experts Panel](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/32f50480-5374-402b-b3a9-10cfb7d15f51.mp4?playbackTicket=d26d1a77dc0b461db8377695c375e24b&site=vmware.mediasite.com)

[MGT8807 - What's New in vRealize Code Stream](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/9002ce06-d69a-4dc3-bc32-648d1c0b9634.mp4?playbackTicket=35e47e1c03d8471a87756e1d216eb9a1&site=vmware.mediasite.com)

[MGT8762 - How to Set Up a Multicloud IT Portal to Deploy, Manage, and Control Applications on Private and Public Clouds](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/9e6ab72b-430d-4a3b-9468-27151330576e.mp4?playbackTicket=9f9fcfb1009547de912f335e03d9bc55&site=vmware.mediasite.com)

[MGT8733R - Application Self-Service with On-Demand Networking & Security from vRealize Automation and NSX](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/68f928aa-795e-4a40-a87c-c7c4cad4dc41.mp4?playbackTicket=80d11a5df33c440a91f8f52f4f8fe926&site=vmware.mediasite.com)

[MGT7737 - Intelligent Operations Management: A Customer Perspective](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/95268c27-2a95-4d78-b215-17e46517017a.mp4?playbackTicket=ce09979216ec473c9d85741d79d8b34c&site=vmware.mediasite.com)

[MGT7629R - 360-Degree Troubleshooting](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/66c85e14-7271-4af5-97ae-c3b5723f4984.mp4?playbackTicket=fb07a278f1a8431cb06a774f55ca8a66&site=vmware.mediasite.com)

[MGT8751-QT - Be the IT Hero of Your Company and Discover How to Save Thousands of Dollars by Reclaiming Underutilized CPU, Memory, and Disk Resources](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/fb6cfd29-e101-47e6-8e7d-3c3f515b59e7.mp4?playbackTicket=8e7a54e91a2b469da31b92c4237148a8&site=vmware.mediasite.com)

[MGT7782-QT - Automating Resource Reclamation in the Modern Data Center](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/f32d79f9-5b42-4875-a1dd-e27fb913ab4e.mp4?playbackTicket=7f0693388d2c4f2d884b8aa6247d0505&site=vmware.mediasite.com)

[MGT8355-QT - Tutorial: Build a data-driven story around capacity planning using VMware vRealizeÂ® Operationsâ¢ and third-party Management Packs](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/f0b3de0f-fcc4-4b25-a595-479987b8df61.mp4?playbackTicket=8072ce9e450449b5ad712e2e696fd364&site=vmware.mediasite.com)

[CNA7741 - From Zero to VMware Photon Platform](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/3c85b6b2-aefa-47c6-ba5c-e7a3e5298f2d.mp4?playbackTicket=4a84355372784372a3a0f445ad7f53eb&site=vmware.mediasite.com)

[CNA8986R - Running Docker on Your Existing Infrastructure with vSphere Integrated Containers](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/a459cc08-49fd-4487-8697-0a1351f1a054.mp4?playbackTicket=c94c4fa8c4ad431aa1ce6209e6ecf454&site=vmware.mediasite.com)

[CNA8313 - Your Open-Source Data Center](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/1666c675-e776-4d67-82db-135c40e81c49.mp4?playbackTicket=6e888794ff534439885bad3a8809e7eb&site=vmware.mediasite.com)

[CNA7524 - Photon Platform, vSphere, or Both?](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/d2d40873-7ad0-4272-b43d-130cbed7587a.mp4?playbackTicket=a73f938b41f24289acb239a0af6b5952&site=vmware.mediasite.com)

[CNA8578 - VMware Private Cloud and Containers in Production: Lessons Learned from a Real-World Deployment at Retailer Otto](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/f3e7ddd3-9397-4bf0-846d-ce83323d80b7.mp4?playbackTicket=22d15750b7cd48b880f9ae71ec78b2db&site=vmware.mediasite.com)

[CNA8145 - From Today to ''CNA'': VMware Technologies and DevOps Frameworks as a Service](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/e4e498af-e8ce-49d3-8a00-4d205692d12b.mp4?playbackTicket=66e57c8b2a644864a26a19b4e648899a&site=vmware.mediasite.com)

[CTO7964 - Cloud Native Buzzwords (Demystified) for Dummies](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/ecd734f3-6c76-4c6c-afbe-1613fca1a917.mp4?playbackTicket=2de28e7588ef4d37a0ed740a83c28514&site=vmware.mediasite.com)

[CNA8986 - Running Docker on Your Existing Infrastructure with vSphere Integrated Containers](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/0a23fdc4-ddbf-4e8b-adde-4668538a5c10.mp4?playbackTicket=5878e426a66c4db4b4e042e69154bc18&site=vmware.mediasite.com)

[SDDC9462-SPO - The Edge is Still Bleeding: A face-melting technical smorgasbord of all things Converged, Hyper-Converged, Cloud Native & Software Defined](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/a18e8431-7d10-4c51-85ba-0470c76df70a.mp4?playbackTicket=a75a7e753b6341038687447f1d59202c&site=vmware.mediasite.com)

[MGT7804 - Container Management with vRealize Automation](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/53af543f-d537-42a2-ab25-44c520c412e3.mp4?playbackTicket=e66f67ba3f53457380df34b7078fc4f1&site=vmware.mediasite.com)

[CNA8897 - Continuous Integration and Continuous Deployment for Containers: Confidently Promote Your Code into Production](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/6e8a6150-3771-428a-b01c-33c01f30366f.mp4?playbackTicket=75e7bd0d00624368a02c81ca11214126&site=vmware.mediasite.com)

[CNA7454 - Introduction to Containers as a Service](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/c00a93e3-64d8-4672-b049-cc47c9fd57c4.mp4?playbackTicket=0d1838cde69745ad8dacc9b1f564ba17&site=vmware.mediasite.com)

[CNA9994-QT - VMware's Cloud Native Stack](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/0e51cd9b-cf8a-4a81-8a22-a9f7722aab57.mp4?playbackTicket=69718b4c395d4ac3bb2aece51a319855&site=vmware.mediasite.com)

[STO9984-QT - Business-Critical Applications for Virtual SAN](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/81cbad16-bc19-43dd-91f1-fb985fc0c09e.mp4?playbackTicket=64d9484d34b74a28b28056bf85019e44&site=vmware.mediasite.com)

[DEVOP7915 - Network as Code: DevOps Implications of Programmable Infrastructure](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/451f8d95-0e35-4d4a-9e06-c013217edc05.mp4?playbackTicket=d45fdc90e11a4fa6973cc8b547f10391&site=vmware.mediasite.com)

[INF8255 - Evolving the vSphere API for the Modern Era](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/fa25d2c4-fc32-43b4-bb5c-c2767bf10b7c.mp4?playbackTicket=7e46e6866fcb48bbaaebe6f25221bafc&site=vmware.mediasite.com)

[MGT8969 - Forrester Research POV on DevOps, Automation, and Virtualization Maturity Trends](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/c6d2d4f4-6465-4c3a-a9dc-5c878a50eda0.mp4?playbackTicket=52ba6070a5d84cbf83cebe15a0d05e03&site=vmware.mediasite.com)

[MGT8499 - Moving to Infrastructure as Code: How Fannie Mae Is Managing the SDDC with the vRCS Management Pack (aka Project Houdini)](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/39c21296-ef06-400c-8d13-3ce4c0da8e2a.mp4?playbackTicket=fdd7851afa434e9d83c20d1225a6e88b&site=vmware.mediasite.com)

[DEVOP9403-SPO - Hacking Your Backups: Making Your Backup Data & Systems Work for You](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/52479be8-d8f4-4551-9d8e-0b40dd2a2922.mp4?playbackTicket=7fdca0572445496db06e521c5f24c73d&site=vmware.mediasite.com)

[DEVOP8924 - Building an Actionable Strategy Around DevOps and Platform as a Service (PaaS)](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/e3282a09-3b57-4119-a7a9-11d156262b62.mp4?playbackTicket=a9756fee8b454d95bba168bba5b11d70&site=vmware.mediasite.com)

[NET7858R - Reference Design for SDDC with NSX and vSphere: Part 2](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/878a7c6a-c7e9-46c4-ba78-d91c10d868da.mp4?playbackTicket=6d7519e494384134b969370fde7d5cf2&site=vmware.mediasite.com)

[DEVOP8971 - Run a Hybrid Application Across VMware and Google Cloud Platform](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/1a9e5995-9f83-4164-8471-94f38d614dc9.mp4?playbackTicket=20178364c6fa44428ab3614186c0649a&site=vmware.mediasite.com)

[MGT8831 - Digital Transformation Through VMware DevOps Code Stream](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/53468bae-c764-4a76-a765-7c975389a135.mp4?playbackTicket=6d1c635c43074a5d88b829d873e195a4&site=vmware.mediasite.com)

[DEVOP7859 - Real-World DevOps Customer Panel](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/26df095b-709e-4221-a6ca-4226bcdf3fb3.mp4?playbackTicket=fa935ca4335f462ea2ccee40a95b0466&site=vmware.mediasite.com)

[DEVOP7730 - DevOps Bootcamp Actual](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/dff45cf0-51e3-43af-afa0-d9810177f42e.mp4?playbackTicket=6f1b38012fbe4c178abd277be17c7140&site=vmware.mediasite.com)

[DEVOP9965-SPO - Implementing DevOps with VMware vRealize and Cisco UCS](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/725fe6a3-9cab-449c-afe3-560a589fd8b6.mp4?playbackTicket=86d58567f6dd46cc9aaf213f785d3141&site=vmware.mediasite.com)

[NET8368 - Network as a Service (NaaS) Transformation with NSX](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/212c06af-c61c-46e9-9424-18cb32fbc742.mp4?playbackTicket=995eb1244d654aeba694929499afb762&site=vmware.mediasite.com)

[INF8540-SPO - Say Yes to vRA and vRO in a Real-World Hybrid Cloud](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/485b49c9-7428-411f-bded-d80dee1739bc.mp4?playbackTicket=bfda0ea767da4198931c03d461a6df21&site=vmware.mediasite.com)

[NET7858R - Reference Design for SDDC with NSX and vSphere: Part 2](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/9e2db62c-0e26-4abe-8be8-47dbf9923a22.mp4?playbackTicket=938ff109bf0c45d2956958439bab6a80&site=vmware.mediasite.com)

[DEVOP7788 - Industry Perspective: Enterprise Reality of Doing DevOps](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/602f7c97-9082-4bc4-ada1-6c6afb1f1361.mp4?playbackTicket=e185fe54569b4b9a9d0e7e0b97339a1a&site=vmware.mediasite.com)

[DEVOP7674 - vRA, API, CI, Oh My!](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/d6743640-1d0c-4ef0-849f-bab15f0268dc.mp4?playbackTicket=4c959febca2646caa528d201cfcfd96d&site=vmware.mediasite.com)

[MGT8766 - How IT Can Enable DevOps and Development Teams to Rapidly Deliver and Iterate Robust Applications in a Multicloud Environment including VMware, AWS, Azure and Softlayer](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/4eab316d-ace5-4486-a642-84e4c5811671.mp4?playbackTicket=3cf488bddcb6435abac1851b1a5377fa&site=vmware.mediasite.com)

[DEVOP7447 - Redefining Enterprise Resource Planning Using vSphere 6 and Workspace ONE](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/b68e46cc-409c-44b5-958e-36175ff360b7.mp4?playbackTicket=9f8a33e59d9f4a53a0110832d9dc5b87&site=vmware.mediasite.com)

[DEVOP8630 - Increased Employee Productivity with Enterprise-Grade Security Using VMware ITâs Managed Public Key Infrastructure Service and AirWatch](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/befc6a60-c561-4e7b-8e96-0fd3faa3064c.mp4?playbackTicket=81effb6947ba4acc83f4d089cfd51347&site=vmware.mediasite.com)

[EUC7799 - Design Horizon the Easy Way with Help from the Horizon Sizing Estimator](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/0751d0e8-46b0-472b-9c04-9ede3e382b87.mp4?playbackTicket=fce0bba7164f45b7b4685b61976dfb05&site=vmware.mediasite.com)

[EUC7562 - Cloud-Hosted Virtual Desktops and Apps: A Technical Deep Dive into Horizon Air](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/3dc80c8a-0c33-45ec-b1b1-d0813053258c.mp4?playbackTicket=e6cdd8dd208049d6a8a389efaad5625a&site=vmware.mediasite.com)

[EUC7998 - The Latest in High-Performance Desktops and Applications with  Horizon 7, Blast Extreme Protocol,  and NVIDIA GRID vGPU](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/24ffd9ea-2f2b-482c-8950-d9a117c0a5c0.mp4?playbackTicket=819db67e6c4e43e7873469b1fef8baa8&site=vmware.mediasite.com)

[EUC9392 - Expand Your Enterprise Mobility Strategy with VMware and the AirWatch Partners](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/3cdeaa04-4ff3-45aa-8aa7-f7d87786a5a4.mp4?playbackTicket=67ad29d8e66445ee81e44d232979b6f8&site=vmware.mediasite.com)

[EUC8938 - Limitless Learning: Leveraging VMware Technology to Provide a Digital Learning and Working Environment for Every Student and All Faculty and Staff](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/2c9d47f7-c4db-4509-b8f0-ddc90df7392c.mp4?playbackTicket=fcee2ea8e71c47d68353dca5c6ef64b6&site=vmware.mediasite.com)

[EUC9386 - Whatâs new with Workspace ONE: Identity meets Mobility](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/0d8d5f67-6515-4e9c-aac3-6b2cc895f0f1.mp4?playbackTicket=40369d2bb7254644acbc1312c35bed95&site=vmware.mediasite.com)

[EUC7870 - VMware's Solution Strategy on Mobilityâs Evolution to Internet of Things into 2016 and Beyond](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/c87ab1e1-d61a-4953-8911-727c2b99c86c.mp4?playbackTicket=4b41ccc33b9b4afc98ff6ba32379a37c&site=vmware.mediasite.com)

[EUC8243R - Troubleshooting 101 for Horizon](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/f8a2493b-71cd-4671-9dca-bfd0807770f5.mp4?playbackTicket=c6429f9850324dafb6aa7544ce2d0988&site=vmware.mediasite.com)

[EUC7644R - Unify Endpoint Management Across Mobile and Desktop](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/ff9b9d5c-3dca-41b2-ab2c-7c42ea7672d1.mp4?playbackTicket=c3d741b447844a36a0a434d717b3fffe&site=vmware.mediasite.com)

[EUC8160r - Discover AirWatch: Enterprise Mobility Management](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/7cefde1a-fe78-46b5-9bf3-7d976f8fcc80.mp4?playbackTicket=ea29a6098b7141aa915e0d0b0ebf1ce9&site=vmware.mediasite.com)

[EUC8853 - Taking Back the Desktop](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/67a58451-7ada-4136-b115-c43e7db21415.mp4?playbackTicket=999c4cedb41a4841a931aec973d178cf&site=vmware.mediasite.com)

[EUC8346 - Modernizing and Mobilizing Retail IT](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/d4bc8d91-2cd0-43f0-993d-769d62815ef3.mp4?playbackTicket=bd87def7a4ce4fe49ddc672e38dcefd2&site=vmware.mediasite.com)

[EUC8725 - Everything You Need to Know About Horizon Remote Desktop Services Hosted Applications (But Probably Do Not)](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/0d23d478-06ea-4e5b-b874-b01ccf6d5dfd.mp4?playbackTicket=59cd97664025428d91454bcefd1168aa&site=vmware.mediasite.com)

[EUC8521 - The Future of VMware Fusion and Workstation](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/426732dd-6b9f-42b5-ace2-a480c6947905.mp4?playbackTicket=8c3d62ea53e64e78afd9ed47edba87d2&site=vmware.mediasite.com)

[EUC7678 - Real-World Examples Using App Volumes, User Environment Manager, Mirage, and vRealize Operations to Deliver Complete Desktop, App, and User Management and Monitoring](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/551f1099-059e-40cc-9a54-23e515b78e1c.mp4?playbackTicket=1448721b705543b1ab23223907a666de&site=vmware.mediasite.com)

[EUC8822 - Case Study: Large-Scale Deployment of VMware App Volumes and User Environment Manager for 10,000 Seats](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/333badbf-1f4c-4ebb-964b-cb49b90e6e3b.mp4?playbackTicket=641c52117a794e8a9b26807c30c9f83a&site=vmware.mediasite.com)

[EUC9179 - Introducing Horizon Air Hybrid Mode: Low-Cost, Simplified Virtual Desktop and Application Deployment and Management](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/4a4e16fa-61bd-46b4-b451-f3db2851327c.mp4?playbackTicket=7736910fc37c41fc92f6248663aee9c7&site=vmware.mediasite.com)

[EUC8605 - Next-Generation Mobile Productivity with Workspace ONE Apps](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/302fee13-a6fa-4c47-ab0e-0deeb22c056f.mp4?playbackTicket=969a0b9f97bb4c97925d56ebf9ec5e5c&site=vmware.mediasite.com)

[EUC7995 - Enterprise Mobility Automation using Software Defined Data Center (SDDC): Role-based Desktop and infrastructure provisioning](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/cac0cea1-25e9-43ee-a38a-535f585f3366.mp4?playbackTicket=5948a118032a4097804854842dc5a385&site=vmware.mediasite.com)

[EUC9451-SPO - Preventing Attacks on Mobile Devices using AirWatch Integration with Palo Alto Networks](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/47bdb86a-ffb3-4698-bf1c-81c4d3de11ad.mp4?playbackTicket=40cf07ed42614ceaac441c7db80beac2&site=vmware.mediasite.com)

[EUC8345 - Mobilizing and Modernizing Government IT to Advance Missions: The Secure Digital Workspace for Government](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/9968bd24-8546-482d-b9ba-2bc1990ece46.mp4?playbackTicket=a7464893b2f7461bb298e1a46d8e2db2&site=vmware.mediasite.com)

[EUC7797 - How to Manage Personal Settings with App Volumes and ThinApp](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/345bb591-6ea5-4abf-b74f-6326b60e96ab.mp4?playbackTicket=217bf55ecb1c451c8fe68e6679464efd&site=vmware.mediasite.com)

[EUC8784-SPO - Architecting Highly Available, Scalabe and Resilient Enterprise Mobility & Desktop/Application Solutions](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/bfab2dd5-02ef-4ff4-8065-05cc2f14d541.mp4?playbackTicket=a18ff5f94ac24b1a9748bcf83cbf636c&site=vmware.mediasite.com)

[EUC8392 - Untethered Yet Secure: Technical Deep Dive on Using Horizon FLEX to Manage VMware Workstation Player and VMware Fusion Pro](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/9bce471a-b9fb-4ae6-a220-5e011b345662.mp4?playbackTicket=79a702603a2a431f839dbb4c29fdac2d&site=vmware.mediasite.com)

[EUC8648R - Architecting VSAN for Horizon the VCDX Way](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/889c34d2-5e13-464d-8c21-221d3d869f96.mp4?playbackTicket=d0917b0f5d364a9fbad0e0bcef8c447d&site=vmware.mediasite.com)

[EUC8745 - Under the Hood with Identity Manager and Office 365](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/56941882-36db-4144-ba46-3ef6f9c471cd.mp4?playbackTicket=6c1f94df6dcb43f9967a1cc8a6e2b4ea&site=vmware.mediasite.com)

[EUC7519 - Access Point: Advances in End-User Computing Remote Access](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/5801bd25-a7d3-4122-8aa6-91d609c00a8c.mp4?playbackTicket=c195052230e6447da8181640cd4487bc&site=vmware.mediasite.com)

[EUC9388 - Customer Panel: How Enterprises Are Using VMware Identity Manager to Enable Their Users to Be Productive on Any Device, Anywhere](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/d8f728a4-bfe8-4cbd-8c5c-784b6a74bc47.mp4?playbackTicket=f7cc61d4751142d6984d2cd43cd833cf&site=vmware.mediasite.com)

[EUC9394 - Horizon Air and Interconnecting the Clouds](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/58c631da-fd14-41bd-bf09-522c23b6168d.mp4?playbackTicket=2415bce0e9744d1c97d5098f3f532eac&site=vmware.mediasite.com)

[EUC9139 - NSX and Horizon Reference Design: Secure End-User Computing](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/3a14c5bf-dc3a-44eb-9128-5373d9cee5ee.mp4?playbackTicket=ccc25986ccf74ab8b783c2e136e1b89a&site=vmware.mediasite.com)

[EUC9391 - Managing Windows in a Modern Mobile-Cloud Framework](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/705317fd-7db1-4c27-942d-a50cceefa3ec.mp4?playbackTicket=833bc005447b46c9a67896e8d5cdd2a0&site=vmware.mediasite.com)

[STO7560 - Four Unique Enterprise Customers Deployment of VMware Virtual SAN](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/f9b56ed8-e637-4547-82f4-7ad1563fcbcc.mp4?playbackTicket=aca9cad1a5e14c96b78be909c1f2a317&site=vmware.mediasite.com)

[STO8754 - Virtual SAN and Horizon: Designed for Simple, Powerful Virtual Desktops](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/ae6ca51e-07e9-4a31-ba27-d33ed60ca211.mp4?playbackTicket=a9a063d1773c4cf1828eabfa14c0baca&site=vmware.mediasite.com)

[EUC9390 - Securing Against Cyber Attacks from Datacenter to Device](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/ca1ca96c-439e-4879-8cbe-2adba1a32723.mp4?playbackTicket=8b9159289a0141f6934c351448506986&site=vmware.mediasite.com)

[EUC7888 - Why Siemens Uses High-Performance Desktops with VMware Horizon and Nvidia GRID vGPU](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/e72851aa-58c4-4460-b904-68a539c6951d.mp4?playbackTicket=d4d2a38af9784790be91e2f7eab7a3ac&site=vmware.mediasite.com)

[EUC8648R - Architecting VSAN for Horizon the VCDX Way](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/8511e61a-b3b4-48e5-a0fd-e3fa562a2417.mp4?playbackTicket=d539d9ca4f24424d901dbe24dab64b19&site=vmware.mediasite.com)

[EUC9610-SPO - Optimize Storage Infrastructure for Horizon Performance](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/3b9e9aa7-9370-4154-93a3-6ebc250e4157.mp4?playbackTicket=2c127a776071411ebd6638dd95386d15&site=vmware.mediasite.com)

[EUC7611 - User Environment Manager 9: Do It Fast, Do It Right, Do It Big!](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/465fdb6d-2db1-49c5-b21d-5761066447cc.mp4?playbackTicket=c5b5ffb37627423694a1f0eebe5b6133&site=vmware.mediasite.com)

[EUC8670 - Your Digital Workspace: How to Plan, How to Start](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/b451012c-7040-450f-b346-4731125316a1.mp4?playbackTicket=de523bbbfded42e9a5a5d0f1e2f4e7c8&site=vmware.mediasite.com)

[EUC7644R - Unify Endpoint Management Across Mobile and Desktop](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/dba82114-36af-4b2a-95b8-180e151ade94.mp4?playbackTicket=ce7845b1ee8948f0b84ead832392e40e&site=vmware.mediasite.com)

[EUC7453 - Horizon for Linux Technical Deep Dive](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/3e238fd9-4693-485e-b66a-c0a545377032.mp4?playbackTicket=05dec06cf1be45b2b94bb55c97cbfc1c&site=vmware.mediasite.com)

[EUC8441 - End-to-End Security for End-User Computing](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/f972d8b3-6167-482f-82a9-72ea1107a807.mp4?playbackTicket=763a3637763b4670bfad46a0c8e7b677&site=vmware.mediasite.com)

[EUC7856 - Solve Your Citrix Problems with VMware Technologies](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/920db7a3-ccba-44e7-87bd-12b1b93f569d.mp4?playbackTicket=85024af55c734c74aaff3e970fc426a5&site=vmware.mediasite.com)

[EUC9992 - Ask the Experts: Practical Tips and Tricks to Help You Succeed in EUC](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/0332e1ad-b459-41e1-abf8-a25209832c01.mp4?playbackTicket=1029c28ff30f4888ae408c8731a2ea9d&site=vmware.mediasite.com)

[EUC8437 - Workspace ONEâs Secure App Token System (SATS) for Mobile Single Sign-On explained](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/aa848ed6-6904-404f-8cac-3350767eceba.mp4?playbackTicket=e9ff8a53c7ac418ca96cdcc703728446&site=vmware.mediasite.com)

[EUC8589 - Best Practices for Effectively Planning and Implementing BYOD Programs](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/ae245971-c6a5-4e2d-a4f4-4f85831e3944.mp4?playbackTicket=1f6a8fda042342029b394879f696826e&site=vmware.mediasite.com)

[EUC9393 - Real-time Endpoint Visibility and Control with VMware TrustPoint](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/695a0ed4-494d-40db-b04f-70337e4c5f71.mp4?playbackTicket=88d61f173ba74b44985f2e5048e4693f&site=vmware.mediasite.com)

[EUC9469-SPO - Scale, Efficiency and Data Management for EUC solutions with NetApp](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/0f441738-4956-4143-a512-5303f8ae6ca0.mp4?playbackTicket=7bf16226e1ab4b05a6270cec2c052aaa&site=vmware.mediasite.com)

[EUC9217 - On-Premises Workloads with Cloud-Based Management: Technical Deep Dive into Horizon Air Hybrid Mode](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/09a96be4-52a3-4e8b-b03e-15b93dc25c3f.mp4?playbackTicket=fbcbae36a45343129b7fd0b500989c5d&site=vmware.mediasite.com)

[STO7443r - How did VMware IT Achieve a Non-Disruptive Disaster Recovery Test in 90 Minutes for 900 Terabytes of Storage and 2000 Production Virtual Machines?](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/a04b4f51-dd0c-47e4-a2e8-4f9460a7ff14.mp4?playbackTicket=7e2dfc861cc34e97938cd7ead2b1669a&site=vmware.mediasite.com)

[EUC9160 - Secure Digital Workspace of the Future: Embracing the Opportunities Presented by Enterprise Mobility in Financial Services](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/758a3a0b-2c40-4ba7-8bf4-a6e35056ba08.mp4?playbackTicket=46a49870e7ef4b9f841af3e00086fec8&site=vmware.mediasite.com)

[EUC8160 - Discover AirWatch: Enterprise Mobility Management](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/1ce83258-307d-4813-a9a4-4a1c47fb4b78.mp4?playbackTicket=af46709231a44562a87740ffc7a09441&site=vmware.mediasite.com)

[EUC9970-SPO - 0-70 with Horizon 7](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/0fbcf7e1-009d-4ffc-914f-886253b97157.mp4?playbackTicket=7279459b7a79432881a8b32e2ae496c1&site=vmware.mediasite.com)

[EUC8990 - CSC Hyper-Productive Digital Workplace](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/42287088-fb98-46a8-97b2-6e02f72cdf1b.mp4?playbackTicket=ec4f4e7140154665917e88d70b735634&site=vmware.mediasite.com)

[EUC7601R - Advances in Remote Display Protocol Technology with VMware Blast Extreme](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/1fff7498-1519-4a87-adc9-9eda2a63eda2.mp4?playbackTicket=4077588e4dcd442cb1e8bd0102e47783&site=vmware.mediasite.com)

[EUC8584 - vRealize Operations: The Authoritative Source for Monitoring and Reporting for Horizon and Citrix XenApp Deployments on vSphere](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/c6bdf625-2bb7-42bc-a996-9a220a87af4e.mp4?playbackTicket=042406d5d7234aa49106e49e9ea24e0a&site=vmware.mediasite.com)

[EUC9389 - What Is VMware Workspace ONE?](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/6980f296-5b3a-48ed-b653-211d9c56ac57.mp4?playbackTicket=8d30e16e9b294384900cad04adfb1f03&site=vmware.mediasite.com)

[EUC9387 - Deployment Best Practices for VMware Identity Manager](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/2b083f40-2cf1-477a-998c-7409584245e5.mp4?playbackTicket=302ce898e1cd4edb86f7d7af05522348&site=vmware.mediasite.com)

[STO7443 - How did VMware IT Achieve a Non-Disruptive Disaster Recovery Test in 90 Minutes for 900 Terabytes of Storage and 2000 Production Virtual Machines?](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/356309a5-f740-4cda-bc4d-5bec22a96d82.mp4?playbackTicket=ea6c769fa7e5438cad034b200acd00bf&site=vmware.mediasite.com)

[HBC7602 - Build True Hybrid Clouds: See How Service Providers Can Use NSX to Extend Customer On-Premises Data Centers](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/38d02c53-daf4-4e0c-bcbf-b66890345119.mp4?playbackTicket=33bd4090e50c471fa21e7cb9a937c53c&site=vmware.mediasite.com)

[HBC8474 - Making It Easy to Orchestrate and Automate Your Hybrid Cloud Environment](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/799aec9e-91f7-424e-bcd3-5292e896d295.mp4?playbackTicket=849caeba54ef4f029c46639a7828f326&site=vmware.mediasite.com)

[HBC8503 - Taking VDI and Published Application Environments to the Next Level with App Volumes](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/3c07d192-efa6-41cf-8625-670210ef8037.mp4?playbackTicket=7783c57e0da44289a9e1e76aecf79585&site=vmware.mediasite.com)

[HBC9463-SPO - Data Protection as a service for your vCloud Director environment with Veeam](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/c1d161f6-d86c-4f51-bd4b-a0ac96dd163a.mp4?playbackTicket=61ee79607f8a40debf40c8eabb43851b&site=vmware.mediasite.com)

[HBC7943 - Designing a Data Center in the Cloud: A vCloud Air Perspective](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/12653315-3309-48f4-8e56-30767992e382.mp4?playbackTicket=9527b0317dc1475089f804b222a3a6c1&site=vmware.mediasite.com)

[HBC8312 - Maintaining Regulatory Compliance in the Hybrid Cloud](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/06d347aa-aac9-4df8-a124-4544d9888e29.mp4?playbackTicket=7265f3dbfb48444f9d6b7f99cdbd67d4&site=vmware.mediasite.com)

[HBC8799 - How OVH, vCloud Air Network Service Provider, Is Using NSX to Easily Onboard Workloads to the Cloud](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/91183f3f-781d-4c55-b60e-f0f5b55468a6.mp4?playbackTicket=819b2ed82a2c41bf85f75c24509f8f56&site=vmware.mediasite.com)

[HBC9171 - Intercontinental vMotion with Purpose](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/a2cbb462-5e27-4897-836d-0b3f009f2d59.mp4?playbackTicket=77ddf61bd45a4ef68579e3ac2ed5ae21&site=vmware.mediasite.com)

[HBC8484 - Data Sovereignty and Compliance Automation In The Cloud](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/4b42e505-08e0-4fec-b301-da013525f163.mp4?playbackTicket=eb5b3ed1dd19437b8865681e9997d434&site=vmware.mediasite.com)

[HBC7999 - VMware Availability for VCAN: Native vSphere Replication](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/025a6455-130f-4542-b0ca-3f9f3191c798.mp4?playbackTicket=7fbd8c9328e24341b6552a491431084f&site=vmware.mediasite.com)

[HBC8504 - Have It Your Way: Hybrid Cloud Management](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/1d006204-6f3e-44fe-b6c0-01dff52f1885.mp4?playbackTicket=51f6aebf726c4f37b1454a0d330d6cec&site=vmware.mediasite.com)

[HBC7928 - Introduction to vCloud Air Networking and Security Portfolio: A Technical Deep Dive](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/72693426-caa8-4829-888e-eac837f33266.mp4?playbackTicket=1bcc4e2b00674bc8957dd1d9ca9b8170&site=vmware.mediasite.com)

[MGT8084 - Hybrid Cloud Case study: City of New York Self-Provisioning Gateway 2.1](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/ed5da4fe-d8f5-4fd6-a5fa-923c04db8c4a.mp4?playbackTicket=c4762cacf24f419ab5c08bbc6ff95af0&site=vmware.mediasite.com)

[HBC8491 - Deep Dive: VMware on IBM Cloud Validated Design](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/2d098a0a-d6b4-43f1-b95f-e9011497d904.mp4?playbackTicket=f0d149a88ce54dc1bb7e23c60faa7ce2&site=vmware.mediasite.com)

[HBC9453-SPO - Achieving New Levels of Cloud Efficiency over vSphere based Hyper-Converged Infrastructure](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/a59122b8-3952-4ee1-81a9-781184008646.mp4?playbackTicket=ab982d46b702457d9f0f3c9e0b07499d&site=vmware.mediasite.com)

[HBC7954 - Implementing Hybrid Cloud with VMware vCloud Air and NSX: A Closer Look](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/ebef739a-a48c-4c29-829e-08943179e525.mp4?playbackTicket=b166c88c2e194f2abb8848950537cacf&site=vmware.mediasite.com)

[HBC9185 - How to Connect Your On-Premises Data Center to the Cloud](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/f6ee960d-55a7-4f01-8e70-0154aa64975f.mp4?playbackTicket=9240a3e6fed04d7eba048f36cf29a6e3&site=vmware.mediasite.com)

[HBC8861 - Getting the Most Out of Your Hybrid Cloud Service Provider](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/8bb37f93-6ecb-4c56-b4ac-fd8ef1217b15.mp4?playbackTicket=32e6f33fc5a64e41818f67eaf8303cc9&site=vmware.mediasite.com)

[HBC7830 - Virtualize, Secure, and Extend Your Data Center to the Cloud Using NSX: A Perspective for Service Providers and End Users](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/96ab1fa7-4fb1-432c-a333-6077482f653d.mp4?playbackTicket=73cbdd829e7a499188e01e11256c0e72&site=vmware.mediasite.com)

[HBC9949-SPO - Hybrid Cloud: Automated and validated VMware deployments on IBM Cloud](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/4797fd28-6cbe-4ba0-8f2f-04d837ff4a45.mp4?playbackTicket=bf121ce87ff441a1992bdf861f2fbcf4&site=vmware.mediasite.com)

[HBC9611-SPO - OnApp: your hybrid cloud delivered](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/0d345739-6ad9-46b1-a9c2-596f1935def3.mp4?playbackTicket=153b9f1c58994fed9f555504f58e63a7&site=vmware.mediasite.com)

[HBC8046-QT - Customer Onboarding with VMware NSX L2VPN Service for VMware vCloud Air Network](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/d632a06b-7662-4524-845f-4350274c1778.mp4?playbackTicket=cee48dbc4df34b5cb7980018a87c383f&site=vmware.mediasite.com)

[HBC7661-QT - Generate Revenue with vSphere Optimization Assessment (VOA) for Service Providers](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/d2d85af5-7f02-408e-8222-f9ae4e5a46c6.mp4?playbackTicket=e34741bc65ee49e698e6d912cd5e8884&site=vmware.mediasite.com)

[HBC8915 - SLED and Cloud: Is Cost Containment the Right Question?  Yes and No](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/79227b2a-7fd1-4bcc-80e7-b5879832f0d7.mp4?playbackTicket=62729e9cbeea47de936334aa07017132&site=vmware.mediasite.com)

[HBC7948 - Extending Your Data Center to vCloud Air in Less than 60 Minutes](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/a4ca518f-da7f-4103-a0c7-5efcfcd619b4.mp4?playbackTicket=0e09727b03d04475be17f57c0d9e5440&site=vmware.mediasite.com)

[HBC9111 - vRealize Operations and vCloud Air: Monitoring Your Cloud](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/f8c7643e-51a5-4c95-901f-00f21ef427df.mp4?playbackTicket=d3dacf65545149ba93502c76ec83c116&site=vmware.mediasite.com)

[HBC8805 - Extend Your Data Center to the Cloud: A Real-World Example](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/7106079c-72a7-4bc4-a587-b90f6651198a.mp4?playbackTicket=3f8e7ecc205747549ec7c06fcddaba8d&site=vmware.mediasite.com)

[HBC10827-SPO - Ensure Success of Hybrid Cloud with Amazon Web Services](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/a749a3ab-4c94-4f7b-abcb-f160de2023d2.mp4?playbackTicket=db34e4487f2d404d803ff6c77527b599&site=vmware.mediasite.com)

[HBC8295 - The VMware Journey to Cloud with vCloud Air](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/f9598f6b-9b50-4f5a-a4bb-ac2c5ed72d08.mp4?playbackTicket=0916641bdc2b4d64a8c35a816a1e963b&site=vmware.mediasite.com)

[HBC9401 - Whats New with vCloud Air](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/f53efd07-a26c-472d-bed0-ba09e4183c97.mp4?playbackTicket=db92014f05b74a07aab66a73fcd1ca7e&site=vmware.mediasite.com)

[HBC9092 - vCloud Air: Advanced Networking Concepts](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/3a1f6d3d-9236-47fc-afd3-fdc163ece69a.mp4?playbackTicket=97a9a56286f14ef392b7e45d0b9b9512&site=vmware.mediasite.com)

[HBC9065 - Better Together: vRealize Automation and vCloud Air](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/5ce767de-b2df-44ab-bf07-1df96e80670e.mp4?playbackTicket=734cb8e643ff401d97560257828dae43&site=vmware.mediasite.com)

[HBC8292 - vCloud Air Recovery as a Service (RaaS) Deep Dive](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/75913957-404b-4b52-a877-1a224fac9ed4.mp4?playbackTicket=3596ae9d863e41c896e788ea86db41d5&site=vmware.mediasite.com)

[HBC8617 - Seamless Security and Compliance in a Hybrid Cloud Architecture](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/4668f565-aa7c-4d04-9219-fa3f2011ea13.mp4?playbackTicket=66d530a87871442cbb9890596b816d41&site=vmware.mediasite.com)

[HBC9164 - Modernizing Healthcare IT with the Public Cloud, Your Way!](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/aa5252bd-f68e-479d-ba82-511a81ad36c2.mp4?playbackTicket=a439e58b9776487f8bece689a8708674&site=vmware.mediasite.com)

[HBC8952 - vCloud Air Design Patterns for Design, Implementation, and Operations](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/0d6a0dad-c682-4206-b611-ecd00d37e0ed.mp4?playbackTicket=69d402c2ca354356a18a90926c0b8990&site=vmware.mediasite.com)

[HBC7646 - St. John's University Leverages vCloud Air Disaster Recovery for Its Critical ERP System, Banner](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/9931795e-75c4-4278-844a-4e81e1589523.mp4?playbackTicket=5721af2f4c0845d580d5385b3e776093&site=vmware.mediasite.com)

[STO8164 - Benchmarking VAIO-Integrated Caching. Is it Really Faster? How Much, and Why?](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/946b3b60-7277-4823-8a43-8e657619c1e2.mp4?playbackTicket=5cfcf3cbd8d84e8ca035accc3273a808&site=vmware.mediasite.com)

[STO7973 - Architecting Site Recovery Manager to Meet Your Recovery Goals](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/145853e6-414b-40d3-9064-3c6258b2c562.mp4?playbackTicket=7be0dabeac31447ba58417be3ec2e4f8&site=vmware.mediasite.com)

[STO8422 - Virtual Volumes: Why?](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/c7322870-0548-49d7-8898-70fa369c71dd.mp4?playbackTicket=b0ed9654478a4989b601990d68abcddc&site=vmware.mediasite.com)

[STO7848 - Virtual SAN Storage Efficiency Technologies](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/51d8e968-a14a-4fd6-9a70-78eea373aa51.mp4?playbackTicket=3e471e9b6eb74651b53c8fba276cb07c&site=vmware.mediasite.com)

[STO7549 - Achieving Agility, Flexibility , Scalability and Performance with VMware Software Defined Storage (SDS) and Virtual Volumes for Business critical databases](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/5d219294-dd04-4027-b8d3-e1d97bc4c07f.mp4?playbackTicket=48fd3827fa9641b39bc25643fca6626f&site=vmware.mediasite.com)

[STO8246R - Virtual SAN Technical Deep Dive and Whatâs New](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/6bc53227-80fd-40bf-9fa2-72f6dec72e4a.mp4?playbackTicket=9e3d04045b6a4453b10cafb84781e05b&site=vmware.mediasite.com)

[STO8619 - Transitioning to VVols: Partner Panel](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/3bbc94f5-0e4d-4eb1-b446-22846fc5fd8d.mp4?playbackTicket=c3f195af560c46bfb72462384ad2945e&site=vmware.mediasite.com)

[STO9925 - Enterprise-grade data protection for Virtual SAN with EMC Recoverpoint for VMs](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/cd4506da-6b6d-4fda-ac49-d32df4784c4d.mp4?playbackTicket=1884526a4e964ef0b2086e58e16b00a0&site=vmware.mediasite.com)

[STO7903 - An Industry Roadmap: From storage to data management](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/d39a396e-cc32-4821-ba43-67ccd49d41bc.mp4?playbackTicket=5cbc44cfa1f947f88c480d5076936ef9&site=vmware.mediasite.com)

[STO9014 - Deploying HCI at datacenter scale](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/02d2d30f-5cfa-41a3-a59b-a339bf394a61.mp4?playbackTicket=08ec0d3f013e4a99b99b3b918095da3b&site=vmware.mediasite.com)

[STO9157R - Achieving Unprecedented Availability, Security, & Cost Savings with VMware Virtual SAN and NSX](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/ffbe6fc0-a23d-434d-90f7-2c569a28943e.mp4?playbackTicket=a8608ef7829f4c3bbb3b22f88211e3e9&site=vmware.mediasite.com)

[STO8795 - Ushering in a New Era of Hyperconverged Big Data - Hadoop over VSAN](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/c9068a08-c05b-4ad7-81eb-c44b2b26bbf2.mp4?playbackTicket=ac6ad2c9d82840b49f01e84d728bcfba&site=vmware.mediasite.com)

[STO8562 - Deployable and Tactical Hyper-Converged Software (HCS) for the Battlefield](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/7dca7dbc-89a1-495b-a2be-d76e6620f8c1.mp4?playbackTicket=6c25caa3eea8479798ea3de43be0f27b&site=vmware.mediasite.com)

[STO8880 - Successful ROBO Design with vSphere & Virtual SAN](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/7fd88b7f-ac04-4d07-acd3-9729fc7e6182.mp4?playbackTicket=639ac0dc19ca480a80e4e3e0365292a7&site=vmware.mediasite.com)

[STO8750 - Troubleshooting Virtual SAN 6.2: Tips & Tricks for the Real World](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/95b66ec6-541c-4fab-a042-61481853b9cd.mp4?playbackTicket=59112732b9d549968f931c7045bd84b4&site=vmware.mediasite.com)

[STO8718-SPO - Building Next-Gen Data Protection for VMware Environments with Rubrik](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/87aa3401-c537-46b4-934c-5e4c098e5b1c.mp4?playbackTicket=80bb8171bb944e8db4316b74a1c8634e&site=vmware.mediasite.com)

[STO9423 - File Services on Virtual SAN](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/55454cf3-9e48-47a2-a9a3-2f10341456f6.mp4?playbackTicket=327d0c2a39a141bfbe353c31bdca52f5&site=vmware.mediasite.com)

[STO8246R - Virtual SAN Technical Deep Dive and Whatâs New](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/f2db2653-853b-47eb-9953-57f83aec95ae.mp4?playbackTicket=4061727c220c4d0ea0abf66eaedb5224&site=vmware.mediasite.com)

[STO8699 - Building a Business Case for VMware Hyper-Converged Software with Virtual SAN](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/b73c509d-4ed1-44d8-9c09-c2deef21b7ba.mp4?playbackTicket=56c3a83e3d4547a496e332c05f4709bf&site=vmware.mediasite.com)

[STO8204 - Cohesity & VMware: Simplifying data protection for Vsphere and Virtual SAN](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/2f498060-c1c2-485c-9ec5-b606dc5c8ae1.mp4?playbackTicket=f1506cf084784c28b142d26ac75dc2c0&site=vmware.mediasite.com)

[STO7645r - Virtual Volumes Technical Deep Dive](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/9aef4a6b-ab4a-414f-abfd-784e217e73e9.mp4?playbackTicket=5423a5d79ffc44ff851d7ae6564d1acd&site=vmware.mediasite.com)

[STO9157R - Achieving Unprecedented Availability, Security, & Cost Savings with VMware Virtual SAN and NSX](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/84b62518-6e36-4c1f-b353-15e795338039.mp4?playbackTicket=ba36220dee76441892d8c05cf188900c&site=vmware.mediasite.com)

[STO7791-SPO - Insights to success: Capitalizing on the software-defined data center with the right management and storage](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/a0db9b50-7680-4818-bf9c-2bdd5a94619c.mp4?playbackTicket=0f6b5758bf7b420d8fa758152cd5f82f&site=vmware.mediasite.com)

[STO8344 - SRM with vRA 7: Automating Disaster Recovery Operations](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/e51b5f6e-6dc8-44d8-b67d-5ad975ecb652.mp4?playbackTicket=adeaa0f9b57946458a993fcd5089c265&site=vmware.mediasite.com)

[STO8159 - Snapshots Suck: How VSAN and VVol fix all your operational nightmares](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/617fe527-34bc-43e8-91bd-2dbba4ed701b.mp4?playbackTicket=5e9def59406a4bd0b6713aff70ae9095&site=vmware.mediasite.com)

[STO9969-SPO - How Did Designer Shoe Warehouse Lace up Success With Flash-Optimized Storage From INFINIDAT?](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/0c14365f-1922-4589-974a-62c23ea6fb38.mp4?playbackTicket=fdce7f22331d429dbb72259723782907&site=vmware.mediasite.com)

[STO7831 - Storage for Cloud Native Applications](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/3a7c36a0-bfed-43a7-a2ab-9f9c6dec42a1.mp4?playbackTicket=a99abfee695f4cec896e2bdade9d779f&site=vmware.mediasite.com)

[STO9422 - Essential Virtual SAN Management](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/404c7a76-5b45-4133-b851-438c9926afa9.mp4?playbackTicket=05f5eb565f5f48f0b257462bc9f06d1d&site=vmware.mediasite.com)

[STO9449-SPO - Journey to the SDDC: The Who, What, Why and Oh No of Moving to a Modern Data Center Platform](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/abbe1b58-7dcf-46c7-a5b9-3742bb96f635.mp4?playbackTicket=5c08540b25d3445daebd914601050045&site=vmware.mediasite.com)

[STO7965 - VMware Site Recovery Manager: Technical Walkthrough and Best Practices](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/817de0e2-acb3-4bdf-bd12-0108388bca94.mp4?playbackTicket=25e751275e474ea790fd8aaedf1f8b78&site=vmware.mediasite.com)

[STO7535 - Conducting a Successful Virtual SAN 6.2 Proof of Concept](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/c65a5a6b-2419-41cd-8a3f-496bdb9e15d9.mp4?playbackTicket=94dbc1bda4b8489bbf7dbcc2cd282e9a&site=vmware.mediasite.com)

[STO9079 - Virtual SAN for VMware Service Providers](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/d0cd2969-d32f-4035-abc8-c53743c95145.mp4?playbackTicket=2acdee5126d6409783f10e313fe66394&site=vmware.mediasite.com)

[STO10801-SPO - Modernizing with Private and Hybrid Cloud: How CSC & VMware move enterprise clients to next-generation infrastructures](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/27af5e3c-a248-42e5-82cd-a273d89782d3.mp4?playbackTicket=6d2d6dbf3ca546b7bd69ac3d320909a8&site=vmware.mediasite.com)

[STO7904 - Virtual SAN Management Current & Future](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/3feebb4d-de31-40c9-8d97-42bde26aacfd.mp4?playbackTicket=32f9c9ab20fa4ad7a1ad3801c2b8d94e&site=vmware.mediasite.com)

[STO8165R - VSAN Networking Deep Dive and Best Practices](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/fa572d71-aa51-4b77-a402-0c3f7de77cdd.mp4?playbackTicket=1bd3051179ff44deae81268e03bfbcfd&site=vmware.mediasite.com)

[STO8694 - High-Speed Heroics: Array-based Replication and Recovery for VMware Virtual Volumes](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/7c7abe95-e28b-48d4-8a41-d94e53ad738b.mp4?playbackTicket=a439c7e7ede4419eaf6e1e42b42c3a48&site=vmware.mediasite.com)

[STO8923 - PowerShelling Storage to the extreme](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/10b3cc7e-cfe1-427a-a39e-ea368f3e6b99.mp4?playbackTicket=db277f5436b54b7f842c5e5e08c49e8c&site=vmware.mediasite.com)

[STO8179R - Understanding the Availability Features of Virtual SAN](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/e6bb9492-8265-4a30-8b9e-e8c7179c5380.mp4?playbackTicket=1002d224e4a24263b318621db812e4f4&site=vmware.mediasite.com)

[STO7802 - Simplifying Disaster Recovery in 2016 using VSAN, NSX and SRM](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/8cd391ca-2d58-47b6-bf48-6c0aba6ca278.mp4?playbackTicket=b768b6817a2f4985a9a45e4c70e4c3aa&site=vmware.mediasite.com)

[STO8144 - VMware vSphere Virtual Volumes in a NetApp Environment](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/c709554e-e853-45f6-a587-868b0cae18c5.mp4?playbackTicket=f99ae3580bf645e18f2346b604a68af3&site=vmware.mediasite.com)

[STO7650 - Software-Defined Storage at VMware Primer](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/ff8fe8c5-04c7-4929-a042-76938a923ae5.mp4?playbackTicket=d2e705151bff466d98ded08322019f99&site=vmware.mediasite.com)

[STO7552r - Architecting High Availability and Workload Balancing for Tier 1 Mission Critical workloads using VMware Software Defined Storage and Extended Oracle RAC](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/4bb00508-f028-4529-8d7a-1dca8a59a57a.mp4?playbackTicket=bf5a2e6583044b5495ec54dcdc221543&site=vmware.mediasite.com)

[STO8840 - Deploy Scalable Private Cloud with vSphere Virtual Volumes](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/4866bb37-d7a1-425a-b4c0-e91e38953280.mp4?playbackTicket=d13e38a2dc1046fcbc66d281e6415e78&site=vmware.mediasite.com)

[STO7557 - Successful Virtual SAN 6 Stretched Clusters](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/cac28377-f056-43e3-8e55-269a901c428f.mp4?playbackTicket=9413c6f7b6204924b7323d0485d56897&site=vmware.mediasite.com)

[STO7953 - The Future is Here:  Turbocharge All Flash Virtual SAN with Next Generation Hardware](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/81287ef0-2e1b-4129-bc3d-5de1d9edf72a.mp4?playbackTicket=6bd5a9bbf6814276997e013ad389d897&site=vmware.mediasite.com)

[STO8179R - Understanding the Availability Features of Virtual SAN](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/ca6f06cd-41c0-4d87-af99-4b825c5d54d9.mp4?playbackTicket=43e650f1c6004ea69d777325f1e3cf2d&site=vmware.mediasite.com)

[STO9058 - Evolution of VMware Virtual SAN](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/67b74fb0-c717-4502-ab2d-844253ca0639.mp4?playbackTicket=c19bd4b66b3349f58cfef6c69b6d90cd&site=vmware.mediasite.com)

[STO7534 - Virtual SAN - Day 2 Operations](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/f760bfc2-3bf7-43be-9392-f9b4cd4b70a3.mp4?playbackTicket=043145f2a2dc4666bdd48965e31129eb&site=vmware.mediasite.com)

[STO9607-SPO - Running Business Critical Applications and the Software Defined Data Center on Hyper-Converged Infrastructure at the Speed of Flash](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/9229c783-b259-47fc-90e9-589761e12cd4.mp4?playbackTicket=dc6bf818db1f4dc9a6a4be8b4caffbb3&site=vmware.mediasite.com)

[STO7875 - A Day in the Life of a VSAN I/O](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/e04d9a51-2380-4ed0-af3e-54857741cfd1.mp4?playbackTicket=2f8864c028ae49d0bc74ca1c5c4a76d0&site=vmware.mediasite.com)

[STO8904 - Hardware Choices in the Software Defined World â Tips on Choosing Hardware for Virtual SAN Deployment](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/9f297417-ea36-49c4-a00d-e64e946c22dd.mp4?playbackTicket=bc100e15801240eabf45be547bcd029b&site=vmware.mediasite.com)

[STO9614-SPO - You have an all-flash Virtual SAN - what's next?](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/7a94fdf7-79a3-4b0f-974d-d0e2bac674a2.mp4?playbackTicket=df8092902507403fb69182052bafa7a3&site=vmware.mediasite.com)

[STO9054 - VVol and Storage Policy-Based Management ? Is It Everything They Said It Would Be?](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/4d7ec3ff-fe19-4773-a6c6-293a09d3b7e0.mp4?playbackTicket=5f9e4d3d0c3741c29a5a318c5186d38f&site=vmware.mediasite.com)

[STO8568 - Virtual SAN with just 2 Failure Domains](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/cceb944d-d62c-4868-9705-4a60d8e0e718.mp4?playbackTicket=5c5f94f2156c4755a6c64b552c27b8dd&site=vmware.mediasite.com)

[STO8743 - Extreme Performance Series: Virtual SAN Performance Troubeshooting](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/0e19ef18-865b-4eba-bd76-d5aae334b7c0.mp4?playbackTicket=226cd0e656f94cfca7dd5a984c619bf7&site=vmware.mediasite.com)

[STO9967-SPO - Rethinking Data Protection:  The Rise of Hyperconverged Infrastructure and Built-in Backup and Disaster Recovery](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/9fcc4072-3062-4ca9-86f8-3002c6f9e568.mp4?playbackTicket=2c431ed5dd0b4ddc800af360a1ef06a0&site=vmware.mediasite.com)

[STO9396-SPO - Real World Guidance for Implementing VMware Virtual SAN from Ready Nodes to Build Your Own](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/f340d793-566e-494e-a74e-2dc27c0ac97b.mp4?playbackTicket=36a02b3ad945438196dc299002fe57a8&site=vmware.mediasite.com)

[STO8165R - VSAN Networking Deep Dive and Best Practices](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/29ff33bf-9d87-41db-87a4-1727893b65d3.mp4?playbackTicket=b7073010ef12421d961727da3a05c60c&site=vmware.mediasite.com)

[STO7977 - SRM with NSX: Simplifying Disaster Recovery Operations & Reducing RTO](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/e500d561-47df-46ec-bed3-4cc833eb23ba.mp4?playbackTicket=4e696b9650934f78af2673086382bec0&site=vmware.mediasite.com)

[STO7552 - Architecting High Availability and Workload Balancing for Tier 1 Mission Critical workloads using VMware Software Defined Storage and Extended Oracle RAC](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/9f2e5ecb-df45-4088-95df-2346c6737be2.mp4?playbackTicket=2d98cd65fd1042458450851bdea9c1b1&site=vmware.mediasite.com)

[STO7914 - Revamped vSphere Storage DRS and SIOC for automating the Data Centers](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/0c379cbf-2658-498d-aca2-4c747d200731.mp4?playbackTicket=254a445995cd42d188d93f2882589338&site=vmware.mediasite.com)

[HBC10704-QT - Backups to the cloud - Leverage the cloud for Business Continuity](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/0d373172-3f12-4322-ad14-453619b57d9c.mp4?playbackTicket=ef0ffd66fc5043ce9acc0b7e42f03dbd&site=vmware.mediasite.com)

[STO9988-QT - Running Epic with VSAN â Modern Architecture for Healthcare](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/5bf7cd9b-79aa-41e1-88c3-23c20319fd94.mp4?playbackTicket=fb63eabb240445209d3e909bec5c1a48&site=vmware.mediasite.com)

[STO9987-QT - Hardware Procurement Guide for Virtual SAN](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/f6be281a-a26c-4e6d-a6ed-10ca4905a4b4.mp4?playbackTicket=7f899efd27014b44a5b11448a385f788&site=vmware.mediasite.com)

[HBC10703-QT - Top Tips for Moving to the Cloud](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/753561a7-293f-4b03-937e-62d8fef159a3.mp4?playbackTicket=48d577223e4143b6bc680980017fb778&site=vmware.mediasite.com)

[STO9977-QT - 5 Tips for Getting The Most From Virtual Volumes and vSphere Storage Policy-Based Management](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/e06cf55d-e91f-4afc-8e5d-ca3b6c1acf83.mp4?playbackTicket=76df4aa6ecdc4369b47b687aab41aaf8&site=vmware.mediasite.com)

[INF9991-QT - vSphere Web Client Plug-in Certification Program](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/1af38b2f-cf0d-45c4-8d59-a440142856a5.mp4?playbackTicket=bc6a5bf0ae404b869e76700ea4866539&site=vmware.mediasite.com)

[STO8267 - Hours to Minutes: Automated Provisioning and Deployment Using PowerCLI, vRealize Automation and vRealize Orchestrator](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/698493fe-181f-4997-b23d-87b3cf22cae2.mp4?playbackTicket=452ad25213ca488fb454e57c3d4edd40&site=vmware.mediasite.com)

[INF9047 - Managing vSphere 6.0 Deployments and Upgrades](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/b4060695-2e20-4abe-a638-a97a2fffebfb.mp4?playbackTicket=2fa56c8ed5d04f3bb547350e4d7a968f&site=vmware.mediasite.com)

[INF8225 - The vCenter Server and Platform Services Controller Guide to the Galaxy](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/3fc56ead-c735-436b-9f49-de699335b666.mp4?playbackTicket=7d073b001f7c4636ac5fd51858ffd5c1&site=vmware.mediasite.com)

[MGT7924 - vRealize Operations Capacity Explained](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/8df89b89-613d-4ecf-b105-0f5548b4995c.mp4?playbackTicket=161b6cec722c4e46b64e89ba20e0e34c&site=vmware.mediasite.com)

[CTO9943 - VMware Chief Technology Officer Panel - Trends and Futures](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/089b2b2c-abb9-4b89-802f-1ae5feafbed5.mp4?playbackTicket=ef08137f422a4469a5556c883e54cc47&site=vmware.mediasite.com)

[CTO7516 - Ask the Experts - Titans of Tech](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/5a6e8319-01e7-4e34-b2fa-8fdfcab5a9f3.mp4?playbackTicket=92f61e3a03b94df59957dee2c5f61dbc&site=vmware.mediasite.com)

[INF7827 - vSphere DRS Deep Dive: Understanding the Best Practices, Advanced Concepts, and Future Direction of DRS](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/9e665824-de61-4007-80c0-6752f6e1f626.mp4?playbackTicket=e65b1e8bfdcd46fea46318448a3a0b20&site=vmware.mediasite.com)

[SDDC8468 - A Beginner's Guide to the Software-Defined Data Center](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/d00dc0a3-1dbf-4ae5-8b5e-d0e64645fadb.mp4?playbackTicket=3ec0d2d3bd504349870a39c727d2e85f&site=vmware.mediasite.com)

[EUC8203 - Beyond the Marketing: Horizon Instant Clones Deep Dive](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/9b6f6f52-5dfa-4fa3-8dc8-f6d51e98f586.mp4?playbackTicket=e3f5267d656746c0878574e8930f89e8&site=vmware.mediasite.com)

[INF8755R - Troubleshooting vSphere 6: Tips and Tricks for the Real World](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/f91f2373-4041-464f-a6d3-c8e5fd14be8f.mp4?playbackTicket=d8c00c9511d04d4ca3f5527d5f3d799d&site=vmware.mediasite.com)

[INF8089 - Extreme Performance Series: vSphere Compute and Memory](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/7ecb27d4-9fe7-44b6-9bc2-8b96206693fb.mp4?playbackTicket=2c51ea2bf28042ed8967a41a18f3d510&site=vmware.mediasite.com)

[CNA7522 - Containers for the vSphere Admin](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/a30fe5bb-d60b-4f33-bd10-3defe6afda99.mp4?playbackTicket=37ff428beff74c4cb74368444dcb0752&site=vmware.mediasite.com)

[INF8430 - vSphere 6.x Host Resource Deep Dive](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/1eb2cc67-845c-4e0f-a99b-a48e2838c638.mp4?playbackTicket=64c78bf4511547a685010d05faaa9157&site=vmware.mediasite.com)

[EUC8243R - Troubleshooting 101 for Horizon](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/a1effcaa-ae5e-481f-9d06-58d29be1928d.mp4?playbackTicket=9f9ce6b8d6ee4d02afea7b286ab8059a&site=vmware.mediasite.com)

[NET7907 - Advanced Network Services with NSX](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/43d2278c-15ff-43a4-8b17-6d6051eb449a.mp4?playbackTicket=5f40c91c23614d719fd6ed8ba4d5c9bf&site=vmware.mediasite.com)

[NET8364R - How to Deploy VMware NSX with Cisco Infrastructure](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/61104286-525e-4c3a-bb62-05b0e4adcf09.mp4?playbackTicket=cf930867dd3b42de8969976cf1a29bd6&site=vmware.mediasite.com)

[INF8092 - The Power Hour: Deep Dive, DevOps, and New Features of PowerCLI](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/4022bd26-efd7-4db0-a63e-9d62dfd006f8.mp4?playbackTicket=90642e5749ed4ef485aec1f8eafcfca7&site=vmware.mediasite.com)

[STO9617-SPO - Containers & VVols - a technical deep dive on new technologies that revolutionize storage for vSphere](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/5b3b9ade-a3c6-4714-9186-a573d8523b7b.mp4?playbackTicket=7bf7ec16c4c74859bb66b70289b42751&site=vmware.mediasite.com)

[VIRT8290R - Monster VMs (Database Virtualization) Doing IT Right](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/23e6a4d1-84d5-488a-ad38-b86ebf82b5c9.mp4?playbackTicket=b490b9cdea1542cc869bbdd56869e05f&site=vmware.mediasite.com)

[EUC8404 - What's New with Horizon 7](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/a23fe748-0d10-43c4-aa4e-32a754dd94a6.mp4?playbackTicket=cd63d35088714f45ac7f88446814ee6d&site=vmware.mediasite.com)

[MGT7718 - The KISS of vRealize Operations!](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/57b0df04-2a8f-4d72-b468-1f553af4a721.mp4?playbackTicket=a6c5d137999742a5bd44336123d14a74&site=vmware.mediasite.com)

[VIRT7621 - Virtualize Active Directory, the Right Way!](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/06fefe16-b378-4167-9022-ea6d1d0c7f64.mp4?playbackTicket=67ef5538655e4923b77360977b6015f4&site=vmware.mediasite.com)

[INF8036 - Enforcing a vSphere Cluster Design with PowerCLI Automation](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/6ba959a6-9220-4524-b886-4a48df46d36d.mp4?playbackTicket=4e9a27c6ef8d4fb7a4530cfb8b015528&site=vmware.mediasite.com)

[INF9083 - Ask the vCenter Server Experts Panel](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/cfecf036-2439-43e9-962e-837f194aea55.mp4?playbackTicket=d54d8a060e3e494485d129dfba217016&site=vmware.mediasite.com)

[STO7645 - Virtual Volumes Technical Deep Dive](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/abe4594f-f57d-4939-9fcf-10b1d0b81683.mp4?playbackTicket=4ccb3a854a094511ac1ea6f7b0e55aa1&site=vmware.mediasite.com)

[INF8038 - Getting Started with PowerShell and PowerCLI for Your VMware Environment](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/6c26b53f-53b8-45d5-8215-395edf199814.mp4?playbackTicket=2a44426b49e84bf886025f15b0b167f6&site=vmware.mediasite.com)

[STO9424-S - Taking HCI Mainstream](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/192fe167-453f-4961-b241-df10a01f9202.mp4?playbackTicket=75da206e71f247489ea4120e5ea1e9d5&site=vmware.mediasite.com)

[EUC7601 - Advances in Remote Display Protocol Technology with VMware Blast Extreme](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/c6dbb3b5-ff86-4071-b6f6-2796cee9af27.mp4?playbackTicket=693c25b015684c2483770025e2c64f38&site=vmware.mediasite.com)

[NET9094 - Customer Case Study on American Tire Distributor (ATD): Migrating to the Software-Defined Data Center with Arista Networks and VMware NSX](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/bc209b25-f681-4f21-92ce-2f4e70f2b23f.mp4?playbackTicket=9a121e37e45a443389a9c9a449d4c318&site=vmware.mediasite.com)

[NET9069 - Automating Traffic Visibility for the Software-Defined Data Center](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/c2ff1815-4b3d-4547-a8dc-6995a89605c6.mp4?playbackTicket=4eaac26ddd30465cbdb8977816713e8d&site=vmware.mediasite.com)

[SEC8081 - Healthcare: The Security Awakens](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/e2ad5f1a-0538-4caa-89b2-77e5e6c3b915.mp4?playbackTicket=3503b2ee79224d96878ab189dd9f3b21&site=vmware.mediasite.com)

[SEC8667 - Deep Dive into Real-Life Data-Center Breaches and How They Could Have Been Avoided](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/f5d438ba-393a-42a9-bc1c-068778d3f801.mp4?playbackTicket=7658372797954cb39c2c45a3385ec652&site=vmware.mediasite.com)

[NET8832 - The Role of VIO and NSX in Virtualizing the Telecoms Infrastructure](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/96f95edc-f786-4735-9f08-b496b9da41b6.mp4?playbackTicket=343edf26fb0845688988455dbcb56872&site=vmware.mediasite.com)

[NET8194 - How VMware IT Implemented Microsegmentation and Deployed a Large-Scale Private Cloud Using NSX](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/eb172374-d40c-45ad-bf73-338bf6c8ad29.mp4?playbackTicket=a2ba963a1ffe42d4807636ce84513cee&site=vmware.mediasite.com)

[NET8131R - NSX for vSphere Logical Routing Deep Dive](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/85057bc4-c329-4d80-9999-647a30321478.mp4?playbackTicket=0c74ce18165e42fd9ea779cf8064dc2a&site=vmware.mediasite.com)

[NET7861R - Multisite Networking and Security with Cross-vCenter NSX: Part 2](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/7c1e5950-7fc5-4b87-ba2e-8434c024c294.mp4?playbackTicket=a00e2b69c1474825ac4eccb46dba3087&site=vmware.mediasite.com)

[NET8758 - vSphere Distributed Switch Deep Dive](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/a448b565-4b05-408f-b97c-3c5755b09c08.mp4?playbackTicket=b6b259d9d39d44fcb7e1b6dad7bbd7c4&site=vmware.mediasite.com)

[SEC7593 - NSX Security for Horizon View 7âDeep Dive](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/e59158e7-78cb-49b8-b062-82399b2a59cf.mp4?playbackTicket=318d9327b0cd461a9e6b36936cd3bc13&site=vmware.mediasite.com)

[NET9447-SPO - Extensible Solution for Software Driven Data Centers (SDDC) with VMware and Arista](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/e80bc914-96f0-4601-8e5e-73b7bfb83e1a.mp4?playbackTicket=c113319838c8462a9e7f632b34532ab1&site=vmware.mediasite.com)

[NET7854R - Multisite Networking and Security with Cross-vCenter NSXâPart 1](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/0b746cbd-40f0-453e-87a1-9604db71e55c.mp4?playbackTicket=8ab7e5f57150483a9a421fc885b2c068&site=vmware.mediasite.com)

[NET8030 - NSX Performance Deep Dive](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/5cef4d73-dccb-47b1-a93e-7290facffc8e.mp4?playbackTicket=4d0fe511233c4dd7b50b2f8c0171f8d2&site=vmware.mediasite.com)

[SEC9450-SPO - Bridging the Gap between Infrastructure and Security Operations](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/7257c5fc-70e3-40bf-bed3-bdf86a570535.mp4?playbackTicket=a227d91b764f42788df702066b55ccb1&site=vmware.mediasite.com)

[NET8109 - Amadeus's Journey Building a Software-Defined Data Center with VMware Integrated OpenStack and NSX](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/fdae400c-842c-4a3d-97db-588cd7a65163.mp4?playbackTicket=8ca1450116134059849ef9f90a0d753a&site=vmware.mediasite.com)

[NET7701 - How to Easily Become a Cool Automation NSX Cloud Network Engineer](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/3d21f392-4660-427c-84d8-ee526fc2193d.mp4?playbackTicket=6c356ed54b7b447780de35bd20e58290&site=vmware.mediasite.com)

[NET7514 - PowerNSX and PyNSXv: Using PowerShell and Python for Automation and Management of VMware NSX for vSphere](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/b0e89702-2a4b-4461-bd52-2263ccc14860.mp4?playbackTicket=40b806b5e39841e78b8b4db2792897f4&site=vmware.mediasite.com)

[SEC10020 - Managing Cybersecurity Risks Within SDDC: VMware and Palo Alto Networks Customers Discuss Their Perspectives and Experiences with NSX and VM-Series Deployments](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/abe989c5-749c-4893-8754-a8f5b30e954e.mp4?playbackTicket=d63c67268626435d9d9e5e858412abd8&site=vmware.mediasite.com)

[SEC9619-SPO - Scale and Segment the Agile Data Center with Software-Defined Security and NSX](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/28217635-14e9-4f98-8c66-fbe1f0c7c7a8.mp4?playbackTicket=7ab79f5df4c1411395c7775ac59d6bf1&site=vmware.mediasite.com)

[NET7648 - How PG&E is Automating Secure Environments with NSX, vRealize Automation, and vRealize Orchestrator](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/c2382388-36a9-4bb1-8657-53ad88850699.mp4?playbackTicket=3610cb3135264b21953c76a2d779ff7f&site=vmware.mediasite.com)

[NET9155 - NSX Policy, Visibility, and Intelligence](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/b7882556-0a6d-42e3-8023-9ae2a2a00ab1.mp4?playbackTicket=037f09b547df443fb0d6bdb45fecdf77&site=vmware.mediasite.com)

[NET8082 - NSX Operationalization: Monitoring and Troubleshooting Your NSX  Software Defined Data Center](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/fbf63ab7-991f-48fa-9de9-14de326b6342.mp4?playbackTicket=2e1f4e6bf71c4fd6802f1075612b15ae&site=vmware.mediasite.com)

[NET9029 - NSX Logical Load Balancing: From Basics to Fine Art](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/174213fc-dfdb-4671-82a2-901fcfd10cb2.mp4?playbackTicket=498ea94896a14e63b16a2452d4dba24b&site=vmware.mediasite.com)

[NET8337 - Leveraging NSX for Remote and Branch Offices](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/64a2941c-824f-473b-b48f-fa3a98f4ef4d.mp4?playbackTicket=94a3ce3cdb8949cd80f3b4f480bc047f&site=vmware.mediasite.com)

[SEC8022 - Implementing Agentless AV and IPS/IDS Security Solutions with NSX](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/e6f36b5a-37e2-4c2d-b70e-8e1afecfd771.mp4?playbackTicket=9d5e29992f624f16b7081af06b256b78&site=vmware.mediasite.com)

[NET8343 - OpenStack Networking in the Enterprise: Real-Life Use Cases](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/f3145cd4-2077-4022-9130-06d4ef8cd34f.mp4?playbackTicket=23d2dd56f59a44118f8d9c298fe0fd2c&site=vmware.mediasite.com)

[STO9886-SPO - Modernize Remote/Branch Office (ROBO) Operations with Software-Defined Edge](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/747af7fa-7640-4384-835a-d19dce0f0c24.mp4?playbackTicket=a996d53ab88c452290579627b58c245b&site=vmware.mediasite.com)

[SEC9446-SPO - Integrating a Threat Defense Lifecycle Security Approach with VMware NSX](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/450ea122-fdae-4dd0-88bb-3b8f367184cd.mp4?playbackTicket=3b94f8e115d14676931b429846e7a95f&site=vmware.mediasite.com)

[SEC8348 - Deploying Security in a Brownfield Environment](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/ea40cabc-8cee-40a6-ac8f-301f6868d355.mp4?playbackTicket=b37e57b0150e46a69048cb9805b26de9&site=vmware.mediasite.com)

[NET7956 - vRealize Automation and NSX Design Best Practices](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/9a06725d-9812-4a63-aaa8-5b715a253d09.mp4?playbackTicket=93b25c1de2e94829a172b4a5425ac5b0&site=vmware.mediasite.com)

[NET8680R - Advanced NSX Troubleshooting: Tips & Tricks for Experienced Users](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/51edbe55-f33b-4f22-aa4a-25ecf7b25d36.mp4?playbackTicket=5a6e8de43e5942239cf6cfab4ec01b08&site=vmware.mediasite.com)

[NET7865 - Operational Best Practices for VMware NSX](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/edd17c7a-726c-4791-91bb-1e691464fc2f.mp4?playbackTicket=b3a50c189ff04595ab9862cd459da787&site=vmware.mediasite.com)

[NET8364R - How to Deploy VMware NSX with Cisco Infrastructure](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/314f9ab0-80f3-4239-b193-c2b408632b0f.mp4?playbackTicket=be94b4dd29284eb2aaf7cbc20367c281&site=vmware.mediasite.com)

[NET7514R - PowerNSX and PyNSXv: Using PowerShell and Python for Automation and Management of VMware NSX for vSphere](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/c9187dbd-bdef-4aa3-8e51-ca14876bab14.mp4?playbackTicket=b9265aa14a124588bc4f37db07a79f78&site=vmware.mediasite.com)

[SEC7836R - Introduction to Security with VMware NSX](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/fb585051-36f5-4258-929a-af2fbfa265a8.mp4?playbackTicket=d56cb13cb5ea4d42a27ce0aeb2cb228a&site=vmware.mediasite.com)

[NET8193R - The Architectural Future of Network Virtualization](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/e9ec6df8-d6c4-49a8-96fa-004d3a4fa4e0.mp4?playbackTicket=510c1a464dda4e279509a815a98d45f3&site=vmware.mediasite.com)

[SEC7628 - Use NSX to Automate Your Security Incident Response so You Can Stay Above Water](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/80b1a787-3cea-46f0-8a62-11a313cc2b32.mp4?playbackTicket=ec264636c8744217846e9dc8d91d780f&site=vmware.mediasite.com)

[NET7857R - Reference Design for SDDC with NSX and vSphere: Part 1](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/39c4ae41-ad86-4156-a203-2b198c9b0bf7.mp4?playbackTicket=2cec8edd39c8449d8cdd9e81f223dd73&site=vmware.mediasite.com)

[NET8039 - Bridging Virtual and Physical in NSX with Open vSwitch Database Management Protocol-Based Hardware VXLAN Tunnel Endpoint Integration](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/ef55ee7e-01bc-4a98-a255-71d584b66d97.mp4?playbackTicket=6cb8ce10099544279790f176e4e45f6d&site=vmware.mediasite.com)

[NET8935 - NSX for Small Data CentersâBreaking Boundaries](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/9c338b26-d1c9-48ec-bc0a-d0e4d0a5c1a0.mp4?playbackTicket=9fa0036e13034f24bccbec7309b8c2b0&site=vmware.mediasite.com)

[NET8675r - The Practical Path to NSX](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/12b342ab-5b04-4fd5-a56f-9e6056891529.mp4?playbackTicket=e553a5c7ed9046529e430131c461a2e2&site=vmware.mediasite.com)

[SEC9609-SPO - Trusted Security in the Software Defined Data Center: Real-World Use Cases Across VMware Platforms, including NSX](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/4f21e3d9-6da0-4e87-b5e0-4bda79132447.mp4?playbackTicket=b32793379db7469888f15de38c9c403b&site=vmware.mediasite.com)

[NET8734 - Automating Networking and Security Operations with NSX Customer Panel](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/fbe6a4a7-b9cd-47d1-b176-55696b43f392.mp4?playbackTicket=488f819f8e844083b4b87f9a50856c05&site=vmware.mediasite.com)

[NET9156 - Customer Case Study: Journey to Automate Security As a Part Of Service Delivery](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/66cb8812-67f5-4f3d-ad06-5f92a6e11018.mp4?playbackTicket=f7671a885b674e52a123a82ecd5f3c4d&site=vmware.mediasite.com)

[NET7861R - Multisite Networking and Security with Cross-vCenter NSX: Part 2](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/19986278-3ecb-455c-94de-d9c6aa3595be.mp4?playbackTicket=b1009468e7f34ac4969d0e3795798fe0&site=vmware.mediasite.com)

[NET7760 - Enhanced Disaster Recovery with NSX](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/00980cda-d66c-4b24-aa16-5b7e1fed8d56.mp4?playbackTicket=dacf57637f1d4795b9328043dc29448c&site=vmware.mediasite.com)

[NET7854R - Multisite Networking and Security with Cross-vCenter NSXâPart 1](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/72adacde-1d18-415a-9b1b-037e6073be50.mp4?playbackTicket=b62fb811d25a47488550fd7dada7cc90&site=vmware.mediasite.com)

[NET8680R - Advanced NSX Troubleshooting: Tips & Tricks for Experienced Users](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/c7b8ab46-fbea-490e-99ae-70b98808152e.mp4?playbackTicket=f1f63ed732c14165aaeebcf4041d5dcb&site=vmware.mediasite.com)

[NET8903 - Stories from the Alexandria SDN Zone](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/f150a565-74b3-4bf3-aecb-d89af91590a7.mp4?playbackTicket=6ca7d1978272477481794f462dcc7cb8&site=vmware.mediasite.com)

[SEC9976-SPO - Extending security beyond the SDDC with VMware NSX and Palo Alto Networks VM-Series Virtualized Next-Generation Firewall](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/99f1a482-e8af-4218-9afc-8a1ac3177fdf.mp4?playbackTicket=4e4aa314d5984940b5b1191442a55d0a&site=vmware.mediasite.com)

[NET8241 - Monitoring and Troubleshooting NSX with vRealize Network Insight (Arkin)](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/fcbe5ea9-3927-4534-a2bf-f1860015e74e.mp4?playbackTicket=af9a8798a9f8424aa28b7a4e014b0627&site=vmware.mediasite.com)

[NET8131R - NSX for vSphere Logical Routing Deep Dive](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/7b9b1d75-dbcc-44d9-8d6a-be1123570aac.mp4?playbackTicket=d1979b85e7ed42a18c2caa5691f910b6&site=vmware.mediasite.com)

[SEC8730 - NSX Security and Micro-segmentation Customer Panel](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/969b9b2b-2fca-4983-aa6d-4a4f81ccc526.mp4?playbackTicket=6d20485fdd58442bb2e405a96c314cb6&site=vmware.mediasite.com)

[NET7834r - Introduction to VMware NSX](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/2006587c-d420-47fa-9812-69df4e0ee2ef.mp4?playbackTicket=66fa5dbe0b674e3ca547219108615c10&site=vmware.mediasite.com)

[NET7944 - NSX Brownfield Deployment Best Practices](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/0a6d7f57-a1ba-4a11-9290-889f4f6dd39c.mp4?playbackTicket=36f91587a8044c56865754f517edebe7&site=vmware.mediasite.com)

[SEC7568 - Practical NSX Distributed Firewall Policy Creation](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/f247242f-0ec7-4bdb-b6fa-375075834e3e.mp4?playbackTicket=949de192d4394b3b8f0bdb063437541b&site=vmware.mediasite.com)

[NET8731 - IT Automation with NSX Network Virtualization and Security](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/3f16f5fc-8a2b-40d9-9181-934b82253229.mp4?playbackTicket=d3b417af1e894bb78de28080dcc8bd2e&site=vmware.mediasite.com)

[SEC9972-SPO - Deep Dive: Secure your multi-tenant cloud with Palo Alto Networks VM-Series and VMware NSX](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/b16415ad-38c1-472c-b253-8ea09f848221.mp4?playbackTicket=3c034545b92d475781f8be2d8482922a&site=vmware.mediasite.com)

[SEC9618-SPO - Deep Dive:  Extending L4-L7 Security Controls for VMware NSX and VMware Integrated OpenStack (VIO) Environments with Fortinet Next Generation Security](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/a7dec1a2-2f6f-4384-a5e6-5d8acef8f14e.mp4?playbackTicket=f44701b19e2446039e426fe214245e9e&site=vmware.mediasite.com)

[SEC9968-SPO - Automate Check Point vSEC Advanced Security with NSX](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/038e1c96-3e9b-4461-89d7-669504d3f6b6.mp4?playbackTicket=044ae31d2c8f45688623afddfb9324e9&site=vmware.mediasite.com)

[NET8729 - NSX on Cisco ACI Customer Panel](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/68087b20-37f4-4d82-b067-dfe0efe595e6.mp4?playbackTicket=243658a2c94a411f90fa80676d5a5940&site=vmware.mediasite.com)

[NET7837 - Introduction to Application Continuity with VMware NSX](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/0bb6466d-f47f-4b33-bb19-c2b690f89554.mp4?playbackTicket=230e18aca7d842fcb2d670676fd067f9&site=vmware.mediasite.com)

[NET7935 - Container Orchestration and Network Virtualization](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/9ebc72ed-5e25-4230-ab48-1e6ca316da3e.mp4?playbackTicket=76d079efe15b44ef8b17a7ac8aaecdf3&site=vmware.mediasite.com)

[NET7656-SPO - Accelerating SDDC through mainstream adoption of network virtualization](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/bf1f215e-1855-452b-8ce9-597a9085da5f.mp4?playbackTicket=c2bc86f7bc1d4e4f95fee4cc3044b3f8&site=vmware.mediasite.com)

[NET8193R - The Architectural Future of Network Virtualization](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/651d9fdd-2b97-45df-89c3-46e2c2ae640e.mp4?playbackTicket=0aef3a50875640f1b6a012be62f67e83&site=vmware.mediasite.com)

[SEC7836R - Introduction to Security with VMware NSX](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/be6cab8f-3195-4d85-8f7e-ad065bc32c78.mp4?playbackTicket=d7949f0f61d24ea3a1928e40e7a4bdf4&site=vmware.mediasite.com)

[NET7834 - Introduction to VMware NSX](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/294283c8-dfcb-4231-8b6d-c65ce9170db7.mp4?playbackTicket=5d8d90d6674648db93fc9f5056e5682f&site=vmware.mediasite.com)

[NET8675 - The Practical Path to NSX](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/5f26a99e-1a15-46a5-a9db-1f4635b5ce5f.mp4?playbackTicket=dc944bf54676474c8548c0d6f94edfa2&site=vmware.mediasite.com)

[NET7857R - Reference Design for SDDC with NSX and vSphere: Part 1](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/0c01d09c-da0c-402c-a89d-971bd9a0ae1a.mp4?playbackTicket=5687311c152e4b66a221915f02dee7e4&site=vmware.mediasite.com)

[SEC10019 - VMware NSX Micro-segmentation â Definition & Benchmark Deep-Dive](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/fc19c529-a917-4251-8af0-623ef49562a6.mp4?playbackTicket=706155a0234d490796b5e57c41f4ae36&site=vmware.mediasite.com)

[NET9381 - Operationalizing NSX Customer Panel](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/be7b7c37-fd03-4d31-a4b7-e578b5b26e02.mp4?playbackTicket=dc30908f4503479289037693e43c60ad&site=vmware.mediasite.com)

[NET9152 - VMware NSXâDeep Dive](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/db352180-d08a-459f-8f0e-c14df9536c58.mp4?playbackTicket=772ab7b6cd6f4206aa6f68e62d91d186&site=vmware.mediasite.com)

[NET10884 - Moving to the next level of the SDDC - a Public Agency introduces VMware NSX, AirWatch, and Palo Alto Networks integration](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/ff96e2fd-c27c-4303-8911-14120e947a00.mp4?playbackTicket=c8c730ec645c4374a8fa3436dfb7759d&site=vmware.mediasite.com)

[NET9004-QT - Virtually Unstoppable: Scaling NSX to Bridge the Gap between Security & Cloud Automation](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/c8282e8c-bb18-4a2a-b711-f36c5636faeb.mp4?playbackTicket=74d3956ff517472b9d663f74912dec35&site=vmware.mediasite.com)

[NET8769-QT - Hyper-convergence in Healthcare:  The Key to Doing More with Less](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/f24888cd-2591-4edc-af87-c4295f15c0d4.mp4?playbackTicket=2443d8ea68734fd08e025254f64137d9&site=vmware.mediasite.com)

[NET7774 - Day Two NSX Operations in VMware's Private Cloud](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/c990199b-c895-4922-a378-ad5128590c58.mp4?playbackTicket=9378f78618544b6bb5dfde7a4800292a&site=vmware.mediasite.com)

[SDDC8621 - VMware Cloud Foundation: Technical Deep Dive](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/145115e1-24d9-4ee7-acf2-137b00cfdd9a.mp4?playbackTicket=6ad68abede6147eaafca1173d7626585&site=vmware.mediasite.com)

[SDDC8472 - An IT Architect's Guide to the Software-Defined Data Center](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/b32b5eb9-e753-4b65-a9c7-8512c0025cd9.mp4?playbackTicket=338812932bfd4e9198afbd1b00c7bb12&site=vmware.mediasite.com)

[SDDC7780 - Agile: The Scrum Master for Your Software-Defined Data Center!](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/c544030e-0807-45d7-b0e9-6c19ffc73da8.mp4?playbackTicket=7b6d67dbe9974eefa42d8a055439d622&site=vmware.mediasite.com)

[SDDC7886 - Implementing An Operating Model for Agility: A Customer Success Story](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/52ceb29a-7e09-404c-b281-d4cd3080cb6a.mp4?playbackTicket=d662a0db991e4f68abf691da2c048e90&site=vmware.mediasite.com)

[SDDC8468R - A Beginner's Guide to the Software-Defined Data Center](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/ca166216-ef18-489e-981e-dee260e77115.mp4?playbackTicket=c7bd115aa8c0441a9a62ecb64b661e05&site=vmware.mediasite.com)

[SDDC9971 - Experience the Business Impact of IT Innovation & Transformation in this Live Interactive Simulation](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/f62de2b4-4429-47c4-b4dd-20f5a14a8207.mp4?playbackTicket=bae6162767674c9880a9de76c769b8ec&site=vmware.mediasite.com)

[SDDC8414 - VMware Validated Design for SDDC: A Technical Deep Dive](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/d37cf776-1e24-4b30-a723-d9bb1a386209.mp4?playbackTicket=c342023d4007470189b42922d8ef5fa2&site=vmware.mediasite.com)

[SDDC7502 - On the Front Line: A VCDX Perspective Working in VMware Global Support Services](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/2dd8fd5b-d366-48d6-a6f1-1621acaae98f.mp4?playbackTicket=01c0d81e390c4446a58ef86e80ac4d34&site=vmware.mediasite.com)

[SDDC9456-SPO - Implementing Self-Service Storage Provisioning with vRealize Automation XaaS](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/7f338d41-d20f-436e-8541-c769183a10ac.mp4?playbackTicket=9158d141782f4d19a01039fbb2602d0d&site=vmware.mediasite.com)

[SDDC8615 - vRealize Automation 7 in VMware Cloud Foundation](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/44ddb3c5-fd34-4ed5-95e7-715ffa4894a6.mp4?playbackTicket=896ecbc76bcb4c5583bcb092b5941cae&site=vmware.mediasite.com)

[SDDC7692 - Tips for Realizing the Full Value of Your SDDC Transformation](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/85b5628a-d8d9-43e1-91a1-7c57d848709d.mp4?playbackTicket=514b44056efc4c4fbc4c86ed1657d6cc&site=vmware.mediasite.com)

[SDDC8748 - Building a Successful Business Case for VMware Cloud Foundation](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/b265578c-561f-43c3-8138-8cfb68d690de.mp4?playbackTicket=181195f08a67457292cdc60d1f150ecc&site=vmware.mediasite.com)

[SDDC9612-SPO - How to design and implement VMwareâs vCloud in production](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/4f441c47-1bb9-448e-8961-d14350103470.mp4?playbackTicket=e2a3289b1c3944f5abcd30a628633b81&site=vmware.mediasite.com)

[SDDC9726-SPO - Making SolidFire Invisible in your VMware Environment](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/6629b6cd-d700-47ba-9676-23c41b4c5fd2.mp4?playbackTicket=7cbe8115cbe84b40a78fbbe948c09ab1&site=vmware.mediasite.com)

[STO9405-SPO - Stopping Global Threats with Converged Infrastructure for the US DoD Cyber Range](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/634f6b69-587c-4eb1-a9ab-589084e3522e.mp4?playbackTicket=e06700b82c7f4b3e953753d866978e46&site=vmware.mediasite.com)

[SDDC9181 - VMware Cloud Foundation Backup and Disaster Recovery](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/59c88da0-75a7-435b-88fa-289317d89211.mp4?playbackTicket=ace04e5524ad4c07a561f521e826d408&site=vmware.mediasite.com)

[SDDC8614 - NSX in VMware Cloud Foundation](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/ad9332ff-7442-4713-90fc-d196c8b98ca6.mp4?playbackTicket=43484ab34f6e4a84aee945df9145b20e&site=vmware.mediasite.com)

[SDDC9465-SPO - Level Up to IT as a Service with Hyper-Converged](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/70383486-f4fd-4e5c-b797-d6ce7a1d2729.mp4?playbackTicket=e882aa3d864744ffb7882210ae9a3f72&site=vmware.mediasite.com)

[SDDC8357 - If They Come - Are You Ready?](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/d45d7d81-cfb4-41e4-ac2c-f2421ecce646.mp4?playbackTicket=0d88dc55e4b74472ab09a98bb7906fcf&site=vmware.mediasite.com)

[SDDC9428-SPO - Practical Strategies for SDI and Security](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/bc29d651-6b57-4ac5-8053-3ced1695bfdb.mp4?playbackTicket=8ff40ff31c584454a476f06724c51dcd&site=vmware.mediasite.com)

[SDDC8946 - Deep Dive into Deploying the vRealize Cloud Management Platform the VMware Validated Designs Way!](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/5f3e1ad2-e8f3-4cfd-80f4-3115a6d6b2a1.mp4?playbackTicket=cfcf938cc4cf4b89ba82f9752ee90b7a&site=vmware.mediasite.com)

[SDDC8445 - VMware Validated Design for Microsegmentation Deepdive](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/a06343f5-12d6-4d01-b902-d19021a126ab.mp4?playbackTicket=ae5388c93c294594bca84220c11a751d&site=vmware.mediasite.com)

[SDDC8628 - Automating Virtual Desktop Deployments with VMware Cloud Foundation](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/fe609247-bc9e-4f36-925f-3c299f32b8e9.mp4?playbackTicket=73050a8ebd814e3793c97cf2d4f6f247&site=vmware.mediasite.com)

[SDDC9921-SPO - Evaluating Tradeoffs in Reducing and Eliminating Downtime Inside and Outside of the Software Defined Data Center](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/c57b7ae0-9841-450b-b245-9caf50e72ece.mp4?playbackTicket=5a45f845bbb145349f4d21379c76f51e&site=vmware.mediasite.com)

[SDDC7587r - Software-Defined Networking in VMware Validated Designs](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/5697883d-eee6-4893-afdf-b75890f2059f.mp4?playbackTicket=3e27b4e0f32047c2b8f2d5467fda2f6b&site=vmware.mediasite.com)

[SDDC9613-SPO - Building the Future Data Center with Province of Nova Scotia](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/1a43a8d3-456c-44a8-aeab-73030eeb2057.mp4?playbackTicket=89284eb7ff6b4e04959a6ededf0860f1&site=vmware.mediasite.com)

[SDDC8520 - No IT Left Behind: Connecting the Software-Defined Data Center to Multi-Modal IT](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/29c4377d-360b-4300-b41d-7a4fa5c37f78.mp4?playbackTicket=27cd1180ce034aa28b82aca0146a6e7c&site=vmware.mediasite.com)

[SDDC8214 - Case Study: VMware's Private Cloud Journey to Over 100K Virtual Machines](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/fcb8f3cf-d3ee-412d-a74c-0f1988d84686.mp4?playbackTicket=6d7b192904ac4cb6b5264e646dfe14bc&site=vmware.mediasite.com)

[SDDC8423 - VMware Validated Design for SDDC â Operations Architecture Technical Deepdive](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/807002c7-14ae-432c-b9b3-907903612542.mp4?playbackTicket=58aab2a2a7f4409aacfeb3effdc43aa3&site=vmware.mediasite.com)

[SDDC8975 - SunTrust's Cloud Journey](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/7a869c4d-1e9c-4c2b-b26a-86f2abcbd3c2.mp4?playbackTicket=53e2d534a36c4aeb95bc0be92fe86e4b&site=vmware.mediasite.com)

[SDDC9025 - VVD 101: Build Your Cloud the Right Way, First Time](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/e793f827-95d9-42f7-adc1-cc4cf1ff48be.mp4?playbackTicket=8ae4fd3e3d474ff193ed385437989f30&site=vmware.mediasite.com)

[SDDC9605-SPO - Using Hyper-intelligence to build next generation storage platforms](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/fcd52ca6-4cc9-4a21-a789-fd1210aedfb2.mp4?playbackTicket=4eee1d20a0a64bb1bc43e2568e24f61a&site=vmware.mediasite.com)

[SDDC9176 - How VMware Cloud Foundation powers the IBM Cloud](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/f1afa7a1-e475-413f-8c1c-52c2226037e6.mp4?playbackTicket=0755bf35dd91467e82f8909ba323772c&site=vmware.mediasite.com)

[SDDC8930 - American Tire Distributors: Our Journey to a Modern Private Cloud](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/e508be8c-02e7-4bf7-9424-4bc65b53f4e8.mp4?playbackTicket=c8c68ef74dfb47de94dddba833206e29&site=vmware.mediasite.com)

[SDDC8994 - Taming the Hydra: IT in a Multi-Cloud World](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/da8988b5-8811-4a9a-b79e-4085cba95b90.mp4?playbackTicket=e3e24f3a7de448b09192cebbac172cd4&site=vmware.mediasite.com)

[SDDC7819-SPO - Lessons learned to provide secure service assurance for your VMware investments](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/9e01af4c-85d6-4d61-8593-216926fe9b94.mp4?playbackTicket=0c396e90c4ea488c9dcbbfc0d2f7b144&site=vmware.mediasite.com)

[NET9460-SPO - Use Cases for Software Defined Data Center with NSX: Transform to Digital Business by deploying multi-tenant agile network in SDDC environment](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/850ba54b-4941-486f-b9dd-e226a6520564.mp4?playbackTicket=37160abed093436ca7e6a733d6348d0e&site=vmware.mediasite.com)

[SDDC9023 - Hyperconverged Infrastructure at Scale with VxRack 1000 SDDC](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/19a8c25d-b824-4b5a-94cb-79d90951be6e.mp4?playbackTicket=9b54cdad524a41e88596834a09c5eca9&site=vmware.mediasite.com)

[SDDC8351 - How VMware Cloud Foundation Makes Your Private Cloud Operation More Efficient](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/1d4654db-b109-4de9-aaf6-6eb791482258.mp4?playbackTicket=a43c08649fc34be98b848f403c0697a9&site=vmware.mediasite.com)

[SDDC9404-SPO - Reinventing Disaster Recovery Leveraging Public Cloud Infrastructure](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/5e2e320e-9f3a-4f65-8712-7456268d8b73.mp4?playbackTicket=c674675a466d4b90b491d8a886b88399&site=vmware.mediasite.com)

[SDDC7616 - Strategizing Cloud Business Management Using vRealize Business](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/dbfd0a69-0569-42a5-80eb-70e995c17217.mp4?playbackTicket=82b81769325245ce8096487d37258d96&site=vmware.mediasite.com)

[SDDC7587 - Software-Defined Networking in VMware Validated Designs](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/91dbf951-2178-452a-bd80-f4e7e27a4878.mp4?playbackTicket=196686df80804378a48f765ba6d5384d&site=vmware.mediasite.com)

[SDDC8475-QT - A Manager's Guide to the Software-Defined Data Center](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/4505b802-2ff3-4dde-9e4d-68b7e023ff46.mp4?playbackTicket=d0de3e149e18455e9def75432184aafc&site=vmware.mediasite.com)

[SDDC7609-QT - How to Respond to the &quot;Bring Your Own Data Center&quot; Trend](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/82391ced-f3bb-41e4-9754-9d048fd69637.mp4?playbackTicket=6d9c2e9f7686473b8fd76f6ca7621ff1&site=vmware.mediasite.com)

[SDDC7881-QT - Cloud Service Lifecycle in a DevOps-Focused Delivery Model](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/0e76123d-776c-4f84-ba61-657bcc3aeacc.mp4?playbackTicket=0cc01b1c43634c88bc2787e608163585&site=vmware.mediasite.com)

[SDDC8945-QT - Learning in the Cloud: VMware Education's New Enterprise Learning Subscription](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/1cb8ea0a-f38d-4742-b703-4712b1a5ff86.mp4?playbackTicket=b05412692da944c5a16590f04b178566&site=vmware.mediasite.com)

[SDDC7876-QT - Service Automation Roadmap: Approach and Samples](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/8c3f94e1-e968-4172-9d02-3187e08faf2b.mp4?playbackTicket=abb591c1701f4a6b8a6cf7176b3c8574&site=vmware.mediasite.com)

[SDDC8024 - VMWorld Hands on Labs Architecture Design](http:)

[CTO8519 - Best of Both Worlds: Achieving Ultra-Low VM Network Latencies and Extreme Bandwidth Without Compromise](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/6486a7e1-de71-437e-a245-7aa3a8ca69a6.mp4?playbackTicket=7277e98ae6e94d4a9c799010cb7ffeaa&site=vmware.mediasite.com)

[CTO9606 - Open Source as Critical Ingredient in Enterprise Computing](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/ec63056a-7995-42a7-a8d3-a339a0c0ec6b.mp4?playbackTicket=dc51f6577a8b40b5b8a111c66fa8edbb&site=vmware.mediasite.com)

[CTO8120 - Debunking the Myths about Virtualizing High Performance Computing](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/7addbc86-091d-49b7-bce1-4b82f4d2300b.mp4?playbackTicket=8ddd9414c4054a63bdb376e27b22be29&site=vmware.mediasite.com)

[CTO9036 - Providing Management Tools for the Emerging IoT Infrastructure](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/5239219a-9e26-43f2-afb3-f292203de50f.mp4?playbackTicket=21edbeec662547cdb8b3a32f7f97b770&site=vmware.mediasite.com)

[CTO9471-SPO - New Capabilities in ONTAP 9 Optimized for All Flash Virtualized Workloads](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/b0a4825f-5c93-4b0f-a434-bfc1c47da3f4.mp4?playbackTicket=1afd8c35b81647bab54868f56874c17e&site=vmware.mediasite.com)

[CTO9951-SPO - Whatâs Old Is New Again: Next Generation Storage](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/d52773e8-b6c5-4523-9113-643a24a4d5b9.mp4?playbackTicket=a0300e7d42b34e88bbd72f65b381bb5f&site=vmware.mediasite.com)

[CTO9018 - VMware Internet of Things Strategy; Unveiled](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/a36f731f-0772-41cb-87ce-c97451f20aba.mp4?playbackTicket=79c48d7fd93a40bdbc30902b69af2979&site=vmware.mediasite.com)

[CTO9032 - Is it Possible to Use NSX to Cut WAN Network Costs in Half?](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/a9038d55-f8bb-40cc-b70d-ebca41e83845.mp4?playbackTicket=6e086ac35ed64d02b50816047e9c0b71&site=vmware.mediasite.com)

[CTO7942 - Unik: A Platform for Automating Unikernels Compilation and Deployment](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/e77b2fd4-110f-4db9-a816-ed7acb8ba825.mp4?playbackTicket=25aae2b8f6dd4f398e86d1308791ac99&site=vmware.mediasite.com)

[CTO9996-SPO - Fortifying the Cloud: What the New Samsung-VMware Partnership Means](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/ef193cad-b079-4716-882c-bab49e29c035.mp4?playbackTicket=0a85354fb7bf4533a5bbd0c0de3c060a&site=vmware.mediasite.com)

[CTO8995-QT - How Do You Manage Security Vs Privacy in IoT Beyond Device Management?](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/ab81a983-a114-4f53-9a10-1172d4f95007.mp4?playbackTicket=cbabcc4081954f29a292eba1f3bf2bff&site=vmware.mediasite.com)

[CTO9002-QT - Artificial Intelligence Is the Future of IT](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/a657dff9-c9e6-42de-9feb-d7655a146def.mp4?playbackTicket=6789e1483dad440e9fd01c04bf1ca42e&site=vmware.mediasite.com)

[VIRT9034 - Oracle Databases Licensing on a Hyper-Converged Platform](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/b541aeb8-6944-4707-aa8a-bdb73d5e1df2.mp4?playbackTicket=027e9809eb39411ab9620c1f4db17ddf&site=vmware.mediasite.com)

[VIRT8443 - Extreme Performance Series: Evaluate the Performance of Your Cloud with Weathervane and VMware vRealize Operations](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/de2b1eb5-c391-4b99-993b-f7fd7aaf0b2c.mp4?playbackTicket=115f126d33804710bdaeb7964531e6c5&site=vmware.mediasite.com)

[VIRT7620 - Successfully Virtualize and Operate Your Microsoft Skype for Business Infrastructure on the VMware vSphere Platform](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/b6d1bf35-22fd-4dcc-b8a2-ad792d73b7e0.mp4?playbackTicket=669c2200b8184e4aa1445bfd3148461b&site=vmware.mediasite.com)

[VIRT7941 - The Best of Both Words: Achieving SQL Server High Availability with VMware](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/308e14df-2601-4c42-8cf0-1ce2bdc581b2.mp4?playbackTicket=18b678ebb0db41cab523acdf34f8e9c6&site=vmware.mediasite.com)

[VIRT8290R - Monster VMs (Database Virtualization) Doing IT Right](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/68f7bf93-4794-49e9-805e-0c50cd4edb28.mp4?playbackTicket=d556402774bf4019bbd9bc172aea4993&site=vmware.mediasite.com)

[VIRT7699 - Use Cases in Performance Root Cause Resolution for SQL Server: How to Use vRealize Operations Manager, SIOS iQ Machine Learning Analytics, and SQL Sentry Performance Advisor](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/74740c5a-9b34-4048-9287-dd04e09cb974.mp4?playbackTicket=5c569386fd27403b91ceefaa94d07d6e&site=vmware.mediasite.com)

[VIRT8182 - Virtualizing Internet of Things with SAP HANA in a Flash](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/ae1514fc-a72d-4b88-836c-17d523abf8d1.mp4?playbackTicket=7663984382d14153a3ed1780c3958159&site=vmware.mediasite.com)

[VIRT9009 - Licensing SQL Server and Oracle  on vSphere](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/38993112-12c8-41ef-8d15-40dbbec89d9d.mp4?playbackTicket=1bfccfb7ccb344d8ab7a540e15a7c80e&site=vmware.mediasite.com)

[VIRT7598 - Extreme Performance Series: Monster VM Database Performance](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/703a6607-5dd8-4c20-811a-3c0eb0c16a09.mp4?playbackTicket=f958840864174fd38701d0ec73c4e489&site=vmware.mediasite.com)

[VIRT7840 - VMware and Microsoft Present: Successfully Virtualizing Microsoft Exchange Server, the Right Way](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/74a36563-6d67-48ea-a05a-df447b25295a.mp4?playbackTicket=345c5b6a4e744a4a8b38523450a0152b&site=vmware.mediasite.com)

[VIRT9402-SPO - Modern Storage Strategies for On-Demand Applications](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/8735e1f6-3ccf-4846-9765-3112f6f3e635.mp4?playbackTicket=167fd8b9acbf4fb5affd84b7e51db07c&site=vmware.mediasite.com)

[VIRT9435-SPO - Accelerate, Simplify and Control: Add Data Virtualization to Your Enterprise](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/90c84369-5407-463a-bcba-00f55e4c7df1.mp4?playbackTicket=1ec799e2ecdb431c9b61786c1db33f71&site=vmware.mediasite.com)

[VIRT7511 - Performance Tuning and Monitoring for Virtualized Database Servers](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/e5735769-400e-4f2a-baa0-475b5917c98e.mp4?playbackTicket=88791da24b8d49a5b362a31578731911&site=vmware.mediasite.com)

[VIRT7575 - Architecting NSX with Business Critical Applications for Security, Automation and Business Continuity](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/077cfabe-994f-4021-b2bb-11fa359fee83.mp4?playbackTicket=fdb62376a2484eda84726d671beb18f2&site=vmware.mediasite.com)

[VIRT8738 - Extreme Performance Series: Virtualized Big Data Performance Best Practices](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/e0b656c2-2c61-4071-90bf-067ba8023943.mp4?playbackTicket=82d3ad447887461998cf8f09efa619b7&site=vmware.mediasite.com)

[VIRT8278 - Snapshots and SQL Server - Technical Deep Dive and Detailed Lab Findings](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/c4e34999-0ac0-49cc-962a-fa2e40c3e2fb.mp4?playbackTicket=d872a2ea09ac43eda07a6103afb26f85&site=vmware.mediasite.com)

[VIRT9459-SPO - High Performance Software Defined Data Center for Business Critical Applications](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/24956ef0-3277-484d-8367-930c7000e3ba.mp4?playbackTicket=ae6a9c56b39b41c293990b13bd7213ca&site=vmware.mediasite.com)

[VIRT7684 - SAP on Virtual SAN](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/938dc975-ecd1-43e4-aac2-7511f9db36ea.mp4?playbackTicket=27d971f2a4ae46349395aaacaf00bdaf&site=vmware.mediasite.com)

[VIRT8530R - Deep Dive on pNUMA & vNUMA - Save Your SQL VMs from Certain DoomA!](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/3dbfa642-cf54-41ad-8035-9d610e15fb44.mp4?playbackTicket=c7ff8a55ca9e45eb877de84136e753a4&site=vmware.mediasite.com)

[VIRT7550 - Providing HA and DR to Mission Critical Oracle Databases using vSphere Metro Storage Cluster and VMware Software defined Storage and Networking](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/7e847d8c-32e4-48b3-8a2c-381905c66afc.mp4?playbackTicket=5f9acac5eb6f444ab6cc28f8a0212a37&site=vmware.mediasite.com)

[VIRT8708 - Understanding Difficult Applications that Require Extra TLC for Better Performance](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/f62f836c-6ef5-4987-ba1c-da31ceb91d90.mp4?playbackTicket=f5c43aed98334cc991447f0d680e4b5c&site=vmware.mediasite.com)

[VIRT7709 - Innovations from Cloudera and VMware for Virtualizing Hadoop](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/fd4c7cb4-17dc-4496-862c-8004b4b6450b.mp4?playbackTicket=e4ff5c47ae9a4a39b855e042bec00a06&site=vmware.mediasite.com)

[VIRT8071 - Making Virtualized Hadoop Deployments Successful](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/79e99643-7392-4679-a2d0-c1146683aeb5.mp4?playbackTicket=1fbfedfb566f4fcb914aa4020f3fbcb2&site=vmware.mediasite.com)

[VIRT7654 - SQL Server on vSphere: A Panel with Some of the World's Most Renowned Experts](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/b2d1c69a-d1aa-4562-b7d1-6b480a0a8944.mp4?playbackTicket=e9d0cb7f3a4a4f748ab95ddf84646922&site=vmware.mediasite.com)

[VIRT9923-SPO - Virtual SQL Server for the Non-DBA](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/2a387a56-0346-464b-8046-2e77ce8d0d57.mp4?playbackTicket=7c2b9aea60934bd086a1c3df98839eac&site=vmware.mediasite.com)

[VIRT8530R - Deep Dive on pNUMA & vNUMA - Save Your SQL VMs from Certain DoomA!](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/5d968302-43ce-4c00-99ce-892ca3ccd0cc.mp4?playbackTicket=208eaa0d72c741e8aca8df463199f974&site=vmware.mediasite.com)

[VIRT7931 - SAP on SDDC: Business Benefits of SAP Automation with SDDC](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/539bf66d-4f9f-48ef-8fe9-731b28d6b896.mp4?playbackTicket=ed93619a965e4c0ab72fc5bb4af13302&site=vmware.mediasite.com)

[VIRT9132 - Virtualized Extended Distance RAC on Hyperconverged Infrastructure in a Private Cloud - The Perfect Marriage of Availability and On-demand Scalability](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/b9de61bb-a773-45b6-87d1-e137aebb5bb8.mp4?playbackTicket=6132a9ae0cd54749b28efb4850c80182&site=vmware.mediasite.com)

[VIRT8198 - Automating Deployments of Mission-Critical Applications - in a Flash!](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/23bb5813-7124-4ecf-82ec-f719203666b9.mp4?playbackTicket=d752a20bfc1047f7ade1ed51490c28ec&site=vmware.mediasite.com)

[VIRT7632 - SQL Server On-Premises in the Cloud](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/701a8981-3b63-4f20-86ff-3e8cb7c24503.mp4?playbackTicket=5640b608b60e46df9a0d17f5f8a8ef5e&site=vmware.mediasite.com)

[VIRT7507 - How to Design and Tune Virtualized Trading Platforms](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/f548e5c6-fde3-4f6f-8b30-b41b647cf8c4.mp4?playbackTicket=1182a403e81147e792f34bf3b4106831&site=vmware.mediasite.com)

[VIRT8530R - Deep Dive on pNUMA & vNUMA - Save Your SQL VMs from Certain DoomA!](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/9f4373e0-8868-4282-984e-5b8328e3e044.mp4?playbackTicket=d7c74780dedb46fcb4ca4d9058333883&site=vmware.mediasite.com)

[VIRT9366-QT - Business Critical Applications at VMware and DBaaS with the Hybrid Cloud](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/117befe9-72c9-401e-ac7c-34e909352c5f.mp4?playbackTicket=67db749692e74de5aba4cbdd6d2e6cb1&site=vmware.mediasite.com)

[VIRT8239-QT - Things You Should Know about Big Data](http://msn-evt7-ims-ond.mediasite.com/media/mediasite02/vmware/MP4Video/745b7d28-7e3d-4aa4-b711-68beefdb2b5f.mp4?playbackTicket=3adc14bd8a4e4afb883dc016756d1acb&site=vmware.mediasite.com)
