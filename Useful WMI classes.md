# Useful WMI classes
## Filesystem, Hardware, Network, PowerShell, Processes, Services, Software 
### URL: https://www.jesusninoc.com/2012/12/10/useful-wmi-classes/
```PowerShell
#Serial Number, Vendor, information
Get-WmiObject -Class Win32_ComputerSystem

#Bios Information , including Version Number of BIOS
Get-WmiObject -Class win32_bios

#Battery Information
Get-WmiObject -Class win32_battery

#Serial Number, Capacity, Part Number of Installed Memory Stick
Get-WmiObject -Class win32_Physicalmemory

#Capacity, Serial Number of Drive and other info of the Hard-disk
Get-WmiObject -Class win32_DiskDrive

#Monitor Information including Resolutions
Get-WmiObject -Class win32_DesktopMonitor

#Information Related Cd Drive
Get-WmiObject -Class win32_cdromdrive

#Network Adaptor information contains, manufacturer, MAC ID etc
Get-WmiObject -Class win32_networkadapter

#Mouse related information
Get-WmiObject -Class win32_pointingdevice

#OS Name, OSArchitecture, Version Info
Get-WmiObject -Class win32_operatingsystem

#DeviceID, Free Space, Size of Partition
Get-WmiObject -Class win32_logicalDisk

#Mapped Network Drives
Get-WmiObject -Class Win32_NetworkConnection

#List of Installed Printers
Get-WmiObject -Class win32_printer

#List of Printer Drivers
Get-WmiObject -Class win32_PrinterDriver

#IP Adress, DHCP , DNS and other information of Network Drivers
Get-WmiObject -Class Win32_NetworkAdapterConfiguration

#Command that runs automatically when a user logs onto the computer system
Get-WmiObject -Class win32_startupCommand

#All Running Processes
Get-WmiObject -Class win32_process

#List of All Services
Get-WmiObject -Class win32_Service

#List of Installed Software
Get-WmiObject -Class win32_Product

```
