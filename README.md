![torusware logo](http://dl.torusware.com/images/torusware_isotipo_small.png "Torusware")
![speedus logo](http://dl.torusware.com/images/speedus_small.jpg "Speedus")
![mongo logo](https://raw.githubusercontent.com/docker-library/docs/master/mongo/logo.png "MongoDB")
# Speedus Plug&Run Lite for MongoDB
MongoDB is a cross-platform document-oriented database. Classified as a NoSQL database, MongoDB uses JSON-like documents with dynamic schemas (MongoDB calls the format BSON), making the integration of data in certain types of applications easier and faster. With the speedus solution for high-performance communications, you can achieve even more speed in the most popular NoSQL database system. Check us out at [our website](http://torusware.com/).

Speedus is your communications highway:

- Accelerates communications in the cloud and corporate IT systems
- Faster applications provide businesses with higher competitive advantages while reducing their IT bill
- 100% nonintrusive software solution which takes full advantage of the underlying hardware

#Supported tags and respective `Dockerfile` link
Each tag corresponds to the tag of the MongoDB base image:

- [`2.2` *(2.2/Dockerfile)*](https://github.com/torusware/speedus-mongo/tree/master/2.2 "2.2 Dockerfile")
- [`2.4` *(2.4/Dockerfile)*](https://github.com/torusware/speedus-mongo/tree/master/2.4 "2.4 Dockerfile")
- [`2.6` *(2.6/Dockerfile)*](https://github.com/torusware/speedus-mongo/tree/master/2.6 "2.6 Dockerfile")
- [`3.0`, `latest` *(3.0/Dockerfile)*](https://github.com/torusware/speedus-mongo/tree/master/3.0 "3.0 Dockerfile")

#Launching instructions
In order to run a container with our image, execute:

    sudo docker run --name speedus-mongo -d torusware/speedus-mongo

As the original MongoDB image, this image exposes port 27017, so standard container linking will make it automatically available to the linked containers.

#Network tests

Moreover, in this image we provide a built-in communication tests, [NetPIPE](http://bitspjoule.org/netpipe/ "NetPIPE"). Just execute:

    NPtcp &
    NPtcp -h localhost

For getting the baseline. To perform the test with our solution:

    speedus NPtcp &
    speedus NPtcp -h localhost

As you can see, using speedus is really easy and non-intrusive, just type `speedus` before your application:

    speedus /path/to/the/program [parameters]
    
#Contact info

If you need more information, you can check the README file inside the container or contact us at <speedus@torusware.com>

#Check our other images in the Docker Hub

- [speedus-ubuntu image](https://registry.hub.docker.com/u/torusware/speedus-ubuntu/ "Speedus Plug&Run Lite for Ubuntu")
- [speedus-centos image](https://registry.hub.docker.com/u/torusware/speedus-centos/ "Speedus Plug&Run Lite for CentOS")
- [speedus-redis image](https://registry.hub.docker.com/u/torusware/speedus-redis/ "Speedus Plug&Run Lite for Redis")

#Example Use Case

- [Optimizing communications between Docker containers](http://blog.torusware.com/2015/04/optimizing-communications-between.html "Optimizing communications between Docker containers")
