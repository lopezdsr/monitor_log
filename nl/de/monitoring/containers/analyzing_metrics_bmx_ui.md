---

copyright:
  years: 2017

lastupdated: "2017-05-25"

---


{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:screen: .screen}

# Container-Metriken über die Bluemix-Konsole analysieren
{: #analyzing_metrics_bmx_ui}

In {{site.data.keyword.Bluemix}} können Sie Metriken über die Registerkarte *Überwachung* anzeigen und analysieren, die für Docker-Container verfügbar ist, die in einer {{site.data.keyword.Bluemix_notm}}-verwalteten Cloudinfrastruktur bereitgestellt sind.
{:shortdesc}

{{site.data.keyword.Bluemix_notm}} Public bietet integrierte Überwachungsfunktionen. 

Beachten Sie die folgenden Informationen zur Verfügbarkeit von Metriken für die Analyse und Datenspeicherung:

* In {{site.data.keyword.Bluemix_notm}} Public werden Metriken standardmäßig für 7 Tage gespeichert. 
* Sie können bis zu 1 GB an Daten pro Tag speichern. 
* Die Metriken, die für die Analyse über die {{site.data.keyword.Bluemix_notm}}-Konsole verfügbar sind, umfassen standardmäßig Daten für den Zeitraum der letzten 24 Stunden.

**Tipp:** Verwenden Sie Grafana für die Analyse von Daten über einen benutzerdefinierten Zeitraum, der vor den letzten 24 Stunden liegt.


##  Zu den Metriken eines Bluemix-verwalteten Docker-Containers navigieren
{: #launch_metrics_tab_bmx_ui_containers}

Zum Anzeigen der Metriken für einen Docker-Container, der in der {{site.data.keyword.Bluemix_notm}}-verwalteten Cloudinfrastruktur bereitgestellt wird, führen Sie die folgenden Schritte aus:

1. Klicken Sie im Dashboard 'Apps' auf einen einzelnen Container oder eine Containergruppe. 
    
2. Klicken Sie auf der App-Detailseite auf **Überwachung und Protokolle**.

3. Wählen Sie die Registerkarte **Überwachung** aus.
    
    Über die Registerkarte **Überwachung** können Sie die Metriken für Ihren Container anzeigen.
