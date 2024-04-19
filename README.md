# World Maps Construction

<h2>Purpose</h2>

- The World Maps Construction feature of Microsoft Sentinel maps geo-data from authentication logs to the closest respective blocks from the geo-data CSV file ingested in an earlier lab (using data points such as IP address, latitude, longitude, city, country) and uses this to generate a visual representation of where these authentication attempts are coming from around the world.

NOTE: VMs should be powered on for this lab.

<h2>Creating New Workbooks</h2>

<h3>linux-ssh-failed-authentication</h3>

<img src="https://raw.githubusercontent.com/melisaaaaaaaaa-er/world-maps-construction-images/main/1.png"/>

Navigate to the Microsoft Sentinel blade and select your LAW → Workbooks  → + Add Workbook.

<img src="https://raw.githubusercontent.com/melisaaaaaaaaa-er/world-maps-construction-images/main/2.png"/>

<img src="https://raw.githubusercontent.com/melisaaaaaaaaa-er/world-maps-construction-images/main/3.png"/>

Select Edit and delete the existing workbooks.

#
<img src="https://raw.githubusercontent.com/melisaaaaaaaaa-er/world-maps-construction-images/main/4.png"/>

Select “+ Add” and choose “Add Query”.

<img src="https://raw.githubusercontent.com/melisaaaaaaaaa-er/world-maps-construction-images/main/5.png"/>

Select “Advanced Editor” to bring up the JSON text editor panel.

#
<img src="https://raw.githubusercontent.com/melisaaaaaaaaa-er/world-maps-construction-images/main/6.png"/>

<img src="https://raw.githubusercontent.com/melisaaaaaaaaa-er/world-maps-construction-images/main/7.png"/>

<img src="https://raw.githubusercontent.com/melisaaaaaaaaa-er/world-maps-construction-images/main/8.png"/>

Navigate to https://github.com/joshmadakor1/Cyber-Course-V2/tree/main/Sentinel-Maps(JSON) and copy+paste the linux-ssh-auth-fail.json JSON file to the workbook advanced editor. 

Select “Done Editing”.

#
<img src="https://raw.githubusercontent.com/melisaaaaaaaaa-er/world-maps-construction-images/main/9.png"/>

<img src="https://raw.githubusercontent.com/melisaaaaaaaaa-er/world-maps-construction-images/main/10.png"/>

<img src="https://raw.githubusercontent.com/melisaaaaaaaaa-er/world-maps-construction-images/main/11.png"/>

A map will be generated displaying the geographic locations of failed linux SSH attempts from around the world.

Select the save icon, input a name for the workbook + resource group + location (these should be the same as the ones used in the other labs up till now), and 
select "Apply".

Repeat these steps for the following logs:
- nsg-malicious-allowed-in
- mssql-auth-fail
- windows-rdp-auth-fail

#
<h3>nsg-malicious-allowed-in</h3>

<img src="https://raw.githubusercontent.com/melisaaaaaaaaa-er/world-maps-construction-images/main/12.png"/>

#
<h3>mssql-auth-fail</h3>

<img src="https://raw.githubusercontent.com/melisaaaaaaaaa-er/world-maps-construction-images/main/13.png"/>

Unless you have left your VMs on for several days, it’s likely this query will not generate results as it can take time for adversaries to find the MS SQL database on windows-vm.

#
<h3>windows-rdp-auth-fail</h3>

<img src="https://raw.githubusercontent.com/melisaaaaaaaaa-er/world-maps-construction-images/main/14.png"/>

<img src="https://raw.githubusercontent.com/melisaaaaaaaaa-er/world-maps-construction-images/main/15.png"/>

Here in the Workbooks blade we can see all the workbooks that have been created.

#
<h2>Generate Results for mssql-mauth-fail</h2>

<img src="https://raw.githubusercontent.com/melisaaaaaaaaa-er/world-maps-construction-images/main/16.png"/>

Use the attack-vm to generate some failed authentication logs for the MS SQL database.

#
At this point you can leave the VMs powered on or turn them off if you will be taking a break from the labs.
