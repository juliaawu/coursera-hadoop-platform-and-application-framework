# Map/Reduce

The Map/Reduce framework requires mapper and reducer functions, where the map function reads in the data and outputs (key, value) pairs. Hadoop then shuffles and groups the (key, value) pairs so that all pairs with the same key are grouped together and passed to the same reducer. The reducer then reads in the intermediary data and processes the results.

We will now apply this framework in the following examples:
  - [Wordcount](https://github.com/juliaawu/coursera-hadoop-platform-and-application-framework/tree/master/map-reduce/wordcount-assignment)
  - [Joining Data](https://github.com/juliaawu/coursera-hadoop-platform-and-application-framework/tree/master/map-reduce)
    * [Simple Join](https://github.com/juliaawu/coursera-hadoop-platform-and-application-framework/tree/master/map-reduce/joining-data-assignment/simple-join)
    * [Advanced Join](https://github.com/juliaawu/coursera-hadoop-platform-and-application-framework/tree/master/map-reduce/joining-data-assignment/advanced-join)