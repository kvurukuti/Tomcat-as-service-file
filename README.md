# Tomcat-as-service-file
STEP-1
cd /opt

STEP-2
sudo wget https://downloads.apache.org/tomcat/tomcat-9/v9.0.62/bin/apache-tomcat-9.0.62.tar.gz

STEP-3
sudo tar -xvf apache-tomcat-9.0.62.tar.gz

STEP-4
sudo rm -rf apache-tomcat-9.0.62.tar.gz

STEP-5
sudo mv apache-tomcat-9.0.62 tomcat

STEP-6
cd /etc/init.d

STEP-7
sudo vi tomcat

STEP-8

#!/bin/bash
# description: Tomcat Start Stop Restart  
# processname: tomcat  
# chkconfig: 234 20 80
CATALINA_HOME=/opt/tomcat
case $1 in  
start)  
sh $CATALINA_HOME/bin/startup.sh  
;;   
stop)     
sh $CATALINA_HOME/bin/shutdown.sh  
;;   
restart)  
sh $CATALINA_HOME/bin/shutdown.sh  
sh $CATALINA_HOME/bin/startup.sh  
;;   
esac      
exit 0 


STEP-9
sudo chmod 755 tomcat

STEP-9
sudo chkconfig --add tomcat

STEP-10
sudo chkconfig --level 234 tomcat on

STEP-11
sudo chkconfig tomcat on
sudo systemctl start tomcat
sudo systemctl status tomcat

###################################################
