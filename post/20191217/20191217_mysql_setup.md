mysql 설치시 항상 생각하자
grant
grant all privileges on *.* to 'root'@'ip-172-31-30-81.ap-northeast-2.compute.internal' identified by 'day7games';

타임존

로케일

한글 깨짐
[client]
default-character-set=utf8

[mysql]
default-character-set=utf8


[mysqld]
collation-server = utf8_unicode_ci
init-connect='SET NAMES utf8'
character-set-server = utf8