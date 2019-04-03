# API-mon
This repo provides a simple python script to troubleshoot an API. The REST API provides an echo service from which the user can POST some text and the server will echo this text back in the response. This is used to monitor the API for uptime.

This script can then be utilized to test/verify specific addresses without changing dns entries on your host machine.


### Setup
<ul>
<li>Clone the repository by running ````git clone https://gitlab.com/csark/api-mon.git````</li>
<li>Change to the working directory to the newly cloned directory</li>
<li>Run ````pip3 install -r requirements.txt````</li>
</ul>

### Usage
See the following examples on how to use this script:

Running these commands:
````
api-mon.py -a "192.168.1.6" -m "Testing the API"
````
````
api-mon.py -a "10.107.45.45" -m "Testing the API"
````

Would yield these results:
````
Sending API call to https://192.168.1.6/vibesimple/rest/v1/echo...

Response:
Server Status Code: 200
Server returned text: Testing the API
````
````
Sending API call to https://10.107.45.45/vibesimple/rest/v1/echo...

Response:
Server Status Code: 200
Server returned text: Testing the API
````
