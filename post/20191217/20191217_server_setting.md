sudo ln -sf /usr/share/zoneinfo/Asia/Seoul /etc/localtime

api server

node 설치
curl -sL https://rpm.nodesource.com/setup_10.x | sudo -E bash -
yum install nodejs -y

pm2 설치
sudo npm install pm2 -g

csm 

자바 설치
sudo yum install java -y

mysql 설치
https://www.lesstif.com/pages/viewpage.action?pageId=24445108
sudo rpm -ivh http://dev.mysql.com/get/mysql-community-release-el7-5.noarch.rpm
sudo yum install mysql-community-server

mysql 세팅
