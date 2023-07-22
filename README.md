# ADGUARDHOME - Network-wide DNS sinkhole
*A user guide to setup adguardhome as network-wide DNS server for dummies...*

## **What is a DNS sinkhole?**
![Security guard](https://media.tenor.com/Q3U3NP4AJ54AAAAC/ziekenhuisbal-steward.gif)


## Create a macvlan network

```sh
sudo docker network create --driver macvlan \
--subnet <your-subnet>/<your-subnet-prefixlength> \
--gateway <default-gateway-of-your-network> \
-o parent=<your-physical-network-interface you want to bind with> \
<name-for-your-network>
```