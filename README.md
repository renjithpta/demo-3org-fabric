# DEMO-APP- FABRIC 

## Network Topology

   Three Orgs(Peer Orgs)

    - Each Org have one peer(Each Endorsing Peer)
    - Each Org have separate Certificate Authority
    - Each Peer has Current State database as couch db


## Orderer Org

    - Three Orderers
    - One Certificate Authority

## Software Prerequisites
	OS: ubuntu
	Hyperledger Fabric 2.3
	Go 1.15
	Node 1.10.x or later
	Curl
	Docker 
	Dockercompose
	POSTMAN API testing tool (optional)

Steps:

1) Clone the repo
2) Give execute rights to shell script using chmod 777 *.sh
3) Run accessRight.sh shells script
4) Run start.sh shell script
5) Run createChannel.sh
6) Run deployChaincode.sh
   
7) Go to apiserver folder and run npm i
8) Start API Server using node app.js
9) Use postman collection to test API

### API

#### Register USER

* Content Type application/json

* http://localhost:4000/users

* method POST

* Payload
{
	"username":"test",
	"orgName": "Org1"
}


#### LOGIN
* URL :http://localhost:4000/users/login
* method POST
* Content Type application/json
* Payload
	{
		"username":"test",
		"orgName": "Org1"
	}	

 Take token and use it as bearerd token in the  header request

#### Add car
* URL :http://65.2.150.8:4000/channels/mychannel/chaincodes/fabcar
* methode : post
* Content Type application/json
* Authorization : Bearer {{TOKEN replace with token from login}}
* Payload
* {
    "fcn": "CreateCar",
    "chaincodeName":"fabcar",
    "channelName": "mychannel",
   "args": ["{\"id\":\"Tesla-400\",\"make\":\"Audi\",\"addedAt\":1600134444309939,\"model\":\"R8\", \"color\":\"red\",\"owner\":\"Pavan\"}"]
}

#### Get car history by asset id
* URL :http://localhost:4000/channels/mychannel/chaincodes/fabcar?args=["Tesla-200"]&fcn=GetHistoryForAsset
* Method : GET
* Authorization : Bearer {{TOKEN replace with token from login}}

The postman collection is shared and can imported and tested


