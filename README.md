## EPAM University Programs Cloud&DevOps Fundamentals Autumn 2022 AWS Cloud Basic.

#1. Review Getting Started with Amazon EC2. Log Into Your AWS Account, Launch, Configure, Connect and Terminate Your Instance. Do not use Amazon Lightsail. It is recommended to use the t2 or t3.micro instance and the CentOS operating system.

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

#2. Create a snapshot of your instance to keep as a backup.

Select your instance:
- From the EC2 dashboard, select the instance you want to create a snapshot of.

Create a snapshot:
- Right-click on the instance and select "Create Snapshot".
- In the "Create Snapshot" dialog box, enter a name and description for the snapshot.
- Click "Create Snapshot".

Verify the snapshot
- Go to the "Snapshots" section of the EC2 dashboard.
- Verify that the snapshot you just created is listed and has a status of "completed".
You can also check the size and time of the snapshot to confirm it is the correct one.

![screen2]()

#3. Create and attach a Disk_D (EBS) to your instance to add more storage space. Create and save
some file on Disk_D.

Create an EBS volume:
- In the EC2 dashboard, click on "Volumes" from the left-hand side menu.
- Click on "Create Volume".
- Configure your EBS volume, including the size, availability zone, and volume type. Make sure to select the same availability zone as your instance.
- Click "Create Volume".

Attach the EBS volume to your instance:
- Select the newly created EBS volume from the list of volumes in the EC2 dashboard.
- Click on "Actions" and select "Attach Volume".
- In the "Attach Volume" dialog box, select your instance from the instance list and enter the device name you want to use (e.g. /dev/sdf).
- Click "Attach".

Connect to your instance:
- Connect to your instance using SSH or RDP, depending on your instance operating system.
- Once connected, run the command sudo lsblk to check if the EBS volume is attached and to determine its device name.

Create a file on the EBS volume:
- Run the command sudo mkfs -t ext4 /dev/xvdf (replace /dev/xvdf with the device name of your EBS volume) to create a file system on the EBS volume.
- Run the command sudo mkdir /data to create a directory for the file(s) on the EBS volume.
- Run the command sudo mount /dev/xvdf /data to mount the EBS volume to the directory you just created.
- Create a file on the EBS volume by running the command sudo touch /data/myfile.txt (replace myfile.txt with the name of your file).
- Add some content to the file by running the command sudo echo "Hello World" > /data/myfile.txt.

Verify the file on the EBS volume:
- Run the command sudo ls /data to list the file(s) in the directory.
- Run the command sudo cat /data/myfile.txt to view the content of the file.

#4. Launch the second instance from backup.

#5. Detach Disk_D from the 1st instance and attach disk_D to the new instance.

#6. Review the 10-minute example. Explore the possibilities of creating your own domain and domain name for your site. Note, that Route 53 not free service. Alternatively you can free register the domain name *.PP.UA and use it.

#7. Launch and configure a WordPress instance with Amazon Lightsail link.

#8. Review the 10-minute Store and Retrieve a File. Repeat, creating your own repository.

#9. Review the 10-minute example Batch upload files to the cloud to Amazon S3 using the AWS CLI. Create a user AWS IAM, configure CLI AWS and upload any files to S3.

#10. Review the 10-minute example Deploy Docker Containers on Amazon Elastic Container Service (Amazon ECS). Repeat, create a cluster, and run the online demo application or better other application with custom settings.

#11. Run a Serverless "Hello, World!" with AWS Lambda.

#12. Create a static website on Amazon S3, publicly available (link1 or link2 - using a custom domain
registered with Route 53). Post on the page your own photo, the name of the educational program (EPAM Cloud&DevOps Fundamentals Autumn 2022), the list of AWS services with which the student worked within the educational program or earlier and the full list with links of completed labs (based on tutorials or qwiklabs). Provide the link to the website in your report and СV.
