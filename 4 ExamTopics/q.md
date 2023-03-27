-----------------------------------------------------------------------------------------------------------
1. A gaming website gives users the ability to **trade game items** with each other on the platform. The platform requires both users' records to be updated and **persisted in one transaction**. If any update fails, the transaction must roll back.
Which AWS solution can provide the transactional capability that is required for this feature?
>  ```Amazon Aurora MySQL with operations made within a transaction block```
-----------------------------------------------------------------------------------------------------------

-----------------------------------------------------------------------------------------------------------
2. A developer has created a Java application that makes HTTP requests directly to AWS services. Application logging shows **5xx HTTP response codes that occur at irregular intervals**. The errors are affecting users.
How should the developer update the application to improve the application's resiliency?
> ``` Use the AWS SDK for Java to interact with AWS APIs.```
-----------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------
3. A global company has a mobile app with static data stored in an Amazon S3 bucket in the us-east-1 Region. The company serves the content through an Amazon
CloudFront distribution. The company is launching the mobile app in South Africa. The data must reside in the af-south-1 Region. The company does not want to deploy a specific mobile client for South Africa.
What should the company do to meet these requirements?
>  ****Create a Lambda@Edge function. Associate the Lambda@Edge function as an ``origin request`` trigger with the CloudFront distribution to change the S3 origin Region**
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
4. A developer is testing an AWS Lambda function by using the AWS Serverless Application Model (AWS SAM) local CLI. The application that is implemented by the
Lambda function makes several AWS API calls by using the AWS software development kit (SDK). The developer wants to allow the function to make AWS API calls in a test AWS account from the developer's laptop.
What should the developer do to meet these requirements?
> **Add a test profile by using the aws configure command with the ``--profile`` option. Run AWS SAM by using the sam local invoke command with the -profile option.**
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
5. A developer designed an application on an Amazon EC2 instance. The application makes API requests to objects in an Amazon S3 bucket.
Which combination of steps will ensure that the application makes the API requests in the MOST secure manner? (Choose two.)
>**Create an IAM role that has permissions to the S3 bucket.**
> **Add the IAM role to an instance profile. Attach the instance profile to the EC2 instance.**
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
6. A developer is configuring an Amazon CloudFront distribution for a new application to provide encryption in transit. The application is running in the eu-west-1
Region. The developer creates a new certificate in AWS Certificate Manager (ACM) in eu-west-1, but the certificate is not visible in the CloudFront distribution settings.
What should the developer do to fix this problem?
> **Create the certificate in the eu-west-1 Region. Ensure that the alternate domain name (CNAME) in the distribution settings matches the domain name in the certificate.**
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
7. A developer is building an application that runs behind an Application Load Balancer (ALB). The ALB is configured as the origin for an Amazon CloudFront distribution. Users will log in to the application by using their social media accounts.
How can the developer authenticate users?
> **Configure the ALB to use Amazon Cognito as one of the authentication providers.**
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
8. A company has an application that analyzes photographs. A developer is preparing the application for deployment to Amazon EC2 instances. The application's image analysis functions require a mix of GPU instances and CPU instances that run on Amazon Linux. The developer needs to add code to the application so that the functions can determine whether they are running on a GPU instance.
What should the functions do to obtain this information?
> **Retrieve the instance type from the instance metadata.**
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
9. A company has an application that uses Amazon Cognito user pools as an identity provider. The company must secure access to user records. The company has set up multi-factor authentication (MFA). The company also wants to send a login activity notification by email every time a user logs in.
What is the MOST operationally efficient solution that meets this requirement?
> **Create an AWS Lambda function that uses Amazon Simple Email Service (Amazon SES) to send the email notification. Add an Amazon Cognito post authentication Lambda trigger for the function.**
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
10. A company hosts a **three-tier web application** on AWS behind an Amazon CloudFront distribution. A developer wants a **dashboard to monitor error rates and anomalies** of the CloudFront distribution with the **shortest possible refresh interval.**
Which combination of slops should the developer take to meet these requirements? (Choose two.)
> **Activate real-time logs on the CloudFront distribution. Create a stream in Amazon Kinesis Data Streams.** 
> **Configure Amazon Kinesis Data Streams to deliver logs to Amazon OpenSearch Service (Amazon Elasticsearch Service). Create a dashboard in OpenSearch Dashboards (Kibana).**
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
11. A developer creates a customer managed key for multiple AWS users to encrypt data in Amazon S3. The developer configures Amazon Simple Notification
Service (Amazon SNS) to publish a message if key deletion is scheduled. **The developer needs to preserve any SNS messages that cannot be delivered so that those messages can be reprocessed.**
Which AWS service or feature should the developer use to meet this requirement?
> **SQS**
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
12. A developer needs to deploy an application to AWS Elastic Beanstalk for a company. The application consists of a **single Docker image**. The company's automated continuous integration and continuous delivery (CI/CD) process builds the Docker image and pushes the image to a public Docker registry.
How should the developer deploy the application to Elastic Beanstalk?
> **Create a ``docker-compose.yml`` file. Use the Elastic Beanstalk CLI to deploy the application.**
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
13. A company is using AWS CodeDeploy for all production deployments. A developer has an Amazon Elastic Container Service (Amazon ECS) application that uses the CodeDeployDefault.ECSAIIAtOnce configuration. The developer needs to update the production environment in increments of 10% until the entire production environment is updated.
Which CodeDeploy configuration should the developer use to meet these requirements?
> **CodeDeployDefault.``ECSLinear10PercentEvery3Minutes``**
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
14. A company is using AWS Elastic Beanstalk to deploy a three-tier application. The application uses an Amazon RDS DB instance as the database tier. The company wants to decouple the DB instance from the Elastic Beanstalk environment.
Which combination of steps should a developer lake to meet this requirement? (Choose two.)
>**Create a new DB instance from a snapshot of the previous DB instance.**
>**Create a new Elastic Beanstalk environment that connects to the DB instance.**
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
15. A company has point-of-sale devices across thousands of retail shops that **synchronize sales transactions with a centralized system.** The system includes an
Amazon API Gateway API that exposes an AWS Lambda function. The Lambda function processes the transactions and stores the transactions in Amazon RDS for MySQL.**The number of transactions increases rapidly during the day and is near zero at night.**
How can a developer increase the elasticity of the system MOST cost-effectively?
> **~~Migrate from Amazon RDS to Amazon Aurora MySQL. Use an Aurora Auto Scaling policy to scale road replicas based on CPU consumption.~~** -> For read
> **~~Migrate from Amazon RDS to Amazon Aurora MySQL. Use an Aurora Auto Scaling policy to scale read replicas based on the number of database connections.~~** -> For read
> **~~Create an Amazon Simple Queue Service (Amazon SQS) queue. Publish transactions to the queue. Set the queue to invoke the Lambda function. Turn on enhanced fanout for the Lambda function.~~** -> Enhanced fanout: for kinesis
> **Create an Amazon Simple Queue Service (Amazon SQS) queue. Publish transactions to the queue. Set the queue to invoke the Lambda function. Set the reserved concurrency of the Lambda function to be less than the number of database connections.**
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
16. A developer is writing an AWS Lambda function. The Lambda function needs to access items that are stored in an Amazon DynamoDB table.
What is the MOST secure way to configure this access for the Lambda function?
> **Create an ``IAM policy that allows access to the DynamoDB table``. Attach this policy to the Lambda function's IAM role**
> **~~Add a resource-based policy to the DynamoDB table to allow access from the Lambda function's IAM role.~~** -> DynamoDB doesnt support
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
17. A developer is implementing user authentication and authorization for a web application that is hosted on an Amazon EC2 instance. The developer needs to ensure that the user credentials are encrypted and secure when they are stored and transmitted.
Which solution will meet these requirements?
> **Use Amazon Cognito to configure a user pool. Use the Amazon Cognito API to authenticate and authorize the users. Most Voted**
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
18. A company that has multiple offices uses an Amazon DynamoDB table to store employee payroll information. Item attributes consist of ``employee names``, ``office identifiers``, and ``cumulative daily hours worked``. **The most frequently used query extracts a report of an alphabetical subset of employees for a specific office.**
Which design of the DynamoDB table primary key will have the MINIMUM performance impact?
> **Partition key on the office identifier and sort key on the employee name**
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
19. A company hosts a microservices application that uses **Amazon API Gateway**. AWS **Lambda**, Amazon Simple Queue Service **(Amazon SQS)**, and Amazon **DynamoDB**. One of the Lambda functions adds messages to an SQS FIFO queue.
When a developer checks the application logs, the developer **finds a few duplicated items in a DynamoDB table**. The items were inserted by another polling function that processes messages from the queue.
What is the MOST likely cause of this issue?
> **The polling function timeout is greater than the queue visibility timeout.**
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
20. A development team has been using a builder server that is hosted on an Amazon EC2 instance to perform builds and deployments for the last 3 months. The
EC2 instance's instance profile uses an IAM role that contains the Administrator Access managed policy. The development team must replace that policy with a policy that provides only the required permissions.
**What is the FASTEST way to create a custom 1AM policy for the EC2 instance to meet this requirement?**
> **Create a new IAM policy that includes all actions that AWS CloudTrail recorded for the IAM role in the last 3 months.**
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

-----------------------------------------------------------------------------------------------------------