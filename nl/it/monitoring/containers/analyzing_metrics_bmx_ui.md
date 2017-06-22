---

copyright:
  years: 2017

lastupdated: "2017-05-25"

---


{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:screen: .screen}

# Analisi delle metriche del contenitore dalla console Bluemix
{: #analyzing_metrics_bmx_ui}

In {{site.data.keyword.Bluemix}}, puoi visualizzare e analizzare le metriche tramite la scheda *Monitoraggio* che è disponibile per i contenitori Docker distribuiti in un'infrastruttura cloud gestita da {{site.data.keyword.Bluemix_notm}}.
{:shortdesc}

{{site.data.keyword.Bluemix_notm}} pubblico offre delle funzionalità di monitoraggio integrate. 

Tieni conto delle seguenti informazioni sulla disponibilità delle metriche per l'analisi e la conservazione dei dati:

* In {{site.data.keyword.Bluemix_notm}} pubblico, le metriche vengono archiviate per 7 giorni per impostazione predefinita. 
* Puoi archiviare fino a 1 GB di dati al giorno. 
* Per impostazione predefinita, le metriche disponibili per l'analisi dalla console {{site.data.keyword.Bluemix_notm}} includono i dati per le ultime 24 ore.

**Suggerimento:** usa Grafana per analizzare i dati per un periodo personalizzato antecedente alle ultime 24 ore.


##  Accesso alle metriche di un contenitore Docker gestito in Bluemix
{: #launch_metrics_tab_bmx_ui_containers}

Per visualizzare le metriche per un contenitore Docker distribuito nell'infrastruttura cloud gestita da {{site.data.keyword.Bluemix_notm}}, completa la seguente procedura:

1. Dal dashboard Applicazioni, fai clic sul singolo contenitore o sul gruppo di contenitori 
    
2. Dalla pagina dei dettagli dell'applicazione, fai clic su **Monitoraggio e log**.

3. Seleziona la scheda **Monitoraggio**.
    
    Dalla scheda **Monitoraggio**, puoi visualizzare le metriche per il tuo contenitore.
