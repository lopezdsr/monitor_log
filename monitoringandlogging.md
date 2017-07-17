---

copyright:
  years: 2015, 2017

lastupdated: "2017-07-17"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:screen: .screen}
{:pre: .pre}

# Overview
{: #monitoringandlogging}

{{site.data.keyword.Bluemix}} offers logging and monitoring capabilities across different services, such as Cloud Foundry and {{site.data.keyword.containershort}}. You can develop, run, and manage applications in any runtime without the complexity of building and maintaining the infrastructure that is typically associated with developing and launching an app. 
{:shortdesc}

## Monitoring in Bluemix
{: #monitoring}

{{site.data.keyword.Bluemix_notm}}, by default, collects and displays metrics for CPU usage, memory utilization, and network I/O for the {{site.data.keyword.containershort}}. You can use the {{site.data.keyword.monitoringlong}} service in {{site.data.keyword.Bluemix_notm}} to automatically collect and measure key metrics from your environment and applications. No special instrumentation is required to collect metrics. For example, you can use information provided by performance metrics to monitor how a service is running in the cloud, detect resource bottlenecks, and keep an eye on the service level agreement (SLA). When you analyze performance data for a service, you can detect situations that can lead to a resource bottleneck and consequently affect your service SLA to your clients. By taking early action, you can prevent situations that can impact your business negatively. 

Use the {{site.data.keyword.monitoringlong}} service to expand your collection, retention, and analysis capabilities in {{site.data.keyword.Bluemix_notm}} when working with metrics:

* Alert into action! {{site.data.keyword.monitoringlong}} offers an API that you can use to set performance thresholds, and to be notified when those thresholds are breached. Define alert rules for a single service instance or app instance, and alert rules that report on a set of instances. When an alert is triggered, get a notification through an e-mail, a PagerDuty event, a webhook notification, or any combination of the three.

* Add custom metrics. {{site.data.keyword.monitoringlong}} premium plan offers APIs that you can use to add relevant application and business metrics to your Cloud Monitoring data. You can also use them to send metric data from outside the {{site.data.keyword.IBM_notm}} Cloud into the {{site.data.keyword.monitoringlong}} service.

* Build reusable dashboards and make them interactive. {{site.data.keyword.monitoringlong}}’s hosted Grafana provides support for building custom dashboards with a large palate of visualization options.  Make your dashboards dynamic with templating by using metric queries with variables.

* Access your service through the {{site.data.keyword.Bluemix_notm}} catalog. {{site.data.keyword.monitoringlong}} is available as a service tile in the DevOps section of the {{site.data.keyword.Bluemix_notm}} catalog.  For the {{site.data.keyword.containershort}} service with single and group containers, you can access the service from the {{site.data.keyword.Bluemix_notm}} UI.

* Choose the service plan that fits your needs. You may choose the Lite service plan or the Premium service plan to match your usage needs. The Lite plan offers metric collection at once per minute, retention for 15 days, and complementary alerting. Alternatively, you can select the Premium plan to enable greater consumption, longer metrics retention, and to gain access to the service APIs, for example, to send or retrieve metrics from the {{site.data.keyword.monitoringlong}} service. {{site.data.keyword.monitoringlong}} offers metric collection at once per minute.  The Lite plan retains metrics at full resolution for 15 days. The Premium plan retains metrics at full resolution for 45 days.

The monitoring features that you get through the Lite plan are the same as the integrated monitoring capabilities offered by default in {{site.data.keyword.Bluemix_notm}}.

For more information, see [Monitoring in Bluemix](/docs/services/cloud-monitoring/monitoring_ov.html#monitoring_ov).

{{site.data.keyword.Bluemix_notm}} also offers infrastructure monitoring, that is available for every server, and easily readable reports. For more information, see [Infrastructure Monitoring & Reporting ![External link icon](../icons/launch-glyph.svg "External link icon")](https://www.ibm.com/cloud-computing/bluemix/infrastructure-monitoring){: new_window}.

## Logging in Bluemix
{: #logging}

{{site.data.keyword.Bluemix_notm}} logging capabilities are integrated in the platform and collection of data is automatically enabled for cloud resources. {{site.data.keyword.Bluemix_notm}}, by default, collects and displays logs for your apps, apps runtimes, and compute runtimes where those apps run. For more information, see [Logging](logging/logging_bmx_ov.html#logging_bmx_ov).








