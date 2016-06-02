# GoogleWordsUsed_Mapreduce
For each year available of Google 1 gram data set, plot the size of the set of words used.  Year on the x-axis, number of words on y-axis.?

(Plot screenshot is also attached)

Approach:

I chose streaming-mode to run map reduce on Google 1 gram data set. I wrote Map and Reduce jobs in python. Map_ng.py and red_ng.py are the map and reduce python files.

Mapper explanation:

Mapper reads each line from HDFS file system and splits each line with Tab char(‘\t’), If it is a tweet from other user it emits [year] as key, [word] from them as value.

Mapper output &lt;year, [word&gt;

Example mapper output:

1989, apple

1990, words

1991, usa

Reducer explanation:

Reducer get word and its year from each mapper. Reducer adds each word in to a dictionary and create a dictionary where years are years and word are just used for counts. It gives year and words used in that year.

Reducer output &lt;year, count&gt;

Reducer Output from HDFS.

1948 6975779

1949 7369983

1942 5489436

1943 5068705
