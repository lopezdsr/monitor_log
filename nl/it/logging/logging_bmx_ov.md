---

copyright:
  years: 2015, 2017

lastupdated: "2017-03-29"

---


{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:screen: .screen}

# Registrazione in Bluemix
{: #logging_bmx_ov}

Le funzionalità di registrazione {{site.data.keyword.Bluemix}} sono integrate nella piattaforma e la raccolta dei dati è abilitata automaticamente per le risorse cloud. Per impostazione predefinita, {{site.data.keyword.Bluemix_notm}}, raccoglie e visualizza i log per le tue applicazioni, i runtime delle applicazioni e i runtime di calcolo in cui queste applicazioni vengono eseguite. 
{:shortdesc}

Puoi utilizzare le funzionalità di registrazione in {{site.data.keyword.Bluemix_notm}} per comprendere il funzionamento della piattaforma cloud e delle risorse eseguite al suo interno. Non è richiesta alcuna strumentazione speciale per raccogliere i log di output standard e di errore standard. Ad esempio, puoi utilizzare i log per fornire un audit trail per un'applicazione, rilevare problemi nel tuo servizio, identificare vulnerabilità, risolvere problemi relativi alle distribuzioni delle applicazioni e al funzionamento del runtime, rilevare problemi nell'infrastruttura in cui è in esecuzione l'applicazione, tracciare la tua applicazione tra i componenti della piattaforma cloud e individuare dei modelli da utilizzare per prevenire azioni che potrebbero compromettere il tuo servizio SLA.

Quando esegui le tue applicazioni nel cloud, potresti non riuscire a stabilire un tunnel SSH o FTP nell'infrastruttura in cui sono in esecuzione le tue applicazioni per accedere ai log, ad esempio se l'applicazione è eseguita in Cloud Foundry. D'altra parte, puoi eseguire la tua applicazione in {{site.data.keyword.containershort}}, un altro runtime di calcolo disponibile in {{site.data.keyword.Bluemix_notm}}, in cui puoi stabilire un tunnel SSH e accedere ai log. Indipendentemente dal runtime di calcolo, l'accesso ai log è critico e {{site.data.keyword.Bluemix_notm}} fornisce un'esperienza comune per visualizzare e analizzare i log nella tua piattaforma cloud.

Mediante la funzionalità di registrazione offerta da {{site.data.keyword.Bluemix_notm}}, puoi:

* Visualizzare le tue risorse cloud e il modo in cui vengono eseguite.
* Definire le tendenze che ti aiutano a identificare gli scenari che richiedono il tuo intervento.
* Definire i tracciati dei dati per un'applicazione che puoi utilizzare, ad esempio, per il controllo.
* Ridurre il tempo e lo sforzo richiesti per individuare e correggere un problema nell'applicazione. 
* Monitorare la distribuzione delle tue applicazioni nella piattaforma cloud.
* Rilevare l'inattività o l'arresto anomalo di un servizio o un'applicazione.
* Seguire l'esecuzione dell'applicazione e il flusso di dati.
* Identificare vulnerabilità nella tua applicazione.
* Rilevare problemi nell'infrastruttura.
* Rilevare problemi nel runtime dell'applicazione.

## Registrazione per le applicazioni CF
{: #logging_bmx_ov_cf}

{{site.data.keyword.Bluemix_notm}} registra i dati di log generati dalla piattaforma Cloud Foundry e dalle applicazioni Cloud Foundry. Nei log, puoi visualizzare gli errori, le avvertenze e i messaggi informativi che vengono generati per la tua applicazione. Per ulteriori informazioni sulla registrazione in Cloud Foundry, vedi [Registrazione per le applicazioni Cloud Foundry in Bluemix](cfapps/logging_cf_apps.html#logging_bluemix_cf_apps).

## Registrazione per i contenitori
{: #logging_bmx_ov_containers}

{{site.data.keyword.Bluemix_notm}} registra i dati di log generati da {{site.data.keyword.containershort}}. Per ulteriori informazioni sulla registrazione in {{site.data.keyword.containershort}}, vedi [Registrazione del servizio IBM Bluemix Container](containers/logging_containers_ov.html#logging_containers_ov).  

**Nota:** puoi analizzare i log del contenitore in {{site.data.keyword.Bluemix_notm}} per i contenitori Docker distribuiti nell'infrastruttura cloud gestita da {{site.data.keyword.IBM}}.

## Analisi dei log in Bluemix
{: #logging_bmx_ov_ui}

In {{site.data.keyword.Bluemix_notm}}, puoi visualizzare in tempo reale i log recenti riguardanti la tua applicazione o le parti finali dei log.

* Puoi visualizzare, filtrare e analizzare i log attraverso l'interfaccia utente. Per ulteriori informazioni, vedi [Analisi dei log dalla console Bluemix](logging_view_dashboard.html#analyzing_logs_bmx_ui).

* Puoi visualizzare, filtrare e analizzare i log utilizzando la riga di comando per gestire i log a livello di programmazione. Per ulteriori informazioni, vedi [Analisi dei log dalla CLI](logging_view_cli.html#analyzing_logs_cli).

## Analisi log avanzata con Kibana
{: #logging_bmx_ov_kibana}

In {{site.data.keyword.Bluemix_notm}}, puoi utilizzare Kibana, una piattaforma di analisi e visualizzazione open source, per monitorare, ricercare, analizzare e visualizzare i tuoi dati in una varietà di grafici, ad esempio, diagrammi e tabelle. Per ulteriori informazioni, vedi [Analisi log avanzata con Kibana](kibana4/analyzing_logs_Kibana.html#analyzing_logs_Kibana).


