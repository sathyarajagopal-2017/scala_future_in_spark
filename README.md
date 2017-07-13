# scala future's with spark

How to efficiently uses scala concurrency - future's in spark.

The objective of this project is to demo how to use scala concurrency future's with FAIR scheduler (spark.scheduler.mode) turned on in spark properties.

1) With Fair Scheduler turned on, within a single SparkContext Instance, multple jobs can run simultaneously, if the jobs are submited with seperate futures.

This increases efficency and processing time, instead of jobs being submitted in FIFO ( default) mode.

2) As a demo, if we are processing multiple dimension tables in HIVE and combine with a FACT table. In FIFO is set we would process each dimension with DataFrame's like in procedural programming and finally process the FACT table. Alternatively we could process all the dimension tables in to DataFrames simultaneously with seperate threads. 

Although blocking on a future is strongly discouraged we would block at the end of the call to ensure all the dimension tables are processed with DataFrames before joining with the FACT table.

