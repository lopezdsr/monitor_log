---

copyright:
  years: 2017

lastupdated: "2017-05-25"

---


{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:screen: .screen}

# 通过 Bluemix 控制台分析容器度量值
{: #analyzing_metrics_bmx_ui}

在 {{site.data.keyword.Bluemix}} 中，可以通过可用于在 {{site.data.keyword.Bluemix_notm}} 受管云基础架构中部署的 Docker 容器的*监视*选项卡来查看和分析日志。
{:shortdesc}

{{site.data.keyword.Bluemix_notm}} Public 提供了集成的监视功能。 

请考虑有关供分析的度量值可用性和数据保留时间的以下信息：

* 在 {{site.data.keyword.Bluemix_notm}} Public 中，缺省情况下度量值存储 7 天。 
* 每天最多可以存储 1 GB 的数据。 
* 缺省情况下，通过 {{site.data.keyword.Bluemix_notm}} 控制台可供分析的度量值包含最近 24 小时的数据。

**提示：**使用 Grafana 分析早于最近 24 小时的定制时间段内的数据。


##  导航至 Bluemix 中受管的 Docker 容器的度量值
{: #launch_metrics_tab_bmx_ui_containers}

要查看在 {{site.data.keyword.Bluemix_notm}} 受管云基础架构中部署的 Docker 容器的度量值，请完成以下步骤：

1. 在“应用程序”仪表板中，单击单个容器或容器组。 
    
2. 在“应用程序详细信息”页面中，单击**监视和日志**。

3. 选择**监视**选项卡。
    
    通过**监视**选项卡，可以查看容器的度量值。
