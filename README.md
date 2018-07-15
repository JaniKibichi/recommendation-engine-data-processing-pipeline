# Building a Data Processing Pipeline with Scala
##### We explore several ways to compose a data processing pipeline in Scala. We look at our entree data and load it to our scala pipeline.

- Run the app to classify restaurants from data downloaded at(/home/graham/Downloads/entree):
````
sbt "runMain com.github.janikibichi.saleemscala.dataprocessing.Stats /home/graham/Downloads/entree"
````
- See the results [here.](https://asciinema.org/a/4U80cKuZarkPnnedgjNPkyzwI)
<br>
- Branch out to explore the Extract Transform Load process:
````
$ git checkout -b extract_transform_load master
````