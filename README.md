# JenkinsInstallation
This folder will explain how to install jenkins
Jenkins_installation
Installation Guide for Jenkins on Redhat Linux 8 (AWS EC2)
Jenkins is a self-contained, open source automation server which can be used to automate all sorts of tasks related to building, testing, and delivering or deploying software.
Features :-

Can be installed through native system packages, Docker, or even run standalone by any machine with a Java Runtime Environment (JRE) installed.
Highly extensible product whose functionality can be extended through the installation of plugins.
Used to automate the non-human part of the software development process, with continuous integration and facilitating technical aspects of continuous delivery.
Supports version control tools, including AccuRev, CVS, Subversion, Git, Mercurial, Perforce, TD/OMS, ClearCase and RTC, and can execute Apache Ant, Apache Maven and sbt based projects as well as arbitrary shell scripts and Windows batch commands
AWS security group configuration for Jenkins : -
Port	Protocol/Service
22	SSh
8080	Custom TCP
Security Group

Step 0
Login into your instance using ssh and perform an quick update.

ssh -i /path/to/key/file hostname@ip_address
sudo yum update 
Step 1
Install dependency for Jenkins installation : -

sudo yum install java
Add the Jenkins repository from the Jenkins website to the package manager first so that we can install it directly from our package manager.
sudo wget -O /etc/yum.repos.d/jenkins.repo http://pkg.jenkins-ci.org/redhat/jenkins.repo
sudo rpm --import https://jenkins-ci.org/redhat/jenkins-ci.org.key

Now update the packages and install Jenkins using the command : -
sudo yum update
sudo yum install jenkins
start and enable the jenkins service using systemctl :-

sudo systemctl enable jenkins
sudo systemctl start jenkins
Now,open your browser and hit your IP address with port 8080,(example : 35.175.231.168:8080 ),it should open a web page asking for One Time Password to unlock Jenkings.



Login to the server and read the output of this file using cat command and paste it in the window.After successful authentication it will prompt you to install plugins ,choose "Install suggested plugins" . 


After the plugin installation it will ask you to set admin user name and password ,put values of your choice and move forward. 



Next it will ask for Jenkins URL ,match it with the IP of your instance and move ahead you will see the welcome page fo Jenkins.



 
