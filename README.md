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
   34  sudo systemctl daemon-reload
   35  sudo systemctl start tomcat
   36  sudo systemctl enable tomcat
   37  cat /opt/tomcat/webapps/host-manager/META-INF/context.xml
   38  cat /opt/tomcat/webapps/manager/META-INF/context.xml
   39  cat /opt/tomcat/conf/tomcat-users.xml
   40  nano /opt/tomcat/conf/tomcat-users.xml
   41  cat  /opt/tomcat/conf/tomcat-users.xml
   42  history
root@server2:~#
