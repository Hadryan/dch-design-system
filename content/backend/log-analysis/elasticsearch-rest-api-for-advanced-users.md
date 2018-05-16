---
title: Elasticsearch REST API (for advanced users)
weight: 6
---

Elasticsearch provides a REST API to communicate with the instance. This means that we can issue cURL commands in the console, e.g. to configure settings or to receive information about the data.

This will rarely be necessary for most users, but it can be very helpful. For example, to obtain a list of all stored indices, we can use this command:

`curl -XGET '<elasticsearch-ip>:<elasticsearch-port>/_cat/indices?v'`

Kibana simplifies this by providing an IO-interface \("Dev Tools" in the sidebar on the left\) where the prefixed Elasticsearch address is omitted, leaving only the Elasticsearch API call.

Here is same call in the Kibana interface:

`GET _cat/indices?v`

---

You can find out about the different Elasticsearch APIs, including the "\_cat" API used above, in the Elasticsearch documentation: [https://www.elastic.co/guide/en/elasticsearch/reference/5.2/](https://www.elastic.co/guide/en/elasticsearch/reference/5.2/)

