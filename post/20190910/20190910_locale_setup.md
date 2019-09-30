https://www.fun25.co.kr/blog/linux-centos-7-change-locale/?page=6

커맨드로 하는거
localectl list-locales | grep -i ko
localectl set-locale LANG=ko_KR.utf8

수동 세팅
/etc/locale.conf