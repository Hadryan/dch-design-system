---
title: ELK - General Info
weight: 1
---

## Elasticsearch

Elasticsearch is the central software unit that acts as a RESTful database, containing all the data. It is based on Apache Lucene.

The data entries are stored as JSON documents in different indices \(each index being a Lucene index underneath\).

## Logstash

Logstash acts as the data shipper, extracting data from a source \(e.g. log files on a storage server\) and writing it to a specified location \(most likely Elasticsearch\) after preparing/processing it in some way.

## Kibana

Kibana provides an interface through the web browser, that enables the user to search through the data contained in Elasticsearch in a user-friendly way, as well as create a number of different visualizations from the data. Kibana is the main \(and in many cases only\) interaction point for people who want to analyze the data.



