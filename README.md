# PrintNightmare
![image](https://user-images.githubusercontent.com/86879266/124354518-146c5500-dc15-11eb-98a3-f84d5ee28585.png)


Windows Print Spooler Service RCE CVE-2021-1675 (PrintNightmare)

How to disable the Print Spooler service ?



# CMD Shell

net start | findstr -i "spooler"

net stop spooler

REG ADD "HKLM\SYSTEM\CurrentControlSet\Services\Spooler" /v "Start " /t REG_DWORD /d "4" /f



# PowerShell

Get-Service -Name Spooler

Stop-Service -Name Spooler -Force

Set-Service -Name Spooler -StartupType Disabled



# Service Control

sc query Spooler

sc config Spooler start=disabled



# References
https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-34527

#CVE-2021-1675 #PrintNightmare #WindowsPrintSpoolerServiceRCE

