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
<<<<<<< HEAD
	OS: windows 10
	Git with gitbash installed
=======
	OS: ubuntu
>>>>>>> 1e1f3f36659b2d927dc82e9e861253ca0dbbbf59
	Hyperledger Fabric 2.3
	Go 1.15
	Node 1.10.x or later
	Curl
	Docker 
	Dockercompose
	POSTMAN API testing tool (optional)

Steps:

1) Clone the repo
2) Give execute rights to shell script 

3) Run accessRight.sh shells script using Gitbash
4) Run start.sh shell script using Gitbash


or For steps 3 -4 , 
   * Go to folder artifacts\channel\create-certificate-with-ca , run docker-compose up -d
   * D:\hyperledger\sample-hyperledgerfabric2.3-3org-fabcar\artifacts , run docker-compose up -d
   * Run createChannel.sh using Gitbash as ./createChannel.sh or using bash command
   * Run deployChaincode.sh using gitbash as ./deployChaincode.sh or using bash command 

Check all the server is up using docker ps.


   
7) Go to apiserver folder and run npm i ( Do it using Gitbash)
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
<<<<<<< HEAD

The postman collection is shared and can imported and tested



#### Get  history of all trasnction expect deployment of chaincodes
* URL :http://localhost:4000/alltransactions/channels/mychannel
* Method : GET
* Authorization : Bearer {{TOKEN replace with token from login}}

The postman collection is shared and can imported and tested


#### Get  detailed history of all trasnction expect deployment of chaincodes
* URL :http://localhost:4000//detiledalltransactions/channels/:channelName
* Method : GET
* Authorization : Bearer {{TOKEN replace with token from login}}

The postman collection is shared and can imported and tested


=======

The postman collection is shared and can imported and tested
>>>>>>> 1e1f3f36659b2d927dc82e9e861253ca0dbbbf59


