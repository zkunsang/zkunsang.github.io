npm run build 하면 dist 폴더가 생성된다

https://brunch.co.kr/@springboot/188

nginx를 설치

server {
        listen 80;
        server_name xxxx.xxxx.xxx; //http를 붙이면 안된다 붙이면 journalctl -xe 와 system nginx status 에서 보면 warn이 뜨고 접속이 안된다

        location / {
                root /home/ec2-user/patch_front/dist;
                index index.html;

        }
}

해당 호스트로 들어가게 되면 403 forbidden이 뜨게 되는데
home/ec2_user 
chmod 701로 해주게 되면 접근이 가능하게 된다.