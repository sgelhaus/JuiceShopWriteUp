## Network 

Kali 10.0.2.3

Nat Network named NatNetwork

Paravirtualized adapter type 

Debian 10.0.2.4

Nat Network named NatNetwork

Paravirtualized adapter type

## Environment

Mac OS host

VirtualBox VM

Debian 13

```
sudo apt update
sudo apt install -y docker.io

sudo systemctl enable docker
sudo systemctl start docker
```

Check docker is running

run the Juice Shop docker

Check Juice Shop process is running in Docker

```
sudo docker --version 
sudo docker run -d --name juice-shop --restart unless-stopped -p 3000:3000 bkimminich/juice-shop
sudo docker ps 
```
