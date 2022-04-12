---
slug: laravel-queues-redis-horizon
title: Setup Laravel Queues using Redis and Horizon
description: 
date: 09-April-2022
---

You can find the repo here: <https://github.com/jsafe00/laravel-queues-redis-horizon>

I’m using the docker-template from <https://github.com/ahmedash95/laravel-docker-template>  with a few changes since I’m using php 8 on my laravel app example.

I will not go through how to implement laravel-export and how to set up mailtrap since I will just focus on how to setup laravel queues using redis and horizon.

If you want to know more about redis and horizon, you can check the laravel documentation.

<https://laravel.com/docs/8.x/redis>

<https://laravel.com/docs/8.x/horizon> 

Procedure:

1.  Lets install first redis by executing  **composer require predis/predis.**

2.  Open .env file and change queue_driver from database to redis.

3.  In this line, we are using Redis::throttle command and passing in the ‘key’. You can change that anything you want. The Redis::throttle using the ‘key’ will be limited to running 10 times and 60 seconds in our example.

**App\Jobs\SendUserEmail.php**

![Alt Text](https://lh3.googleusercontent.com/5mMB0ZCgxlmTvsEu8Dn-IDQ3dRpD1ROV9nBNKUb8TkX5zSwbZLtzvtP7Ni0YuozRARAH8J3Uoczd4sFekI8fP01fvRS3tjv7KeBLmVc7eUHI5AuCBYrboKaFzMJm8v_8QJA8-dj08vk=w2400)

4. Next we’ll install horizon by executing:

\*\*composer require laravel/horizon \*\*

Then publish the configuration: **php artisan vendor:publish --provider="Laravel\Horizon\HorizonServiceProvider"**

5. Then, in config/horizon.php add the following in Queue Worker Configuration part.

![Alt Text](https://lh3.googleusercontent.com/yxBhstCw-BNe7gqUJeLCKUPKXLJgKojc7RIdfedUm_XdBg2CxfZ4wRIkxgA2QhsqJM1HuJckoP-1XZTkZGXXD9wv8vXzC7Qq6Cq_SNhAAfwL3nwq1iArTYpKqOr3YK_r6FB1zq3FFjM=w2400)

6. Execute horizon in the terminal.

![](https://lh3.googleusercontent.com/7i6EE6z0p8aKS-U_VbABu6eDPqvo3PRUvZGhBTZDBkO_XsjTvfhTdVeC6rIg3qIc9rgV0Ls-7molJ2SgGdJQBsIE7TDmrMQJfHryYRDpW20CGe-JMcrkb4kkmjj8Ctx1bMcXmlJxnPs=w2400)

7. Make sure when you check horizon dashboard the status is active.![](https://lh3.googleusercontent.com/aLxAtOBChQS7GpEJon-pR_UBwiyVDKSAS3bGcc-FIPcYKshrYa3AwPfWB4wSKJtHufZQYJZ1lemUp3r1bOht-P2aZAP80YOP7SRdj5TcFEh5oUH03FfHIpWvt44pFhqLtnA2_eGaVPM=w2400)

![](https://lh3.googleusercontent.com/RJR21gH6VrXr4CxqqRrtAy8CZZFgkZ_33MpM4cqkS8_YZh0lqzNkaRI8QfWnvS22KFneloS9tmq-otMOpVqmgH2X482h6W2EAHcWd9WRtt5bydW5EI5LI9AM1weH8itu1xfWbZmuh24=w2400)

![](https://lh3.googleusercontent.com/lxchbrwDtQdS9qL17TFb30vCm0b8gKbehyCgE-AUzIFu3tyq44ssUcA9ezSzFqz18-MnCb1ix84Env72CLEqKNfDDzW-9iurM42aLCW5BmN-K7pMoaw8mYG7E9DBBiQkLqtsDvyD15s=w2400)


![](https://lh3.googleusercontent.com/7c1G5f3RHJnH8-C28feQzAuUdrdCNuEp_m_cYhDp3nUTMHEX6fnIra4LRGElmC0yqBtXsdGS8u1xL15lMH0Ac-_zh3IIctmejRYPj9l3K3EKPwlQKsAoj5jLRhMwea-a6ugkaSNbXaM=w2400)


