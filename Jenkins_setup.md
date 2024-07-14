# Jenkins Setup
* ALways Refer Jenkins Documentation https://www.jenkins.io/doc/book/installing/linux/#debianubuntu

* Create EC2 Refer [https://github.com/kirangundamala/Jenkins-Zero-To-Hero](https://github.com/kirangundamala/Jenkins-Zero-To-Hero?tab=readme-ov-file#installation-on-ec2-instance)
* Install Java
```
sudo apt update
sudo apt install fontconfig openjdk-17-jre
```

```
java -version
```

* Install Jenkins
```
sudo wget -O /usr/share/keyrings/jenkins-keyring.asc \
  https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key
echo "deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc]" \
  https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null
sudo apt-get update
sudo apt-get install jenkins
```
* Run the following commands individually, This will Jenkins user will be able to run docker jobs.
```
sudo su -
```
```
usermod -aG docker jenkins
```
```
usermod -aG docker ubuntu
```
```
systemctl restart docker
```
