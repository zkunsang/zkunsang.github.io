Data types

Strings(set)

Lists(lpush)
ltrim - 최대 개수 보다 많은것은 삭제

Sets(sadd)
sadd
srem - remove one or more members from a set
scard - get the number of memebers in a set
smembers - get all the members in a set

sinter
sunion

sinter

Sorted sets(zadd)
key value 가중치 
zremrangeByRank 가장 마지막에 되있는것을 삭제 하기 위해서 음수 표기법 0 번째를 삭제하는게 아니라 -6번째를 삭제하는 방법도 생각해 보자
zrevrange

Hashes
key field value