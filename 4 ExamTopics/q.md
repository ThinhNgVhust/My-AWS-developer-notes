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
> **Invoke the ``GenerateDataKey API`` to retrieve the ``plaintext`` version of the data encryption key to encrypt the data**

-----------------------------------------------------------------------------------------------------------------------
41. An application uses ``Amazon Kinesis Data Streams`` to ingest and process large streams of data records in real time. Amazon EC2 instances consume and process the data from the shards of the Kinesis data stream by using Amazon Kinesis Client Library (KCL). The application handles the failure scenarios and does not require standby workers. The application reports that a specific shard is receiving more data than expected. To adapt to the changes in the rate of data flow, the `hot` shard is resharded.               
Assuming that the initial number of shards in the Kinesis data stream is 4, and after resharding the number of shards increased to 6, what is the maximum number of EC2 instances that can be deployed to process data from all the shards?         
> **6**
-----------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------
42. A Company runs continuous integration/continuous delivery (CI/CD) pipelines for its application on AWS **CodePipeline**. A Developer must write ``unit tests`` and run them as part of the pipelines before staging the artifacts for testing.             
How should the Developer incorporate unit tests as part of CI/CD pipelines?         
> **Update the AWS CodeBuild specification to include a phase for running unit tests**
-----------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------
43. A Developer has written an application that runs on Amazon EC2 instances and generates a value every minute. The Developer wants to **monitor and graph the values generated over time** without logging in to the instance **each time**.                      
Which approach should the Developer use to achieve this goal?
>**Publish each generated value as a custom metric to Amazon CloudWatch using available AWS SDKs.**                        
-----------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------
44. A developer is trying to get data from an Amazon DynamoDB table called demoman-table. The developer configured the AWS CLI to use a specific IAM user's credentials and executed the following command:``aws dynamodb get-item --table-name deamon-tale --key '{"id":{"N":"1993"}}'``   
The command returned errors and no rows were returned.               
What is the MOST likely cause of these issues?          
> **The IAM user needs an associated policy with read access to demoman-table.**
-----------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------
45. A Development team is working on a case management solution that allows **medical claims to be processed and reviewed**. **Users log in to provide information related to their medical and financial situations**.                  
As part of the application, sensitive documents such as medical records, medical imaging, bank statements, and receipts are uploaded to Amazon S3. All documents must be **securely transmitted and stored**. **All access to the documents must be recorded for auditing**.                   
What is the MOST secure approach?            
> **Use client-side encryption/decryption with Amazon S3 and AWS KMS.**
-----------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------
46. A developer is planning to use an **Amazon API Gateway** and **AWS Lambda** to provide a REST API. The developer will have three distinct environments to manage: ``development``, ``test``, and ``production``.            
How should the application be deployed while minimizing the number of resources to manage?     
>**Create one API Gateway with multiple stages with one Lambda function with multiple aliases.**                
-----------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------
47. An application needs to use the IP address of the client in its processing. The application has been moved into AWS and has been placed behind an Application
Load Balancer (ALB). However, all the client IP addresses now appear to be the same. The application must maintain the ability to scale horizontally.
Based on this scenario, what is the MOST cost-effective solution to this problem?             
>**Alter the application code to inspect the ``X-Forwarded-For`` header. Ensure that the code can work properly if a list of IP addresses is passed in the header.**             
-----------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------
48. A developer tested an application locally and then deployed it to **AWS Lambda**. While testing the application remotely, the Lambda function fails with an **access denied message**.
How can this issue be addressed?         
> **Update the Lambda function's ``execution role`` to include the missing permissions**           
-----------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------
49. A Developer must **analyze performance** issues with production-distributed applications written as AWS **Lambda** functions. These distributed Lambda applications invoke other components that make up the applications.         
How should the Developer identify and troubleshoot the root cause of the performance issues in production?      
>**Use AWS X-Ray, then examine the segments and errors.**   
-----------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------
50. A company is building a compute-intensive application that will run on a fleet of Amazon EC2 instances. The application uses attached Amazon EBS disks for storing data. The application will process sensitive information and all the data must be encrypted.
What should a Developer do to ensure the data is encrypted on disk without impacting performance?
>**Configure the Amazon EC2 instance fleet to use encrypted EBS volumes for storing data.**
-----------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------
51. A Developer is working on a serverless project based in Java. Initial testing shows a cold start takes about 8 seconds on average for AWS Lambda functions.
What should the Developer do to **reduce the cold start time**? (Choose two.)        
> **Reduce the deployment package by including only needed modules from the AWS SDK for Java.**
> **Increase the memory allocation setting for the Lambda function**               
-----------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------
52. A company runs an **e-commerce websit**e** that uses Amazon **DynamoDB** where **pricing for items is dynamically updated in real time**. At any given time, multiple updates may occur simultaneously for pricing information on a particular product. This is causing the original editor's changes to be overwritten without a proper review process.        
Which DynamoDB write option should be selected to prevent this overwriting?             
>**Conditional writes**                  
-----------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------
53. A developer is storing JSON files in an Amazon S3 bucket. The developer wants to securely share an object with a specific group of people.             
How can the developer securely provide temporary access to the objects that are stored in the S3 bucket?    
> **Use the AWS software development kit (SDK) to generate a presigned URL. Provide the ``presigned URL``.**     
-----------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------
54. A front-end web application is using Amazon ``Cognito user pools`` to handle the user authentication flow. A developer is integrating ``Amazon DynamoDB`` into the application using the AWS SDK for ``JavaScript``.          
How would the developer securely call the API without exposing the access or secret keys?
>**Configure Amazon Cognito identity pools and exchange the JSON Web Token (JWT) for temporary credentials.**                
-----------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------
55. A Developer must build an application that uses Amazon DynamoDB. The requirements state that the items being stored in the DynamoDB table will be ``7KB`` in size and that reads must be ``strongly consistent``. The maximum ``read rate is 3 items per second``, and the maximum ``write rate is 10 items per second``.
How should the Developer size the DynamoDB table to meet these requirements?  
> 1strongly consistent = 1RCU. 6RCU and 70WCU               
-----------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------
56. A company needs to ``ingest terabytes of data each hour from thousands of sources`` that are delivered almost continually throughout the day. The volume of messages generated varies over the course of the day. Messages must be delivered in ``real time for fraud detection and live operational dashboards``.                  
Which approach will meet these requirements?                  
>Use **Amazon Kinesis Data Streams** with Kinesis Client Library to ingest and deliver messages      
-----------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------
57. A developer is debugging an AWS Lambda function behind an Amazon API Gateway. Whenever the API Gateway endpoint is called, HTTP status code 200 is returned even though AWS Lambda is recording a 4xx error.                
What change needs to be made to return a proper error code through the API Gateway?      
>**Use a Lambda proxy integration to return HTTP codes and headers**                          
-----------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------
58. For a deployment using AWS CodeDeploy, what is the run order of the **hooks** for in-place deployments?         

    1. ~~Before Install -> Application Stop -> Application Start -> After Install~~  -> Application Stop phải đứng đầu tiên
    2. **Application Stop -> Before Install -> After Install -> Application Start**
    3. ~~Before Install -> Application Stop -> Validate Service -> Application Start~~  ->  Validate Service phải ở sau cùng
    4. ~~Application Stop -> Before Install -> Validate Service -> Application Start~~->  Validate Service phải ở sau cùng
-----------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------
59. A developer is using Amazon S3 as the event source that invokes a Lambda function when new objects are created in the bucket. The event source mapping information is stored in the bucket notification configuration. The developer is working with different versions of the Lambda function, and has a constant need to update notification configuration so that Amazon S3 invokes the correct version.                                                                              
What is the MOST efficient and effective way to achieve mapping between the S3 event and Lambda?              
> **Use a Lambda alias.**     
-----------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------
60. A company has a multi-tier application that uses Amazon API Gateway, AWS Lambda, and Amazon RDS. The company wants to investigate a slow response time to calls that come from the API Gateway API.                                                                                                                          
What is the MOST operationally efficient way for the company to determine which internal call is causing the slow response times?   
>**Use AWS X-Ray**                  
-----------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------
61. A developer is deploying an application that will store files in an Amazon S3 bucket. The files must be encrypted at rest. The developer wants to automatically replicate the files to an S3 bucket in a different AWS Region for disaster recovery.          
How can the developer accomplish this task with the LEAST amount of configuration?       
> **Encrypt the files by using server-side encryption with S3 managed encryption keys (SSE-S3). Enable S3 bucket replication.**                   
-----------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------
62. A serverless application is using AWS **Step Functions** to process data and save it to a database. The application needs to validate some data with an external service before saving the data. The application will call the external service from an AWS Lambda function, and the external service will take a few hours to validate the data. The external service will respond to a webhook when the validation is complete.       
A developer needs to pause the Step Functions workflow and wait for the response from the external service.            
What should the developer do to meet this requirement?        
>**Use the ``.wait ForTaskToken`` option in the Lambda function task state. Pass the token in the body**            
-----------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------
63. A developer must use AWS X-Ray to monitor an application that is running on an Amazon EC2 instance. The developer has prepared the application by using the
X-Ray SDK.             
What should the developer do to perform the monitoring?          
>**Install the X-Ray ``daemon``. Configure it to forward data to Amazon EventBridge (Amazon CloudWatch Events). Grant the EC2 instance permission to write to Event Bridge (CloudWatch Events).**
-----------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------
64. A developer is designing a full-stack serverless application. Files for the website are stored in an Amazon S3 bucket. AWS Lambda functions that use Amazon
API Gateway endpoints return results from an Amazon DynamoDB table.                         
The developer must create a solution that securely provides registration and authentication for the application while minimizing the amount of configuration.
Which solution meets these requirements?              
> Create an Amazon Cognito user pool and an app client. Configure the app client to use the user pool and provide the hosted web UI provided for sign-up and sign-in. 
-----------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------
65. A company has an application that writes files to an Amazon S3 bucket. Whenever there is a new file, an S3 notification event invokes an AWS Lambda function to process the file. The Lambda function code works as expected. However, when a developer checks the Lambda function logs, the developer finds that multiple invocations occur for every file.               
What is causing the duplicate entries?            
> The Lambda function did not run correctly, and Lambda retried the invocation with a delay.                    
-----------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------
66. A developer needs to use the AWS CLI on an on-premises development server temporarily to access AWS services while performing maintenance. The developer needs to authenticate to AWS with their identity for ``several hours``.                 
What is the MOST secure way to call AWS CLI commands with the developer's IAM identity?             
> **Run the get-session-token CLI command with the developer's IAM user. Use the returned credentials to call the CLI**                             
-----------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------
67. An AWS Lambda function accesses two Amazon DynamoDB tables. A developer wants to improve the performance of the Lambda function by identifying bottlenecks in the function.        
How can the developer inspect the timing of the DynamoDB API calls?        
> Enable AWS X-Ray tracing for the function. View the traces from the X-Ray service.
-----------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------
68. A developer deployed an application to an Amazon EC2 instance. The application needs to know the public ``IPv4 address`` of the instance.
How can the application find this information?
> **Query the instance metadata from ``http://169.254.169.254/latest/meta-data/``**
-----------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------
69. A developer is designing an AWS Lambda function to perform a maintenance activity. The developer will use Amazon EventBridge (Amazon CloudWatch Events) to invoke the function on an hourly schedule. The developer wants the function to log information at different levels of detail according to the value of a log level variable. The developer must design the function so that the log level can be set without requiring a change to the function code.             
Which solution will meet these requirements?              
A. Add a custom log level parameter for the Lambda function. Set the parameter by using the Lambda console                                             
B. **Set the log level in a Lambda environment variable**                                                
C. Set the log level in the Amazon CloudWatch Logs console.                                             
D. Add a custom log level parameter for the Lambda function. Set the parameter by using the AWS CLI.                   
 

-----------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------
70.  A developer is creating a **serverless application** that uses an AWS Lambda function The developer will use AWS **CloudFormation** to deploy the application The application will write logs to Amazon CloudWatch Logs. The developer has created a log group in a CloudFormation template for the application to use. The developer needs to modify the CloudFormation template to make the name of the log group available to the application at runtime.                             
Which solution will meet this requirement?                                 
A. Use the AWS::Include transform in CloudFormation to provide the log group's name to the application.                               
B. Pass the log group's name to the application in the user data section of the CloudFormation template                         
C. Use the CloudFormation template's Mappings section to specify the log group's name for the application.                                                             
D. **Pass the log group's Amazon Resource Name (ARN) as an environment variable to the Lambda function.**      

-----------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------
71.A company is running an application on Amazon Elastic Container Service (Amazon ECS). When the company deploys a new version of the application, the company initially needs to expose 10% of live traffic to the new version. After a period of time, the company needs to immediately route all the remaining live traffic to the new version.             
Which ECS deployment should the company use to meet these requirements?           
> **Blue/green with canary**
-----------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------
72. A microservices application is deployed across multiple containers in Amazon Elastic Container Service (Amazon ECS). To improve performance, a developer wants to capture trace information between the microservices and visualize the microservices architecture.             
Which solution will meet these requirements?              
>**Build the container from the amazon/aws-xray-daemon base image. Use the AWS X-Ray SDK to instrument the application.**              
-----------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------
73. A company is planning to use AWS CodeDeploy to deploy an application to Amazon Elastic Container Service (Amazon ECS). During the deployment of a new version of the application, the company initially must expose only 10% of live traffic to the new version of the deployed application. Then, after 15 minutes elapse, the company must route all the remaining live traffic to the new version of the deployed application.         
Which CodeDeploy predefined configuration will meet these requirements?              
> ``CodeDeployDefault.ECSCanary10Percent15Minutes``
-----------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------
74. A developer notices timeouts from the AWS CLI when the developer runs list commands.         
What should the developer do to avoid these timeouts?            
> **Use the ``--page-size`` parameter to request a smaller number of items.**
-----------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------
75. A company has moved a legacy on-premises application to AWS by performing a lift and shift. The application exposes a REST API that can be used to retrieve billing information. The application is running on a single Amazon EC2 instance. The application code cannot support concurrent invocations. Many clients access the API, and the company adds new clients all the time.
A developer is concerned that the application might become overwhelmed by too many requests. The developer **needs to limit the number of requests to the API for all current and future clients**. **The developer must not change the API, the application, or the client code.**             
What should the developer do to meet these requirements?           
> **Place the API behind an Amazon API Gateway API. Set the ``per-client throttling limits``.**                    
-----------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------
76. An ecommerce company wants to redirect users to a country-specific website when they enter the ``example.com`` website. For example, the company wants to redirect ``United States`` users to ``example.com/us/`` and wants to redirect ``French`` users to ``example.com/fr/``. The web application is using Amazon CloudFront and an Application Load Balancer with an Amazon Elastic Container Service (Amazon ECS) cluster. The application's domain name resolution is configured in an Amazon Route 53 public hosted zone.            
Which solution will meet these requirements with the ``LEAST`` operational effort?        
>**Create a CloudFront function to inspect the CloudFront-Viewer-Country header and return redirect responses to different URLs based on user location.**               
-----------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------
77. A developer deploys an AWS Lambda function that runs each time a new Amazon S3 bucket is created. The Lambda function is supposed to attach an S3           
Lifecycle policy to each new S3 bucket. The developer discovers that newly created S3 buckets have no S3 Lifecycle policy attached.             
Which AWS service should the developer use to find a possible error in the Lambda function?       
>**CloudWatch**           
-----------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------
78. A developer has created a web API that uses Amazon Elastic Container Service **(Amazon ECS)** and an Application Load Balancer **(ALB)**. An Amazon **CloudFront** distribution uses the API as an origin for web clients. The application has received millions of requests with a JSON Web Token **(JWT)** that is not valid in the authorization header. The developer has scaled out the application to handle the unauthenticated requests.             
What should the developer do to reduce the number of unauthenticated requests to the API?          
> **Create a CloudFront function for the distribution Use the crypto module in the function to validate the JWT**
-----------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------
79. A developer is creating a mobile application that will not require users to log in.             
What is the MOST efficient method to grant users access to AWS resources?               
> **Use Amazon Cognito to associate unauthenticated users with an IAM role that has limited access to resources.**             
-----------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------
80. A developer has created on AWS Lambda function tool uses 15 MB of memory. When the developer runs the code natively on a laptop that has 4 cores, the function runs within 100 ms. When the developer deploys the code as a Lambda function with 128 MB of memory, the first run takes 3 seconds. Subsequent runs take more than 500 ms to finish.               
The developer needs to improve the performance of the Lambda function so that the function runs consistently in less than 100 ms, excluding the initial startup time.
Which solution will meet this requirement?                 
> **Increase the memory of the Lambda function.**
-----------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------
81. A developer has built an application that inserts data into an Amazon ``DynamoDB`` table. The table is configured to use provisioned capacity. The application is deployed on a burstable nano Amazon EC2 Instance. The application logs show that the application has been failing because of a
```ProvisionedThroughputExceedException``` error.             
Which actions should the developer take to resolve this issue? (Choose two.)     
> **Expotenial backoffs**
> **Change the capacity mode of the DynamoDB table from provisioned to on-demand.**       
-----------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------
82. A developer is deploying on application on Amazon EC2 instances that run in Account A. In certain cases, this application needs to read data from a private
Amazon S3 bucket in Account B. The developer must provide the application access to the S3 bucket without exposing the S3 bucket to anyone else.          
Which combination of actions should the developer take to meet these requirements? (Choose two.)             
> **Configure the bucket policy in Account B to grant permissions to the instance profile role.**              
> **Update the instance profile IAM role in Account A with S3 read permissions** 

-----------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------
83. A developer at a company recently created a serverless application to process and show data from business reports. The application's user interface (UI) allows users to select and start processing the flies. The UI displays a message when the result is available to view. The application uses AWS Step Functions with AWS                    
Lambda functions to process the files. The developer used Amazon API Gateway and Lambda functions to create an API to support the UI.             
The company's UI team reports that the request to process a file s often returning timeout errors because of the size or complexity of the files. The UI team wants the API to provide an immediate response so that the UI can display a message while the files are being processed. The backend process that is invoked by the                   
API needs to send an email message when the report processing is complete.       
What should the developer do to configure the API to meet these requirements?                                 
-----------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------
84. 
-----------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------
85. 
-----------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------
86. A developer at a company recently created a **serverless application** to process and show data from business reports. The application's user interface (UI) allows users to select and start processing the flies. The UI displays a message when the result is available to view. The application uses AWS Step Functions with AWS                 
Lambda functions to process the files. The developer used **Amazon API Gateway** and Lambda functions to create an API to support the UI.                      
The company's UI team reports that the request to process a file s often returning **timeout errors** because of the **size or complexity** of the files. The UI team wants the API to provide an immediate response so that the UI can display a message while the files are being processed. The backend process that is invoked by the                                          
API needs to send an email message when the report processing is complete.                
What should the developer do to configure the API to meet these requirements?                              
## > Change the API Gateway route to add an X-Amz-Invocation-Type header with a static value of 'Event' in the integration request. Deploy the API Gateway stage to apply the changes. 
-----------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------
87. A developer needs to create an application that supports Security Assertion Markup Language (SAML) and authentication with social media providers. It must also allow access to AWS services, such as Amazon DynamoDB.               
Which AWS service or feature will meet these requirements with the LEAST amount of additional coding?     
> **Amazon Cognito identity pools**
-----------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------
88. A developer is designing a **serverless application** for an ecommerce website. An Amazon API Gateway API exposes AWS Lambda functions for billing, payment, and user operations. The website features shopping carts for the users. The shopping carts must be stored for extended periods of time and will be retrieved frequently by the front-end application.
The load on the application will vary significantly based on the time of day and the promotional sales that are offered on the website. The application must be **able to scale automatically** to meet these changing demands.                 
Which solution will meet these requirements?      

> ~~A. Store the data objects on an Amazon RDS DB instance. Cache the data objects in memory by using Amazon ElastiCache.~~   -> Not serveless  
> ~~B. Store the data objects on Amazon EC2 instances behind an Application Load Balancer. Use session affinity (sticky sessions) for each user's shopping cart.~~    -> Not serveless 
> C. ~~Store the data objects in Amazon S3 buckets. Cache the data objects by using Amazon CloudFront with the maximum TTL.~~   -> Not scale automatically
> D. Store the data objects in Amazon DynamoDB tables. Cache the data objects by using DynamoDB Accelerator (DAX).              
-----------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------
89. A company is migrating its on-premises database to Amazon RDS for MySQL. The company has ``read-heavy workloads``, and wants to make sure it re-factors its code to achieve optimum read performance for its queries.                
How can this objective be met?                
> **Add a connection string to use an RDS read replica for read queries.**           
-----------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------
90. An application running on Amazon EC2 opens connections to an Amazon RDS SQL Server database. ``The developer does not want to store the user name and password for the database in the code``. The developer would also like to ``automatically rotate the credentials``.                  
What is the MOST secure way to store and access the database credentials?               
> **Use AWS Secrets Manager to store the credentials. Retrieve the credentials from Secrets Manager as needed.**
-----------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------
91. A developer received the following error message during an AWS CloudFormation deployment:
``DELETE_FAILED`` (The following resource(s) failed to delete: [ASGInstanceRolel2345678].)
Which action should the developer take to resolve this error?
> **Modify the CloudFormation template to retain the ASGInstanceRolel2345678 resource. Then manually delete the resource after deployment.**       
-----------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------
92. An application runs on multiple EC2 instances behind an ELB.         
Where is the session data best written so that it can be served reliably across multiple requests?           
> Write data to Amazon ElastiCache.
-----------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------
93. A company is using continuous integration/continuous delivery (CI/CD) systems. A developer must automate the deployment of an application software package to Amazon EC2 instances and virtual servers that run on premises.         
Which AWS service should the developer use to meet these requirements?                      
> Code Deploy          
-----------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------
94. A software company is using AWS CodeBuild to build an application. The buildspec runs the application build and creates a Docker image that contains the application. The company needs to push the Docker image to Amazon Elastic Container Registry (Amazon ECR) only upon the completion of each successful build.
Which solution meets these requirements?
> **Change the buildspec by adding a post_build phase that uses the commands block to push the Docker image.**            
-----------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------
95. A company is using Amazon RDS as the backend database for its application. After a recent marketing campaign, a surge of read requests to the database increased the latency of data retrieval from the database.                   
The company has decided to implement a caching layer in front of the database. The cached content must be encrypted and must be highly available.           
Which solution will meet these requirements?                      
> **Amazon ElastiCache for Redis in cluster mode**               
-----------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------
96. 
-----------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------
97. 
-----------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------
98. A company is developing a report implemented using AWS Step Functions. Amazon CloudWatch shows errors in the Step Functions task state machine. To troubleshoot each task, the state input needs to be included along with the error message in the state output.        
Which coding practice can **preserve both the original input and the error** for the state?           
> **Use ``ResultPath`` in a Catch statement to include the error with the original input.**            
-----------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------
99. A developer is receiving **HTTP 400: ThrottlingException** errors intermittently when calling the Amazon CloudWatch API. When a call fails, no data is retrieved.
What best practice should first be applied to address this issue?
> **Exponential backoff**
-----------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------
100. 
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