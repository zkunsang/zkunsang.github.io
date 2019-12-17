docker 설치
curl -fsSL https://get.docker.com/ | sudo sh

sudo wget -O /usr/local/bin/docker-compose https://github.com/docker/compose/releases/download/1.23.2/docker-compose-Linux-x86_64
sudo chmod +x /usr/local/bin/docker-compose

sudo docker run -u root --rm -p 18080:8080 --name jenkins -v /home/jenkins:/var/jenkins_home -v /var/run/docker.sock:/var/run/docker.sock jenkins


curl -fsSL https://get.docker.com/ | sudo sh

docker ps -a 에서 Names값
docker diff git_v001

IMAGE와 변경된 내용들을 확인하게 된다.

docker commit git_v001 game_api:v0001
docker ps Names와 새롭게 생성할 REPOSITORY:TAG로 생성하게 된다.

docker run -i -t --name git:v001 ubuntu:git

iteraction -i
psuedo-tty -y
NAMES --name
ubuntu:git REPOSITORY:TAG