# Jenkins Server Setup in Linux VM

## Step - 1 : Create Linux VM ##

1) Create Ubuntu VM using AWS EC2 (t2.medium) <br/>
2) Enable 8080 Port Number in Security Group Inbound Rules
3) Connect to VM using Putty

## Step-2 : Instal Java ##

```
sudo apt update
sudo apt install fontconfig openjdk-17-jre
java -version
```
## Step-3 : Install Jenkins ##
```
sudo mkdir -p /etc/apt/keyrings
sudo wget -O /etc/apt/keyrings/jenkins-keyring.asc https://pkg.jenkins.io/debian-stable/jenkins.io-2026.key
echo "deb [signed-by=/etc/apt/keyrings/jenkins-keyring.asc]" https://pkg.jenkins.io/debian-stable binary/ | sudo tee /etc/apt/sources.list.d/jenkins.list > /dev/null
sudo apt update
sudo apt install jenkins -y
```
## Step-4 : Start Jenkins ## 

```
sudo systemctl enable jenkins
sudo systemctl start jenkins
```
## Step-5 : Verify Jenkins ##

```
sudo systemctl status jenkins
```

## Step-6 : Open jenkins server in browser using VM public ip ##

```
http://public-ip:8080/
Note: here public-ip is your actual public ip address of your ec2 instance.
```
## Step-7 : Know jenkins admin password and Copy that ##
```
sudo cat /var/lib/jenkins/secrets/initialAdminPassword
```
## Step-8 : Create Admin Account & Install Required Plugins in Jenkins ##
