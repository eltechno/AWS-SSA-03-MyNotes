Model: Default

> ACT AS a profesional writter and transcribe, fix the identation the following text: Hello, cloud gurus, and welcome back. In this lesson, we're going to take a look at some of our exam tips for the high availability and scaling lessons. So let's go ahead and dive right on in. We're going to go over four important questions that I want you to ask yourself in the exam anytime you see a question that seems to relate to scaling and high availability. Now, the first one here is, is it highly available? We always want to pick answers that include high availability. Even if the question isn't specifically asking, "Is this solution highly available?" We still want to gear ourselves towards picking answers that are highly available. Unless you are presented with a situation that explicitly calls out that you do not need high availability and it is only focusing on cost, We always want to make sure that our resources can withstand failure and are spread out across those multiple availability zones. Whenever we're presented with a situation that involves scaling, we have to ask ourselves, should this be horizontal or vertically scaled? Now, as we talked about in those previous lessons, we generally want to focus on horizontal scaling because we can continue to spin up more resources, more architecture. It helps us be more highly available where vertical scaling just resizing that instance has that natural limit. Now that doesn't mean that we never want to vertically scale on the exam. You might see a situation which says we want to increase that network throughput for that t2 micro instance. The only real answer there is you need to scale vertically. You need to upsize that to be something that's a bit more appropriate. So we want to generally favor horizontal, but that doesn't mean we always want to write off vertical scaling. Is the scaling solution cost effective? Even if the question is not specifically asking for a cost-effective solution, we want to keep cost in mind. You might be seeing a question that says, how do we scale out this architecture? And one of the answers is we need to spin up that fleet of X1, 32 XL instances. And sure, would that technically solve the problem? Yeah, but that's going to cost a lot more money than it should. So we always want to balance in how much does the solution cost and does it meet the situation that we're being provided with? Could we switch the database to fix our problem? I know what you're thinking. If you've worked in IT before, switching databases is a very complex task. There's no magic button that I can just press to move from a relational database to a NoSQL database. However, on the exam in the wonderful world of AWS questions, we can easily flip between them with no real work. So when you're looking at a situation, if it says, perhaps we have that relational database that's just falling over and we're spending too much money and we need something that's a little bit more flexible, we might want to think, Hey, would that DynamoDB option work for us, that non-relational database? We can select an answer that does that migration, even though actually doing that migration would be a huge burden on our team. Now that we've got those four questions in mind, let's go through some specific tips relating to auto scaling that can hopefully help us out on the exam. Our first point to keep in mind is, Auto scaling is only for EC2 instances. So no other service can be added into an auto scaling group. It cannot be used to add in load balancers or RDS databases or Lambda functions or anything else. Now, some of those services that I mentioned do have the ability to scale, but that is separate and independent from those EC2 auto scaling groups. And this is a common pitfall but I've seen a lot of folks, well, stumble their way into. You might be presented with a scenario that says we'll scale the RDS database by using an auto scaling group, and that's just not possible. Whenever we can, we wanna select answers that get ahead of the workload. If you're given a situation that says, hey, we have a predictable consistent workload at 5 p.m. every single day, you wouldn't want to pick an answer that says we're spinning up instances after that workload has started. If it makes it seem like there is a consistent pattern to what's going on, we need to get ahead of that. This is where you're going to want to pick an answer that says maybe we're spinning up those instances at 4.45 to get ahead of that five o'clock rush. It's better to be ahead rather than playing catch up. You're often presented with scenarios that talk about how do we better fine tune or tweak our auto scaling groups. And one of the problems that you might run into on the exam is that your instances are taking just too long to come online. You have a really long provisioning time and that's causing an issue when you need those instances to respond to a workload that has just hit your architecture. So whenever we can, we wanna bake everything inside of that AMI. By baking those AMIs, by loading it up with our dependencies and our code, they're going to provision a lot quicker than trying to do it using that user data or another solution. We want to focus on picking answers that include that short provisioning time whenever possible. Let's take a look at a few more important tips here. We want to ensure that we are spreading out. you are never going to pick a right answer on the exam that includes one single availability zone. We always want to spread out our content over at least two availability zones because you can't really make a highly available solution in a single availability zone. So ensure that your auto scaling groups, and in general, the rest of your architecture is spread out across multiple AZs. that gives us the ability for that one AZ to fail, the architecture to have problems, and for us to have that backup. Now in that previous lesson, we took a look at that steady state group. Remember, it's that auto scaling group that has that min, maxed and desired capacity of one. This is great for that situation where maybe we have that legacy instance, that NAT instance, that resource where there can't be more than one at a time. We saw this during that demo where if that instance fails, auto scaling will automatically recover that architecture. Keep this in mind if you're asked about creating a highly available solution for that legacy resource where we can't have more than one online at once. While we just talked about that your load balancers cannot be included inside of your auto scaling groups for scaling purposes, they are best friends with your auto scaling group when it comes distributing traffic to those instances and also determining if an instance has failed that health check and needs to be replaced. Now this doesn't happen by default, so ensure that you are picking answers that include a load balancer to distribute the traffic and that you've checked that checkbox to make sure that any unhealthy instances in the load balancer are terminated by the auto scaling group. that is not default behavior and therefore we have to make sure that it is explicitly called out in the answers that we are choosing. Alright that's a bit about auto scaling. Let's take a quick look at a few points that we need to remember when it comes time to scale those databases. Now a lot of the scaling questions that you're going to run into have to do with RDS because RDS has the most amount of database scaling options available to us. Now we talked about those in our RDS scaling lesson, but let's do a quick recap here. Remember we have the ability to scale vertically, which sometimes is needed. Remember that EC2 instance, it's a T2 micro. We're probably going to need something that's a little bit bigger. We have the ability to scale out with additional storage. if we're running out of storage in that database. And we also have the ability to do horizontal scaling. Now I know what you're thinking, horizontal scaling, how do we do that with a relational database? Well, we really do that through the use of those read replicas. And read replicas are your best friend. If you see a question that calls out a read heavy workload, you automatically wanna think read replicas. I need to spin up read replicas, adjust my code, to point my reads to that read replica away from that primary database. So as you're going through the exam, think through because it's more than just horizontal scaling, we have a variety of solutions for RDS architecture. When it comes to DynamoDB, it's a lot simpler for us because AWS handles almost everything. Now, if we wanna think back to that DynamoDB lesson that we had just a little bit ago, we talked about the two types of tables that we could create. If we have that consistent access pattern where it's predictable, where we gradually need to scale up and then scale those reads and writes back down, that's when we're gonna wanna select the auto scaling method. If we see a scenario given to us that has an unpredictable workload, where that access pattern spikes up and down and up and down and we can't really predict what we need, then we wanna pick that on-demand option. So when it comes to scaling DynamoDB, it's all about that access pattern. All right, folks, thanks for joining me in these exam tips. Hopefully this was helpful here for us to summarize all of that content that we talked about with high availability and scaling, and I can't wait to see you in our next lesson.

Hello, cloud gurus, and welcome back.

In this lesson, we're going to take a look at some of our exam tips for the high availability and scaling lessons. So let's go ahead and dive right on in.

We're going to go over four important questions that I want you to ask yourself in the exam anytime you see a question that seems to relate to scaling and high availability.

Now, the first one here is, is it highly available? We always want to pick answers that include high availability. Even if the question isn't specifically asking, "Is this solution highly available?" We still want to gear ourselves towards picking answers that are highly available. Unless you are presented with a situation that explicitly calls out that you do not need high availability and it is only focusing on cost. We always want to make sure that our resources can withstand failure and are spread out across those multiple availability zones.

Whenever we're presented with a situation that involves scaling, we have to ask ourselves, should this be horizontal or vertically scaled? Now, as we talked about in those previous lessons, we generally want to focus on horizontal scaling because we can continue to spin up more resources, more architecture. It helps us be more highly available where vertical scaling just resizing that instance has that natural limit. Now that doesn't mean that we never want to vertically scale on the exam. You might see a situation which says we want to increase that network throughput for that t2 micro instance. The only real answer there is you need to scale vertically. You need to upsize that to be something that's a bit more appropriate. So we want to generally favor horizontal, but that doesn't mean we always want to write off vertical scaling.

Is the scaling solution cost effective? Even if the question is not specifically asking for a cost-effective solution, we want to keep cost in mind. You might be seeing a question that says, how do we scale out this architecture? And one of the answers is we need to spin up that fleet of X1, 32 XL instances. And sure, would that technically solve the problem? Yeah, but that's going to cost a lot more money than it should. So we always want to balance in how much does the solution cost and does it meet the situation that we're being provided with?

Could we switch the database to fix our problem? I know what you're thinking. If you've worked in IT before, switching databases is a very complex task. There's no magic button that I can just press to move from a relational database to a NoSQL database. However, on the exam in the wonderful world of AWS questions, we can easily flip between them with no real work. So when you're looking at a situation, if it says, perhaps we have that relational database that's just falling over and we're spending too much money and we need something that's a little bit more flexible, we might want to think, Hey, would that DynamoDB option work for us, that non-relational database? We can select an answer that does that migration, even though actually doing that migration would be a huge burden on our team.

Now that we've got those four questions in mind, let's go through some specific tips relating to auto scaling that can hopefully help us out on the exam.

Our first point to keep in mind is, Auto scaling is only for EC2 instances. So no other service can be added into an auto scaling group. It cannot be used to add in load balancers or RDS databases or Lambda functions or anything else. Now, some of those services that I mentioned do have the ability to scale, but that is separate and independent from those EC2 auto scaling groups. And this is a common pitfall but I've seen a lot of folks, well,

> continue

stumble their way into. You might be presented with a scenario that says we'll scale the RDS database by using an auto scaling group, and that's just not possible.

Whenever we can, we wanna select answers that get ahead of the workload. If you're given a situation that says, hey, we have a predictable consistent workload at 5 p.m. every single day, you wouldn't want to pick an answer that says we're spinning up instances after that workload has started. If it makes it seem like there is a consistent pattern to what's going on, we need to get ahead of that. This is where you're going to want to pick an answer that says maybe we're spinning up those instances at 4.45 to get ahead of that five o'clock rush. It's better to be ahead rather than playing catch up.

You're often presented with scenarios that talk about how do we better fine tune or tweak our auto scaling groups. And one of the problems that you might run into on the exam is that your instances are taking just too long to come online. You have a really long provisioning time and that's causing an issue when you need those instances to respond to a workload that has just hit your architecture. So whenever we can, we wanna bake everything inside of that AMI. By baking those AMIs, by loading it up with our dependencies and our code, they're going to provision a lot quicker than trying to do it using that user data or another solution. We want to focus on picking answers that include that short provisioning time whenever possible.

Let's take a look at a few more important tips here. We want to ensure that we are spreading out. You are never going to pick a right answer on the exam that includes one single availability zone. We always want to spread out our content over at least two availability zones because you can't really make a highly available solution in a single availability zone. So ensure that your auto scaling groups, and in general, the rest of your architecture is spread out across multiple AZs. That gives us the ability for that one AZ to fail, the architecture to have problems, and for us to have that backup.

Now in that previous lesson, we took a look at that steady state group. Remember, it's that auto scaling group that has that min, maxed and desired capacity of one. This is great for that situation where maybe we have that legacy instance, that NAT instance, that resource where there can't be more than one at a time. We saw this during that demo where if that instance fails, auto scaling will automatically recover that architecture. Keep this in mind if you're asked about creating a highly available solution for that legacy resource where we can't have more than one online at once.

While we just talked about that your load balancers cannot be included inside of your auto scaling groups for scaling purposes, they are best friends with your auto scaling group when it comes distributing traffic to those instances and also determining if an instance has failed that health check and needs to be replaced. Now this doesn't happen by default, so ensure that you are picking answers that include a load balancer to distribute the traffic and that you've checked that checkbox to make sure that any unhealthy instances in the load balancer are terminated by the auto scaling group. That is not default behavior and therefore we have to make sure that it is explicitly called out in the answers that we are choosing.

Alright, that's a bit about auto scaling. Let's take a quick look at a few points that we need to remember when it comes time to scale those databases.

Now a lot of the scaling questions that you're going to run into have to do with RDS because RDS has the most amount of database scaling options available to us. Now we

> continue

talked about those in our RDS scaling lesson, but let's do a quick recap here. Remember we have the ability to scale vertically, which sometimes is needed. Remember that EC2 instance, it's a T2 micro. We're probably going to need something that's a little bit bigger. We have the ability to scale out with additional storage. If we're running out of storage in that database. And we also have the ability to do horizontal scaling. Now I know what you're thinking, horizontal scaling, how do we do that with a relational database? Well, we really do that through the use of those read replicas. And read replicas are your best friend. If you see a question that calls out a read heavy workload, you automatically wanna think read replicas. I need to spin up read replicas, adjust my code, to point my reads to that read replica away from that primary database.

So as you're going through the exam, think through because it's more than just horizontal scaling, we have a variety of solutions for RDS architecture. When it comes to DynamoDB, it's a lot simpler for us because AWS handles almost everything. Now, if we wanna think back to that DynamoDB lesson that we had just a little bit ago, we talked about the two types of tables that we could create. If we have that consistent access pattern where it's predictable, where we gradually need to scale up and then scale those reads and writes back down, that's when we're gonna wanna select the auto scaling method. If we see a scenario given to us that has an unpredictable workload, where that access pattern spikes up and down and up and down and we can't really predict what we need, then we wanna pick that on-demand option. So when it comes to scaling DynamoDB, it's all about that access pattern.

Alright, folks, thanks for joining me in these exam tips. Hopefully this was helpful here for us to summarize all of that content that we talked about with high availability and scaling, and I can't wait to see you in our next lesson.

> now i want to use that text and I want you to act as a AWS Certified solution architect and that information about the certification's material for AWS Solution Architect Associated certification, check,verify and correct, the information if it’s necessary to have relevant and important information. If there is any information missing, add all necessary material to improve the study information, please list all the key points to lear/remember

As an AWS Certified Solutions Architect, I can confirm that the information provided in the transcribed text is relevant to the AWS Solution Architect Associate certification. The text covers important topics related to high availability and scaling, which are key areas of focus for the certification exam.

To summarize the key points covered in the text:

*   High availability is a critical consideration for any AWS architecture, and we should always choose answers that include high availability.
*   Scaling can be achieved through horizontal or vertical scaling. Horizontal scaling is generally preferred because it allows us to add more resources and increase availability, while vertical scaling has a natural limit.
*   Cost-effectiveness is also an important consideration when scaling, and we should aim to balance cost and functionality.
*   Switching databases can be a useful solution in certain situations, and we should be aware of the different types of databases available in AWS.
*   Auto scaling is a powerful tool for managing EC2 instances and can help to ensure that resources are available to meet demand.
*   Load balancers are essential for distributing traffic across instances and ensuring that unhealthy instances are replaced as necessary.
*   RDS databases can be scaled vertically or horizontally, and read replicas can be used to achieve horizontal scaling for read-heavy workloads.
*   DynamoDB offers different scaling options depending on the access pattern, and auto scaling can be used for predictable workloads while on-demand scaling is best for unpredictable workloads.

Overall, these concepts are crucial to understanding how to design and implement highly available and scalable architectures on AWS, and are important topics to study for the AWS Solution Architect Associate certification.

> show the Key points to remember for the AWS Certified Solutions Architect - Associate certification in relation to the text, in tabular way, and add your recomendations to study on a secondary tab, do not include services out of the scope of the main text

Sure, here are the key points to remember for the AWS Certified Solutions Architect - Associate certification in relation to the text:

|     | Key Points                                                                              |
| --- | --------------------------------------------------------------------------------------- |
|     | Always choose answers that include high availability                                    |
|     | Horizontal scaling is generally preferred over vertical scaling                         |
|     | Balance cost and functionality when scaling                                             |
|     | Switching databases can be a useful solution                                            |
|     | Auto scaling is a powerful tool for managing EC2 instances                              |
|     | Load balancers are essential for distributing traffic and replacing unhealthy instances |
|     | RDS databases can be scaled vertically or horizontally                                  |
|     | Read replicas can be used for horizontal scaling of read-heavy workloads in RDS         |
|     | DynamoDB offers different scaling options depending on the access pattern               |


Here are my recommendations for studying for the AWS Certified Solutions Architect - Associate certification:

|     | Recommendations                                                                                                                |
| --- | ------------------------------------------------------------------------------------------------------------------------------ |
|     | Review the AWS documentation on high availability and scaling                                                                  |
|     | Practice designing and implementing highly available and scalable architectures using AWS services like EC2, RDS, and DynamoDB |
|     | Familiarize yourself with AWS Auto Scaling and load balancing services                                                         |
|     | Understand the different types of databases available in AWS and their use cases                                               |
|     | Practice interpreting AWS exam questions and selecting the most appropriate answer based on the available information          |


It's also important to note that while the text covers important topics, there are other concepts that are also covered on the AWS Solutions Architect - Associate certification exam, such as security, networking, and AWS services like S3 and CloudFront. So, be sure to review the full scope of the exam and study all relevant materials.

> explain in tabular way the scaling groups

Sure, here's a breakdown of scaling groups in a tabular format:


| Scaling Groups | Description |
| --- | --- |
| Auto Scaling Groups | Used to automatically adjust the number of EC2 instances in response to changes in demand. |
| Scaling Policies | Define how an Auto Scaling Group should scale in response to changes in demand. |
| Scaling Cooldowns | The amount of time that an Auto Scaling Group will wait before scaling again after a scaling event. |
| Scheduled Scaling | Allows for predictable changes to an Auto Scaling Group, such as increasing capacity in anticipation of a known event. |
| Step Scaling | A type of scaling policy that allows for fine-grained control over the scaling process, with multiple thresholds and scaling actions. |
| Target Tracking Scaling | A type of scaling policy that adjusts the number of instances in an Auto Scaling Group in response to a target metric. |


These scaling groups are important to understand when designing and implementing highly available and scalable architectures on AWS. By using Auto Scaling Groups and the various scaling policies available, we can ensure that resources are available to meet demand, while also optimizing costs and minimizing downtime.

It's also important to note that while these scaling groups are important, they are just one piece of the larger puzzle when it comes to designing and implementing AWS architectures. It's essential to have a thorough understanding of all relevant AWS services and best practices in order to ensure that your architectures are secure, cost-effective, and highly available.

> explain Scale RDS in tabular way

Sure, here's a breakdown of scaling RDS in a tabular format:


| Scaling RDS | Description |
| --- | --- |
| Vertical Scaling | Increasing or decreasing the size of an RDS instance, such as increasing the amount of memory or CPU. |
| Horizontal Scaling | Adding or removing read replicas to handle read-heavy workloads or to improve availability. |
| Multi-AZ Deployment | Deploying an RDS instance across multiple Availability Zones to improve availability and minimize downtime. |
| Storage Scaling | Increasing or decreasing the amount of storage available for an RDS instance. |
| Automated Backups | Automatically creating backups of an RDS instance, which can be used to restore the instance in case of failure. |
| Manual Snapshots | Creating manual snapshots of an RDS instance for more granular control over backups and restores. |


These scaling options are important to understand when working with RDS in order to ensure that your database is available, scalable, and cost-effective. By using a combination of vertical and horizontal scaling, multi-AZ deployment, and storage scaling, we can ensure that our RDS instances can handle changes in demand, while also optimizing costs.

In addition to these scaling options, it's important to also consider factors such as security, networking, and performance when working with RDS. Understanding best practices for RDS is key to ensuring that your database is secure, performant, and highly available.

> explain the Dynamodb scaling options in tabular way

Sure, here's a breakdown of DynamoDB scaling options in a tabular format:


| DynamoDB Scaling Options | Description |
| --- | --- |
| Auto Scaling | Automatically adjusts the provisioned capacity of a DynamoDB table in response to changes in demand. |
| On-Demand | Dynamically allocates capacity in response to actual traffic to the table, eliminating the need to manually provision capacity. |
| Provisioned Capacity | Manually provision capacity for a DynamoDB table, based on expected traffic patterns. |
| Global Tables | Allows for replication of a DynamoDB table across multiple regions for improved availability and lower latency. |


These scaling options are important to understand when working with DynamoDB in order to ensure that your tables can handle changes in demand, while also optimizing costs. By using a combination of auto scaling, on-demand, and provisioned capacity, we can ensure that our tables can handle changes in demand while minimizing costs.

In addition to these scaling options, it's important to also consider factors such as security, indexing, and performance when working with DynamoDB. Understanding best practices for DynamoDB is key to ensuring that your tables are secure, performant, and highly available.