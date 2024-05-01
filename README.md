# 530_Final_Project
An Application development (like yelp)

# Technical architecture: Spring Boot + Spring + Spring MVC + Mybatis + Redis + RabbitMQ

## Project Description:
A local life service platform (just like the Yelp app) with user reviews and merchant information as its main content. Based on SpringBoot, it implements functions such as login, registration, and likes. The project focuses on using the characteristics of Redis to solve problems in different business scenarios. The core work includes designing and implementing cache update strategies, solving problems such as cache breakdown and cache penetration, solving the thread safety problem of coupon overselling, and implementing it based on Redis Distributed lock.


### Login and registration: 
Use Redis to store verification codes and tokens, use custom interceptors to complete user authentication, and use double interceptors to solve the problem of token refresh;

### Cache consistency issues: 
In-depth understanding of common solutions to cache consistency issues, and a cache update scheme of active update + timeout elimination in the system to meet higher data consistency requirements;

### Likes and Follows: 
Using different data types (Set and SortedSet) in Redis, the functions of like lists, like rankings, following, and joint following between users are realized;

### Flash sale coupon: 
Optimistic lock solves the problem of oversold inventory, and uses Redisson distributed lock to solve the problem of one person per order;

### Flash sale performance optimization:
rabbitMQ message queue + lua script realizes asynchronous processing of ordering process, changes synchronous ordering to asynchronous ordering, optimizes the process of flash sale business, and reduces the average time consumption from more than 400 ms to more than 100 ms;

### Preservation of user permissions: 
Use Threadlocal to cooperate with interceptors to verify tokens, determine whether the current user is logged in, and solve the problem of HTTP statelessness, achieving the effect of the server remembering user information.

The practical solution to cache penetration and cache breakdown problems is encapsulated into a universal solution through generics + functional programming.
