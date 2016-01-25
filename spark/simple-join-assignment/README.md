# Spark - Simple Join
We will repeat the [Join 1](https://github.com/juliaawu/coursera-hadoop-platform-and-application-framework/tree/master/map-reduce/joining-data-assignment/simple-join) exercise using spark. Instead of having 1 mapper, we will have 2 - 1 for fileA and 1 for fileB.
   - [split_fileA.py](https://github.com/juliaawu/coursera-hadoop-platform-and-application-framework/blob/master/spark/simple-join-assignment/split_fileA.py) emits (word, total-count) as the (key, value)
   - [split_fileB.py](https://github.com/juliaawu/coursera-hadoop-platform-and-application-framework/blob/master/spark/simple-join-assignment/split_fileB.py) emits (word, date day-count) as the (key, value)

We run the mappers on the files like so:

fileA_output = fileA.map(split_fileA)  
fileB_data = fileB.map(split_fileB)

Then, we run join on the two outputs:

fileB_joined_fileA = fileB_output.join(fileA_output)

to produce [fileB_joined_fileA](https://github.com/juliaawu/coursera-hadoop-platform-and-application-framework/blob/master/spark/simple-join-assignment/fileB_joined_fileA.txt).