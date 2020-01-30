pm2 로그 로테이트를 셋업하고 있었다.
logrotate의 conf들을 예제에 맞게 세팅하고 로그로테이트를 강제로 돌리고 나면
이상하게 파일도 제대로 생성이 안되고
생성된 파일에 로그를 제대로 쌓지도 못하는 상황이 발생했다.

그래서 항상 로그를 날리기 위해서 썼던 /dev/null > /home/ec2-user/.pm2/logs/*.log를 해주면
이전 로그는 날라가고 다시 써지는 로그도 잘 써졌다.

스크립트로 짜고 나서 
sharedscripts -- 한번만 실행
plstrltate
    /home/ec2-user/.pm2/recycle_file_log.sh
endscript
를 해주었다.

스크립트 내용은 
searchdir=/home/ec2-user/.pm2/logs
for entry in $searchdir/*
do
        echo "$entry"
        cat /dev/null > $entry
done

이러한 스크립트를 돌려도 제대로 동작하지 않는다. 파일 역시 이상하게 생성되고 생성된 파일에 로그를 제대로 쌓지도 못했다.
logrotate -d 옵션으로 디버깅을 해봤는데 로그 로테이트의 기본 동작은 
1. 기존의 파일의 이름을 변경하고
2. 새로운 파일을 생성

이 과정에서 프로세스가 어디다거 써야하는지 위치를 잃어버리게 된다.

아래 사이트를 보면 위와 같은 내용의 내용이 있다.
copytruncate와 같은 옵션이 존재 하지만

이거는 기존 파일 복사후에 파일을 비우는 형태이다.

일단 파일 사이즈가 작으니 copytruncate를 사용하도록...

df


https://brunch.co.kr/@alden/27