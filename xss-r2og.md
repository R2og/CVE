# blood-bank-system-in-php has Cross Site Scripting vulnerability

## supplier 
https://code-projects.org/blood-bank-system-in-php-with-source-code/
## Vulnerability file
/admin/user.php
## describe
There is an  Cross Site Scripting vulnerability in blood-bank-system-in-php  in /admin/user.php. Control parameter: $email

A malicious attacker can use this vulnerability to obtain administrator login credentials or phishing websites

## code analysis

In /admin/user.php，get $row['usermail'], and echo it in no filter.

![Image](https://github.com/user-attachments/assets/9c9c9b60-409e-45bf-81eb-fc31f53d0a56)

## POC

```
GET /admin/user.php HTTP/1.1
Host: bloodbankmgmtsystem
Cache-Control: max-age=0
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/122.0.6261.112 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7
Accept-Encoding: gzip, deflate, br
Accept-Language: zh-CN,zh;q=0.9
Cookie: PHPSESSID=804anp674fsb2cu5c12kqkrka4
Connection: close


```

**Result**

![Image](https://github.com/user-attachments/assets/3791565c-425a-4b51-8e7d-8dd875fa7fde)

![Image](https://github.com/user-attachments/assets/3372f459-1806-421b-9230-8dd933dd61a3)