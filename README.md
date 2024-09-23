

![n3](https://github.com/user-attachments/assets/0b8d794e-23b1-49df-8df0-ea30e54f7098)

# Run Network3 Node di Docker

## Tutor dari Maouam ( Founder Maouam's Node Labs )


Masuk ke user root
```
sudo su
```
Update paket
```
apt update
```
Install docker jika blm install
```
apt install docker.io -y
```
Run docker container
```
docker run -it -p 8081:8080 -v /sys:/sys --privileged --name network3-1 ubuntu:22.04
```
Keluar dulu
```
exit
```
Start docker container 
```
docker container start network3-1
```
Masuk ke container
```
docker container exec -it network3-1 /bin/bash
```
Install network3 di dalam docker
```
apt update && apt upgrade -y && apt install wget -y && apt install net-tools -y && apt install iproute2 -y && apt install iptables -y && wget https://network3.io/ubuntu-node-v2.1.0.tar && tar -xvf ubuntu-node-v2.1.0.tar && cd ubuntu-node
```
Run network3 dan tampilkan key
```
bash manager.sh up && bash manager.sh key
```
Run network3 dan tampilkan key ( Run sekali lagi )
```
bash manager.sh up && bash manager.sh key
```
Simpan Key anda 

* Login ke dashboard (wajib menggunakan mozila firefox) 
https://account.network3.ai/login_page 

* Paste url berikut (di mozila firefox, ganti ip anda/ip vps) 
http://account.network3.ai:8080/main?o=xx.nx.xx.nx:8081 

* Klik add, masukan key anda 

* Done

Keluar dari docker network3-1
```
exit
``` 



### Running docker yg kedua dan seterusnya menggunakan vps sama ( max 5 )
- mulai tutor dari "Run docker container"
- ubah port dan nama container
contoh : \
  1 = docker run -it -p 8081:8080 -v /sys:/sys --privileged --name network3-1 ubuntu:22.04 \
  2 = docker run -it -p 8082:8080 -v /sys:/sys --privileged --name network3-2 ubuntu:22.04
- port berubah dari 8081 ke 8082
- nama berubah dari network3-1 menjadi network3-2
- ketika paste link port juga diubah
contoh : \
  1 = http://account.network3.ai:8080/main?o=xx.nx.xx.nx:8081 \
  2 = http://account.network3.ai:8080/main?o=xx.nx.xx.nx:8082 

untuk yg ketiga juga sama ubah port dari 8081 ke 8083 dan ubah nama dari network3-1 menjadi network3-3
