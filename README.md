# Bitcoin Regtest with Insight API [![Docker Build Status](https://img.shields.io/docker/build/hunterlong/btcregtest-insight.svg)](https://hub.docker.com/r/hunterlong/btcregtest-insight)

Finally, a way to test your bitcoin applications using a Bitcoin Regtest network for temporary use. All you have to do is start this docker image, and connect your application to the Insight API endpoint! I've also created a [Litecoin Regtest Docker image](https://github.com/hunterlong/ltcregtest-insight) if that something you needed. 

Start in Docker: `docker run -it -p 3001:3001 hunterlong/btcregtest-insight:latest`

Get BTC Balance for address: `http://localhost:3001/api/addr/mnJQyeDFmGjNoxyxKQC6MMFdpx77rYV3Bo/balance`

I recommend reviewing the [Insight API Documentation](https://github.com/bitpay/insight-api) so you can use all the features of this image. 

## How does it work?
This Docker image will start a Bitcoin Regtest Server with the Insight API so you can fetch UTXO's balances, and everything else. This Docker image is for developers who want to test their Bitcoin applications without waiting for transactions to be confirmed on the real BTC testnet3 blockchain.

The wallets below have a couple BTC in them so you can begin testing quickly! **New blocks are mined automatically every 5 seconds!**

## Wallet Private Keys
The private keys are based on a mnemonic phrase by default. For ease of use, use these private keys while interacting with your application. 
```
            ADDRESS                |                     PRIVATE KEY

mnJQyeDFmGjNoxyxKQC6MMFdpx77rYV3Bo | cVVGgzVgcc5S3owCskoneK8R1BNGkBveiEcGDaxu8RRDvFcaQaSG
mzdF3oEx8mKrpGb5rVnTE7MhQfL8N8oSnW | cRGkipHiYFRSAgdY9NjUT7egHTuNXoKYWQea3kWVbkSJAs4VDi8r
mtdVMhiWWmegkkBhzYDrz84yfgofPNLNmb | cTc8XCQZuSt5E1LArqCxyaXhn1cQkvcBMAGQ159raPSQTuBpHWdi
mqNnZTyFxhB6EzF1iDEAp9enrT84fwd1X5 | cQ9JwsoYHC2Md41uDbczDVpsuWAeYjDDrDiGbCBZ4stZhZvLZWj8
mnk2URqujBqMEfhALMby1WZHoBRauW37Kg | cQrY4VypAuemJtHmNNJLyx1SNjY7mpfkdQEJpccpLSvan5YoMAkM
```
Mnemonic phrase: `myth like bonus scare over problem client lizard pioneer submit female collect`

## Why use this Docker Image?
You are probably working on a Bitcoin application and you might be doing automated testing on Travis-CI, Drone, etc. Using this image will allow your testing to fully test the blockchain transaction features of your application. You would use the addresses and private keys above for testing transactions in your tests. 
