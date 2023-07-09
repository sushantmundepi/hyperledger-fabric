# Hyperledger-fabric
To initiate the first Hyperledger Fabric network, we will utilize the Fabric-samples repository. This repository consists of CLI tool binaries and Fabric Docker Images, which are essential for comprehending and utilizing the fundamentals of Fabric. Before commencing the project, it is necessary to install the following dependencies:

# 1.Install Docker

    sudo apt-get -y install docker-compose

# 2. Install Golang-go

    sudo apt install golang-go

# 3. Install jq

    sudo apt install jq

# 4. Install Node/java

    sudo apt install npm
    npm install node

# 5. Installing Fabric-samples Repository

    curl -sSLO https://raw.githubusercontent.com/hyperledger/fabric/main/scripts/install-fabric.sh && chmod +x install-fabric.sh
    
Then you can pull docker containers by running one of these commands:

    ./install-fabric.sh docker samples
    ./install-fabric.sh d s 

To install binaries for Fabric samples you can use the command below:

    ./install-fabric.sh binary
    
# Building First Network

1.Navigate through the Fabric-samples folder and then through the Test network folder where you can find script files using these we can run our network.

    cd fabric-samples/test-network

2.We would be running ./network.sh down command to remove any previous network containers or artifacts that still exist. 

    ./network.sh down

3.we can bring up a network using the following command. This command creates a fabric network that consists of two peer nodes and one ordering node.

    ./network.sh up
# Creating first channel :

Run the following command :

    ./network.sh createChannel

# Deploy the smart contract :
### Command syntax :

    ./network.sh deployCC -ccn <chaincode name> -ccp <chaincode path> -c <channel_name>
## Smart contract in typescript language

    ./network.sh deployCC -ccn basic -ccp ../asset-transfer-basic/chaincode-typescript/ -ccl typescript

## Smart contract in go language
    ./network.sh deployCC -ccn basic -ccp ../asset-transfer-basic/chaincode-go/ -ccl go
    
You can deploy   the smart contract or chaincode in any language like go, java, javascript just specify the language in the "-ccl" parameter. 
