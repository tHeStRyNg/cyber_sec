### Metasploit
``` msfconsole ```

``` use <module> ```

``` check <ip> after module in use checks if exp ```

``` info after module in use ```

``` search <reg_module_name_expression> ```

``` set ForceExploit false ```

``` set AutoCheck false ```

``` set LHOST 95.179.242.45 ```

``` set RHOSTS 195.208.40.50 ```

``` set SRVPORT 4899 ```

``` run  ```

### Encoders - 
Resource - ```https://www.scriptjunkie.us/2011/04/why-encoding-does-not-matter-and-how-metasploit-generates-exes/ ```
``` msfencode was replaced by msfvenom in 2015 so to encode use msfvenom -e and it should encode

### Exe Generation with no Payload
``` echo -n | msfvenom -a x86 --platform Windows -e generic/none -f exe > myn.exe ```

### Example for Virus Total test with generic none encoding.
``` root@cloud1:/opt/sqlmap# echo -n | msfvenom -a x86 --platform Windows -e generic/none -f exe > myn.exe
Attempting to read payload from STDIN...
Found 1 compatible encoders
Attempting to encode payload with 1 iterations of generic/none
generic/none succeeded with size 0 (iteration=0)
generic/none chosen with final size 0
Payload size: 0 bytes
Final size of exe file: 73802 bytes
```
### Check file encoded 

``` ls -ls myn.exe && file myn.exe ```

``` 76 -rw-r--r-- 1 root root 73802 Apr 13 23:15 myn.exe ```

``` myn.exe: PE32 executable (GUI) Intel 80386, for MS Windows ```

## SqlMap
``` https://book.hacktricks.xyz/pentesting-web/sql-injection/sqlmap ```

## AV Engines
VirusTotal - ``` https://www.virustotal.com/gui/home/upload ```

```
root@cloud1:/opt/sqlmap# curl -X POST https://www.virustotal.com/vtapi/v2/file/scan -F apikey=b5b24bcfc00757dc6d4e566207d51cf97f6e0ea34f6643475cf726475b9bdf29 -F file=@myn.exe
{"md5":"d3bb436495fa55c27609acfd8397235d","permalink":"f-5c9488072190679ef15825888b34e0486425991a451cb780e8cf1364f5bac200-1713051502","resource":"5c9488072190679ef15825888b34e0486425991a451cb780e8cf1364f5bac200","response_code":1,"scan_id":"5c9488072190679ef15825888b34e0486425991a451cb780e8cf1364f5bac200-1713051502","sha1":"6c5ac1b984a859d18b8955531b46e7459eca87cc","sha256":"5c9488072190679ef15825888b34e0486425991a451cb780e8cf1364f5bac200","verbose_msg":"Scan request successfully queued, come back later for the report"}
```
## Submit a file

``` curl -X POST https://www.virustotal.com/vtapi/v2/file/scan -F apikey=b5b24bcfc00757dc6d4e566207d51cf97f6e0ea34f6643475cf726475b9bdf29 -F file=@myn.exe ```

## Get the report on the above submission
``` curl --request GET --url "https://www.virustotal.com/vtapi/v2/file/report?apikey=b5b24bcfc00757dc6d4e566207d51cf97f6e0ea34f6643475cf726475b9bdf29&scan_id=5c9488072190679ef15825888b34e0486425991a451cb780e8cf1364f5bac200-171305150&resource=5c9488072190679ef15825888b34e0486425991a451cb780e8cf1364f5bac200"

```

### Response with report url:

```
{"md5":"d3bb436495fa55c27609acfd8397235d","permalink":"https://www.virustotal.com/gui/file/5c9488072190679ef15825888b34e0486425991a451cb780e8cf1364f5bac200/detection/f-5c9488072190679ef15825888b34e0486425991a451cb780e8cf1364f5bac200-1713051502","positives":57,"resource":"5c9488072190679ef15825888b34e0486425991a451cb780e8cf1364f5bac200","response_code":1,"scan_date":"2024-04-13 23:38:22","scan_id":"5c9488072190679ef15825888b34e0486425991a451cb780e8cf1364f5bac200-1713051502","scans":{"ALYac":{"detected":true,"result":"Trojan.CryptZ.Marte.1.Gen","update":"20240413","version":"2.0.0.10"},"APEX":{"detected":true,"result":"Malicious","update":"20240413","version":"6.521"},"AVG":{"detected":true,"result":"Win32:SwPatch [Wrm]","update":"20240413","version":"23.
```

## DNS Tools

``` https://dnsdumpster.com/ ``` - Visual on services and diagrams of domain dependencies and addresss

## Other

``` https://hackertarget.com ```

``` https://www.shodan.io ```

info ```nikto - ubuntu 20.x web vulerability scanner shell - 2024 version 2.1.5```

### Example

``` nikto -C all -h https://skilledfundedtraders.com ```

Info Install --> ``` apt-get install nikto -y ```

4 - Burp Suite Community Edition - ``` https://portswigger.net/burp/communitydownload``` 

5 - Malware Analysis -- ``` https://remnux.org/ ```

6 - Penetration test OS - ``` https://www.kali.org/ ```

``` https://hashcat.net/hashcat/ ``` - Advanced Pwd Recovery

### WarGames

``` https://hackthissite.org/ ```

