## EPAM University Programs Cloud&DevOps Fundamentals Autumn 2022 AWS Cloud Basic.

1. Review Getting Started with Amazon EC2. Log Into Your AWS Account, Launch, Configure, Connect and Terminate Your Instance. Do not use Amazon Lightsail. It is recommended to use the t2 or t3.micro instance and the CentOS operating system.

Launch an EC2 Instance:
- In the AWS Management Console, click on the "EC2" service.
- Click the "Launch Instance" button.
- Select the "Amazon Linux 2 AMI" (or any other CentOS-based AMI of your choice) and the t2 or t3.micro instance type.
- Configure your instance settings, including instance details, storage, tags, and security groups. Make sure to select the correct VPC and subnet for your instance.
- Review your settings, and then click "Launch".

Connect to your Instance
- In the EC2 Dashboard, select your instance and click on "Connect".
- Follow the instructions to access your instance using the SSH client of your choice. Make sure to use the key pair you selected during instance launch to authenticate the connection.

![screen1]()

2. Create a snapshot of your instance to keep as a backup.

3. Create and attach a Disk_D (EBS) to your instance to add more storage space. Create and save
some file on Disk_D.

4. Launch the second instance from backup.

5. Detach Disk_D from the 1st instance and attach disk_D to the new instance.

6. Review the 10-minute example. Explore the possibilities of creating your own domain and domain name for your site. Note, that Route 53 not free service. Alternatively you can free register the domain name *.PP.UA and use it.

7. Launch and configure a WordPress instance with Amazon Lightsail link.

8. Review the 10-minute Store and Retrieve a File. Repeat, creating your own repository.

9. Review the 10-minute example Batch upload files to the cloud to Amazon S3 using the AWS CLI. Create a user AWS IAM, configure CLI AWS and upload any files to S3.

10. Review the 10-minute example Deploy Docker Containers on Amazon Elastic Container Service (Amazon ECS). Repeat, create a cluster, and run the online demo application or better other application with custom settings.

11. Run a Serverless "Hello, World!" with AWS Lambda.

12. Create a static website on Amazon S3, publicly available (link1 or link2 - using a custom domain
registered with Route 53). Post on the page your own photo, the name of the educational program (EPAM Cloud&DevOps Fundamentals Autumn 2022), the list of AWS services with which the student worked within the educational program or earlier and the full list with links of completed labs (based on tutorials or qwiklabs). Provide the link to the website in your report and СV.
