## IAM Policies
1. JSON document
2. Inheritance
3. Structure
```javascript
{
    "version":"",
    "Id":"",
    "Statement":{
        "Sid":"",
        "Effect":"",
        "Principal":{
            "...":"...",
        },
        "Action":{
            "...":"..."
        },
        "Resource":"..."
    }

}
```

## IAM Roles
1. assign permission to AWS services to access other AWS services

## IAM Security Tools:
1. IAM Credential Report(account-level)
    > a report that lists all your account's users and the status of their various credentials
2. IAM Access Advisor(user-level)

## How can Users access to AWS services
1. AWS Management Console: (protected by password + MFA)
2. AWS Command Line Interface (CLI): protected by access key
3. AWS Software Developement Kit(SDK)-for code:  protected by access key