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





-----------------------------------------------------------------------------------------------------------------------