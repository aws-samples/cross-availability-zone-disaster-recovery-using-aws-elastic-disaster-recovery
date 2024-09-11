## Cross Availability Zone (AZ) disaster recovery using AWS Elastic Disaster Recovery (DRS)

This repository contains a sample CloudFormation template to deploy the architecture defined in the blog post 'Cross Availability Zone (AZ) disaster recovery using AWS Elastic Disaster Recovery (DRS)'. 

### Deployed Architecture
![cross-az-blog-solution-overview](https://github.com/user-attachments/assets/c39f7cda-f5d3-45eb-92be-4fa639e3e0f5)

The CloudFormation template will set up the following components:
- Three VPCs
  - 'blog-primary-vpc'
  - 'blog-staging-vpc'
  - 'blog-recovery-vpc'
- Three subnets
  - 'blog-primary-public-subnet'
  - 'blog-staging-public-subnet'
  - 'blog-recovery-public-subnet'
- Internet Gateways, VPC Peering, Route tables, VPC Endpoint, Security Groups and a DRS IAM replication agent user
- A NGINX web server instance in the ‘blog-primary-vpc’, which is the source server to be replicated as part of the blog solution

Once deployed, you can then follow the blog to set up AWS Elastic Disaster Recovery, install the replication agent and server, and perform a cross AZ failover to a recovered NGINX web application instance.

### Pre-requisites
For this walkthrough, you should have the following prerequisites: 
- An [AWS account](https://aws.amazon.com/resources/create-account/ "Create account")
- An Amazon EC2 key pair (required for authentication). For more details, see [Amazon EC2 key pairs](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-key-pairs.html "EC2 key pairs")

### Deploy the infrastructure CloudFormation Template
1.	Log in to the AWS Management Console and open the ‘CloudFormation’ service.
2.	Create the infrastructure stack using the cross-az-drs-setup.yaml template
3.	Note the ‘DRSIAMAccessKeyId’ and ‘DRSIAMSecretAccessKey’ values in the ‘Outputs’ tab for the created stack as these will be used as part of the replication agent installation.

## Security

See [CONTRIBUTING](CONTRIBUTING.md#security-issue-notifications) for more information.

## License

This library is licensed under the MIT-0 License. See the LICENSE file.

