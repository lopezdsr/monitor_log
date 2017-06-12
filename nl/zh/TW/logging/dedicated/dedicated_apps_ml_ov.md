---



copyright:

  years: 2016, 2017

lastupdated: "2017-04-06"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:screen: .screen}

<!-- audience blue staging only begin -->

# 專用和本端版本中的 Cloud Foundry 應用程式的監視及記載功能
{: #dedicated_apps_ml_ov}


在 {{site.data.keyword.Bluemix_dedicated_notm}} 及 {{site.data.keyword.Bluemix_local_notm}} 中，Cloud Foundry 應用程式有內建的記載功能。您可以在 {{site.data.keyword.Bluemix_notm}} 主控台上檢閱從您的應用程式收集到的資料。
{:shortdesc}

Cloud Foundry 應用程式會使用 Cloud Foundry 日誌聚集器，從應用程式之外監視並轉遞日誌。您不需要在應用程式內安裝代理程式。

## 硬體需求


| **需求** |    **1 個節點**     | **3 個節點（針對高可用性）** |
|-----------------|-------------------|-------------------|
vCPU | 19 | 57 |
記憶體 | 80 GB | 240 GB |
本端儲存空間 | 2.98 TB | 8.94 TB |
{: caption="表 1. {{site.data.keyword.Bluemix_local_notm:}} 的記載硬體需求" caption-side="top"}

## 設定

在「{{site.data.keyword.Bluemix}} 專用」和「{{site.data.keyword.Bluemix}} 本端」中，對於所有應用程式，日誌依預設為作用中。若要檢視讀取標準日誌的相關資訊，請參閱「Cloud Foundry 上執行之應用程式的記載」。此外，也可在「{{site.data.keyword.Bluemix}} 專用」和「{{site.data.keyword.Bluemix}} 本端」環境中啟用進階記載。

## 日誌保留

在「{{site.data.keyword.Bluemix}} 專用」和「{{site.data.keyword.Bluemix}} 本端」的 Cloud Foundry 應用程式中，日誌資料依預設會儲存 30 天。

## 檢視 {{site.data.keyword.Bluemix}} 專用和 {{site.data.keyword.Bluemix}} 本端中 Cloud Foundry 應用程式的日誌
{: #dedicated_apps_ml_logs_dash}

您可以檢閱正在「{{site.data.keyword.Bluemix_notm}} 專用」和「{{site.data.keyword.Bluemix_notm}} 本端」上執行之應用程式的日誌。
{:shortdesc}

若要檢視您的應用程式日誌，請遵循下列步驟。
1. 選取執行中應用程式。
2. 按一下**日誌**。在**日誌**視圖中，您可以檢視來自執行中應用程式的日誌。
4. 按一下**進階視圖**按鈕。**進階視圖**會使用 Kibana 顯示更詳細的日誌視圖。Kibana 是一種視覺化工具，其會使用日誌及時間戳記資料來建立自訂視覺化。如需使用進階視圖的相關資訊，請參閱 [Kibana User Guide ![外部鏈結圖示](../../../icons/launch-glyph.svg "外部鏈結圖示")](https://www.elastic.co/guide/en/kibana/4.1/index.html){: new_window}。

接下來，您可以自訂 Kibana 儀表板。如需相關資訊，請參閱[使用 Kibana 執行進階日誌分析](../kibana4/analyzing_logs_Kibana.html#analyzing_logs_Kibana)。

<!-- audience blue staging only end comment -->
