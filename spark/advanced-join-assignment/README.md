# Spark - Advanced Join
Using the data from the Join 2 exercise, the objective is to find out the total number of viewers across all shows for the channel BAT.
   - [split_show_views.py](https://github.com/juliaawu/coursera-hadoop-platform-and-application-framework/blob/master/spark/advanced-join-assignment/split_show_views.py) emits (show, views) as the (key, value)
   - [split_show_channel.py](https://github.com/juliaawu/coursera-hadoop-platform-and-application-framework/blob/master/spark/advanced-join-assignment/split_show_channel.py) emits (show, channel) as the (key, value)
   - [extract_channel_views.py](https://github.com/juliaawu/coursera-hadoop-platform-and-application-framework/blob/master/spark/advanced-join-assignment/extract_channel_views.py) emits (channel, views) as the (key, value)
   - [sum_channel_views.py](https://github.com/juliaawu/coursera-hadoop-platform-and-application-framework/blob/master/spark/advanced-join-assignment/sum_channel_views.py) sums all of the views for each channel

Parse show files:  
show_views_file = sc.textFile("input3/join2_gennum?.txt")  
show_views = show_views_file.map(split_show_views)

Parse channel files:  
show_channel_file = sc.textFile("input3/join2_genchan?.txt")  
show_channel = show_channel_file.map(split_show_channel)

Join the 2 datasets:  
joined_dataset = show_channel.join(show_views)

Extract channel as key:  
channel_views = joined_dataset.map(extract_channel_views)

Sum viewers across channels:  
channel_views.reduceByKey(sum_channel_views).collect()

Output: [channel_views_output.txt](https://github.com/juliaawu/coursera-hadoop-platform-and-application-framework/blob/master/spark/advanced-join-assignment/channel_views_output.txt)