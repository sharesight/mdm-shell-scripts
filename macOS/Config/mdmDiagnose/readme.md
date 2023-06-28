# Intune MDM Log Gather Script

This is a script to help with macOS log gathering. The intent is to use [Intune Shell Script](https://docs.microsoft.com/en-us/mem/intune/apps/macos-shell-scripts) to deploy the script and then to download the gathered logs for MDM troubleshooting diagnosis.

The steps to use this script are as follows:

1. Deploy script via [Intune Shell Scripting](https://docs.microsoft.com/en-us/mem/intune/apps/macos-shell-scripts)
2. Wait for script to complete
3. Use [Intune Script Agent Log Collection](https://docs.microsoft.com/en-us/mem/intune/apps/macos-shell-scripts#troubleshoot-macos-shell-script-policies-using-log-collection) to gather the log files
4. Download the logs from Intune to your desktop

---
**NOTE**

It's often useful to target this script to a Log Gathering group in AAD and set it to run daily. 

---

# Tip for log collection

When the script completes, in the output window it will print a semi-colon separated list of log files that it has created. This line can be copied and pasted directly into the log gathering UI of Intune to avoid having to type out each file manually.


```
####################################### ## ## The following logs were created ## ####################### /Library/Logs/Jamf/Scripts/mdmDiagnose/mdmclientLogs.txt;/Library/Logs/Jamf/Scripts/mdmDiagnose/appInstallLogs.txt;/Library/Logs/Jamf/Scripts/mdmDiagnose/InstalledProfiles.txt;/Library/Logs/Jamf/Scripts/mdmDiagnose/enrollmentProfileInfo.txt;/Library/Logs/Jamf/Scripts/mdmDiagnose/system.log.3.gz;/Library/Logs/Jamf/Scripts/mdmDiagnose/InstalledApps.txt;/Library/Logs/Jamf/Scripts/mdmDiagnose/system.log.2.gz;/Library/Logs/Jamf/Scripts/mdmDiagnose/system.log.1.gz;/Library/Logs/Jamf/Scripts/mdmDiagnose/DeviceInformation.txt;/Library/Logs/Jamf/Scripts/mdmDiagnose/system.log.0.gz;/Library/Logs/Jamf/Scripts/mdmDiagnose/system.log;/Library/Logs/Jamf/Scripts/mdmDiagnose/install.log;/Library/Logs/Jamf/Scripts/mdmDiagnose/InstalledCerts.txt;/Library/Logs/Jamf/Scripts/mdmDiagnose/SecurityInfo.txt;
```




# Example set of output logs
```
/Library/Logs/Jamf/Scripts/mdmDiagnose/mdmclientLogs.txt
/Library/Logs/Jamf/Scripts/mdmDiagnose/appInstallLogs.txt
/Library/Logs/Jamf/Scripts/mdmDiagnose/InstalledProfiles.txt
/Library/Logs/Jamf/Scripts/mdmDiagnose/enrollmentProfileInfo.txt
/Library/Logs/Jamf/Scripts/mdmDiagnose/system.log.3.gz
/Library/Logs/Jamf/Scripts/mdmDiagnose/InstalledApps.txt
/Library/Logs/Jamf/Scripts/mdmDiagnose/system.log.2.gz
/Library/Logs/Jamf/Scripts/mdmDiagnose/system.log.1.gz
/Library/Logs/Jamf/Scripts/mdmDiagnose/DeviceInformation.txt
/Library/Logs/Jamf/Scripts/mdmDiagnose/system.log.0.gz
/Library/Logs/Jamf/Scripts/mdmDiagnose/system.log
/Library/Logs/Jamf/Scripts/mdmDiagnose/install.log
/Library/Logs/Jamf/Scripts/mdmDiagnose/InstalledCerts.txt
/Library/Logs/Jamf/Scripts/mdmDiagnose/SecurityInfo.txt
```
