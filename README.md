# **🔍 Google Dorks Collection for Ethical Hacking & Penetration Testing**  

A curated list of **150+ Google dorks** to help security researchers, bug bounty hunters, and penetration testers find exposed sensitive data, misconfigurations, and vulnerabilities.  

### **📌 Key Features**  
- **Admin Panels & Login Pages** – Discover unprotected access points.  
- **Database Leaks** – Find exposed SQL files, credentials, and configs.  
- **Open Directories** – Locate unsecured file listings.  
- **IoT & Cameras** – Identify exposed devices.  
- **API Keys & Secrets** – Detect leaked credentials.  
- **Cloud & Git Exposures** – Uncover misconfigured S3 buckets, `.git` folders, and more.  

### **⚠️ Legal & Ethical Use**  
- **Only test systems you own or have explicit permission to scan.**  
- **Unauthorized use may violate laws like the CFAA, GDPR, etc.**  
- **Responsible disclosure is mandatory—report vulnerabilities to owners.**  

### **🚀 Quick Start**  
```bash
git clone https://github.com/your-repo/google-dorks.git  
```  

**Contributions welcome!** Add new dorks, improve categorization, or suggest defenses.  

🔐 **Stay Ethical, Stay Secure.**  

### **1. Exposed Admin Panels & Login Pages**  
1. `intitle:"Admin login"`  
2. `inurl:/admin/login.php`  
3. `intitle:"Login" inurl:/admin`  
4. `inurl:"/wp-admin" -"wp-content"` (WordPress)  
5. `inurl:"/administrator" intitle:"Joomla"`  
6. `intitle:"Dashboard" inurl:"/admin"`  
7. `inurl:"/admin" filetype:php`  
8. `intitle:"Webmin" inurl:"/session_login.cgi"`  
9. `inurl:"/cpanel" intitle:"cPanel"`  
10. `intitle:"Login - Drupal"`  

### **2. Database & Configuration File Leaks**  
11. `filetype:sql "CREATE TABLE"`  
12. `filetype:env DB_USERNAME NOT root`  
13. `ext:ini "[database]"`  
14. `filetype:bak intext:"password"`  
15. `filetype:log "error" "password"`  
16. `intext:"DB_PASSWORD" filetype:env`  
17. `ext:sql "INSERT INTO" "users"`  
18. `filetype:config intext:"<connectionString>"`  
19. `intext:"API_KEY" filetype:env`  
20. `filetype:json "api_key"`  

### **3. Exposed Sensitive Documents**  
21. `filetype:pdf "confidential"`  
22. `filetype:xls "password"`  
23. `filetype:docx "internal use only"`  
24. `ext:csv "credit card"`  
25. `filetype:txt "username" "password"`  
26. `filetype:rtf "proprietary"`  
27. `filetype:pptx "financial report"`  
28. `intext:"SSN" filetype:csv`  
29. `filetype:bak "backup"`  
30. `filetype:xml "credentials"`  

### **4. Open Directories & File Listings**  
31. `intitle:"Index of /" "parent directory"`  
32. `inurl:/backup "index of"`  
33. `intitle:"Index of /" "database.sql"`  
34. `inurl:"/logs" "index of"`  
35. `intitle:"Index of /" "wp-config.php"`  
36. `inurl:"/backup" filetype:zip`  
37. `intitle:"Index of /" "credentials"`  
38. `inurl:"/uploads" "index of"`  
39. `intitle:"Index of /" "backup.tar.gz"`  
40. `inurl:"/wwwroot" "index of"`  

### **5. Vulnerable Web Applications**  
41. `inurl:"/phpmyadmin" intitle:"phpMyAdmin"`  
42. `inurl:"/shell" intitle:"r57"` (Potential backdoor)  
43. `inurl:"/debug" intitle:"Debug Console"`  
44. `inurl:"/console" intitle:"Web Console"`  
45. `inurl:"/filemanager" intitle:"FileManager"`  
46. `inurl:"/test" intitle:"Test Page"`  
47. `inurl:"/git" intitle:"Index of /.git"`  
48. `inurl:"/backdoor" filetype:php`  
49. `inurl:"/cgi-bin" "password"`  
50. `inurl:"/api" intext:"API key"`  

### **6. Exposed IoT & Cameras**  
51. `intitle:"Live View" inurl:"/view/viewer.shtml"`  
52. `inurl:"/view/index.shtml"`  
53. `intitle:"webcamXP" inurl:":8080"`  
54. `inurl:"/axis-cgi/mjpg"`  
55. `intitle:"Network Camera" inurl:"/admin/"`  
56. `inurl:"/cgi-bin/viewer/video.jpg"`  
57. `intitle:"IP Camera" inurl:"/login.htm"`  
58. `inurl:"/video.mjpg"`  
59. `intitle:"Camera Viewer" inurl:"/view/view.shtml"`  
60. `inurl:"/webcapture.jpg"`  

### **7. Git & Version Control Exposures**  
61. `inurl:"/.git/config"`  
62. `intitle:"Index of /.git"`  
63. `filetype:git "HEAD"`  
64. `inurl:"/.git/HEAD"`  
65. `inurl:"/gitlab" intitle:"GitLab"`  
66. `inurl:"/bitbucket" intitle:"Bitbucket"`  
67. `inurl:"/.svn/entries"`  
68. `filetype:svn "svn://"`  
69. `inurl:"/github" intext:"API_TOKEN"`  
70. `inurl:"/repo" intitle:"Repository"`  

### **8. API & Developer Key Leaks**  
71. `intext:"API_KEY" filetype:env`  
72. `intext:"SECRET_KEY" filetype:yml`  
73. `inurl:"/api/v1" intext:"token"`  
74. `filetype:json "api_key"`  
75. `intext:"AWS_ACCESS_KEY_ID" filetype:env`  
76. `intext:"Bearer Token" filetype:txt`  
77. `intext:"Firebase API key"`  
78. `intext:"OAuth" filetype:json`  
79. `intext:"JWT_SECRET" filetype:env`  
80. `intext:"Stripe API key"`  

### **9. Misconfigured Cloud Services**  
81. `inurl:"s3.amazonaws.com" "public"`  
82. `inurl:"blob.core.windows.net" "public"`  
83. `inurl:"storage.googleapis.com" "open"`  
84. `intext:"AWS S3 Bucket" filetype:csv`  
85. `inurl:"digitaloceanspaces.com" "listing"`  
86. `intext:"Azure Storage Account" filetype:txt`  
87. `inurl:"/s3cfg" filetype:conf`  
88. `inurl:"/aws.yml" filetype:yml`  
89. `intext:"Google Cloud API key"`  
90. `inurl:"/storage" intitle:"Bucket Listing"`  

### **10. Exposed VPN & Remote Access**  
91. `intitle:"OpenVPN Client" filetype:ovpn`  
92. `inurl:"/remote/login" intitle:"Remote Desktop"`  
93. `intext:"PPTP VPN" filetype:conf`  
94. `inurl:"/sslvpn" intitle:"SSL VPN"`  
95. `filetype:rdp "full address:s:"`  
96. `inurl:"/vpn/index.html"`  
97. `intext:"Cisco VPN" filetype:txt`  
98. `inurl:"/forticlient" intitle:"FortiClient"`  
99. `inurl:"/vpnconfig.ovpn"`  
100. `intext:"WireGuard Config" filetype:conf`  

### **11. Default Passwords & Credentials**  
101. `intitle:"Default Password"`  
102. `intext:"Default username admin"`  
103. `inurl:"/password.txt"`  
104. `filetype:txt "default credentials"`  
105. `intext:"Default login admin:admin"`  
106. `inurl:"/passwords.csv"`  
107. `intext:"Router Default Password"`  
108. `filetype:xls "username" "password"`  
109. `intext:"Default SSH key"`  
110. `inurl:"/creds.txt"`  

### **12. Exposed Backups & Archives**  
111. `filetype:zip "backup"`  
112. `inurl:"/backup.sql"`  
113. `filetype:tar.gz "var/www"`  
114. `inurl:"/dump.sql"`  
115. `filetype:bak "password"`  
116. `inurl:"/wwwroot.zip"`  
117. `filetype:rar "confidential"`  
118. `inurl:"/backup.tar"`  
119. `filetype:7z "database"`  
120. `inurl:"/db_backup"`  

### **13. Exposed GitLab & CI/CD Configs**  
121. `inurl:"/.gitlab-ci.yml"`  
122. `filetype:yaml "stages" "deploy"`  
123. `intext:"CI_JOB_TOKEN" filetype:yml`  
124. `inurl:"/gitlab-runner/config.toml"`  
125. `intext:"DOCKER_REGISTRY" filetype:env`  
126. `inurl:"/pipeline.yml"`  
127. `intext:"KUBECONFIG" filetype:yaml`  
128. `inurl:"/deploy.sh"`  
129. `intext:"ANSIBLE_VAULT" filetype:yml`  
130. `inurl:"/docker-compose.yml"`  

### **14. Exposed Payment & Financial Data**  
131. `filetype:csv "credit card"`  
132. `intext:"Invoice" filetype:xlsx`  
133. `filetype:pdf "bank statement"`  
134. `intext:"Payment Gateway" filetype:env`  
135. `inurl:"/transactions.csv"`  
136. `filetype:xml "PAN"` (Primary Account Number)  
137. `intext:"Stripe Secret Key"`  
138. `filetype:log "payment failed"`  
139. `intext:"PayPal API" filetype:txt`  
140. `inurl:"/billing" intitle:"Billing Records"`  

### **15. Miscellaneous Security Exposures**  
141. `inurl:"/phpinfo.php"`  
142. `intext:"SQL syntax error" filetype:log`  
143. `inurl:"/debug.log"`  
144. `filetype:txt "password reset link"`  
145. `inurl:"/wp-config.php~"` (WordPress backup)  
146. `intext:"Firewall Rule" filetype:conf`  
147. `inurl:"/redacted.pdf"` (Possible sensitive docs)  
148. `intext:"VPN Config" filetype:ovpn`  
149. `inurl:"/secrets.yml"`  
150. `filetype:sh "chmod 777"`  
