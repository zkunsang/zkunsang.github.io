kill $(ps aux | grep 'src/redis-server *' | grep :6 | awk '{print $2}')

https://stackoverflow.com/questions/3510673/find-and-kill-a-process-in-one-line-using-bash-and-regex