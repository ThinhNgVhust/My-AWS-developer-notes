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