# Twitter Decahose Access for University of Michigan
At this time, it is possible to process the twitter decahose data set with Great Lakes, or the Cavium Hadoop and Spark service. You may also transfer the files using the Globus high speed file transfer service.

We understand that this may be a lot of information to assimilate, so if you wish to have a meeting to help get started, please let us know.

Instructions on each aspect are below.

### Tutorial
CSCAR's documentation on how to process the Twitter Decahose data is located here:  
https://github.com/caocscar/twitter-decahose-pyspark

### Great Lakes
To access the data on Great Lakes, you may find it located here:  
`/nfs/turbo/twitter-decahose/decahose/raw`
and
`/nfs/locker/twitter-decahose-locker`

You can check the date range availabililty of the data on Great Lakes via this [calendar chart](https://observablehq.com/@caocscar/calendar-view)

### Cavium
If you wish to use a Cavium Hadoop account, please send email to hpc-support@umich.edu asking for a cavium hadoop account.
Please note that there is no charge for usage of the Cavium Hadoop service.

The user guide for the Cavium Hadoop service is located here:  
https://arc-ts.umich.edu/cavium/user-guide/

The location in HDFS on Cavium Hadoop is here:  
`/var/twitter/decahose/raw`
and
`/data/twitter/decahose/parquet`

### Example
An example of processing the data with spark:
```python
pyspark --master yarn --num-executors 100  --executor-memory 5g    

from pyspark.sql import SQLContext
sqlC = SQLContext(sc)
twitter = sqlC.read.json("/var/twitter/decahose/raw/decahose.2018-08*")
```
### Globus Info
You will need to navigate to this location on the umich#greatlakes or umich#flux endpoint:  
`/nfs/turbo/twitter-decahose/decahose/raw` or `/nfs/locker/twitter-decahose-locker`

This is the url for the globus web portal to get started:  
https://www.globus.org/app/login

### Other Info
Extra Hadoop and Spark training slides are available here:  
https://tinyurl.com/vyyhqv3

And here:  
https://github.com/caocscar/workshops/blob/master/pyspark/pyspark.md

Information on the Great Lakes cluster is available here:  
https://arc-ts.umich.edu/greatlakes/

And the user guide is here:  
https://arc-ts.umich.edu/greatlakes/user-guide/

And the Slurm guide is here:  
https://arc-ts.umich.edu/greatlakes/slurm-user-guide/

### Contact Info
If you have any questions or issues, you can contact Seth Meyer (smeyer) or Alex Cao (caoa).
