version: '3'
services:
  api1:
    image: "mocdorisara/storypick:6"
  api2:
    image: "mocdorisara/storypick:6"
  nginx:
    image: "nginx:test"
    links:
      - api1
      - api2
    ports:
      - "80:80"
    volumes:
      - ./nginx.conf:/etc/nginx/nginx.conf


docker_compose에서 api1, api2에 
port: 
 - 12000: 2200
이렇게 작성을 했엇는데 이렇게 하면 172.0.0.1이 아닌(루프백?)
172.0.0.2 와 같은곳에 12000번 포트가 연결되게 된다
이렇게 되면 nginx의 포트 바인딩을 했을때 해당 포트에 대한 연결이 거절된다
connection refused 111