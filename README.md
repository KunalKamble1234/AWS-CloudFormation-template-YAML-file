# CloudFormation Template for a Load Balancer and Auto Scaling Group

This CloudFormation template deploys an Application Load Balancer (ALB) and an Auto Scaling Group (ASG) in your AWS account. 

## Features

* Creates a security group that allows HTTP, SSH, and Tomcat manager access (port 8080).
* Creates a Launch Template that specifies the EC2 instance configuration.
* Installs Java 8 and 17 JDKs, a Ruby environment, Tomcat 9, and the AWS CodeDeploy agent on the instances.
* Creates a Target Group to route traffic to healthy instances.
* Creates a public-facing ALB with two Availability Zones for high availability.
* Creates an Auto Scaling Group with a desired capacity of 2 instances, a minimum of 1, and a maximum of 3.
* Outputs the DNS name of the Load Balancer for easy access.

## Requirements

* An existing AWS account with IAM permissions to create the necessary resources.
* An EC2 key pair to enable SSH access to the instances.

## Deployment

1. Create a file named `cloudformation.yaml` and paste the contents of this CloudFormation template.
2. Update the following parameters in the template with your specific values:
    * `KeyName`: The name of your existing EC2 key pair.
    * `ImageId`: The ID of the desired AMI (Amazon Machine Image).
    * `VpcId`: The ID of your VPC (Virtual Private Cloud).
    * `SubnetIds`: A comma-separated list of subnet IDs within your VPC (at least two in different Availability Zones).
    * `SecurityGroupId`: The ID of an existing security group (optional, if you want to use a pre-configured security group).

3. Deploy the CloudFormation template using the AWS CLI or the AWS Management Console.

## Additional Notes

* This template is for demonstration purposes only and may need modifications for your specific production environment.
* Make sure to review the IAM permissions required for the resources before deployment.
* Consider implementing additional security measures like access control lists (ACLs) on your resources.

## Contributing

We welcome contributions to improve this template. Please feel free to submit a pull request with your changes.
