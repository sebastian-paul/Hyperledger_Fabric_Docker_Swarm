## Hyperledger Fabric Balance Transfer using docker Swarm (2 machines)


### Example details of PC1 and PC2

* PC1
```
hostname: host1
IP: 192.168.0.50
```

* PC2
```
hostname: host2
IP: 192.168.0.60
```


modify ./artifacts/network-config.yaml file with corresponding IP adsress of PC1 and PC2

modify ./org1/ca.yaml , ./org1/orderer.yaml, ./org1/peer0.yaml /org1/peer1.yaml with hostname of PC1

modify ./org2/ca.yaml , ./org2/peer0.yaml , ./org2/peer1.yaml with hostname of PC2


* Terminal PC1
```
docker swarm init
```

```
docker swarm join-token manager
```
[copy and paste token in PC2 Terminal]


* Terminal PC2
[copy and paste token in PC2 Terminal]


* Terminal PC1
```
./createNetwork.sh
```

```
cd org1
```

```
./deploy.sh
```

* Terminal PC2
```
cd org2
```

```
./deploy.sh
```

* Terminal PC1
```
npm install
```
```
node app
```