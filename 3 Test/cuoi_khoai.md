## Attempt1

1. Question 1:
- A company developed an app-based service for citizens to book transportation rides in the local community. The platform is running on AWS EC2 instances and uses Amazon Relational Database Service (RDS) for storing transportation data. A new feature has been requested where receipts would be emailed to customers with PDF attachments retrieved from Amazon Simple Storage Service (S3).

- Which of the following options will provide EC2 instances with the right permissions to upload files to Amazon S3 and generate S3 Signed URL?

- Answer: Create IAM Role for EC2


-  EC2 User Data: You can specify user data when you launch an instance and you would not want to hard code the AWS credentials in the user data.
-  Run **aws configure** on the EC2 instance: 
-  CloudFormation: AWS CloudFormation gives developers and businesses an easy way to create a collection of related AWS and third-party resources and provision them in an orderly and predictable fashion.
------------------------------------------------------------------------------------------------------------------------
2. Q2:
-  An IT company has a **HealthCare application with data security requirements** such that the **encryption key must be stored in a custom application running on-premises**. The company wants to offload the data storage as well as the encryption process to Amazon S3 but continue to use the existing encryption keys.

-  Which of the following S3 encryption options allows the company to leverage Amazon S3 for storing data with given constraints?

-  SSE:Request Amazon S3 to encrypt your object before saving it on disks in its data centers and then decrypt it when you download the objects.
-  CSE: Encrypt data client-side and upload the encrypted data to Amazon S3. In this case, you manage the encryption process, the encryption keys, and related tools.

-  Explain:
    -  We can encrypt objects in S3 using 4 methods:
        -  **Sever-side encryption**(SSE): 
            -  With **S3 Managed Key** (default SSE-S3)
            -  with **KMS Keys Stored in AWS KMS** (SSE-KMS)
            -  With **Customer-Provide Keys** (SSE-C)
        -  **Client-side encryption 
-----------------------------------------------------------------------------------------------------------------

3. Q3:
-  A new recruit is trying to understand the nuances of EC2 Auto Scaling. As an AWS Certified Developer Associate, you have been asked to mentor the new recruit.

- Can you identify and explain the correct statements about Auto Scaling to the new recruit? (Select two).

- Answer:
    -  **Amazon EC2 Auto Scaling cannot add a volume to an existing instance if the existing volume is approaching capacity** - A volume is attached to a new instance when it is added. Amazon EC2 Auto Scaling doesn't automatically add a volume when the existing one is approaching capacity. You can use the EC2 API to add a volume to an existing instance.
    -  **Amazon EC2 Auto Scaling works with both Application Load Balancers and Network Load Balancers** - Amazon EC2 Auto Scaling works with Application Load Balancers and Network Load Balancers including their health check feature.

-  Incorrect options:
    -  **EC2 Auto Scaling groups are regional constructs. They span across Availability Zones and AWS regions** --  Than can span AZ, not AWS regions
    -  **Every time you create an Auto Scaling group from an existing instance, it creates a new AMI (Amazon Machine Image)** ---   When you create an Auto Scaling group from an existing instance, **it does not create a new AMI.**
    -  **You cannot use Amazon EC2 Auto Scaling for health checks (to replace unhealthy instances) if you are not using Elastic Load Balancing (ELB)** --  You don't have to use ELB to use Auto Scaling. You can use the EC2 health check to identify and replace unhealthy instances.
--------------------------------------------------------------------------------------------------------------------

4. Q4:**Skipped**
-  A client has hired you as an AWS Certified Developer Associate for a consulting project. **The client wants to weigh their options of choosing between an Amazon SQS standard queue and Amazon Simple Workflow Service (SWF).**

-  Which of the following statements are correct regarding the two services? (Select two)

-  Answer:
    -  **SWF ensures the task is assigned only once** while **SQS may deliver the message multiple times**
    -  **SWF has task-oriented APIs** and **SQS has message-oriented APIs** 

- Knowledge: 
    -  Amazon Simple Workflow Service (Amazon SWF), you can implement distributed, **asynchronous applications** as workflows. Workflows coordinate and manage the execution of activities that can be run asynchronously across multiple computing devices and that can feature both sequential and parallel processing.
    -  When designing a workflow, **you analyze your application to identify its component tasks**. In Amazon SWF, these tasks are represented by activities. The order in which activities are performed is determined by the workflow's coordination logic.
-  Incorrect options:
-----------------------------------------------------------------------------------------------------------------------
5. Q5:You are working for a technology startup building web and mobile applications. **You would like to pull Docker images from the ECR repository called demo so you can start running local tests against the latest application version.**

-  Which of the following commands must you run to pull existing Docker images from ECR? (**Select two**)

-  Answer:
    -  ```$(aws ecr get-login --no-include-email)```
    -  ```docker pull 1234567890.dkr.ecr.eu-west-1.amazonaws.com/demo:latest```
The get-login command retrieves a token that is valid for a specified registry for 12 hours, and then it prints a docker login command with that authorization token. You can execute the printed command to log in to your registry with Docker, or just run it automatically using the $() command wrapper. After you have logged in to an Amazon ECR registry with this command, you can use the Docker CLI to push and pull images from that registry until the token expires. The docker pull command is used to pull an image from the ECR registry.

-  Incorrect options:
    -  ```docker login -u $AWS_ACCESS_KEY_ID -p $AWS_SECRET_ACCESS_KEY``` - You cannot login to AWS ECR this way. AWS_ACCESS_KEY_ID and AWS_SECRET_ACCESS_KEY are only used by the CLI and not by docker.
    - ```aws docker push 1234567890.dkr.ecr.eu-west-1.amazonaws.com/demo:latest`` - docker push here is the wrong answer, you need to use docker pull.
    - ```docker build -t 1234567890.dkr.ecr.eu-west-1.amazonaws.com/demo:latest``` - This is a docker command that is used to build Docker images from a Dockerfile.
-----------------------------------------------------------------------------------------------------------------------
6. Question 6: Correct
- A Developer is configuring Amazon EC2 Auto Scaling group to scale dynamically.

- Which metric below is **NOT** part of Target Tracking Scaling Policy?

- Answer: 
    - ``ApproximateNumberOfMessagesVisible`` -This is a CloudWatch Amazon SQS queue metric. The number of messages in a queue might not change proportionally to the size of the Auto Scaling group that processes messages from the queue. Hence, this metric does not work for target tracking.
- Choose metrics:
    - In a target tracking scaling policy, you can use predefined or custom metrics.

    - The following predefined metrics are available:
        - ```ASGAverageCPUUtilization```—Average CPU utilization of the Auto Scaling group.
        - ```ASGAverageNetworkIn```—Average number of bytes received by a single instance on all network interfaces.
        - ``ASGAverageNetworkOut``—Average number of bytes sent out from a single instance on all network interfaces.
        - ``ALBRequestCountPerTarget``—Average Application Load Balancer request count per target.
-----------------------------------------------------------------------------------------------------------------------

7. Question7
- You are a developer working at a cloud company that embraces serverless. You have performed your initial deployment and would like to work towards adding API Gateway stages and associate them with existing deployments. Your stages will include prod, test, and dev and will need to match a Lambda function variant that can be updated over time.

- Which of the following features must you add to achieve this? (select two)

    - **Stage Variables**
    - Lambda Versions -> Versions are **immutable and cannot be updated over time**. So this option is not correct.
    - **Lambda Aliases**
    - Lambda X-Ray integration -> This is good for **tracing and debugging requests**
    - Mapping Templates -> Mapping templates can be used to modify request / responses, change output....

-----------------------------------------------------------------------------------------------------------------------
8. Q8
- A video encoding application running on an EC2 instance takes about 20 seconds on average to process each raw footage file. The application picks the new job messages from an SQS queue. The development team needs to account for the use-case when the **video encoding process takes longer than usual so that the same raw footage is not processed by multiple consumers**.

- As a Developer Associate, which of the following solutions would you recommend to address this use-case?


    - **Use ChangeMessageVisibility action to extend a message's visibility timeout** -> To prevent other consumers from processing the message again. Default 30 second, minimum is 0, maximum is 12h
    - **Use DelaySeconds action to delay a message's visibility timeout** -> consumers don’t see it immediately
    - Use WaitTimeSeconds action to short poll and extend a message's visibility timeout
    - Use WaitTimeSeconds action to long poll and extend a message's visibility timeout

- Must know API:
    - **CreateQueue (MessageRetentionPeriod), DeleteQueue**
    - **PurgeQueue**: delete all the messages in queue
    - **SendMessage (DelaySeconds), ReceiveMessage, DeleteMessage**
    - **MaxNumberOfMessages**: default 1, max 10 (for ReceiveMessage API)
    - **ReceiveMessageWaitTimeSeconds**: Long Polling to reduce API call 
    - **ChangeMessageVisibility**: change the message timeout


-----------------------------------------------------------------------------------------------------------------------
9. Q9
- Your team-mate has configured an Amazon S3 event notification for an S3 bucket that holds sensitive audit data of a firm. As the Team Lead, you are receiving the SNS notifications for every event in this bucket. After validating the event data, you realized that few events are missing.

- What could be the reason for this behavior and how to avoid this in the future?

- Correct option:

    - **If two writes are made to a single non-versioned object at the same time, it is possible that only a single event notification will be sent** - Amazon S3 event notifications are designed to be delivered at least once. Typically, event notifications are delivered in seconds but can sometimes take a minute or longer.

    - **If two writes are made to a single non-versioned object at the same time, it is possible that only a single event notification will be sent.** If you want to ensure that an event notification is sent for every successful write, you can enable versioning on your bucket. With versioning, every successful write will create a new version of your object and will also send event notification.

- Incorrect options:

    - **Someone could have created a new notification configuration and that has overridden your existing configuration** - It is possible that the configuration can be overridden. But, in the current scenario, the team lead is receiving notifications for most of the events, which nullifies the claim that the configuration is overridden.

    - **Versioning is enabled on the S3 bucket and event notifications are getting fired for only one version** - This is an incorrect statement. If you want to ensure that an event notification is sent for every successful write, you should enable versioning on your bucket. With versioning, every successful write will create a new version of your object and will also send event notification.

    - **Your notification action is writing to the same bucket that triggers the notification** - If your notification ends up writing to the bucket that triggers the notification, **this could cause an execution loop**. But it will not result in missing events.
-----------------------------------------------------------------------------------------------------------------------
10. Q10
- A multi-national company maintains separate AWS accounts for different verticals in their organization. The project manager of a team wants to migrate the Elastic Beanstalk environment from Team A's AWS account into Team B's AWS account. As a Developer, you have been roped in to help him in this process.

- Which of the following will you suggest?
Explanation
- Correct option:

    - **Create a saved configuration in Team A's account and download it to your local machine. Make the account-specific parameter changes and upload to the S3 bucket in Team B's account. From Elastic Beanstalk console, create an application from 'Saved Configurations** - You must use saved configurations to migrate an Elastic Beanstalk environment between AWS accounts. You can save your environment's configuration as an object in Amazon Simple Storage Service (Amazon S3) that can be applied to other environments during environment creation, or applied to a running environment. Saved configurations are YAML formatted templates that define an environment's platform version, tier, configuration option settings, and tags.

        - Download the saved configuration to your local machine. Change your account-specific parameters in the downloaded configuration file, and then save the changes. For example, change the key pair name, subnet ID, or application name (such as application-b-name). Upload the saved configuration from your local machine to an S3 bucket in Team B's account. From this account, create a new Beanstalk application by choosing 'Saved Configurations' from the navigation panel.

- Incorrect options:

    - **Create a saved configuration in Team A's account and configure it to Export. Now, log into Team B's account and choose the Import option. Here, you need to specify the name of the saved configuration and allow the system to create the new application. This takes a little time based on the Regions the two accounts belong to** - There is no direct Export and Import option for migrating Elastic Beanstalk configurations.

    - **It is not possible to migrate Elastic Beanstalk environment from one AWS account to the other** - This is an incorrect statement.

    - **Create an export configuration from the Elastic Beanstalk console from Team A's account. This configuration has to be shared with the IAM Role of Team B's account. The import option of the Team B's account will show the saved configuration, that can be used to create a new Beanstalk application** - This contradicts the explanation provided earlier.

-----------------------------------------------------------------------------------------------------------------------
11. Q11
- Your company has been hired to build a resilient mobile voting app for an upcoming music award show that expects to have 5 to 20 million viewers. The mobile voting app will be marketed heavily months in advance so you are expected to handle millions of messages in the system. You are configuring Amazon Simple Queue Service (SQS) queues for your architecture that should receive messages **from 20 KB to 200 KB**.

- Is it possible to send these messages to SQS?

    - **Yes, the max message size is 256KB** (Correct)
    - Yes, the max message size is 512KB - The max size is 256KB
    - No, the max message size is 128KB - The max size is 256KB
    - No, the max message size is 64KB - The max size is 256KB

-----------------------------------------------------------------------------------------------------------------------
12. Q12
- A firm runs its technology operations on a fleet of Amazon EC2 instances. The firm needs a certain software to be available on the instances to support their daily workflows. The developer team has been told to use the user data feature of EC2 instances.

- Which of the following are true about the user data EC2 configuration? ( Select two)
    - **By default, scripts entered as user data are executed with root user privileges.**
    - **By default, user data runs only during the boot cycle when you first launch an instance.**
    - **~~By default, user data is executed every time an EC2 instance is re-started.~~**
    - **~~When an instance is running, you can update user data by using root user credentials.~~**
    - **~~By default, scripts entered as user data do not have root user privileges for executing.~~**
-----------------------------------------------------------------------------------------------------------------------
13. Q13
- Your team has just signed **up an year-long contract** with a client maintaining a three-tier web application, that needs to be moved to **AWS Cloud**. **The application has steady traffic throughout the day and needs to be on a reliable system with no down-time or access issues.** The solution needs to be cost-optimal for this startup.

- Which of the following options should you choose?
    - ~~ Amazon EC2 Spot Instances~~ -> Cheap but can lose sometime
    - ~~Amazon EC2 On-Demand Instances~~ -> Same but more cost
    - ~~On-premise EC2 instance~~ -> maintan the physical, not moving on the cloud
    - **Amazon EC2 Reserved Instances**