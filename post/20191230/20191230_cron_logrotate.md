0 3 * * * /home/ec2-user/api_logrotate.sh

크론에서 쉘 스크립트 실행

/sbin/logrotate -f /home/ec2-user/api_logrotate

를 하면 찾을 수가 없다.
크론 결과는 mail을 통해서 확인할 수 있다

vi /var/spool/mail/ec2-user

logrotate

