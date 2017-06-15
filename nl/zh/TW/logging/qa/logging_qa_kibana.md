---

copyright:
  years: 2015, 2017

lastupdated: "2017-05-22"

---


{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:screen: .screen}


# Kibana 常見問題 (FAQ)
{: #logging_qa_kibana}

以下是關於使用 {{site.data.keyword.Bluemix}} 記載功能的常見問題與解答。{:shortdesc}

* [如果在 Kibana 的「探索」頁面中看不到資料，我該怎麼辦](logging_qa_kibana.html#logging_qa_no_data_discover_kibana)
* [如果發生鑑別異常狀況，我該怎麼辦](logging_qa_kibana.html#logging_qa_no_data_dashboard_kibana)
* [如何啟動 Kibana 3](logging_qa_kibana.html#logging_qa_kibana3)
* [為什麼會在 Kibana「探索」頁面中的欄位中看到符號 ?](logging_qa_kibana.html#logging_qa_kibana_question)

## 如果在 Kibana 的「探索」頁面中看不到資料，我該怎麼辦
{: #logging_qa_no_data_discover_kibana}

您在 Kibana 中看不到資料，可能會有以下幾種不同情境：

1. 啟動 Kibana 時，您在「探索」頁面中可能未看到任何資料，並且收到下列訊息：**找不到任何結果**。 
2. 您可能正在 Kibana 的「探索」頁面中工作。不過，一段時間之後，當您嘗試在 Kibana 中執行作業時，收到下列訊息：**找不到任何結果**。

若要解決這個問題，請完成下列步驟：

1. 檢查「探索」頁面中設定的*時間選取器*，並增長時段。 

    **附註**：依預設，在 {{site.data.keyword.Bluemix_notm}} 中，*時間選取器* 設定為顯示前 15 分鐘的資料。

    如需如何設定*時間選取器* 的相關資訊，請參閱[設定時間過濾器](../kibana4/k4_filter_logs.html#set_time_filter)。
       
2. 按一下位於*探索* 頁面搜尋列中的放大鏡。頁面資料會根據預設搜尋查詢來重新整理。

    或者，您也可以設定*自動重新整理* 週期。

    **附註**：依預設，在 {{site.data.keyword.Bluemix_notm}} 中，*自動重新整理* 週期設定為**關閉**。
    
    如需如何啟用此功能的相關資訊，請參閱[自動重新整理資料](../kibana4/logging_kibana_analize_logs_interactively.html#kibana_discover_view_refresh_interval)。



## 如果發生鑑別異常狀況，我該怎麼辦
{: #logging_qa_no_data_dashboard_kibana}

如果您在「儀表板」頁面中，看不到以視覺化顯示的資料，並收到錯誤訊息：**錯誤：授權異常狀況。**，請檢查您查看各視覺化資料的許可權。

請考量下列資訊：您可以在「儀表板」頁面中配置一個以上的視覺化。當「儀表板」頁面要求收集透過那些視覺化顯示的資料時，針對所有視覺化，僅發出一個要求。如果您沒有查看其中一項視覺化資料的許可權，整個要求都會失敗。

若要解決這個問題，請完成下列步驟：

1. 識別您沒有許可權的視覺化。

    1. 在*儀表板* 頁面中按一下視覺化的*鉛筆* 圖示。該視覺化會在*視覺化* 頁面中開啟。或者，您也可以在*視覺化* 頁面中，載入一個視覺化。 
    2. 驗證您可以看到資料。
    
    重複這些步驟來處理每一個視覺化。

2. 向您的雲端管理者要求查看那些視覺化中之資料的存取權。

3. 建立新的「儀表板」頁面，排除您沒有許可權的視覺化，但您有權查看造成問題之視覺化中的資料。 

    如果您共用該「儀表板」，請勿刪除視覺化，因為那樣會影響其他使用相同儀表板的團隊成員。

## 如何啟動 Kibana 3
{: #logging_qa_kibana3}

**附註：**Kibana 3 已被淘汰。

您可以從瀏覽器啟動 Kibana 3。

請完成下列步驟，以從瀏覽器啟動 Kibana 3：

1. 開啟 [https://logmet.<span class="keyword" data-hd-keyref="DomainName">DomainName</span>](https://logmet.{DomainName})，以登入 Kibana 使用者介面。
    
2. 選取您要用來分析日誌的 Kibana 版本。
    * 選取 **Kibana 4** 標籤，以使用 Kibana 4。「探索」頁面即會開啟。如需相關資訊，請參閱 [在 Kibana 中以互動方式分析日誌](logging_kibana_analize_logs_interactively.html#kibana_analize_logs_interactively)。
    * 選取 **Kibana 3** 標籤，以使用 Kibana 3。預設的 Kibana 儀表板即會開啟。如需使用 Kibana 3 來分析日誌的相關資訊，請參閱[在 Kibana 3（已淘汰）中分析日誌](../logging_view_kibana3.html#analyzing_logs_Kibana3)。如需自訂 Kibana 3 儀表板的相關資訊，請參閱[此部落格文章 ![外部鏈結圖示](../../../icons/launch-glyph.svg "外部鏈結圖示")](https://www.ibm.com/blogs/bluemix/2015/09/creating-custom-kibana-dashboard-in-bluemix/)。
     

## 為什麼會在 Kibana「探索」頁面中的欄位中看到符號 ?
{: #logging_qa_kibana_question}

當您在 Kibana 中開啟「探索」頁面時，可能會在可用欄位區段中所列的欄位中看到 `?`，而不是字元 `t`。當您重新載入欄位清單時，會分析欄位類型，並將 `?` 取代為字元 `t`。如需相關資訊，請參閱[重新載入欄位清單](../kibana4/logging_kibana_analize_logs_interactively.html#kibana_discover_view_reload_fields)。



