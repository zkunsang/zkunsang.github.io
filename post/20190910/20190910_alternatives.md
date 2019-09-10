https://tecadmin.net/install-java-8-on-centos-rhel-and-fedora/
https://skyoo2003.github.io/post/2017/03/17/what-is-alternatives-command

cd jdk1.8.0_201/
alternatives --install /usr/bin/java java /opt/jdk1.8.0_201/bin/java 2
alternatives --config java
alternatives --install /usr/bin/jar jar /opt/jdk1.8.0_201/bin/jar 2
alternatives --install /usr/bin/javac javac /opt/jdk1.8.0_201/bin/javac 2
alternatives --set jar /opt/jdk1.8.0_201/bin/jar
alternatives --set javac /opt/jdk1.8.0_201/bin/javac