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
