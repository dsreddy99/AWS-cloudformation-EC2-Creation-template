This is a sample project called 'AWS-cloudformation-EC2-Creation-template'. This is to demonstrate using Cloudformation, how to create an instance with the existing VPC and Subnet.

# EC2 Creation/Updation
#### This is a sample template which creates an EC2 Instance, using existing VPC & Subnet and assign a public ip


## How to Use

#### Install AWS CLI
[Amazon link for installing AWS CLI](https://docs.aws.amazon.com/cli/latest/userguide/installing.html)

#### Configure your CLI
```
[default]
aws_access_key_id = XXXXXXXXXXXXXXXXXXXX
aws_secret_access_key = XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
region = eu-west-2
```

#### Validate your template
``` 
aws cloudformation validate-template --template-body file://./Launch_EC2_Instance_Sample_Config.yaml
```

#### Create a stack using your template
``` 
aws cloudformation create-stack --stack-name ec2-test-stack --template-body  file://./Launch_EC2_Instance_Sample_Config.yaml 
```

#### Update your stack in-case of any modification on the template
``` 
aws cloudformation update-stack --stack-name ec2-test-stack --template-body  file://./Launch_EC2_Instance_Sample_Config.yaml
```
___
## Optional way to update stack
#### You can create a change set and execute it for updating the stack from the cloudformation UI.
```
aws cloudformation create-change-set --stack-name ec2-test-stack --template-body file://./Launch_EC2_Instance_Sample_Config.yaml --change-set-name port-update --description "updating the lambda function name"
```

