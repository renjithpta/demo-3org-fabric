#DEMO

Network Topology

Three Orgs(Peer Orgs)

    - Each Org have one peer(Each Endorsing Peer)
    - Each Org have separate Certificate Authority
    - Each Peer has Current State database as couch db


One Orderer Org

    - Three Orderers
    - One Certificate Authority

Software Prerequisites
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

API
Register USER
Content Type application/json
http://localhost:4000/users
method POST
Payload
{
	"username":"test",
	"orgName": "Org1"
}	
LOGIN
http://localhost:4000/users/login
method POST
Content Type application/json
Payload
{
	"username":"test",
	"orgName": "Org1"
}	

take token and use it as bearerd token header


