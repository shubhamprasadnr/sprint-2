# POC For Static Code Analysis 

## Table of Content 

## Prerequisites 
clone java project 
java install 
install unzip

## Install Sonarqube on Ubuntu 

step1: cd project 
step2: sudo apt update 
step3: Sudo apt install openjdk-17-jdk 
step4: sudo apt install unzip 
step5: cd /opt/sonarqube
step6:sudo wget https://binaries.sonarsource.com/Distribution/sonarqube/sonarqube-7.5.zip
step7: sudo unzip sonarqube-7.5.zip
step8:sudo rm sonarqube-7.5.zip
step9: sudo chown -R sonarqube:sonarqube /opt/sonarqube

 Configuring the SonarQube Server
 step1: sudo nano sonarqube-7.5/conf/sonar.properties
 step2: sonar.jdbc.username=sonarqube
    sonar.jdbc.password=some_secure_password

step3: sonar.jdbc.url=jdbc:mysql://localhost:3306/sonarqube?useUnicode=true&characterEncoding=utf8&rewriteBatchedStatements=true&useConfigs=maxPerformance&useSSL=false
step4:sonar.web.javaAdditionalOpts=-server
    sonar.web.host=127.0.0.1

    save the file : ctrl+s+x 

    

step5:sudo nano /etc/systemd/system/sonarqube.service

[Unit]
Description=SonarQube service
After=syslog.target network.target

[Service]
Type=forking

ExecStart=/opt/sonarqube/sonarqube-7.5/bin/linux-x86-64/sonar.sh start
ExecStop=/opt/sonarqube/sonarqube-7.5/bin/linux-x86-64/sonar.sh stop

User=sonarqube
Group=sonarqube
Restart=always

[Install]
WantedBy=multi-user.target


step6:sudo service sonarqube start
atep7:sudo service sonarqube status

