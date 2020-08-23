# teiid-gsoc-2020
This repository contains the details of my work in Google Summer of Code 2020.

During the three months long summer of 2020, I worked with Teiid team of Red Hat JBoss Middleware (JBoss Community) under [Google Summer of Code 2020](https://summerofcode.withgoogle.com/projects/#6223618771517440).

## Teiid Overview
Teiid is a data virtualization tool that enables you to connect to multiple heterogeneous data sources.
It creates a logical layer on the top of the data sources(relational and non-relational both) you wish to work on. This virtual layer consists of just the metadata and no actual data.
The basic concepts involve translators and connectors. Whenever a query is made, the translator translates the teiid specific query into a native query, executes it, and then returns the response to the client. Any interaction with a resource(a file source, database, etc.) is managed by the resource adapters also known as the connectors.

## Project Outline
My project included the following tasks:
1. Developing a connector or data source support for Hadoop Distributed File System(HDFS) that would support reading of files from HDFS.
2. Developing a connector or data source support for S3 that would support reading of files from S3.
3. Developing a translator to read Parquet Files that may be present in any of the supported sources. 

## Community Bonding Period
This was one of the most challenging part as it's always tough in the beginning. In this period,
I worked toward bringing in the support of Cassandra source from teiid-parent project to teiid-spring-boot project.
I also wrote a sample to show how to use teiid-spring-boot to integrate with Cassandra source.

## Phase 1 [Evaluation 1]
This was the time around which I got familiar with the project and began understanding it more and more each day.
The next task in hand was to write a data source support/connector for HDFS. With the help of my mentors I was able to do this real quick.
I also completed the source support for S3 during this phase. 

## Phase 2 [Evaluation 2]
Showcasing the examples on how to use HDFS and S3 data source to read files stored in them marked the beginning of this phase.
Later, I moved on to a much more challenging task of developing a translator to read Parquet files.
The details of a translator API were overwhelming for me in the beginning, but after a lot of meetings and chat with mentors I was slowly able to figure out 
what was to be done and started developing the translator. There were many intricacies in the way a parquet file is read, and in the way a translator
is to be developed. By the end of this phase, translator was able to support full pushdown of projection. 

## Phase 3 [Evaluation 3]
This is the phase where I worked upon increasing the capabilities of the translator. I implemented the directory based partitioning for parquet files
which would help save a lot of time by only reading the files that are required. The other things that were done are supporting literal comparison, partial filtering for 
partitioned columns, and complete filtering for non partitioned columns. We are currently working on making the partitioned columns selectable and would soon merge the initial implementation of parquet
translator for use in the next release.

## Post GSoC
Like one of my mentors Steve said "There's always more to do.", I'm looking forward to enhancing the parquet translator and
taking up new and challenging tasks in teiid. I'd also like to take a moment to thank my mentors [Steve](https://github.com/shawkins) and [Ramesh](https://github.com/rareddy), because it's for their continuous support
and guidance that I was able to do things that won't have been possible for me otherwise. Their only motive was to make me learn more. I look forward to     
keep on working with them and learning from them. Thank you very much! 