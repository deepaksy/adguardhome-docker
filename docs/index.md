
# ADGUARDHOME - Network-wide DNS sinkhole - **\(Work in progress!\)**
*A user guide to setup adguardhome as network-wide DNS server for dummies...*
![Adguardhome](/assets/adguardhome.png)
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

## Create a ipvlan network

```sh
sudo docker network create --driver macvlan \
--subnet <your-subnet>/<your-subnet-prefixlength> \
--gateway <default-gateway-of-your-network> \
-o parent=<your-physical-network-interface you want to bind with> \
<name-for-your-network>
```

### If you choose to opt for macvlan network
If you have choosen to deploy your container to macvlan network, you need to enable promiscious mode on your network interface.
In linux, follow the below command to turn on promisicous mode on you nic(network interace card).

```bash
sudo ip link set <your-interface> promisc on
```
to permanently enable promiscious mode on your nic follow below command.

```bash
sudo ipconfig <your-interface> promisc
```
