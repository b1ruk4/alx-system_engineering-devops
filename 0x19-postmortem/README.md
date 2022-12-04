<img src=./meme.jepg width=50%>

# requests failure report
This week, it was reported that the main online store platform was returning 500 Error on all requests made on the platform routes, all the services were down.  75% of the users were affected. The root cause was the failure of our master server web-01.

## Timeline
The error was realized on Thursday Dec 1 0600 hours (East Africa Time) when our Site Reliability Engineer, Mrs boo saw the master server lagging in speed. Our engineers on call disconnected the master server web-01 for further system analysis and channelled all requests to client server web-02. They solved the problem by  Dec 3 1200 hours (East Africa Time).

## Root cause and resolution
The main online store platform is served by 2 ubuntu cloud servers. The master server web-01 was connected to serve all requests, and it stopped functioning due to power outage as a results server web-02 was disconnected temporarily for testing and was not connected to the load balancer afterwards. 


The issue was fixed when the master server was connected to the new power supply both the master and client servers wore back to accpting requests.

## Measures against such problem in future
- Choose the best power supliers
- Always keep an eye on your servers to ensure they are running properly
- Have extra back-up generators.
