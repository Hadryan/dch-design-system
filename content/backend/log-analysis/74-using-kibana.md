---
title: Using Kibana
weight:
---

Below, will find a short overview of the Kibana web page. The official Kibana documentation provides a more detailed description of all functionality: [https://www.elastic.co/guide/en/kibana/5.2/index.html](https://www.elastic.co/guide/en/kibana/5.2/index.html)

## Connect

The Kibana instance is available at [http://172.30.1.206:8080](http://172.30.1.206:8080).

You will need VPN access to load the website.

## "Discover" Panel

This is the first panel that gets loaded. Its purpose is to be able to explore the data quickly. The log entries can be searched, filtered and ordered.

You can specify a time frame from which logs are visible in the top right corner.

An index pattern can be selected on the top left, directly below the search bar \(see [7.2 Current Setup](7.0 Log Analysis/72-current-setup.md) -&gt; "Index Patterns" section for information on how index patterns work\).

The fields that are visible for each entry in the log list can be toggled by clicking on "add" in the field list on the left.

After opening the detailed view of one of the log entries, a filter can be applied by clicking on the **+** or **-** buttons next to one of the field names. By clicking on the **+** button, only the specific log entries are shown that have the same value in their field. The **-** button creates a negative filter, so all log entries with the same value are hidden. For a list of all field names and their meaning, see [7.3 List of log fields](7.0 Log Analysis/73-list-of-log-fields.md).

Detailed instructions on how to use this panel can be found here: [https://www.elastic.co/guide/en/kibana/5.2/discover.html](https://www.elastic.co/guide/en/kibana/5.2/discover.html)

## "Visualize" Panel

On this panel, the data can be visualized in a variety of ways.

You can open an existing visualization on the right, or create a new one on the left. When creating a new visualization, you have to specify for which index pattern you want to create the visualization, i.e. for what set of data \(see [7.2 Current Setup](7.0 Log Analysis/72-current-setup.md) -&gt; "Index Patterns" section for information on how index patterns work\). A newly created visualization can be saved by clicking on "Save" on the top bar.

_Note that visualizations are stored on the remote system, so all visualizations are visible and accessible to other users._

Detailed instructions on how to use this panel can be found here: [https://www.elastic.co/guide/en/kibana/5.2/visualize.html](https://www.elastic.co/guide/en/kibana/5.2/visualize.html)

## "Dashboard" Panel

On this panel, multiple saved visualizations \(created on the "Visualize" panel\) can be put together on one screen to give an overview on certain metrics, graphs etc.

Click "Add" on the top bar to add a visualization to a dashboard. To save the finished dashboard, click "Save".

_Note that dashboards are stored on the remote system, so all dashboards are visible and accessible to other users._

Detailed instructions on how to use this panel can be found here: [https://www.elastic.co/guide/en/kibana/5.2/dashboard.html](https://www.elastic.co/guide/en/kibana/5.2/dashboard.html)

