## Docker for blockchain dapp development (Truffle/Ganache/Solidity)

A docker imgage is baked to spin up a container that comes with an adequate Web3 ecosystem that allows you to follow through an excellent hands-on tutorial on Solidity smart contracts for Ethereum blockchains right away. Again, thanks to the author, Greg McCubbin, for the great contributions, https://www.dappuniversity.com/articles/how-to-build-a-blockchain-app.

### 1 Intermediate staging container
Download the Dockerfile to the current directory, build the image and run the staging container.
```
sudo docker build -t snpsuen/web3-truffle-ganache:v022 .
sudo docker run --name web3con -p 8545:8545 -p 3000:3000 -d snpsuen/web3-truffle-ganache:v022
```

### 2 Apply the following changes to the container and save it to the target docker image.




