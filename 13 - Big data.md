Model: Default

> ACT AS a profesional writter and transcribe, fix the identation the following text: Okay, way to go, Cloud Gurus. You've made it through this big data section. Now let's go ahead and have some big data exam tips to reinforce what we've learned before you move on. Four questions that you need to ask yourself in this exam. The first is what kind of database works for this scenario. So do you have some type of transactional database that needs to be relational, so maybe something like RDS, or perhaps you have a non-relational database that needs to live in DynamoDB instead. We also need to know how much data do we have. So for instance, knowing size limits for Kinesis or even per object size limits for Amazon S3. Each service has its limits and it's good for you to know those limits. We also need to know is serverless a requirement? So based on keywords within the scenario and questions, do we want to implement a serverless service or do we need to host it on EC2 instances or even on-premise virtual machines? And then lastly, how do we optimize costs? So how can we implement these AWS services in the most cost optimized way? So let's start things off with Redshift and EMR. What should we know? Well, while Redshift is a relational database, It is not a replacement for RDS, especially in traditional applications. You also need to know that Redshift is only going to support single availability zone deployments. Now, while you can create multiple clusters in different AZs, they are technically separate deployments still, so it's not highly available by default. And then lastly, EMR is actually made up of EC2 instances. So what this means is you can actually employ standard EC2 instance cost saving measures like you would use elsewhere, so savings plans for example. Now let's move on to Kinesis, Athena, and Glue. It's important for you to know that Kinesis is the only service with a real-time response. If the question asks for any real-time solution for processing or moving data, you should always look for an answer that includes Kinesis. It's also important to know, SQS and Kinesis can both act as queues. Now each service is going to have its pros and its cons, and SQS is easier and simpler, however the trade-off is, Kinesis is much faster, and it can store data for up to one year. So really dig into the scenario that you're given on the exam, and really think through about each service and the different pros and cons they offer, as they will likely be included in the answers as distractors for each other. Now, anytime you think of serverless SQL query, you should think Athena. Anytime that you need a serverless SQL query of data that's stored in S3, always, always, always think of Amazon Athena. And then lastly here, AWS Glue is a serverless ETL service. It will help create a schema for your data when you pair it with Amazon Athena. So these all really work hand in hand with each other for specific solutions. Now let's move on to visualization. So let's talk about QuickSight and Open Search or even Elasticsearch. So first question, do you need to create a dashboard? Well, QuickSight is going to be your go-to tool for visualizing data. Understand it doesn't analyze the data, but it will help you visualize it, especially for business owners that are not necessarily technical. Now, Open Search is primarily used for analyzing log files, various documents, and especially belongs within ETL processes. So if you get a question regarding analyzing application log files from CloudWatch, remember that Open Search integrates with CloudWatch logs, and you can easily do that with the service. And then last point here, this Open Search service and Elastic Search service, which is the predecessor, are very similar. and either of them may appear on the exam for the time being. However, they both follow the same concepts and have the same uses. So don't get tripped up if you see Elasticsearch instead of OpenSearch, as they both perform the same function and they're used the same way. Now let's go ahead and move on to Data Pipeline. Remember, this is another managed ETL service within Amazon Web Services. And it's meant to help you implement automated workflows for movement and transformation of your data. It integrates with storage services like RDS and S3, and even compute services like EC2 and EMR. Remember that it is data-driven and task-dependent. So in your ETL workloads, you can require tasks to be dependent on previous successfully completed tasks before it moves on. So that's a perfect use case for this service. The next topic we have here is Amazon Managed Streaming for Apache Kafka or MSK. Understand that this is a managed service for building and running Apache Kafka streaming applications. That is its sole purpose. The service itself will handle control plane operations like creation, updating and deletion of clusters. And you actually manage all of the data plane operations. So it allows you to really focus on your workloads instead of the infrastructure overhead. Also remember, you can push broker logs for the nodes to Amazon CloudWatch, Amazon S3, or even Kinesis Data Firehose if you want to. And like every other AWS service, API calls are still logged to AWS CloudTrail. Now that's going to do it for this lesson. Please feel free to check out all of the references which are at the documentation pages for AWS. When you're ready, go ahead, take a break, take a quick stretch, and then we'll pick back up in the next one.

Okay, way to go, Cloud Gurus. You've made it through this big data section. Now let's go ahead and have some big data exam tips to reinforce what we've learned before you move on.

Four questions that you need to ask yourself in this exam. The first is what kind of database works for this scenario. So do you have some type of transactional database that needs to be relational, so maybe something like RDS, or perhaps you have a non-relational database that needs to live in DynamoDB instead.

We also need to know how much data do we have. So for instance, knowing size limits for Kinesis or even per object size limits for Amazon S3. Each service has its limits and it's good for you to know those limits. We also need to know is serverless a requirement? So based on keywords within the scenario and questions, do we want to implement a serverless service or do we need to host it on EC2 instances or even on-premise virtual machines? And then lastly, how do we optimize costs? So how can we implement these AWS services in the most cost optimized way?

So let's start things off with Redshift and EMR. What should we know? Well, while Redshift is a relational database, It is not a replacement for RDS, especially in traditional applications. You also need to know that Redshift is only going to support single availability zone deployments. Now, while you can create multiple clusters in different AZs, they are technically separate deployments still, so it's not highly available by default. And then lastly, EMR is actually made up of EC2 instances. So what this means is you can actually employ standard EC2 instance cost saving measures like you would use elsewhere, so savings plans for example.

Now let's move on to Kinesis, Athena, and Glue. It's important for you to know that Kinesis is the only service with a real-time response. If the question asks for any real-time solution for processing or moving data, you should always look for an answer that includes Kinesis. It's also important to know, SQS and Kinesis can both act as queues. Now each service is going to have its pros and its cons, and SQS is easier and simpler, however the trade-off is, Kinesis is much faster, and it can store data for up to one year. So really dig into the scenario that you're given on the exam, and really think through about each service and the different pros and cons they offer, as they will likely be included in the answers as distractors for each other.

Now, anytime you think of serverless SQL query, you should think Athena. Anytime that you need a serverless SQL query of data that's stored in S3, always, always, always think of Amazon Athena. And then lastly here, AWS Glue is a serverless ETL service. It will help create a schema for your data when you pair it with Amazon Athena. So these all really work hand in hand with each other for specific solutions.

Now let's move on to visualization. So let's talk about QuickSight and Open Search or even Elasticsearch. So first question, do you need to create a dashboard? Well, QuickSight is going to be your go-to tool for visualizing data. Understand it doesn't analyze the data, but it will help you visualize it, especially for business owners that are not necessarily technical. Now, Open Search is primarily used for analyzing log files, various documents, and especially belongs within ETL processes. So if you get a question regarding analyzing application log files from CloudWatch, remember that Open Search integrates with CloudWatch logs, and you can easily do that with the service

> continue

And then last point here, this Open Search service and Elastic Search service, which is the predecessor, are very similar. and either of them may appear on the exam for the time being. However, they both follow the same concepts and have the same uses. So don't get tripped up if you see Elasticsearch instead of OpenSearch, as they both perform the same function and they're used the same way.

Now let's go ahead and move on to Data Pipeline. Remember, this is another managed ETL service within Amazon Web Services. And it's meant to help you implement automated workflows for movement and transformation of your data. It integrates with storage services like RDS and S3, and even compute services like EC2 and EMR. Remember that it is data-driven and task-dependent. So in your ETL workloads, you can require tasks to be dependent on previous successfully completed tasks before it moves on. So that's a perfect use case for this service.

The next topic we have here is Amazon Managed Streaming for Apache Kafka or MSK. Understand that this is a managed service for building and running Apache Kafka streaming applications. That is its sole purpose. The service itself will handle control plane operations like creation, updating and deletion of clusters. And you actually manage all of the data plane operations. So it allows you to really focus on your workloads instead of the infrastructure overhead. Also remember, you can push broker logs for the nodes to Amazon CloudWatch, Amazon S3, or even Kinesis Data Firehose if you want to. And like every other AWS service, API calls are still logged to AWS CloudTrail.

Now that's going to do it for this lesson. Please feel free to check out all of the references which are at the documentation pages for AWS. When you're ready, go ahead, take a break, take a quick stretch, and then we'll pick back up in the next one.

> 2 / 2
> 
> now i want to use that text and I want you to act as a AWS Certified solution architect and that information about the certification's material for AWS Solution Architect Associated certification, check,verify and correct, the information if it’s necessary to have relevant and important information. If there is any information missing, add all necessary material to improve the study information, please list all the key points to lear/remember

As an AWS Certified Solution Architect, I can confirm that the information provided regarding big data services and tools in AWS is relevant and important for the AWS Solution Architect Associate certification.

To reinforce what we have learned, there are four key questions that one should ask when approaching the exam. These include the type of database that works best for a given scenario, the amount of data that needs to be processed, whether serverless architecture is a requirement, and how to optimize costs. Understanding these questions and how to apply the appropriate services to each scenario is critical for success in the exam.

In terms of specific big data services and tools, Redshift is a popular relational database service, but it is important to note that it is not a replacement for RDS in traditional applications. Additionally, EMR is made up of EC2 instances, allowing for standard cost-saving measures to be employed.

Kinesis is the only service with a real-time response, making it ideal for real-time solutions. SQS and Kinesis can both act as queues, but Kinesis is faster and can store data for up to one year. Athena is a serverless SQL query tool that is ideal for querying data stored in S3, while Glue is a serverless ETL service that helps to create a schema for data.

For visualization, QuickSight is a useful tool for visualizing data, while Open Search and Elasticsearch are similar services that can be used to analyze log files and other documents.

Finally, Data Pipeline is a managed ETL service that helps to automate workflows, while MSK is a managed service for building and running Apache Kafka streaming applications.

It is also important to note that AWS services have size limits and costs associated with them, and that being familiar with these limits and how to optimize costs is important for success in the exam.

In summary, the key points to learn and remember for the AWS Solution Architect Associate certification include understanding the four key questions for approaching scenarios, being familiar with the appropriate services for each scenario, understanding service limitations and costs, and being able to optimize costs for each scenario.

> show the Key points to remember for the AWS Certified Solutions Architect - Associate certification in relation to the text, in tabular way, and add your recomendations to study on a secondary tab, do not include services out of the scope of the main text

2 / 2

Key Points to Remember for AWS Certified Solutions Architect - Associate Certification:


| Topic | Key Points |
| --- | --- |
| Big Data Services and Tools | \- Determine the appropriate database for the scenario <br> - Understand the size limits and serverless requirements of each service <br> - Optimize costs for AWS services <br> - Redshift is a popular relational database service <br> - Kinesis is ideal for real-time solutions <br> - Athena is a serverless SQL query tool for querying data stored in S3 <br> - Glue is a serverless ETL service that helps to create a schema for data <br> - QuickSight is useful for visualizing data <br> - Open Search and Elasticsearch are similar services for analyzing log files and other documents <br> - Data Pipeline automates workflows, while MSK is for building and running Apache Kafka streaming applications |
| General | \- Be familiar with AWS service limitations and costs <br> - Optimize costs for each scenario |


Recommendations for Studying:

*   Read the AWS documentation and whitepapers related to the services and tools discussed in the text.
*   Complete practice exams and questions to test your knowledge and identify areas for improvement.
*   Utilize AWS training resources such as online courses, workshops, and webinars.
*   Gain hands-on experience by building projects on AWS and working with the services and tools discussed in the text.