# Hyperledger Sawtooth Tic-Tac-Toe

Tic-Tac-Toe sawtooth hyperledger blockchain game 

## Getting Started

These instructions will help you install and play a tic-tac-toe game in your terminal.

### Prerequisites

* Operating Systems: Ubuntu Linux 16.04, or Mac OS 10.12 
* Have access to public ssh key
* Docker Engine (Latest Version)
* Docker Compose (Latest Version)

### Installing

Follow the steps below to install and run the application

**Step 1**: In Azure, set-up a Virtual Machine with Ubuntu 16.04 as the operating system.

**Step 2**: Embed your [public ssh](https://confluence.atlassian.com/bitbucketserver/creating-ssh-keys-776639788.html) key to create VM.

**Step 3**: Once the VM is created, navigate to overview tab and select connect.

**Step 4**: In your computers terminal/command line interface login to the VM by using the credentials found in the connect tab. 

**Step 5**: Inside terminal download the sawtooth-default yaml file. This file will allow to set the docker containers.

```
wget https://sawtooth.hyperledger.org/docs/core/releases/1.0/app_developers_guide/sawtooth-default.yaml
```
**Step 6**: [Install Docker](https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-on-ubuntu-16-04). NOTE: Only follow Step 1 - Installing Docker.

**Step 7**: Install Docker Compose. NOTE: This is a two part process done in the VM terminal.

Part One: 

```
curl -L https://github.com/docker/compose/releases/download/1.25.0-rc2/docker-compose-`uname -s`-`uname -m` -o /usr/local/bin/docker-compose
```
Part Two: 

```
chmod +x /usr/local/bin/docker-compose
```
**Step 8**: Access Docker Compose navigate to:

```
/usr/local/bin
```

**Step 9**: Check your Docker Compose version

```
sudo /usr/local/bin/docker-compose –v
```

**Step 10**: Inside the same folder run this command

```
sudo /usr/local/bin/docker-compose –f sawtooth-default.yaml up
```

**Now you're ready to open the container and play the game**

### Game Setup

**Step 1**: Open another terminal window and access your VM (see Step 4 above).

**Step 2**: List all the docker containers

```
sudo docker ps 
```
**Step 3**: Access the container that has the tic-tac-toe game

```
sudo docker exec –it [ContainerID number hyperledger/sawtooth-all] bash
```
Container ID Example :
```
sudo docker exec –it 493e5ecb014b bash
```

**Step 4**: Create a new game
```
xo create myGame –url rest-api:8008
```
**Step 5**: Playing the game, squares are numbered from 1-9 starting from the top left corner. To take a square write.

```
xo take [gametitle] [1-9]--url rest-api:8008
```
Example: xo take myGame5 –url rest-api:8008

**Step 6**: At any point to show the result use.

```
use xo show [gametitle] --url rest-api:8008
```
Example: xo show newGame --url rest-api:8008

**Step 7** Play until someone wins, ties or loses!

## References

* [A Step by Step Guide for Setting-up Hyperledger Sawtooth](https://medium.com/akeo-tech/setting-up-a-hyperledger-sawtooth-3a7ff7fc0fcb) - Another guide for this game.
* [How To Install and Use Docker on Ubuntu 16.04](https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-on-ubuntu-16-04) - Guide on how to install Docker
* [xo](https://sawtooth.hyperledger.org/docs/core/releases/1.0/cli/xo.html) - Game Documentation
* [Playing with the XO Transaction Family](https://sawtooth.hyperledger.org/docs/core/releases/1.1/app_developers_guide/intro_xo_transaction_family.html) - Sawtooth Documentation

## Authors

* **Research and Prototype Team**

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details

## Acknowledgments

* Stratégie, Architecture et Relations d'Affaires - Strategy, Architecture and Business Relationship (SARA - SABR)
