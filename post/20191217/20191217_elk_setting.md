-- 자바 설치
alternatives --install /usr/bin/java java /usr/local/jdk1.8.0_211/bin/java 1
alternatives --install /usr/bin/jar jar /usr/local/jdk1.8.0_211/bin/jar 2
alternatives --install /usr/bin/javac javac /usr/local/jdk1.8.0_211/bin/javac 2

-- 아파치 설치
yum install httpd


-- 로케일 변경
https://www.fun25.co.kr/blog/linux-centos-7-change-locale/?page=6



-- 아파치 셋업 log_config_modules(WebServer)
LogFormat "{ \"time\":\"%t\", \"clientip\":\"%a\",\"host\":\"%V\", \"request\":\"%U\", \"query\":\"%q\", \"method\":\"%m\", \"status\":\"%s\", \"userAgent\":\"%{User-agent}i\", \"referer\":\"%{Referer}i\ }" json_format
Customlog "logs/jsonaccess_log" json_format

추가

-- logstash 설치(WebServer)
wget https://artifacts.elastic.co/downloads/logstash/logstash-7.1.1.tar.gz

-- logstash 로그 conf(WebServer)
input{
	file{
                path=>"/var/log/apache2/jsonaccess_log"
                type=>apache
                codec=>json
                start_position => beginning
        }
}
filter{
        geoip{source=>"clientip"}
}
output{
        elasticsearch{
                hosts=>"192.168.56.102:9200"
        }
        stdout { codec => rubydebug }
}


-- 키바나, 엘라스틱 설치 ESServer
wget https://artifacts.elastic.co/downloads/elasticsearch/elasticsearch-7.1.1-linux-x86_64.tar.gz
wget https://artifacts.elastic.co/downloads/kibana/kibana-7.1.1-linux-x86_64.tar.gz


-- 엘라스틱 설치 
root유저로 설치하면안된다.
adduser elasticsearch

root로 설정했으면 chown -R elasticsearch.elasticsearch

UseConcMarkSweepGC 관련된에러는
config/jvm.options 
UseConcMarkSweepGC 를 주석처리해준다


ulmits -aH // 하드
ulmits -a  // 소프트
/etc/security/limits.conf

여러가지 오류들이 발생했는데 검색 -> 수정, 검색 -> 수정 금방금방 찾으면 나옴
bootstrap checks failed
그 중 JVM오류가 계속해서 발생했는데 JAVA_HOME이 제대로 설정되었는지 확인해야한다.
config/jvm.options 
# -XX:+UseSerialGC


the default discovery settings are unsuitable for production use