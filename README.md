How to Deploy a Website on EC2 Using Jenkins

Step 1: Create an EC2 Instance

1. Go to the AWS dashboard and click on the EC2 service.
2. Click on “Launch Instance.”
3. Select an AMI.
4. Choose an ubuntu instance type and set the Key Pair name.
5. Create the Security Group.
6. Click on “Launch Instance.”

Step 2: Configure Jenkins server
1. ssh into jenkins server
2. install java, jenkins
3. Browse IP:8080 , Setup Basic Configuration of Jenkins, Install Default Jenkins Plugs
4. go to new items --> give project name new-project --> choose free style project --> OK --> in build stage choose execute shell
5. in execute shell paste these commands
6. ```bash
sudo apt install -y git
sudo apt install -y apache2
sudo systemctl start apache2
sudo systemctl enable apache2
sudo rm -rf /var/www/html
sudo git clone <https://github.com/zakaullah075/project-jenkins> /var/www/html
```
7. Click on Save to save the job configuration.
8. Step 7: Trigger the Jenkins Job using build now
9. Access the Deployed Website
Once the job is complete, open a browser and type the EC2 instance’s IP address with the port number 8080 (e.g., http://<aws_ip_address:8080>). You should see that the website is accessible.
By following these steps, you have successfully deployed your website on an EC2 instance using Jenkins for continuous integration.
