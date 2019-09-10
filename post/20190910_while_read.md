# (20190519)깃 허브 블로그 만들기

패치 시스템을 구현하면서 ssh로 접근해 스크립트 실행하는것을 구성하고 있었다.  
shell 스크립트를 공부해야겠다

file_path="server_list"

while read line; do  
    echo $line  
done < $file_path  

server리스트를 파일에 두고 출력하려했는다  
파일에는 server가 한개 밖에 없었는데 출력이 되질 않았다  

read를 할때는 (CR)캐리지 리턴을 필요로 한다 
서버가 1개의 줄이 있고 파일의 CR이 없다면 없는것으로 판단된다.

서버 1개 + CR 즉 enter를 하나 입력해 줘야 한다
CR이 보기 싫어서 항상 줄의 마지막에 붙이는 습관이 있었는데 삽질삽질