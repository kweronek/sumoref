# Sumo Reference
##	Master Data-Files
###	Nodes
myNet.nod.xml

###	Edges and Lanes
myNet.edg.xml

###	Traffic-Lights


###	Net-Files
####	Generate nets from Data-Files
netconvert --node-files=myNet.nod.xml --edge-files=sumotest.edg.xml -o myNet.net.xml 

myNet.net.xml

####	Generate grid nets
netgenerate --grid --grid.x-number=6 --grid.y-number=3 --grid.x-length=500 –grid.y-length=100 -o myNet.net.xml

##	Demand-Files
###Trips
randomtrips.py -n myNet.net.xml -e 600 -o myNet.trips.xml

###	Routes
duarouter -n myNet.net.xml --route-files myNet.trips.xml -o myNet.rou.xml --ignore-errors
(also creates myNet.rou.alt.xml)

##	sumo.cfg 
Create: myNet.sumo.cfg
![image](https://user-images.githubusercontent.com/24410452/143917536-17920724-3078-4bea-87c6-75e5587364ae.png)
