Install Jenkins on Ubuntu 22.0.4 using Docker Compose | Setup Jenkins on AWS EC2 Ubuntu instance | How to setup Jenkins in Ubuntu EC2 instance using Docker?
Please follow the steps to install Jenkins using Docker compose on Ubuntu 22.0.4 instance. 

What is Docker Compose?
Compose is a tool for defining and running multi-container Docker applications. With Compose, you use a YAML file to configure your application’s services. Then, with a single command, you create and start all the services from your configuration.
 
The purpose of docker-compose is to function as docker cli but to issue multiple commands much more quickly. To make use of docker-compose, you need to encode the commands you were running before into a docker-compose.yml file
 
Run docker-compose up and Compose starts and runs your entire app.

# Change Host Name to Jenkins
 sudo hostname Jenkins

# Perform update first
sudo apt update

Now lets start Docker. compose installation first:

# Install Docker-Compose
sudo apt-get install docker-compose -y

# add current user to docker group
sudo usermod -aG docker $USER

# Create directory
mkdir ~/jenkins

Jenkins Setup
# Now execute the compose file using Docker compose command:
sudo docker-compose up -d 




# Make sure Jenkins is up and running
sudo docker-compose logs --follow
You can also get the admin password



How to get Jenkins admin password in another way?
# Identify Docker container name

sudo docker ps



# Get admin password by executing below command
sudo docker exec -it jenkins cat /var/jenkins_home/secrets/initialAdminPassword



Access Jenkins in web browser

Now Go to AWS console. Click on EC2, click on running instances link. Select the checkbox of EC2 you installed Jenkins. Click on Action. Copy the value from step 4 that says --> Connect to your instance using its Public DNS:


# Now go to browser. enter public dns name or public IP address with port no 8080.
http://EC2_public_dns_name:8080

Unlock Jenkins
You may get screen, enter the below command in Git bash( Ubuntu console)


Copy the password and paste in the browser.
Then click on install suggested plug-ins. 

Also create user name and password.
enter everything as admin. at least user name as admin password as admin

Click on Save and Finish. Click on start using Jenkins. Now you should see a screen like below:




That's it we have setup Jenkins successfully using Docker compose. 