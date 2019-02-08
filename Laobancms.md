#### File upload

In `laobancms/admin/wenjian.php` line 103 to 112

![File_upload_1](.\images\File_upload_1.png)



It  simply validates the existence of '.jpg |.png |.gif |.jpeg |.html |.js |.css' in the file name by using the strstr() function.

So ,upload `test.jpg.php`

First,login the admin page by setting the cookie(id=1)  (CVE-2018-19224)



![Cookie](.\images\Cookie.png)



Visit `admin/wenjian.php?wj=../templets/pc`, upload `test.jpg.php`

![File_upload_2](.\images\File_upload_2.png)



Vist: `templets/pc/test.jpg.php`

![File_upload_3](.\images\File_upload_3.png)

We can get shell !



#### XSS1

Visit: `admin/info.php?shuyu=基础设置`

Fill `"><script>alert(1)</script>` in the  "网站SEO关键词"  form

![XSS_1_1](.\images\XSS_1_1.png)



![XSS_1_2](.\images\XSS_1_2.png)



#### XSS2

Visit:  `admin/info.php?shuyu=我的参数`

Fill   `<script>alert(1)</script>` in the  "首页简介"  form

![XSS_2_1](.\images\XSS_2_1.png)



![XSS_2_2](.\images\XSS_2_2.png)

