# EPAM University Programs Cloud&DevOps Fundamentals Autumn 2022 AWS Cloud Basic.

## 1. Review Getting Started with Amazon EC2. Log Into Your AWS Account, Launch, Configure, Connect and Terminate Your Instance. Do not use Amazon Lightsail. It is recommended to use the t2 or t3.micro instance and the CentOS operating system.

Launch an EC2 Instance:
- In the AWS Management Console, click on the "EC2" service.
- Click the "Launch Instance" button.
- Select the "Amazon Linux 2 AMI" (or any other CentOS-based AMI of your choice) and the t2 or t3.micro instance type.
- Configure your instance settings, including instance details, storage, tags, and security groups. Make sure to select the correct VPC and subnet for your instance.
- Review your settings, and then click "Launch".

Connect to your Instance
- In the EC2 Dashboard, select your instance and click on "Connect".
- Follow the instructions to access your instance using the SSH client of your choice. Make sure to use the key pair you selected during instance launch to authenticate the connection.

![screen1](https://github.com/d-SAVCHUK/EPAM_DevOps_HT_AWS/blob/main/Screen1.png)

## 2. Create a snapshot of your instance to keep as a backup.

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

![screen2](https://github.com/d-SAVCHUK/EPAM_DevOps_HT_AWS/blob/main/Screen2.png)

## 3. Create and attach a Disk_D (EBS) to your instance to add more storage space. Create and save some file on Disk_D.

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

![screen3](https://github.com/d-SAVCHUK/EPAM_DevOps_HT_AWS/blob/main/Screen3.png)

Create a file on the EBS volume:
- Run the command sudo mkfs -t ext4 /dev/xvdf to create a file system on the EBS volume.
- Run the command sudo mkdir /data to create a directory for the file(s) on the EBS volume.
- Run the command sudo mount /dev/xvdf /data to mount the EBS volume to the directory you just created.
- Create a file on the EBS volume by running the command sudo touch /data/epam_test.txt 
- Add some content to the file by running the command sudo echo "EPAM DevOps Course" > /data/epam_test.txt.

Verify the file on the EBS volume:
- Run the command sudo ls /data to list the file(s) in the directory.
- Run the command sudo cat /data/epam_test.txt to view the content of the file.

![screen4](https://github.com/d-SAVCHUK/EPAM_DevOps_HT_AWS/blob/main/Screen4.png)

## 4. Launch the second instance from backup.

To launch a new instance from a backup snapshot, you can follow these steps:
- Navigate to the Amazon EC2 console at https://console.aws.amazon.com/ec2/.
- Click on "Snapshots" in the left sidebar.
- Select the snapshot you created earlier and click "Create Volume" from the "Actions" dropdown menu.
- Configure the volume settings as desired, including the availability zone and volume type. You can leave the other settings at their default values if they are appropriate for your needs.
- Click "Create Volume" to create the new volume from the snapshot.
- Navigate back to the EC2 dashboard by clicking "EC2 Dashboard" in the top left corner.
- Click "Launch Instance" to create a new instance.
- Choose the desired Amazon Machine Image (AMI) for your instance.
- Choose an instance type, such as t2.micro or t3.micro.
- In the "Add Storage" section, click "Add New Volume" and select the volume you created from the backup snapshot. This will add the volume as a new disk to the instance.
- Complete the remaining configuration options for your instance, including security groups, key pairs, and any user data scripts you may want to run.
- Click "Launch Instance" to create the new instance.

![screen5](https://github.com/d-SAVCHUK/EPAM_DevOps_HT_AWS/blob/main/Screen5.png)

## 5. Detach Disk_D from the 1st instance and attach disk_D to the new instance.

- Log in to the AWS Management Console and navigate to the EC2 dashboard.
- Click on "Instances" in the left sidebar and select the first instance from which you want to detach the Disk_D.
- In the "Description" tab of the instance view, scroll down to the "Block devices" section and locate the Disk_D volume.
- Click on the "EBS ID" link for the Disk_D volume to open the EBS volume details page.
- In the "Actions" dropdown menu, select "Detach Volume" and confirm the action.
- Once the volume has been detached, go back to the EC2 dashboard and select the new instance to which you want to attach the Disk_D.
- Follow steps 3 and 4 to locate the Disk_D volume, and then click "Attach Volume" in the "Actions" dropdown menu.
- In the "Attach EBS Volume" dialog box, select the instance ID of the new instance from the "Instance" dropdown menu.
- In the "Device" field, enter the name of the device where you want to mount the volume, such as "/dev/sdf" or "/dev/xvdf". Note that the device name must be unique for each volume attached to the instance.
- Click "Attach" to attach the Disk_D volume to the new instance.
- Once the volume has been attached, log in to the new instance and use the lsblk command to verify that the volume is available and mounted to the correct device.
- You should now be able to access the files you previously saved on the Disk_D volume.

![screen6](https://github.com/d-SAVCHUK/EPAM_DevOps_HT_AWS/blob/main/Screen7.png)

## 6. Review the 10-minute example (https://aws.amazon.com/getting-started/hands-on/get-a-domain/?nc1=h_ls). Explore the possibilities of creating your own domain and domain name for your site. Note, that Route 53 not free service. Alternatively you can free register the domain name *.PP.UA and use it.

...

## 7. Launch and configure a WordPress instance with Amazon Lightsail link (https://aws.amazon.com/getting-started/hands-on/launch-a-wordpress-website/?trk=gs_card).

- Go to the Amazon Lightsail homepage (https://lightsail.aws.amazon.com/) and click the "Create instance" button.
- Select the "WordPress" blueprint or choose "Linux/Unix" as the platform and "WordPress" as the application.
- Choose the instance location, size, and payment plan. For example, you can choose the "Monthly" payment plan and the "t3.nano" instance size.
- Choose a unique instance name and click "Create instance".
- Once the instance is created, click on the instance name to access the management console.
- In the management console, click on the "Connect using SSH" button to open a terminal window.
- In the terminal window, update the system packages by running the following command:
```bash
sudo apt-get update && sudo apt-get upgrade -y
```
- Install the WordPress package by running the following command:
```bash
sudo apt-get install -y wordpress
```
- Once the installation is complete, configure the WordPress package by running the following command:
```bash
sudo dpkg-reconfigure wordpress
```
- Follow the prompts to set the database name, database user, and database password for your WordPress installation.
- Create a virtual host configuration file for your WordPress site by running the following command:
```bash
sudo nano /etc/apache2/sites-available/wordpress.conf
```
Add the following content to the file:
```txt
<VirtualHost *:80>
  ServerAdmin webmaster@localhost
  DocumentRoot /usr/share/wordpress
  <Directory /usr/share/wordpress>
    Options FollowSymLinks
    AllowOverride All
    Require all granted
  </Directory>
  ErrorLog ${APACHE_LOG_DIR}/error.log
  CustomLog ${APACHE_LOG_DIR}/access.log combined
</VirtualHost>
```
Save the file and exit the text editor.

Enable the virtual host configuration and restart the Apache server by running the following commands:
```bash
sudo a2ensite wordpress
sudo systemctl restart apache2
```
- Finally, log in to your WordPress site by going to your instance's public IP address in a web browser. You should see the WordPress installation page where you can create an administrator account and customize your site.

My IP is: 35.180.202.38

![screen7](https://github.com/d-SAVCHUK/EPAM_DevOps_HT_AWS/blob/main/Screen8.png)

## 8. Review the 10-minute Store and Retrieve a File (https://aws.amazon.com/getting-started/hands-on/backup-files-to-amazon-s3/). Repeat, creating your own repository.

- Go to the AWS Management Console and navigate to the S3 service.
- Create a new bucket by clicking the "Create bucket" button and following the prompts. Choose a unique bucket name and the region where you want the bucket to be located.
- Once the bucket is created, click on the bucket name to access the management console.
- Click the "Upload" button and select a file to upload to the bucket. You can choose any file on your computer.
- Follow the prompts to set the file's permissions, metadata, and storage class.
- Once the file is uploaded, you can view it in the bucket's management console.

![screen8](https://github.com/d-SAVCHUK/EPAM_DevOps_HT_AWS/blob/main/Screen9.png)

## 9. Review the 10-minute example (https://aws.amazon.com/getting-started/hands-on/backup-to-s3-cli/?nc1=h_ls) Batch upload files to the cloud to Amazon S3 using the AWS CLI. Create a user AWS IAM, configure CLI AWS and upload any files to S3.

- Create an IAM user in the AWS Management Console with the necessary permissions to upload files to S3. This can be done by navigating to the IAM service, selecting "Users" in the left navigation pane, and clicking "Add user". Follow the prompts to create the user and attach the "AmazonS3FullAccess" policy to it.
- Install the AWS CLI on your local machine
```bash
curl "https://awscli.amazonaws.com/AWSCLIV2.pkg" -o "AWSCLIV2.pkg"
sudo installer -pkg AWSCLIV2.pkg -target /
```
- Configure the AWS CLI with your IAM user's access key and secret access key by running the following command and following the prompts:
```bash
aws configure
```
- Create a bucket in the S3 service by running the following command:
```bash
aws s3 mb s3://epam-bucket2
```
- Create a local directory to store the files you want to upload to S3.
- Copy the files to the local directory.
- Upload the files to S3 by running the following command:
```bash
aws s3 sync /Desktop/test_site_copy.html s3://epam-bucket2
```
- Verify that the files were uploaded to S3 by navigating to the S3 service in the AWS Management Console and selecting your bucket. You should see the files listed in the bucket's management console.

![screen9](https://github.com/d-SAVCHUK/EPAM_DevOps_HT_AWS/blob/main/Screen10.png)

## 10. Review the 10-minute example (https://aws.amazon.com/getting-started/hands-on/deploy-docker-containers/?nc1=h_ls) Deploy Docker Containers on Amazon Elastic Container Service (Amazon ECS). Repeat, create a cluster, and run the online demo application or better other application with custom settings.

- Go to the Amazon ECS console (https://console.aws.amazon.com/ecs/) and click on the "Get Started" button.
- Create a new cluster, and give it a name.
- Navigate to the "Task Definitions" section and create a new task definition. Enter a name and a container name for your task, and specify the Docker image to use. You can either use a public image from Docker Hub, or you can specify a custom image from your own repository.
- Configure the task memory, CPU, and network settings as desired, and click on "Create".
- Navigate back to the "Clusters" section and select your new cluster. Click on the "Create Service" button.
- Enter a name for your service, and select the task definition you just created. Configure your network and security settings as desired.
- Review your settings, and click on "Create Service". Your service will now be created, and you can monitor its status in the "Services" section of the ECS console.

![screen10](https://github.com/d-SAVCHUK/EPAM_DevOps_HT_AWS/blob/main/Screen12.png)
  
## 11. Run a Serverless "Hello, World!" with AWS Lambda (https://aws.amazon.com/getting-started/hands-on/run-serverless-code/?nc1=h_ls).

- Sign in to the AWS Management Console.
- Open the Lambda console.
- Choose "Create function".
- Select "Author from scratch".
- Give your function a name.
- Select a runtime for your function, for example "Python 3.8".
- Under "Permissions", select "Use an existing role" and choose "Basic Lambda@Edge permissions".
- Choose "Create function".
- In the "Function code" section, replace the existing code with the following code:
```python
def lambda_handler(event, context):
    return {
        'statusCode': 200,
        'body': 'Hello, EPAM!'
    }
```
- Choose "Deploy".
- Test the function by choosing "Test" and then "Create new test event".
- For the test event, enter a name, for example "test-event", and leave the default JSON data.
- Choose "Create".
- Choose "Test" again to run the function.
- After the function runs successfully, you should see the message "Execution result: succeeded".
  
![screen11](https://github.com/d-SAVCHUK/EPAM_DevOps_HT_AWS/blob/main/Screen13.png)

## 12. Create a static website on Amazon S3, publicly available (link1 or link2 - using a custom domain registered with Route 53). Post on the page your own photo, the name of the educational program (EPAM Cloud&DevOps Fundamentals Autumn 2022), the list of AWS services with which the student worked within the educational program or earlier and the full list with links of completed labs (based on tutorials or qwiklabs). Provide the link to the website in your report and СV.

-Website was created as continue of S3 bucket practice with adding public permission
```JSON
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "PublicReadGetObject",
            "Effect": "Allow",
            "Principal": "*",
            "Action": "s3:GetObject",
            "Resource": "arn:aws:s3:::epam-bucket2/*"
        }
    ]
}
```

Link: https://epam-bucket2.s3.eu-west-3.amazonaws.com/test_site_copy.html

![screen12](https://github.com/d-SAVCHUK/EPAM_DevOps_HT_AWS/blob/main/Screen14.png)
