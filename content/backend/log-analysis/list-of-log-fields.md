---
title: List of log fields
weight: 3
---

This is a list of all relevant fields that a log entry \(in the form of an Elasticsearch document\) can contain.

Most fields are directly extracted from the log line, but because they are stored as individual fields in the document, they can be used for visualizations, and documents can be searched and filtered based on these fields.

A field can have a number of different datatypes. These datatypes are described in the Elasticsearch documentation: [https://www.elastic.co/guide/en/elasticsearch/reference/5.2/mapping-types.html](https://www.elastic.co/guide/en/elasticsearch/reference/5.2/mapping-types.html)

## General fields

The following fields can be present in every entry:

| Field name | Datatype | Description |
| :--- | :--- | :--- |
| @timestamp | date | The time at which the log event took place. It matches the timestamp specified in the log line. If for any reason the time in the log line could not be read, it corresponds to the time at which the entry was written to Elasticsearch. |
| message | text | the complete original log line as it was written to the log file |
| tags | keyword | Arbitrary tags that were added to the entry before it was written to Elasticsearch. For example, "\_grokparsefailure" means that the log line could not be parsed correctly by Logstash. \(In that case, refer to the "message" field for the original log line\) |
| host | keyword | the host name of the server the log line originated from, e.g. "dchlive1" |
| source | keyword | the log file that the log line was written in, e.g. "/var/log/apache/www.digitalconcerthall.com.log" |

## Access log fields

| Field name | Datatype | Description |
| :--- | :--- | :--- |
| vhost | keyword | virtual host the log line belongs to, e.g. "tv", "be", "www"; not applicable for logs from dch-dev-tv |
| duration | long | duration of the request in milliseconds |
| clientip | ip | IP of the client that issued the request |
| ips | object \(contains ip's\) | \(only applicable for logs that have the "combined\_proxy\_dch" format -&gt; e.g. LIVE, TEST\) numbered IP list \("ips.0", "ips.1" etc.\) of proxy IPs, will never contain more than 5 IPs |
| ident | keyword | the RFC 1413 identity of the client determined by identd on the clients machine |
| auth | keyword | the userid of the person requesting the document as determined by HTTP authentication |
| method | keyword | request method issued by the client, e.g. "GET", "POST", "OPTIONS" |
| request | keyword | request issued by the client, e.g. "/json\_services/get\_user" |
| rawrequest | text | the raw request string, if the request did not follow standard syntax |
| httpversion | keyword | HTTP version that was transferred with the request, e.g. "1.1" |
| response | long | the HTTP response code from the server |
| bytes | long | the total amount of bytes transmitted |
| referrer | keyword | the "Referer" HTTP request header - the site that the client reports having been referred from |
| agent | keyword | the User-Agent HTTP request header - the identifying information that the client browser reports about itself |
| app | keyword | the application this request was issued for, e.g. "API 1.2", "API 2.x", "Miniscripts" |
| requestjson | object | for API 1.2 JSON-calls, the JSON-object is decoded and written into this field |
| nonssl | boolean | \(only applicable for DEV logs\) boolean that indicates if the log line belongs to non-SSL logs or not |

## Error log fields

| Field name | Datatype | Description |
| :--- | :--- | :--- |
| vhost | keyword | virtual host the log line belongs to, e.g. "tv", "be", "www" |
| module | keyword | module the error originated from |
| severity | keyword | log level of the error message, e.g. 'error', 'trace' etc. |
| pid | keyword | PID of the process producing the error |
| tid | keyword | thread ID of the thread producing the error |
| clientip | ip | IP of the client that generated the error |
| clientport | long | port of the client that generated the error |
| error | text | the actual error message contained in the log line |



