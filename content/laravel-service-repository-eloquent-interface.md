---
slug: laravel-service-repository-eloquent-interface
title:  Implement CRUD with Laravel Service-Repository Pattern with Eloquent Interface
description: 
date: 11-April-2022
---

This is a continuation of my previous post: https://josafebalili.vercel.app/laravel-service-repository-interface

Eloquent for me means querying data in database in an elegant way.

https://laravel.com/docs/8.x/eloquent



![](https://lh3.googleusercontent.com/roY3w--2Y7v0-ab8caeOpwq\_2wpBpAv-3IF68iN-x2bFfEkkszkZH5Yedn0Di0HJ8bBeGWMBan6ka1I06s8xJ5Q7PmyX7laKQ4Xk7fwsKZGt4uE91nFqsz9EBbou5bNXxoJVfWwy38Y=w2400)

Let's bind it.

![](https://lh3.googleusercontent.com/KDlEML2lPN-UHnLhDagHuOSmd6Vgyb0dg1v6xslD-3c18UvVjyw6OIBWWg7TtUos7Jz9XUMyhckPBAu-HbCNQZyq5IlFpBe4kx3pm1u5Hb1UHYTre0\_oRejLELjpz7m87dcf0HDFruc=w2400)

Don't forget to change your PostService constructor to EloquentPostRepositoryInterface.

######

public function \__construct(EloquentPostRepositoryInterface $postRepository)

{        

$this->postRepository = $postRepository;   

 }

You can check the repo at https://github.com/jsafe00/laravel-service-repository/tree/with-eloquent-interface
