#### File upload

In `laobancms/admin/wenjian.php` line 103 to 112

![](https://github.com/Cumtyuanfeng/Laobancms/blob/master/images/File_upload_1.png)




It  simply validates the existence of '.jpg |.png |.gif |.jpeg |.html |.js |.css' in the file name by using the strstr() function.

So ,upload `test.jpg.php`

First,login the admin page by setting the cookie(id=1)  (CVE-2018-19224)




![](https://github.com/Cumtyuanfeng/Laobancms/blob/master/images/Cookie.png)






Visit `admin/wenjian.php?wj=../templets/pc`, upload `test.jpg.php`

![](https://github.com/Cumtyuanfeng/Laobancms/blob/master/images/File_upload_2.png)






Vist: `templets/pc/test.jpg.php`

![](https://github.com/Cumtyuanfeng/Laobancms/blob/master/images/File_upload_3.png)

We can get shell !





#### XSS1

Login the admin page by setting the cookie(id=1)  (CVE-2018-19224)

Visit: `admin/info.php?shuyu=基础设置`

Fill `"><script>alert(1)</script>` in the  "网站SEO关键词"  form

Click the '保存更改' button to save the changes

Click the '生成'->'更新今日' button in the upper right corner to update

Then visit the index

![](https://github.com/Cumtyuanfeng/Laobancms/blob/master/images/XSS_1_1.png)




![](https://github.com/Cumtyuanfeng/Laobancms/blob/master/images/XSS_1_2.png)





#### XSS2

Login the admin page by setting the cookie(id=1)  (CVE-2018-19224)

Visit:  `admin/info.php?shuyu=我的参数`

Fill   `<script>alert(1)</script>` in the  "首页简介"  form

Click the '保存更改' button to save the changes

Click the '生成'->'更新今日' button in the upper right corner to update

Then visit the index

![](https://github.com/Cumtyuanfeng/Laobancms/blob/master/images/XSS_2_1.png)



![](https://github.com/Cumtyuanfeng/Laobancms/blob/master/images/XSS_2_2.png)

