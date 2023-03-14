Model: Default

> ACT AS a profesional writter and transcribe, fix the identation the following text: Hello, cloud gurus and welcome back. In this lesson, we're going to be taking a look at some exam tips for those caching services that we just finished talking about. So let's go ahead and dive right on in. Now, as always, we have those four questions that we want to ask ourselves with every question that we see on the exam. The first one is, can it be cached? Is there a situation in the application scenario in which I can cache my data. Is there a way that I can use caching to speed up performance of my application, to reduce my costs, or to even just deal with a technical problem, such as users seeing a stale version of my application because of a failure? We always want to be thinking, "Can a cache benefit this architecture?" If it can, what kind of cache should we put there? We've covered quite a few so far in the previous lessons. And hopefully at this point, you should have an understanding of where do they sit inside of my architecture. So the question is asking for how do we cache a database solution? We shouldn't be putting CloudFront there. We should be thinking Redis, Memcache, DAX, depending on the type of database that we're going to see. If it's talking about how do we distribute our content out to our users faster, And then we should be thinking CloudFront, as that's the natural solution that should be used there. In the cache, how does the content in your cache get updated? Well, usually it's by setting those TTLs correctly, right? Those time to live settings. This is simply going to dictate how long will the data live in that cache. And we need to have that approach of not too hot, not too cold, just right for our data. It's important to remember with CloudFront, how do we get our content out of the cache? Whether it's through that purge, that expiration of our data, or just simply letting it expire, waiting for that TTL to pass. Does that caching solution help with anything besides speed? That's kind of an interesting question to think about because normally we do associate caches equal speed. But with things like CloudFront, we can attach that web application firewall to add in that additional layer of security at those edge locations closer to the end users. So it helps with security and it helps with speed. With global accelerator, it helps with speed, but it also helps deal with that technical problem of I have an issue with those IP addresses being cached. So caching is not always just for speed. We have to think, does it add additional benefits? Now let's take a look at some exam tips for CloudFront as well as Global Accelerator. CloudFront is the only option to add HTTPS, right? That's secure connection to a static website that is being hosted in an S3 bucket. I have seen this as an exam question, right? We wanna add security to that static website. It's not supported by only using S3. we have to front that S3 website with a CloudFront distribution. And CloudFront, as we recall, uses HTTPS natively, right? That is built right in. When given a situation that compares one solution to the other, if one has a cache and the other doesn't, we want to focus on the one that includes a caching option. Now, it's generally not going to be diving in too deep on caching solutions. We just want to know, okay, is there an appropriate cash in front of the part of the architecture where it should be? Are we using the correct kind of cash in front of the database? The correct kind of cash in front of my web application? On the exam, it doesn't really dive too deeply into the fact that it might cost a bit more money versus not having it, if it's not configured correctly. It's generally considered it as a high level solution and it only paints those caches in a positive light. On the exam, if you see a scenario that's talking about IP caching, you should immediately be thinking global accelerator. As we talked about in our previous lessons, global accelerator gives you those two static IP addresses. That way, customers can cache those IP addresses, and when the architecture behind them rotates, such as the load balance are changing out or you're failing from one region to another, It doesn't really matter for your end user. They still hit those two global accelerator IP addresses and everything's good. Now, while global accelerator can help with speed and waiting and there's additional benefits to using it, the exam will generally focus on using it to solve that problem of IP caching. Well, that covers getting data into our environment. Well, let's take a look at those database caches. What do we need to know for that exam? If we see the words in memory database, we have two options, Redis and DynamoDB. These are both NoSQL solutions, and they can be used when it doesn't make sense to have that relational database, when we wanna focus on speed. So Redis is both a cache and a standalone database if you want it to be. Now, given a situation where you're comparing the two, pick DynamoDB. I'm sure in the real world, you can come up with situations where Redis is a better answer compared to DynamoDB, but on the AWS exam, they generally tend to favor answers that are using the more managed AWS tools rather than a managed open source tool like ElasticHash and Redis. On the exam, if you see the terminology in-memory database, you should be immediately thinking either Redis or DynamoDB. Now Redis could be a standalone database. It could also be used as a cache where DynamoDB is going to be used in general just as that database solution. Now, if given the option to pick between the two, generally favor DynamoDB, I wouldn't expect something like that to come up too often though. You're not going to be asked to take a technical deep dive of the differences between the two types, but we need to know that both are in-memory database solutions and provide flexibility as they are non-relational databases and speed. That's where they both excel. Now, when comparing the two versions of ElasticCache, either Redis or Memcache, we need to know that Redis has more features. It can be used as that persistent data storage. It can be used as a cache. It has the support for backups. It's just a bit more robust. Where Memcache at the end of the day is just a cache. Now that means that you should not be using a caching solution as the source of truth for your data. The only caching or slash database solution that supports backups is Redis. Memcache and DAX do not support backups and are not a source of truth for your data. They are simply there to help with performance. So you need to ensure that you're picking answers that stores that data in a permanent data storage solution, such as RDS or DynamoDB. All right, folks, thanks for going through these caching exam tips with me. I can't wait to see you in the next video.

Hello, cloud gurus and welcome back. In this lesson, we're going to be taking a look at some exam tips for those caching services that we just finished talking about. So let's go ahead and dive right on in.

Now, as always, we have those four questions that we want to ask ourselves with every question that we see on the exam. The first one is, can it be cached? Is there a situation in the application scenario in which I can cache my data? Is there a way that I can use caching to speed up performance of my application, to reduce my costs, or to even just deal with a technical problem, such as users seeing a stale version of my application because of a failure? We always want to be thinking, "Can a cache benefit this architecture?" If it can, what kind of cache should we put there? We've covered quite a few so far in the previous lessons. And hopefully at this point, you should have an understanding of where do they sit inside of my architecture.

So the question is asking for how do we cache a database solution? We shouldn't be putting CloudFront there. We should be thinking Redis, Memcache, DAX, depending on the type of database that we're going to see. If it's talking about how do we distribute our content out to our users faster, then we should be thinking CloudFront, as that's the natural solution that should be used there.

In the cache, how does the content in your cache get updated? Well, usually it's by setting those TTLs correctly, right? Those time to live settings. This is simply going to dictate how long will the data live in that cache. And we need to have that approach of not too hot, not too cold, just right for our data. It's important to remember with CloudFront, how do we get our content out of the cache? Whether it's through that purge, that expiration of our data, or just simply letting it expire, waiting for that TTL to pass.

Does that caching solution help with anything besides speed? That's kind of an interesting question to think about because normally we do associate caches equal speed. But with things like CloudFront, we can attach that web application firewall to add in that additional layer of security at those edge locations closer to the end users. So it helps with security and it helps with speed. With global accelerator, it helps with speed, but it also helps deal with that technical problem of I have an issue with those IP addresses being cached. So caching is not always just for speed. We have to think, does it add additional benefits?

Now let's take a look at some exam tips for CloudFront as well as Global Accelerator. CloudFront is the only option to add HTTPS, right? That's secure connection to a static website that is being hosted in an S3 bucket. I have seen this as an exam question, right? We wanna add security to that static website. It's not supported by only using S3. We have to front that S3 website with a CloudFront distribution. And CloudFront, as we recall, uses HTTPS natively, right? That is built right in.

When given a situation that compares one solution to the other, if one has a cache and the other doesn't, we want to focus on the one that includes a caching option. Now, it's generally not going to be diving in too deep on caching solutions. We just want to know, okay, is there an appropriate cache in front of the part of the architecture where it should be? Are we using the correct kind of cache in front of the database? The correct kind of cache in front of my web application? On the exam, it doesn't really dive too deeply into the

> continue

fact that it might cost a bit more money versus not having it, if it's not configured correctly. It's generally considered it as a high level solution and it only paints those caches in a positive light.

On the exam, if you see a scenario that's talking about IP caching, you should immediately be thinking global accelerator. As we talked about in our previous lessons, global accelerator gives you those two static IP addresses. That way, customers can cache those IP addresses, and when the architecture behind them rotates, such as the load balance are changing out or you're failing from one region to another, it doesn't really matter for your end user. They still hit those two global accelerator IP addresses and everything's good.

Now, while global accelerator can help with speed and waiting and there's additional benefits to using it, the exam will generally focus on using it to solve that problem of IP caching.

Well, that covers getting data into our environment. Well, let's take a look at those database caches. What do we need to know for that exam? If we see the words in memory database, we have two options, Redis and DynamoDB. These are both NoSQL solutions, and they can be used when it doesn't make sense to have that relational database, when we wanna focus on speed. So Redis is both a cache and a standalone database if you want it to be.

Now, given a situation where you're comparing the two, pick DynamoDB. I'm sure in the real world, you can come up with situations where Redis is a better answer compared to DynamoDB, but on the AWS exam, they generally tend to favor answers that are using the more managed AWS tools rather than a managed open source tool like ElasticHash and Redis.

On the exam, if you see the terminology in-memory database, you should be immediately thinking either Redis or DynamoDB. Now Redis could be a standalone database. It could also be used as a cache where DynamoDB is going to be used in general just as that database solution.

Now, if given the option to pick between the two, generally favor DynamoDB, I wouldn't expect something like that to come up too often though. You're not going to be asked to take a technical deep dive of the differences between the two types, but we need to know that both are in-memory database solutions and provide flexibility as they are non-relational databases and speed. That's where they both excel.

When comparing the two versions of ElasticCache, either Redis or Memcache, we need to know that Redis has more features. It can be used as that persistent data storage. It can be used as a cache. It has the support for backups. It's just a bit more robust. Where Memcache at the end of the day is just a cache.

Now that means that you should not be using a caching solution as the source of truth for your data. The only caching or slash database solution that supports backups is Redis. Memcache and DAX do not support backups and are not a source of truth for your data. They are simply there to help with performance. So you need to ensure that you're picking answers that stores that data in a permanent data storage solution, such as RDS or DynamoDB.

Alright, folks, thanks for going through these caching exam tips with me. I can't wait to see you in the next video.

> 2 / 2
> 
> ACT AS an AWS Certified Solutions Architect, please check on your knoledge base the information provided in the transcript if it is accurate and useful for those preparing for the AWS certification exams. list the key points to remember from this lesson included

As an AWS Certified Solutions Architect, I can confirm that the information provided in the transcript is accurate and useful for those preparing for the AWS certification exams. The key points to remember from this lesson include:

1.  Always ask the four questions when approaching a caching scenario: Can it be cached? What kind of cache should be used? How does content get updated? Does the caching solution offer benefits beyond speed?
    
2.  CloudFront is the only option to add HTTPS to a static website hosted in an S3 bucket.
    
3.  When comparing two solutions, choose the one that includes a caching option.
    
4.  Global accelerator is the solution for IP caching.
    
5.  In-memory database options include Redis and DynamoDB, and Redis can be used as both a cache and standalone database.
    
6.  Redis has more features than Memcache and is a better option for persistent data storage and backup.
    
7.  Always store data in a permanent data storage solution such as RDS or DynamoDB, and not just in a caching solution.
    

Remembering these key points will help AWS certification exam takers approach caching scenarios with confidence and choose the best solutions for the given scenarios.

> show the Key points to remember for the AWS Certified Solutions Architect - Associate certification in relation to the text, in tabular way, and add your recomendations to study on a secondary tab, do not include services out of the scope of the main text

2 / 2


|     | Key Points to Remember                                                                                                                                                                                           |
| --- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
|     | 1\. Always ask the four questions when approaching a caching scenario: Can it be cached? What kind of cache should be used? How does content get updated? Does the caching solution offer benefits beyond speed? |
|     | 2\. CloudFront is the only option to add HTTPS to a static website hosted in an S3 bucket.                                                                                                                       |
|     | 3\. When comparing two solutions, choose the one that includes a caching option.                                                                                                                                 |
|     | 4\. Global accelerator is the solution for IP caching.                                                                                                                                                           |
|     | 5\. In-memory database options include Redis and DynamoDB, and Redis can be used as both a cache and standalone database.                                                                                        |
|     | 6\. Redis has more features than Memcache and is a better option for persistent data storage and backup.                                                                                                         |
|     | 7\. Always store data in a permanent data storage solution such as RDS or DynamoDB, and not just in a caching solution.                                                                                          |


Recommendations to study:

1.  Familiarize yourself with the various caching services available in AWS, including CloudFront, ElasticCache, and DAX.
2.  Understand how caching can benefit an architecture, and ask the four questions when approaching a caching scenario.
3.  Learn about Global Accelerator and its benefits for IP caching.
4.  Understand the differences between Redis and DynamoDB, and their use cases.
5.  Know the features of ElasticCache, and the differences between Redis and Memcache.
6.  Understand the importance of storing data in a permanent data storage solution such as RDS or DynamoDB, and not just in a caching solution.

> explain in detail all the AWS chaching services and technologies available in tabular way

Sure, here's a table detailing the AWS caching services and technologies:


| Service/Technology | Description |
| --- | --- |
| CloudFront | Content Delivery Network (CDN) that caches data globally, improving latency and reducing server load. Supports static and dynamic content, as well as SSL/TLS. |
| ElasticCache | In-memory data store service that supports two open-source engines: Redis and Memcached. Provides caching for frequently accessed data to improve performance and reduce load on databases. |
| DAX (DynamoDB Accelerator) | In-memory cache for DynamoDB databases, designed to improve read performance for read-heavy workloads. Fully managed and integrates with existing DynamoDB applications. |
| Global Accelerator | A networking service that routes traffic to optimal AWS endpoints over the AWS global network. Can be used to improve availability, latency, and security, as well as IP caching. |
| Direct Connect | A dedicated network connection from on-premises infrastructure to AWS. Improves performance and security by bypassing the public internet. Can be used for caching purposes if needed. |


It's important to note that while all of these services can be used for caching purposes, they each have unique features and use cases. As such, it's important to carefully consider the requirements of your architecture before choosing a caching solution.