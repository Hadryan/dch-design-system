---
title: Current Setup
weight: 2
---

The current setup processes and stores Apache HTTP logs from all LIVE, TEST, and DEV systems. It is running on a single AWS machine \("DCH ELK \(WIP\)"\).

The logs are being fed by Filebeat, which is installed individually on all servers where log files are located \(i.e. the LIVE, TEST and DEV servers\). Filebeat is a light-weight data shipper similar to Logstash, but with limited capabilities. It is designed specifically to read local log files line by line, while putting very little strain on the machine's hardware resources.

The local Filebeat instances are sending the logs to Logstash for further processing \(mainly extracting the individual data fields out of a single log line\), which afterwards sends them to Elasticsearch for storage.

## Elasticsearch Indices

All log lines are stored in weekly indices. The Apache log lines are assigned to index names that follow this pattern:

`apache_<log type>_<host type>-<year>.<week>`

---

`<log type>` is replaced by "access" or "error", depending on the type of log file.

`<host type>` is replaced by the type of server the log line originated from: "live" for LIVE \#1-4, "adminvm" for the LIVE Admin VM, "test" for TEST \#1-2, "dev" for DEV \#1-9 and "devtv" for DEV-TV.

`<year>` is replaced by the year the line was written in, compliant with the week date specification of ISO 8601.

`<week>` is replaced by the week number \(of the year\) the line was written in, compliant with the week date specification of ISO 8601.

## Index Patterns

An index pattern represents all Elasticsearch indices matching the indicated pattern and determines which logs are visible and ready to be analyzed/searched through. For example, if you wanted to look at the access logs of all LIVE servers, you would choose the `apache_access_live-*` pattern. The `*` character is a wildcard, i.e. in this case, all indices are included that start with `apache_access_live-` are included \(the only thing that follows is the date, see "Elasticsearch Indices" section above\).

If you wanted to look at the error logs of all DEV servers, you would choose the `apache_error_dev-*` pattern.



