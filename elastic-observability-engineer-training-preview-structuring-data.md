# Elastic Observability Engineer Training Preview: structuring data

Thursday, May 21 2020

Observability in elastic search.

This is a technical presentation so for the purpose of the sumary I have only kept the concepts and overview.

## Elastick Stack

\[diagram\]

* Kibana: View the data, manage
* elastic: store data
* Ingest layer= 
* * beats ; family of software with dedicated purpose
  * logstash

## Structuring and Processing Data in elasticsearch

Modules 7 & 8 from the official course on observability.

### Datasets

Data can come from many sources and in many formats. this is why we want to first structure tihs data before storing it.

The goal is to parse and transform the unstructured data into discrete fields and make it easier to aggregate and visualiez the data.

### Where can data be structured

\[diagram\]

There are to places where the data can be strucured

* within logstack
* Within elasticsearch

### Elastic vs logstash

Logstash is a dedicated flexible ETL tool. Thus it can do further work than the basic pipeline of elasticsearch. But this ingest pipeline can be enough

.....

### What if your logs are not in a known format

### elasticsearch ingest pipelines

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

