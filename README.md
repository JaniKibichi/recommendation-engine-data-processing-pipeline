# Building a Data Processing Pipeline with Scala
##### We explore several ways to compose a data processing pipeline in Scala. We look at our entree data and load it to our scala pipeline.

- Run the app to classify restaurants from data downloaded at(/home/graham/Downloads/entree):
````
sbt "runMain com.github.janikibichi.saleemscala.dataprocessing.Stats /home/graham/Downloads/entree"
````
- See the results [here.](https://asciinema.org/a/4U80cKuZarkPnnedgjNPkyzwI)
<br>
##### Branch out to explore the Extract Transform Load process:
````
$ git checkout -b extract_transform_load master
````
1. Extract<br>
Data is obtained from different data sources.

2. Transform<br>
Data is changed to a common and consistent format.

3. Load<br>
The common and consistently formatted data is put in a data store.
<br>
##### Branch out to set up MongoDB and Kafka using Docker
````
$ git checkout -b mongo_kafka_setup extract_transform_load
````
- Create a volume to hold data (optional)
````
$ mkdir ~/data
$ sudo docker run -d -p 27017:27017 -v ~/data:/data/db mongo
````
- Use the MongoDB client to connect to the container
````
$ sudo apt-get install mongodb-clients
$ mongo localhost/recommenddb
````
- Configure casbah by adding it to build.sbt
````
libraryDependencies += "org.mongodb" %% "casbah" % "3.1.1"
````
- For Kafka, we also need to run Zookeeper
````
$ wget -c http://www-us.apache.org/dist/kafka/1.1.0/kafka_2.11-1.1.0.tgz
$ tar xzf kafka_2.11-1.1.0.tgz

#First Start Zookeeper
$ bin/zookeeper-server-start.sh config/zookeeper.properties

#Start kafka server in a separate terminal
$ bin/kafka-server-start.sh config/server.properties
````
- Add the Kafka dependencies to build.sbt
````
libraryDependencies += "org.apache.kafka" %% "kafka" % "1.1.0"
````
##### Branch out to explore the Data Processing Pipeline with:
 - Akka
 - MongoDB
 - Apache Kafka
 - Apache Spark
````
$ git checkout -b final_data_processing_pipeline mongo_kafka_setup
````
 

