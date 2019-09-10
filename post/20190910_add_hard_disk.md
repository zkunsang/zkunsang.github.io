https://zero-gravity.tistory.com/297

드라이브 목록 확인
fdisk -l



fdisk /dev/디스크명
n - new
    primary
w - write

mkfs -t ext4 /dev/sdb1
mount -t ext4 /dev/sdb1 /backup