---

copyright:
  years: 2015, 2017

lastupdated: "2017-05-22"

---


{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:screen: .screen}


# Zum Kibana-Dashboard navigieren
{: #k4_launch}

Sie können Kibana über die {{site.data.keyword.Bluemix}}-Benutzerschnittstelle oder direkt über einen Browser starten.
{:shortdesc}

Starten Sie Kibana über {{site.data.keyword.Bluemix_notm}}, um Daten im Kontext der Ressource, von der aus Sie Kibana starten, anzuzeigen und zu analysieren. Sie können beispielsweise Ihre speziellen CF-App-Protokolle in Kibana und im Kontext für diese spezifische App starten.
    
Starten Sie Kibana über einen direkten Browser-Link, wenn Sie aggregierte Protokolldaten aus Services in einem angegebenen {{site.data.keyword.Bluemix_notm}}-Bereich anzeigen möchten. Die Abfrage, durch die die Daten gefiltert werden, die im Dashboard angezeigt werden, ruft Protokolleinträge für einen Bereich in der {{site.data.keyword.Bluemix_notm}}-Organisation ab. Die Protokollinformationen, die in Kibana angezeigt werden, umfassen Einträge für alle Ressourcen, die innerhalb des Bereichs der {{site.data.keyword.Bluemix_notm}}-Organisation bereitgestellt wurden, an der Sie angemeldet sind. 

In der folgenden Tabelle sind die Ressourcen und die unterstützte Navigationsmethode zum Starten von Kibana aufgelistet:

<table>
<caption>Tabelle 1. Liste der Ressourcen und unterstützten Navigationsmethoden.</caption>
  <tr>
    <th>Ressource</th>
    <th>Zum Kibana-Dashboard über das Bluemix-Dashboard navigieren</th>
    <th>Zum Kibana-Dashboard über einen Web-Browser navigieren</th>
  <tr>
  <tr>
    <td>CF-App</td>
    <td>Ja</td>
    <td>Ja</td>
  <tr>  
  <tr>
    <td>In einem Kubernetes-Cluster bereitgestellter Container</td>
    <td>Nein</td>
    <td>Ja</td>
  <tr>  
  <tr>
    <td>In einer {{site.data.keyword.Bluemix_notm}}-verwalteten Cloudinfrastruktur bereitgestellter Container</td>
    <td>Ja</td>
    <td>Ja</td>
  <tr>  
</table>

Weitere Informationen zu Kibana finden Sie in der Veröffentlichung [Kibana User Guide ![Symbol für externen Link](../../../icons/launch-glyph.svg "Symbol für externen Link")](https://www.elastic.co/guide/en/kibana/4.1/index.html){: new_window}.
    

##  Zum Kibana-Dashboard über das Bluemix-Dashboard navigieren
{: #launch_Kibana_from_bluemix}

Die Abfrage, durch die die Daten gefiltert werden, die in Kibana angezeigt werden, ruft Protokolleinträge für die {{site.data.keyword.Bluemix_notm}}-CF-App oder für den Container von der Position aus ab, an der Sie Kibana starten.

Führen Sie die folgenden Schritte aus, um die Protokolle einer Cloud Foundry-Anwendung oder eines Docker-Containers in Kibana anzuzeigen:

1. Melden Sie sich bei {{site.data.keyword.Bluemix_notm}} an und klicken Sie auf den App-Namen oder den Container im {{site.data.keyword.Bluemix_notm}}-Dashboard. 
    
2. Öffnen Sie die Registerkarte für Protokolle in der {{site.data.keyword.Bluemix_notm}}-Benutzerschnittstelle.

    * Klicken Sie für CF-Apps auf **Protokolle** in der Navigationsleiste. 
    * Für Container, die in der {{site.data.keyword.Bluemix_notm}}-verwalteten Cloudinfrastruktur bereitgestellt werden, wählen Sie in der Navigationsleiste **Überwachung und Protokolle** aus und klicken Sie anschließend auf die Registerkarte **Protokollierung**. 
    
        Die Registerkarte für Protokolle wird geöffnet.  

3. Klicken Sie auf **Erweiterte Ansicht**. Das Kibana-Dashboard wird geöffnet.

    Die Seite **Discover** wird standardmäßig mit dem ausgewählten Standardindexmuster und einem Zeitfilter, der auf die letzten 30 Sekunden eingestellt ist, angezeigt. Die Suchabfrage ist so definiert, dass sie allen Einträgen für Ihre CF-App oder Ihren Docker-Container entspricht.

    Wenn die Seite 'Discover' keine Protokolleinträge anzeigt, passen Sie das Zeitauswahlfeld an. Weitere Informationen finden Sie unter [Zeitfilter festlegen](logging_kibana_set_time_filter.html#set_time_filter).


##  Zum Kibana-Dashboard über einen Web-Browser navigieren
{: #launch_Kibana_from_browser}

Die Abfrage, durch die die Daten gefiltert werden, die in Kibana angezeigt werden, ruft Protokolleinträge für einen Bereich in der {{site.data.keyword.Bluemix_notm}}-Organisation ab. Die Protokollinformationen, die in Kibana angezeigt werden, umfassen Einträge für alle Ressourcen, die innerhalb des Bereichs der {{site.data.keyword.Bluemix_notm}}-Organisation bereitgestellt wurden, an der Sie angemeldet sind.

Führen Sie den folgenden Schritt aus, um Kibana über einen Browser zu starten: 

1. Öffnen Sie [https://logging.<span class="keyword" data-hd-keyref="DomainName">DomainName</span>](https://logging.{DomainName}), um sich an der Kibana-Benutzerschnittstelle anzumelden.
    
    Beispiel: 
      
        <table>
          <caption>Tabelle 1. URLs zum Starten von Kibana</caption>
           <tr>
            <th>Region</th>
            <th>URL</th>
          </tr>
          <tr>
            <td>Vereinigte Staaten (Süden)</td>
            <td>https://logging.ng.bluemix.net/ </td>
          </tr>
          <tr>
            <td>Vereintes Königreich</td>
            <td>https://logging.eu-gb.bluemix.net/ </td>
          </tr>
        </table>

    Wenn die Seite 'Discover' keine Protokolleinträge anzeigt, passen Sie das Zeitauswahlfeld an. Weitere Informationen finden Sie unter [Zeitfilter festlegen](logging_kibana_set_time_filter.html#set_time_filter).


