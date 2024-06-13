# tomcat-deploy

 apt install openjdk-11-jre-headless
   19  java --version
   20  apt install default-jdk
   21  apt upgrade -y
   22  sudo useradd -r -m -U -d /opt/tomcat -s /bin/false tomcat
   23  wget https://downloads.apache.org/tomcat/tomcat-10/v10.1.19/bin/apache-tomcat-10.1.19.tar.gz
   24  wget https://dlcdn.apache.org/tomcat/tomcat-10/v10.1.24/bin/apache-tomcat-10.1.24.tar.gz
   25  sudo tar xzf apache-tomcat-*.tar.gz -C /opt/tomcat
   26  tar -xvzf apache-tomcat-10.1.24.tar.gz -C /opt/tomcat --strip-components=1
   27  mkdir -p /opt/tomcat
   28  tar -xvzf apache-tomcat-10.1.24.tar.gz -C /opt/tomcat --strip-components=1
   29  sudo chown -R tomcat: /opt/tomcat
   30  sudo sh -c 'chmod +x /opt/tomcat/bin/*.sh'
   31  sudo nano /opt/tomcat/webapps/manager/META-INF/context.xml
   32  sudo nano /opt/tomcat/webapps/host-manager/META-INF/context.xml
   33  sudo nano /etc/systemd/system/tomcat.service

[Unit]
Description=Tomcat webs servlet container
After=network.target

[Service]
Type=forking

User=tomcat
Group=tomcat
RestartSec=10
Restart=always
Environment="JAVA_HOME=/usr/lib/jvm/java-1.11.0-openjdk-amd64"
Environment="JAVA_OPTS=-Djava.awt.headless=true -Djava.security.egd=file:/dev/./urandom"

Environment="CATALINA_BASE=/opt/tomcat"
Environment="CATALINA_HOME=/opt/tomcat"
Environment="CATALINA_PID=/opt/tomcat/temp/tomcat.pid"
Environment="CATALINA_OPTS=-Xms512M -Xmx1024M -server -XX:+UseParallelGC"

ExecStart=/opt/tomcat/bin/startup.sh
ExecStop=/opt/tomcat/bin/shutdown.sh

[Install]
WantedBy=multi-user.target
   
   34  sudo systemctl daemon-reload
   35  sudo systemctl start tomcat
   36  sudo systemctl enable tomcat
   37  cat /opt/tomcat/webapps/host-manager/META-INF/context.xml
   38  cat /opt/tomcat/webapps/manager/META-INF/context.xml
   39  cat /opt/tomcat/conf/tomcat-users.xml
  <role rolename="admin"/>
<role rolename="admin-gui"/>
<role rolename="manager"/>
<role rolename="manager-gui"/>

<user username="abishek" password="123" roles="admin,admin-gui,manager,manager-gui"/>


   
   40  nano /opt/tomcat/conf/tomcat-users.xml
   41  cat  /opt/tomcat/conf/tomcat-users.xml
   42  history
root@server2:~#




add java-sample-project
https://tomcat.apache.org/tomcat-7.0-doc/appdev/sample/sample.war

2..

https://github.com/hammad-hub/java-hello-world-webapp.git
