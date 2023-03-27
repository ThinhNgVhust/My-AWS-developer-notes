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
15. A company has point-of-sale devices across thousands of retail shops that **synchronize sales transactions with a centralized system.** The system includes an Amazon API Gateway API that exposes an AWS Lambda function. The Lambda function processes the transactions and stores the transactions in Amazon RDS for MySQL.**The number of transactions increases rapidly during the day and is near zero at night.**    
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
20. A development team has been using a builder server that is hosted on an Amazon EC2 instance to perform builds and deployments for the last 3 months. The EC2 instance's instance profile uses an IAM role that contains the Administrator Access managed policy. The development team must replace that policy with a policy that provides only the required permissions.     
**What is the FASTEST way to create a custom 1AM policy for the EC2 instance to meet this requirement?**     
> **Create a new IAM policy that includes all actions that AWS CloudTrail recorded for the IAM role in the last 3 months.**       
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
21. A developer needs to write an **AWS CloudFormation template on a local machine and deploy a CloudFormation stack to AWS**. What must the developer do to complete these tasks?
> **Install the AWS CLI. Configure the AWS CLI by using an IAM user ``access key`` and ``secret key``**
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
22. A developer is working on a web application that runs on Amazon Elastic Container Service (Amazon **ECS**) and uses an Amazon DynamoDB table to store data.            
The application performs a large number of read requests against a small set of the table data.          
How can the developer improve the performance of these requests? (Choose two.)           
> **Create a DynamoDB Accelerator (DAX) cluster. Configure the application to use the ``DAX`` cluster for DynamoDB requests.**
> 
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
23. A developer needs to use Amazon DynamoDB to store customer orders. The developer's company requires all customer data to be encrypted at rest with a key that the company generates.          
What should the developer do to meet these requirements?              
> 
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
24. A developer is creating a solution to track an account's Amazon S3 buckets over time. The developer has created an AWS Lambda function that will run on a schedule. The function will list the account's S3 buckets and will store the list in an Amazon DynamoDB table. The developer receives a permissions error when the developer runs the function with the ``AWSLambdaBasicExecutionRole`` AWS managed policy.     
Which combination of permissions should the developer use to resolve this error? (Choose two.)    
> **Permission for the Lambda function to list buckets in Amazon S3**    
> **Permission for the Lambda function to write in DynamoDB**    
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
25. A company is adding items to an Amazon DynamoDB table from an AWS Lambda function that is written in Python. A developer **needs to implement a solution that inserts records in the DynamoDB table and performs automatic retry when the insert fails**.           
Which solution meets these requirements with MINIMUM code changes?      
> **Use the AWS software development kit (SDK) for Python (boto3) to call the PutItem operation** -> AWS SDKs implements exponential backoff     
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
26. Question #26Topic 1
A developer is writing an AWS **Lambda** function. **The developer wants to log key events that occur during the Lambda function and include a unique identifier to associate the events with a specific function invocation.**         
Which of the following will help the developer accomplish this objective?         
> **Obtain the request identifier from the ``Lambda context object``. Architect the application to ``write logs to the console``**
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
27. A company experienced partial downtime during the last deployment of a new application. AWS Elastic Beanstalk split the environment's Amazon EC2 instances into batches and deployed a new version one batch at a time after taking them out of service. Therefore, full capacity was not maintained during deployment.        
The developer plans to release a new version of the application, and is looking for a policy that will **maintain full capacity and minimize the impact of the failed deployment.**           
Which deployment policy should the developer use?         
> **Immutable**   
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
28. A company is providing services to many downstream consumers. Each consumer may **connect to one or more services**. This has resulted in a complex architecture that is difficult to manage and does not scale well. The company needs a **single interface** to manage these services to consumers.      
Which AWS service should be used to refactor this architecture?       
> API Gateway
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
29. When a Developer tries to run an AWS CodeBuild project, it raises an error because **the length of all environment variables exceeds the limit for the combined maximum of characters.**          
What is the recommended solution?          
> Use AWS ``Systems Manager Parameter Store`` to store large numbers of environment variables.    
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
30. A Development team decides to adopt a continuous integration/continuous delivery (CI/CD) process using AWS CodePipeline and AWS CodeCommit for a new application. However, management wants a person to review and approve the code before it is deployed to production.     
How can the Development team add a **manual approver** to the CI/CD pipeline?      
> Add an approval action to the pipeline. **Configure the approval action to publish to an Amazon SNS topic when approval is required. The pipeline execution will stop and wait for an approval.**
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
31. A Developer is migrating an on-premises application to AWS. The application currently takes user uploads and saves them to a local directory on the server. **All uploads must be saved and made immediately available to all instances in an Auto Scaling group.**
Which approach will meet these requirements?    
> **Use Amazon S3 and rearchitect the application so all uploads are placed in S3.**
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
32. A developer is creating a script to automate the deployment process for a serverless application. The developer wants to use an existing AWS Serverless      
Application Model (AWS SAM) template for the application.       
What should the developer use for the project? (Choose two.)      
>**Call ``aws cloudformation package`` to create the deployment package. Call ``aws cloudformation deploy`` to deploy the package afterward.**
>**Call ``sam package`` to create the deployment package. Call ``sam deploy`` to deploy the package afterward**
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
33. A developer has built a market application that stores pricing data in **Amazon DynamoDB** with **Amazon ElastiCache** in front. **The prices of items in the market change frequently**. Sellers have begun complaining that, after they update the price of an item, the price does not actually change in the product listing.           
What could be causing this issue?     
> **The cache is not being invalidated when the price of the item is changed**      
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
34. The developer is creating a web application that collects highly regulated and confidential user data through a POST request. The web application is served through Amazon CloudFront. User names and phone numbers must be encrypted at the edge and must remain encrypted throughout the **entire application stack**.
What is the MOST secure way to meet these requirements?
> **Use field-level encryption on CloudFront.**
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
35. A Developer has been asked to create an AWS Lambda function that is triggered any time updates are made to items in an Amazon DynamoDB table. The function has been created, and appropriate permissions have been added to the Lambda execution role. **Amazon DynamoDB** streams have been enabled for the table, but the function is still not being triggered.
Which option would enable DynamoDB table updates to trigger the Lambda function?      
> **Configure event source mapping for the Lambda function**               
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
36. (*)(*)(*)(*)(*)(*) A company maintains a REST service using Amazon API Gateway and the API Gateway native API key validation. The company recently launched a new registration page, which allows users to sign up for the service. The registration page creates a new API key using **CreateApiKey** and sends the new key to the user. When the user attempts to call the API using this key, the user receives a **403 Forbidden error**. Existing users are unaffected and can still call the API.             
What code updates will grant these new users access to the API?                  
> **The ``createUsagePlanKey`` method must be called to associate the newly created API key with the correct usage plan.** 
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
37. An application uploads photos to an Amazon S3 bucket. Each photo that is uploaded to the S3 bucket must be resized to a thumbnail image by the application.         
Each thumbnail image is uploaded with a new name in the same S3 bucket.             
Which AWS service can a developer configure to directly process each single S3 event for each S3 object upload?
> **AWS Lambda**                       
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
38. A company is running a Docker application on **Amazon ECS**. **The application must scale based on user load in the last 15 seconds**.            
How should a Developer instrument the code so that the requirement can be met?            
> **Create a ``high-resolution custom`` Amazon CloudWatch metric for user activity data, then publish data every 5 seconds**
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
39. Where should the appspec.yml file be placed in order for AWS CodeDeploy to work?
> **In the root of the application source code directory structure**
-----------------------------------------------------------------------------------------------------------
40. A Developer is working on an application that handles **10MB documents** that contain **highly-sensitive data**. The application will use AWS KMS to perform client- side encryption.                      
What steps must be followed?                
> **Invoke the ``GenerateDataKey API`` to retrieve the plaintext version of the data encryption key to encrypt the data**

-----------------------------------------------------------------------------------------------------------------------

-----------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------

-----------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------

-----------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------

-----------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------

-----------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------

-----------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------

-----------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------

-----------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------

-----------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------

-----------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------

-----------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------

-----------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------

-----------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------

-----------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------

-----------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------

-----------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------

-----------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------

-----------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------

-----------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------

-----------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------

-----------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------

-----------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------

-----------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------

-----------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------

-----------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------

-----------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------

-----------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------

-----------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------

-----------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------

-----------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------

-----------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------

-----------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------

-----------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------

-----------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------

-----------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------

-----------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------

-----------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------

-----------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------

-----------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------

-----------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------

-----------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------

-----------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------

-----------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------

-----------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------

-----------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------

-----------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------

-----------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------

-----------------------------------------------------------------------------------------------------------------------
