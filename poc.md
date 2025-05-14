# POC for Static Code Analysis using SonarQube

## Table of Contents
- [Prerequisites](#prerequisites)
- [Install SonarQube on Ubuntu](#install-sonarqube-on-ubuntu)
- [Configure SonarQube](#configure-sonarqube)
- [Create systemd Service File](#create-systemd-service-file)
- [Start and Verify SonarQube](#start-and-verify-sonarqube)

---

## Prerequisites

Before installing SonarQube, ensure the following:

- A Java project is cloned to your machine.
- Java (OpenJDK 17) is installed.
- `unzip` is installed.
- A dedicated Linux user named `sonarqube` is created.

---

## Install SonarQube on Ubuntu
#### Create SonarQube system user
````bash
sudo adduser --system --no-create-home --group --disabled-login sonarqube
````
### Move to project directory
```bash
cd <project>
```

### Update system packages
```bash
sudo apt update
```

### Install Java 17
```bash
sudo apt install openjdk-17-jdk -y
```

### Install unzip utility
```bash
sudo apt install unzip -y
```

### Navigate to /opt directory
```bash
cd /opt
sudo mkdir sonarqube
cd sonarqube
```

### Download SonarQube 7.5
```bash
sudo wget https://binaries.sonarsource.com/Distribution/sonarqube/sonarqube-7.5.zip
```

### Unzip the archive
```bash
sudo unzip sonarqube-7.5.zip
```

### Remove the zip file
```bash
sudo rm sonarqube-7.5.zip
```

### Change ownership to sonarqube user
```bash
sudo chown -R sonarqube:sonarqube /opt/sonarqube
```

---

## Configure SonarQube

### Open `sonar.properties` file
```bash
sudo nano /opt/sonarqube/sonarqube-7.5/conf/sonar.properties
```

### Update the following properties:

```properties
sonar.jdbc.username=sonarqube
sonar.jdbc.password=some_secure_password
sonar.jdbc.url=jdbc:mysql://localhost:3306/sonarqube?useUnicode=true&characterEncoding=utf8&rewriteBatchedStatements=true&useConfigs=maxPerformance&useSSL=false

sonar.web.javaAdditionalOpts=-server
sonar.web.host=127.0.0.1
```

---

## Create systemd Service File

Create a new service file at `/etc/systemd/system/sonarqube.service`:

```ini
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
```

---

## Start and Verify SonarQube

### Reload the systemd daemon
```bash
sudo systemctl daemon-reexec
sudo systemctl daemon-reload
```

### Start the SonarQube service
```bash
sudo systemctl start sonarqube
```

### Enable SonarQube to start at boot
```bash
sudo systemctl enable sonarqube
```

### Check the service status
```bash
sudo systemctl status sonarqube
```
