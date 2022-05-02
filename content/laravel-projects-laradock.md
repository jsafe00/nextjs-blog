---
slug: laravel-projects-laradock
title: Run Multiple Laravel Projects with Databases using Laradock
description: 
date: 05-April-2022
---

Your folder structure should look like this:

*   laradock

*   project-1

*   project-2

In your root folder execute:

**git clone  https://github.com/laradock/laradock.git**

Go to laradock folder

**cd laradock**

Copy env-example and rename it to .env

**cp env-example .env**

In laradock env file, type DB_HOST=mysql at the top.

![](https://dev-to-uploads.s3.amazonaws.com/i/1goh7t81fe5wn1o75tnw.PNG)

In nginx/sites, copy laravel.conf and rename it to your laravel project names

![](https://lh3.googleusercontent.com/v2gNAAZBSrKOH5x3ae4SA09RH8hZn591cCcSUXUtgDvDHdjVQNwxJGOYNdecAtFC8V9MZ3HSTeAid8wdkmkjKfP61z2LxhB94KC4Oq0Hkk-w0fjCCvoQkKPpI-Hhz1slFYMz5jkAWM8=w2400)

Don’t forget to update host file at C:\Windows\System32\drivers\etc\hosts and add this at the end of the file.

127.0.0.1  blog.test

127.0.0.1  laravel.test

Then execute:

**docker-compose up -d nginx mysql phpmyadmin**

![](https://lh3.googleusercontent.com/ZugeWKGHWDi7pFHqV-MAx2AUI6CvG8e3XMlBRHQT7MkSRdbSbuD-6uDbJV9pFP3exWJuwIW8Qgecor-_NV_A54aVkNP8J3ClJshvEmVJyYmC6lgA2yHm4Ksuaqr0wJ_3lNqvxdB95E0=w2400)

Access your sites in the browser:

![](https://dev-to-uploads.s3.amazonaws.com/i/nii41tqvjt4s13f9e3cr.PNG)

![](https://dev-to-uploads.s3.amazonaws.com/i/pru1147aa6iuczcylglf.PNG)

**Database Migration**

In your laradock env, update MYSQL_DATABASE with the name of your databases

**laradock env**

![](https://s1.imghub.io/KXqkl.png)

**blog env**



![](https://dev-to-uploads.s3.amazonaws.com/i/7xl0x73r9ni174f0t8d7.PNG)

**laravel env**

![](https://dev-to-uploads.s3.amazonaws.com/i/5k7nj9czslfrns3voa7v.PNG)

Execute **winpty docker-compose exec workspace bash** and go to each laravel project then execute  **php artisan migrate**

![](https://dev-to-uploads.s3.amazonaws.com/i/48168j5dm8hg7n8rhxb4.PNG)

***

***

![](https://dev-to-uploads.s3.amazonaws.com/i/0ike93ve6uujb9n7qn60.PNG)

Accessing database in Heidi:

**Hostname: 127.0.0.1**

**User: default**

**Password: secret**

**Port: 3306**

![](https://dev-to-uploads.s3.amazonaws.com/i/qoovpa8osdq1bms58c6x.PNG)

If you're having an error about access denied, just go to mysql container and execute the ff:

![](https://lh3.googleusercontent.com/yN9FNyzb2HRrcZ3xLpPWpbtKlp57bvZww_yQJhjthfWpwGAFVM0vc-HyAhqj15kqLTNLUb-nabFLEyWSCoI5mlqzT2xLV2oPE0OPMmlxcrnwJqoV21L1LhKNd5TjnXj-5_mMC9fvB_0=w2400)

**winpty docker exec -it {mysql container} bash**

![](https://lh3.googleusercontent.com/aJAFgxKVvcKwbH8sEzm4y9FRLIG2jPIS3vCetfcLecNTXNEJ8YRY7jAJWJAl5IJuytOaS9xQMwa-w0yKu_DMLhX-qT-8uxj3NKf2nVd4aGZi4b1ZMQrwM81Tu-YRExIdW726jgjt-LY=w2400)

![](https://lh3.googleusercontent.com/-QiCFktvlTbsBt9e2seXfDAOILVLBQHdZ83ePXpyTZ30SHFIte9AkwX98px7bECk7chzpu7FXNliFslmMHDP3T23FQjoMl4IaP0bOJvVl493F5r00rExxUlTItNmF7NhJOJkz4cBoW4=w2400)

![](https://lh3.googleusercontent.com/hqzpMu56JeZrXoo-1VCrux_gjDpfmgNQHh2LInuE_IhOUGQ_wTVDbvHyH6kMjr8olE7R1JksWSRjCOD0A3_Fc0JrCuQIAX3CJNvobtTDxrvMM0k1zVOogFxRahFIwvX5vN9BCZrXHWc=w2400)


