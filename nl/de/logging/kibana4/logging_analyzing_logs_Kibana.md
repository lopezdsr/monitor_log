---

copyright:
  years: 2015, 2017

lastupdated: "2017-03-13"

---


{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:screen: .screen}

# Erweiterte Protokollanalyse mit Kibana
{:#analyzing_logs_Kibana}

In {{site.data.keyword.Bluemix}} können Sie Kibana, eine quelloffene Analyse- und Visualisierungsplattform, dazu verwenden, Ihre Daten in einer Reihe von Darstellungsarten, wie zum Beispiel Diagrammen und Tabellen, zu überwachen, zu durchsuchen, zu analysieren und zu visualisieren. Verwenden Sie Kibana für erweiterte Analysetasks.
{:shortdesc}

Sie können Kibana auf eine beliebige der folgenden Arten starten:

* Über {{site.data.keyword.Bluemix_notm}}

    Sie können Ihre CF-App-Protokolle in Kibana im Kontext der jeweiligen App starten. 
    
    Sie können Ihre bestimmten Docker-Container-Protokolle in Kibana im Kontext des jeweiligen Containers starten.  
    
    Für CF-Apps ruft die Abfrage, die zum Filtern der für die Analyse in Kibana verfügbaren Daten verwendet wird, Protokolleinträge für die Cloud Foundry-Anwendung ab. Die Protokollinformationen, die standardmäßig in Kibana angezeigt werden, beziehen sich sämtlich auf eine einzelne Cloud Foundry-Anwendung und alle zugehörigen Instanzen.  
    
    Für Container ruft die Abfrage, die zum Filtern der für die Analyse in Kibana verfügbaren Daten verwendet wird, Protokolleinträge für alle Instanzen des Containers ab. Die Protokollinformationen, die standardmäßig in Kibana angezeigt werden, beziehen sich sämtlich auf einen einzelnen Container oder eine Containergruppe und alle zugehörigen Instanzen.  
    
    Weitere Informationen finden Sie unter [Kibana-Dashboard über das Bluemix-Dashboard aufrufen](logging_analyzing_logs_Kibana.html#launch_Kibana_from_bluemix). 

* Über einen direkten Browser-Link

    Sie können Kibana so starten, dass die Daten, die angezeigt werden, Protokolle aus Services in einem angegebenen {{site.data.keyword.Bluemix_notm}}-Bereich aggregieren. 
    
    Die Abfrage, durch die die Daten gefiltert werden, die im Dashboard angezeigt werden, ruft Protokolleinträge für einen Bereich in der {{site.data.keyword.Bluemix_notm}}-Organisation ab. Die Protokollinformationen, die in Kibana angezeigt werden, umfassen Einträge für alle Ressourcen, die innerhalb des Bereichs der {{site.data.keyword.Bluemix_notm}}-Organisation bereitgestellt wurden, an der Sie angemeldet sind.  
    
    Weitere Informationen finden Sie unter [Kibana-Dashboard im Web-Browser aufrufen](logging_analyzing_logs_Kibana.html#launch_Kibana_from_browser).
    
    Wenn Sie Kibana in einem Browser starten, können Sie auswählen, ob Sie mit Kibana 4 oder Kibana 3 arbeiten möchten. **Hinweis:** Kibana 3 ist veraltet. Informationen zur Verwendung von Kibana 3 zur Analyse Ihrer Protokolle finden Sie unter [Protokolle in Kibana 3 analysieren (veraltet)](../logging_view_kibana3.html#analyzing_logs_Kibana3). 

<br>    

Kibana ist eine browserbasierte Schnittstelle, in der Sie Daten interaktiv analysieren und Dashboards anpassen können, mit denen Sie anschließend Protokolldaten analysieren und erweiterte Management-Tasks durchführen können.  

Die Daten, die auf einer Kibana-Seite angezeigt werden, werden durch eine Suche beschränkt. Die Standarddatengruppe wird durch das vorkonfigurierte Indexmuster (Index Pattern) definiert. Zum Filtern der Informationen können Sie neue Suchabfragen hinzufügen und Filter auf die Standarddatengruppe anwenden. Anschließend können Sie die Suche zur künftigen Wiederverwendung speichern.  

Kibana enthält verschiedene Seiten, die Sie zur Analyse Ihrer Protokolle nutzen können: 

| Kibana-Seite | Beschreibung |
|-------------|-------------|
| Discover | Auf dieser Seite können Sie Suchen definieren und Ihre Protokolle interaktiv über eine Tabelle und ein Histogramm analysieren. |
| Visualize | Auf dieser Seite können Sie Visualisierungen wie Diagramme und Tabellen erstellen, mit denen Sie Ihre Protokolldaten analysieren und Ergebnisse vergleichen können.  |
| Dashboard | Auf dieser Seite können Sie Ihre Protokolle mithilfe von gespeicherten Visualisierungen und Suchen analysieren.  |

**Hinweis:** Sie können nur einen vollständigen Tag gleichzeitig auf der Seite 'Visualize' oder der Seite 'Dashboard' analysieren, obwohl Sie sieben Tage zurückgehen können. Protokolldaten werden standardmäßig sieben Tage lang gespeichert.  

| Kibana-Seite | Informationen zum Zeitraum |
|-------------|-------------------------|
| Discover | Datenanalyse über maximal sieben Tage. |
| Visualize | Datenanalyse über einen Zeitraum von 24 Stunden. <br> Sie können Protokolldaten für einen angepassten Zeitraum filtern, der nach 24 Stunden abläuft.  |
| Dashboard | Datenanalyse über einen Zeitraum von 24 Stunden. <br> Sie können Protokolldaten für einen angepassten Zeitraum filtern, der nach 24 Stunden abläuft.<br> Der Zeitraum, den Sie über das Zeitauswahlfeld festlegen, wird auf alle Visualisierungen angewendet, die im Dashboard enthalten sind.  |


Sie können Kibana zum Beispiel wie folgt zum Anzeigen von Informationen zu einer CF-App oder zu einem Container in Ihrem Bereich auf den verschiedenen Seiten verwenden: 

* Auf der Seite 'Discover' können Sie neue Suchabfragen definieren und Filter auf einzelne Abfragen anwenden. Die Protokolldaten werden in einer Tabelle oder einem Histogramm angezeigt. Mit diesen Visualisierungen können Sie die Daten interaktiv analysieren. Weitere Informationen finden Sie unter [Protokolle in Kibana interaktiv analysieren](logging_kibana_analize_logs_interactively.html#kibana_analize_logs_interactively). 

    Sie können Filter für Protokollfelder wie zum Beispiel 'message_type' und 'instance_ID' konfigurieren und einen Zeitraum festlegen. Sie können diese Filter dynamisch aktivieren oder inaktivieren. In der Tabelle und im Histogramm werden die Protokolleinträge angezeigt, die der Abfrage und den Filterkriterien entsprechen, die Sie aktivieren. Weitere Informationen finden Sie unter [Protokolle in Kibana filtern](logging_kibana_filtering_logs.html#kibana_filtering_logs). 
    
* Auf der Seite 'Visualize' können Sie neue Suchabfragen und Visualisierungen definieren. 

    Zur Analyse der Daten können Sie Visualisierungen auf der Basis einer vorhandenen Suche oder einer neuen Suche erstellen. Kibana enthält verschiedene Typen von Visualisierungen, wie zum Beispiel Tabellen, Trends und Histogramme, die Sie zur Analyse der Informationen verwenden können. Der Zweck jeder Visualisierung variiert. Einige Visualisierungen werden in Zeilen aufbereitet, in denen die Ergebnisse einer oder mehrerer Abfragen dargestellt werden. Andere Visualisierungen enthalten Dokumente oder angepasste Informationen. Die Daten in einer Visualisierung können fest sein oder sich ändern, wenn eine Suchabfrage aktualisiert wird. Sie können die Visualisierung in eine Webseite einbetten oder zur gemeinsamen Nutzung verfügbar machen. Weitere Informationen finden Sie unter [Protokolle mit Visualisierungen analysieren](logging_kibana_visualizations.html#logging_kibana_visualizations). 

* Auf der Seite 'Dashboard' können Sie mehrere Visualisierungen und Suchen gleichzeitig anpassen, speichern und zur gemeinsamen Nutzung verfügbar machen.  

    Sie können Visualisierungen im Dashboard hinzufügen, entfernen und neu anordnen. Weitere Informationen finden Sie unter [Protokolle in Kibana über ein Dashboard analysieren](logging_kibana_analize_logs_dashboard.html#kibana_analize_logs_dashboard). 
    
    Nach der Anpassung eines Kibana-Dashboards können Sie die Daten in den Visualisierungen analysieren und zur künftigen Wiederverwendung speichern. Weitere Informationen finden Sie unter [Kibana-Dashboard speichern](logging_kibana_analize_logs_dashboard.html#save_Kibana_dashboard).

In Kibana finden Sie darüber hinaus eine Einstellungsseite *Settings*, über die Sie Kibana konfigurieren sowie Suchen, Visualisierungen und Dashboards speichern, löschen, exportieren und importieren können. 

Weitere Informationen finden Sie in der Veröffentlichung [Kibana User Guide ![Symbol für externen Link](../../../icons/launch-glyph.svg "Symbol für externen Link")](https://www.elastic.co/guide/en/kibana/4.1/index.html){: new_window}. 

**Hinweis:** Kibana 4 und Kibana 3 werden unterstützt. Kibana 3 ist veraltet.


##  Kibana-Dashboard über das Bluemix-Dashboard aufrufen
{: #launch_Kibana_from_bluemix}

Die Abfrage, durch die die Daten gefiltert werden, die in Kibana angezeigt werden, ruft Protokolleinträge für die {{site.data.keyword.Bluemix_notm}}-CF-App oder für den Container von der Position aus ab, an der Sie Kibana starten.  

Führen Sie die folgenden Schritte aus, um die Protokolle einer Cloud Foundry-Anwendung oder eines Docker-Containers in Kibana anzuzeigen: 

1. Melden Sie sich bei {{site.data.keyword.Bluemix_notm}} an und klicken Sie auf den App-Namen oder den Container im {{site.data.keyword.Bluemix_notm}}-Dashboard.  
    
2. Öffnen Sie die Registerkarte für Protokolle in der {{site.data.keyword.Bluemix_notm}}-Benutzerschnittstelle. 

    * Klicken Sie für CF-Apps auf **Protokolle** in der Navigationsleiste.  
    * Wählen Sie für Container **Überwachung und Protokolle** in der Navigationsleiste aus und klicken Sie auf die Registerkarte **Protokollierung**.  
    
    Die Registerkarte für Protokolle wird geöffnet. 
    
3. Klicken Sie auf **Erweiterte Ansicht**. Das Dashboard von **Kibana 4** wird geöffnet. 

    Die Seite **Discover** wird standardmäßig mit dem ausgewählten Standardindexmuster und einem Zeitfilter, der auf die letzten 30 Sekunden eingestellt ist, angezeigt. Die Suchabfrage ist so definiert, dass sie allen Einträgen für Ihre CF-App oder Ihren Docker-Container entspricht. 

    Wenn die Seite 'Discover' keine Protokolleinträge anzeigt, passen Sie das Zeitauswahlfeld an. Weitere Informationen finden Sie unter [Zeitfilter festlegen](logging_kibana_set_time_filter.html#set_time_filter).

Weitere Informationen zu Kibana finden Sie in der Veröffentlichung [Kibana User Guide](https://www.elastic.co/guide/en/kibana/current/index.html). 

##  Kibana-Dashboard im Web-Browser aufrufen
{: #launch_Kibana_from_browser}

Die Abfrage, durch die die Daten gefiltert werden, die in Kibana angezeigt werden, ruft Protokolleinträge für einen Bereich in der {{site.data.keyword.Bluemix_notm}}-Organisation ab. Die Protokollinformationen, die in Kibana angezeigt werden, umfassen Einträge für alle Ressourcen, die innerhalb des Bereichs der {{site.data.keyword.Bluemix_notm}}-Organisation bereitgestellt wurden, an der Sie angemeldet sind.

Führen Sie die folgenden Schritte aus, um Kibana über einen Browser zu starten: 

1. Öffnen Sie [https://logmet.<span class="keyword" data-hd-keyref="DomainName">Domänenname</span>](https://logmet.{DomainName}), um sich bei der Kibana-Benutzerschnittstelle anzumelden.

2. Wählen Sie die Version von Kibana aus, die Sie zur Analyse Ihrer Protokolle verwenden wollen. 
    * Wählen Sie die Registerkarte **Kibana 4** aus, um mit Kibana 4 zu arbeiten. Die Seite 'Discover' wird geöffnet. Weitere Informationen finden Sie unter [logging_kibana_analize_logs_interactively.html#kibana_analize_logs_interactively). 
    * Wählen Sie die Registerkarte **Kibana 3** aus, um mit Kibana 3 zu arbeiten. Das Kibana-Standarddashboard wird geöffnet. Weitere Informationen zur Anpassung eines Kibana 3-Dashboard finden Sie [in diesem Blogbeitrag](https://www.ibm.com/blogs/bluemix/2015/09/creating-custom-kibana-dashboard-in-bluemix/). 
     
        **Hinweis:** Kibana 3 ist veraltet. 

    Wenn die Seite 'Discover' keine Protokolleinträge anzeigt, passen Sie das Zeitauswahlfeld an. Weitere Informationen finden Sie unter [Zeitfilter festlegen](logging_kibana_set_time_filter.html#set_time_filter).

Weitere Informationen zu Kibana finden Sie in der Veröffentlichung [Kibana User Guide ![Symbol für externen Link](../../../icons/launch-glyph.svg "Symbol für externen Link")](https://www.elastic.co/guide/en/kibana/4.1/index.html){: new_window}.

