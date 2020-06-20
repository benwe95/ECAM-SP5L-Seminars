---
description: 'Live Conference - Elastic - Thursday, May 21 2020'
---

# Elastic Observability Engineer Training Preview: structuring data

This is a technical presentation about the observability in Elasticsearch. Thus for the purpose of the summary I have only kept the concepts and overview that were presented.

## Elastic and the Elastic Stack

Elastic is a company specialized in the **exploration and analysis of data**. They offer many open source products that can be used individually or as a whole stack.

![Elastic Stack](.gitbook/assets/stack.png)

### Kibana

Kibana can be considered as the top layer of the stack. It's a user interface that allows to view and manage the data. It's a great way to present the information with dashboards containing graphs, charts, ...

### Elasticsearch

Elastic search is the core layer that stores the data. It's not a classical database \(neither relational nor NoSQL\). Instead its a **reverse index** that allows to construct a distributed search engine for fast request and analysis of the data.

### Logstash

As part of the ingest layer, logstach is a software component for data processing. It aggregates data from many sources and transform it then sends it to the storage layer.

### Beats

Beats is a family of softwares with dedicated purposes.

## Structuring and Processing Data in Elasticsearch

Modules 7 & 8 from the official course on observability.

### Datasets

Data can come from many sources and in **many formats**. This is why we want to **first structure** this data **before storing** it.

Thus the goal is to **parse** and **transform** the unstructured data into discrete fields and make it easier to aggregate and visualize the data.

In the simple example below we can see that the log message is automatically parsed to structure the information as different fields: _timestamp, loglevel, status._

So instead of storing the only the core message we get more precise information that represent a huge benefit when it comes to query and analyse the data. Our goal is to understand how we can create a nice pipeline that exctract this kind of information ifficiently.

![Data transformation example](.gitbook/assets/example.png)

### Where can data be structured?

There are to places where the data can be strucured:

* within logstach
* within elasticsearch

![](.gitbook/assets/where-2.png)

### What's the difference? Elastic vs logstash

Most of the time we can get what we want with the pipeline of Elasticsearch. This is a straight solution which can be **easier** to implement instead of adding and configuring a logstach component \(if it's not already running in the stack\). The pipeline is a good starting point that can be scaled by adding new nodes.

In the other hand Logstash is a dedicated flexible **ETL tool** _\(Extract, Transform, Load\)_. Thus it can do further work than the basic pipeline of elasticsearch which has some limitations.

### What if your logs are not in a known format

If the data is not in specific format then it's necessary to build our own pipeline by defining the rules of the different **ingest processors** that strucuture the data in a sequential way. This is the topic of the next section. 

## Elasticsearch ingest pipelines

a set of processors that can modify the documents passed through it. Each processor is dedicated to a task. This happens within the ingest node.

The pipeline can be define using the ingest API and tested with the \_simulate endpoint by providing a sample document.

How and where to use these pipelines??

1. within the Filebeart EL output
2. defin a default pipeline for an index -&gt; every documents will go through this pipeline.

### Dissect processor

#### A more complex example

\[diagram\]

Define a pattern that tells the processor how to separate the message according to its structure = dissection.

It can also be used to extract Key-Value pairs : %{field-key}=%{field-value}

### Script Processors

There are some existing processors that are already fully functional.But because its not posible to cover use case it's possible to create its own processor. This is made by using a special syntax- Painless

Two ways to run Painless script: inline \(for small task\) and stored.



## Demo

Using cloud.elastic.co and its Learning portal from the training section.

Its important to remember that is a pipeline. Each processor is executed in a queue an the result from one feeds the next one.

the key-value  processor is great but the extraction can also be done within the dissect processor.

The script is really useful example for doing math with pre-build java functions or conditional operations...

the if option is accessible with every pipeline.

Painless lab is accessible throught the cloud.

The ingest node is the one who executes the pipeline

