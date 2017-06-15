---

copyright:
  years: 2017

lastupdated: "2017-05-25"

---


{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:screen: .screen}

# 從 Bluemix 主控台分析容器度量值
{: #analyzing_metrics_bmx_ui}

在 {{site.data.keyword.Bluemix}} 中，您可以透過 Docker 容器可用的*監視*標籤來檢視及分析度量值，而 Docker 容器部署在 {{site.data.keyword.Bluemix_notm}} 所管理雲端基礎架構中。
{:shortdesc}

「{{site.data.keyword.Bluemix_notm}} 公用」提供整合式監視功能。 

請考慮分析及資料保留的度量值可用性的下列資訊：

* 在「{{site.data.keyword.Bluemix_notm}} 公用」中，度量值預設會儲存 7 天。 
* 您每天最多可以儲存 1 GB 的資料。 
* 來自 {{site.data.keyword.Bluemix_notm}} 主控台可供分析的度量值預設會包括過去 24 小時的資料。

**提示：**使用 Grafana 來分析超過過去 24 小時之自訂期間的資料。


##  導覽至 Bluemix 中所管理 Docker 容器的度量值
{: #launch_metrics_tab_bmx_ui_containers}

若要查看 {{site.data.keyword.Bluemix_notm}} 所管理雲端基礎架構中所部署 Docker 容器的度量值，請完成下列步驟：

1. 從「應用程式」儀表板，按一下單一容器或容器群組。 
    
2. 從應用程式詳細資料頁面，按一下**監視及記載**。

3. 選取**監視**標籤。
    
    從**監視**標籤中，您可以檢視容器的度量值。
