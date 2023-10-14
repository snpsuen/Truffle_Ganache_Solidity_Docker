## Docker for blockchain dapp development (Truffle/Ganache/Solidity)

A docker imgage is baked to spin up a container that comes with an adequate Web3 ecosystem allowing you to follow through an excellent hands-on tutorial on Solidity smart contracts for Ethereum blockchains right away. Again, thanks to the author, Gregory McCubbin, for the great contributions, https://www.dappuniversity.com/articles/how-to-build-a-blockchain-app.

### 1 Intermediate staging container
Download the Dockerfile to the current directory, build the image and run the staging container.
```
sudo docker build -t snpsuen/web3-truffle-ganache:v022 .
sudo docker run --name web3con -p 8545:8545 -p 3000:3000 -d snpsuen/web3-truffle-ganache:v022
```

### 2 Final docker image
Enter the staging container and apply changes.
```
sudo docker exec -it web3con bash
```

1. Modify truffle-config.js to indicate that the local Ganache blockchain is running on 0.0.0.0:8545.
```
sed -i '/host:/ s/127.0.0.1/0.0.0.0/ ; /port:/ s/7545/8545/'/web3/marketplace/truffle-config.js
```
2. Set NODE_OPTIONS=--openssl-legacy-provider to avoid the digital envelope error when starting a React frontend app with npm run start.
```
export NODE_OPTIONS=--openssl-legacy-provider
```
3. Commit the changes to finalise the target image.
```
docker commit <web3con id> snpsuen/web3-truffle-ganache:v022
```

### 3 Dapp project ready container
There you have it, a well-stocked docker image that gives rise to a container ready for you to develope Solity smart contracts on Ethereum blockchains for the featured Marketplace [tutorial] (https://www.dappuniversity.com/articles/how-to-build-a-blockchain-app).
```
sudo docker run --name web3con -p 8545:8545 -p 3000:3000 -d snpsuen/web3-truffle-ganache:v022
```
Now that the project has been fully set up, without further do you may parachute straight into the thick of Part One of the tutorial








