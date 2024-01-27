<h1>Failed RDP to IP Geolocation Information</h1>

<h2>Description:</h2>
<b>The Powershell script in this repository is responsible for parsing out Windows Event Log information for failed RDP attacks and using a third-party API to collect geographic information about the attackers' location.
</b>

<h2>Languages Used:</h2>

- <b>PowerShell:</b> Extract RDP failed logon logs from Windows Event Viewer 

<h2>Utilities Used:</h2>

- <b>ipgeolocation.io:</b> IP Address to Geolocation API

<h2>Architecture:</h2>
<img src="https://imgur.com/Ia0XrBO.png" height="85%" width="85%" alt="Architecture"/>

 <h2>Program Walkthrough:</h2>
 
- Used custom PowerShell script to extract metadata from Windows Event Viewer to be forwarded to third-party API to drive geolocation data.
- Configured Log Analytics Workspace in Azure to ingest custom logs containing geographic information (latitude, longitude,state/province, and country).
- Configured Custom Fields in Log Analytics Workspace with the intent to mapping geo data in Azure Sentinel.
- Configure Azure Sentinel (Microsoft's cloud SIEM) workbook to display global attack data (RDP brute force) on a world map according to a physical location and magnitude of attacks.

<p align="center">
Running The Log Exporter PowerShell Script: <br/>
<img src="https://imgur.com/vfGQL3i.png" height="80%" width="80%" alt=" steps"/>
<br />
<br />
Creating The Workbook : <br/>
<img src="https://imgur.com/Jsl4vwX.png" height="80%" width="80%" alt=" steps"/>
<br />
<br />
World map of incoming attacks (built custom logs including geodata) : <br/>
<img src="https://imgur.com/gMKEiHm.png" height="80%" width="80%" alt=" steps"/>
<br />
<br />

