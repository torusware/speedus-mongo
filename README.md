![torusware logo](http://dl.torusware.com/images/torusware_isotipo_small.png "Torusware")
![speedus logo](http://dl.torusware.com/images/speedus_small.jpg "Speedus")
![mongo logo](https://raw.githubusercontent.com/docker-library/docs/master/mongo/logo.png "MongoDB")
# Speedus Plug&Run for MongoDB
MongoDB is a cross-platform document-oriented database. Classified as a NoSQL database, MongoDB uses JSON-like documents with dynamic schemas (MongoDB calls the format BSON), making the integration of data in certain types of applications easier and faster. With the speedus solution for high-performance communications, you can achieve even more speed in the most popular NoSQL database system. Check us out at [our website](https://bit.ly/1MKxCuh).

Speedus is your communications highway:

- Accelerates communications in the cloud and corporate IT systems
- Faster applications provide businesses with higher competitive advantages while reducing their IT bill
- 100% nonintrusive software solution which takes full advantage of the underlying hardware

# Supported tags and respective `Dockerfile` link
Each tag corresponds to the tag of the MongoDB base image:

- [`2.2` *(2.2/Dockerfile)*](https://github.com/torusware/speedus-mongo/tree/master/2.2 "2.2 Dockerfile")
- [`2.4` *(2.4/Dockerfile)*](https://github.com/torusware/speedus-mongo/tree/master/2.4 "2.4 Dockerfile")
- [`2.6` *(2.6/Dockerfile)*](https://github.com/torusware/speedus-mongo/tree/master/2.6 "2.6 Dockerfile")
- [`3.0`, `latest` *(3.0/Dockerfile)*](https://github.com/torusware/speedus-mongo/tree/master/3.0 "3.0 Dockerfile")
- [`3.1` *(3.1/Dockerfile)*](https://github.com/torusware/speedus-mongo/tree/master/3.1 "3.1 Dockerfile")
- [`3.2`, `latest` *(3.2/Dockerfile)*](https://github.com/torusware/speedus-mongo/tree/master/3.2 "3.2 Dockerfile")
- [`3.3` *(3.3/Dockerfile)*](https://github.com/torusware/speedus-mongo/tree/master/3.3 "3.3 Dockerfile")

# Launching instructions
In order to run a container with our image, execute:
```bash
sudo docker run --name speedus-mongo -v /dev/shm:/dev/shm -d torusware/speedus-mongo
```
As the original MongoDB image, this image exposes port 27017, so standard container linking will make it automatically available to the linked containers.

If you want to test its performance, you can use the torusware/speedus-ycsb docker image, which contains the Yahoo! Cloud Service Benchmark.
```bash
sudo docker run --rm -ti --net=container:speedus-mongo -v /dev/shm:/dev/shm torusware/speedus-ycsb
// Indicate the YCSB to use ipv4 as the MongoDB server
# export JAVA_OPTIONS=-Djava.net.preferIPv4Stack=true
// Load the Data
# speedus ycsb load mongodb-async -s -p mongodb.url=mongodb://127.0.0.1:27017/ycsb -threads 1 -P ~/YCSB/workloads/workloadb -p recordcount=100000 > /dev/null
// Execute the workload
# speedus ycsb run mongodb-async -s -p mongodb.url=mongodb://127.0.0.1:27017/ycsb -threads 1 -P ~/YCSB/workloads/workloadb -p recordcount=100000 1> extendedResults.txt
```

# Network tests

Moreover, in this image we provide a built-in communication tests, [NetPIPE](http://bitspjoule.org/netpipe/ "NetPIPE"). Just execute:
```bash
NPtcp &
NPtcp -h localhost
```
For getting the baseline. To perform the test with our solution:
```bash
speedus NPtcp &
speedus NPtcp -h localhost
```
As you can see, using speedus is really easy and non-intrusive, just type `speedus` before your application:
```bash
speedus /path/to/the/program [parameters]
```
# Contact info

If you need more information, you can check the README file inside the container or contact us at **info@torusware.com**

# Check our other images in the Docker Hub

- [Speedus Plug&Run for Ubuntu](https://registry.hub.docker.com/u/torusware/speedus-ubuntu/)
- [Speedus Plug&Run for CentOS](https://registry.hub.docker.com/u/torusware/speedus-centos/)
- [Speedus Plug&Run for Redis](https://registry.hub.docker.com/u/torusware/speedus-redis/)
- [Speedus Plug&Run for YCSB](https://registry.hub.docker.com/u/torusware/speedus-ycsb/)

# Example Use Cases

- [Optimizing communications between Docker containers](https://bit.ly/1IZdodU)
- [Increasing performace of a MongoDB Docker container in Azure](https://bit.ly/1KGHxNW)
- [Increasing performace of a Redis Docker container in Amazon Web Services](https://bit.ly/1KsVBJW)
