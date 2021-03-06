# Installing Hyperledger Fabric and Composer

Follow these instructions to obtain the Hyperledger Composer development tools (primarily used to create Business Networks) and stand up a Hyperledger Fabric (primarily used to run/deploy your Business Networks locally). Note that the Business Networks you create can also be deployed to Hyperledger Fabric runtimes in other environments e.g. on a cloud platform.

---

## Before you begin

Make sure you have installed the required pre-requisites, following the instructions in [Installing pre-requisites](../README.md).

---

## Installing components

---

### Step 1: Install the CLI tools

There are a few useful CLI tools for Composer developers. The most important one is composer-cli, which contains all the essential operations, so we'll install that first. Next, we'll also pick up composer-rest-server. Make sure to pick up version 0.20. This will not work with older versions.

_Note:_ 
1. Maybe you should also verify with this commands: Do you use the right **node** version?
```sh
touch .bash_profile
nvm —-version
nvm use --lts
node --version
```
2. You *not* should use su or sudo for the following npm commands. 

1. Essential CLI tools:    
```sh
npm install -g composer-cli@0.20
```

2. Utility for running a **REST Server** for the **composer** on your machine to **expose** your **business** networks as RESTful APIs:
```sh  
npm install -g composer-rest-server@0.20
```

---

### Step 2: Install Playground

If you've already tried [Composer](https://composer-playground.mybluemix.net/) online, you'll have seen the browser app **"Playground"**. You can run this locally on your development machine too, giving you a UI for viewing and demonstrating your business networks.

Browser app called **"Playground"** for simple editing and testing Business Networks:
```sh
npm install -g composer-playground@0.20
```

---

### Step 4: Download the Hyperledger Fabric Docker Containers

This step gives you a local Hyperledger Fabric Docker containers. These will be used to start the Hyperledger Fabric platform to deploy the Fitcoin business network to.

Run the following command within the fabric-dev-servers directory.
```sh
 ./downloadFabric.sh
```
---

## Controlling the Blockchain environment

---

### Starting and stopping Hyperledger Fabric

From within the fabric-dev-servers directory, run the following command to start the servers.
```sh
./startFabric.sh
```

_Note:_ If this is the **first time** starting the server, you will also need to run the following command to load the [Admin card](https://hyperledger.github.io/composer/v0.16/playground/id-cards-playground) to the **network**.

```sh
./createPeerAdminCard.sh
```

From within the **fabric-dev-servers** directory, run the following command to start the servers.
```sh
./stopFabric.sh
```

**Congratulations!** You now have a working Hyperledger Fabric and Composer environment.

Next, you can [Build and deploy the Fitcoin Blockchain Network](../wolfpack-fitclub-fitcoin/README.md)