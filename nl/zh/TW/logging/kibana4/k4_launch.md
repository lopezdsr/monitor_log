---

copyright:
  years: 2015, 2017

lastupdated: "2017-05-22"

---


{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:screen: .screen}


# 導覽至 Kibana 儀表板
{: #k4_launch}

您可以從 {{site.data.keyword.Bluemix}} 使用者介面啟動 Kibana，或直接從 Web 瀏覽器啟動 Kibana。
{:shortdesc}

從 {{site.data.keyword.Bluemix_notm}} 啟動 Kibana，以根據啟動 Kibana 所用之資源的環境定義來檢視及分析資料。例如，在 Kibana 中，您可以在特定 CF 應用程式的環境定義下，啟動至該特定應用程式的日誌。
    
如果您要查看所提供 {{site.data.keyword.Bluemix_notm}} 空間內的服務的聚集日誌資料，請從直接瀏覽器鏈結啟動 Kibana。用來過濾儀表板顯示資料的查詢，會擷取 {{site.data.keyword.Bluemix_notm}} 組織中某個空間的日誌項目。Kibana 顯示的日誌資訊，包括部署在您登入之 {{site.data.keyword.Bluemix_notm}} 組織的空間內的所有資源記錄。 

下表列出啟動 Kibana 的資源及支援的導覽方法：

<table>
<caption>表 1. 資源及支援的導覽方法清單。</caption>
  <tr>
    <th>資源</th>
    <th>從 Bluemix 儀表板導覽至 Kibana 儀表板</th>
    <th>從 Web 瀏覽器導覽至 Kibana 儀表板</th>
  <tr>
  <tr>
    <td>CF 應用程式</td>
    <td>是</td>
    <td>是</td>
  <tr>  
  <tr>
    <td>Kubernetes 叢集中所部署的容器</td>
    <td>否</td>
    <td>是</td>
  <tr>  
  <tr>
    <td>{{site.data.keyword.Bluemix_notm}} 所管理雲端基礎架構中所部署的容器</td>
    <td>是</td>
    <td>是</td>
  <tr>  
</table>

如需 Kibana 的相關資訊，請參閱 [Kibana User Guide ![外部鏈結圖示](../../../icons/launch-glyph.svg "外部鏈結圖示")](https://www.elastic.co/guide/en/kibana/4.1/index.html){: new_window}。
    

##  從 Bluemix 儀表板導覽至 Kibana 儀表板
{: #launch_Kibana_from_bluemix}

用來過濾 Kibana 顯示資料的查詢，會從您啟動 Kibana 的位置擷取 {{site.data.keyword.Bluemix_notm}} CF 應用程式或容器的日誌項目。

若要在 Kibana 中查看 Cloud Foundry 應用程式或 Docker 容器的日誌，請完成下列步驟：

1. 登入 {{site.data.keyword.Bluemix_notm}}，然後從 {{site.data.keyword.Bluemix_notm}} 儀表板按一下應用程式名稱或容器。 
    
2. 在 {{site.data.keyword.Bluemix_notm}} 使用者介面開啟日誌標籤。

    * 若為 CF 應用程式，請按一下導覽列中的**日誌**。 
    * 針對 {{site.data.keyword.Bluemix_notm}} 所管理雲端基礎架構中所部署的容器，選取導覽列中的**監視及日誌**，然後按一下**記載**標籤。 
    
        即會開啟「日誌」標籤。  

3. 按一下**進階視圖**。即會開啟 Kibana 儀表板。

    依預設，**探索**頁面會載入，並選取預設索引型樣，且時間過濾器設為前 30 秒。搜尋查詢設為比對 CF 應用程式或 Docker 容器的所有項目。

    如果「探索」頁面未顯示任何日誌項目，請調整時間選取器。如需相關資訊，請參閱[設定時間過濾器](logging_kibana_set_time_filter.html#set_time_filter)。


##  從 Web 瀏覽器導覽至 Kibana 儀表板
{: #launch_Kibana_from_browser}

用來過濾 Kibana 中顯示資料的查詢，會擷取 {{site.data.keyword.Bluemix_notm}} 組織中某個空間的日誌項目。Kibana 顯示的日誌資訊，包括部署在 {{site.data.keyword.Bluemix_notm}} 組織中您登入之空間內的所有資源記錄。

請完成下列步驟，以從瀏覽器啟動 Kibana：

1. 開啟 [https://logging.<span class="keyword" data-hd-keyref="DomainName">DomainName</span>](https://logging.{DomainName})，以登入 Kibana 使用者介面。
    
    例如， 
      
        <table>
          <caption>表 1. 啟動 Kibana 的 URL</caption>
           <tr>
            <th>地區</th>
            <th>URL</th>
          </tr>
          <tr>
            <td>美國南部</td>
            <td>https://logging.ng.bluemix.net/ </td>
          </tr>
          <tr>
            <td>英國</td>
            <td>https://logging.eu-gb.bluemix.net/ </td>
          </tr>
        </table>

    如果「探索」頁面未顯示任何日誌項目，請調整時間選取器。如需相關資訊，請參閱[設定時間過濾器](logging_kibana_set_time_filter.html#set_time_filter)。


