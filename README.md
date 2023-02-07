# Attachemnt Tool
A desktop application that facilitates efficient bulk transfer of files to and from the CRM system.

## Application Context
TecEx is a company that provides customs compliance solutions through turnkey Import or Export Representation (IOR) services, serving as an Exporter of Record (EOR) and offering full door-to-door (DDP) solutions across various sectors. They use Salesforce as their Customer Relationship Management (CRM) tool.

TecEx is committed to delivering exceptional client service and have a strong focus on scalability of their technology. To achieve this, the company's Cloud team, creates innovative applications that automate processes, streamlines workflows, and eliminates manual errors. The aim is to ensure that the company can efficiently handle increasing demands from clients while maintaining a high level of service quality.

As part of my role in TecEx's Cloud team, I developed this Attachment Tool.  This app is used by various teams throughout the company.

## Application Overview

The attachment tool is a desktop application, which allows a user to upload or download files to the CRM system - Salesforce. In Salesforce, multilpe object types exist which could have files attached to them. Each object can have multiple instances, called records. The Attachment Tool enables a user to transfer large amounts of files between their PC and Salesforce - a process that is extreamly time consuming when carried out manually or file by file. 

<p align="center">
  <img width="739" height="354" src="https://github.com/AButton90/Attachment_Tool/blob/main/images/Att_Tool_Flow.png">
</p>

Excel files are used by the user to specify the details of the file transfer. To download files, the user only specifies the record IDs which attachements they require.  For an upload of files, the user specifies the record ID and the file name they want to upload. Once the user has captured the information, the tool is launched from their desktop.

<p align="center">
  <img width="550" height="270" src="https://github.com/AButton90/Attachment_Tool/blob/main/images/Att_Tool_Config.png">
</p>


### Application

Launching the app will propmt the user for their login details - if it is the user's first time using the app, it will additionally ask for a password and security token. Making use of the Keyring library the user's credentials are saved in their Windows Credential Manager, allowing them use of the tool without supplying credentials upon each launch.

<p align="center">
  <img width="557" height="150" src="https://github.com/AButton90/Attachment_Tool/blob/main/images/Att_Tool_Login.png">
</p>

Once the user's is connected to Salesforce throught the app, they will be prompted to pick a process they want to follow: Upload files or Download files. The user also needs to supply the path the the config file.

<p align="center">
  <img width="678" height="386" src="https://github.com/AButton90/Attachment_Tool/blob/main/images/Att_Tool_Process.png">
</p>

### Download

  If downloading files from the CRM system, the tool will display the record IDs provided in the config file as well as the record type - this allows the user to confirm that the correct IDs were supplied.  The user also needs to specify the path where they want to download the files to.

<p align="center">
  <img width="706" height="371" src="https://github.com/AButton90/Attachment_Tool/blob/main/images/Att_Tool_Download.png">
</p>

### Upload

  Similar to the download process, when uploading the user will be able to review the info provided in the config file as well as specify the path on their PC where the files are stored

<p align="center">
  <img width="784" height="334" src="https://github.com/AButton90/Attachment_Tool/blob/main/images/Att_Tool_Upload.png">
</p>


While the up- or download is running, the user is able to view the progress of the process. Next to each document's ID the status of the download will be indicated, if a failure occurs, the error message will give more info on the failure.  The tool is also setup to compare all files attached to the record and if the content of two documents are identical, only one file will be downloaded.

<p align="center">
  <img width="546" height="479" src="https://github.com/AButton90/Attachment_Tool/blob/main/images/Att_Tool_Processing.png">
</p>

### Reporting

Once done, the app will email a report with the up-/download results to the user.  The report contains information on each record and all its attachments, including file names, saved names, status, size, created date and any errors that occured in the process 

<p align="center">
  <img width="1248" height="209" src="https://github.com/AButton90/Attachment_Tool/blob/main/images/Att_Tool_Report.png">
</p>


## Python Libraries

The follwing Python libraries were used in the Attachment Tool desktop app:

- keyring
- PySimpleGUI
- simple_salesforce
- openpyxl
- requests
- base64
- json
- os
- hashlib
- re
- threading
- queue
- smtplib
- email
