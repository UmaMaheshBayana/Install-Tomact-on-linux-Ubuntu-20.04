# Install-Tomact-on-linux-Ubuntu-20.04

# EC2 Instance

Take one Ec2 instance in AWS as per the requirement (existing we have “t2 Large” Ubuntu machine with 64GB storage


# Install JAVA in the machine 

```Sudo apt-get update```

```sudo apt install openjdk-8-jdk```

```cd /usr/lib/jvm/java-8-openjdk-amd64/```

```pwd``` 

copy the path

```sudo nano /etc/environment```

Past the below line in environment file

JAVA_HOME="/usr/lib/jvm/java-8-openjdk-amd64"

# To check java version : 

```java -version```
 
# Install Tomcat in the machine:
 
```sudo wget https://archive.apache.org/dist/tomcat/tomcat-8/v8.0.46/bin/apache-tomcat-8.0.46.tar.gz```

```sudo tar -xvf apache-tomcat-8.0.46.tar.gz```

```sudo mv apache-tomcat-8.0.46 tomcat```

```cd tomcat/```

```echo "export CATALINA_HOME="/home/ubuntu/tomcat8"" >> ~/.bashrc```

```cd /home/ubuntu/tomcat/bin```

# Create sanela and server directory in /opt Move tomcat to server

```mv /home/ubuntu/tomcat/  /opt/sanela/server/```

# To check the tomcat status

```ps -ef | grep tomcat```

# To start the tomcat

```cd /opt/sanela/server/tomcat/bin/```

```sudo sh startup.sh```

# To restart tomcat

```sudo kill -9 ‘tomcat id’```

# create tomcat username password

```cd  /opt/sanela/server/tomcat/conf```

```sudo nano tomcat-users.xml```

Past below lines in the file above tomcat user line

``` 
<role rolename="manager-gui"/>

<user username="tomcat" password="san3la" roles="manager-gui"/>
```

And save the file(ctl+x , y , enter)

# To change the tomcat port

```cd  /opt/sanela/server/tomcat/conf```

```sudo nano service.xml```

Change Connector port 8080 to 9090 and save the file(ctrl+x, y, enter)  
