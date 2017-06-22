---

copyright:
  years: 2015, 2017

lastupdated: "2017-05-23"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:screen: .screen}


# Registrazione del servizio IBM Bluemix Container
{: #logging_containers_ov}

Puoi visualizzare, filtrare e analizzare i log per i contenitori Docker distribuiti nell'infrastruttura cloud gestita da {{site.data.keyword.IBM}} e per i contenitori Docker che vengono eseguiti nei cluster Kubernetes. La registrazione dei contenitori è abilitata automaticamente quando distribuisci un contenitore in {{site.data.keyword.Bluemix_notm}} o in un cluster Kubernetes.
{:shortdesc}

I log del contenitore sono monitorati e inoltrati dall'esterno del contenitore utilizzando i crawler. I dati vengono inviati dai crawler a un
Elasticsearch a più tenant in {{site.data.keyword.Bluemix_notm}}.



## Raccolta dei log per un contenitore che viene eseguito in un cluster Kubernetes
{: #logging_containers_ov_logs_collected_kubernetes}

La seguente figura mostra una vista di alto livello della registrazione per {{site.data.keyword.containershort}}:

![Panoramica dei componenti di alto livello per i contenitori distribuiti in un cluster Kubernetes](images/containers_kube.gif "Panoramica dei componenti di alto livello per i contenitori distribuiti in un cluster Kubernetes")

In {{site.data.keyword.Bluemix_notm}}, quando distribuisci le applicazioni in un cluster Kubernetes, tieni conto delle seguenti informazioni:

* In un account {{site.data.keyword.Bluemix_notm}}, puoi avere 1 o più organizzazioni. 
* Ciascuna organizzazione può avere 1 o più spazi {{site.data.keyword.Bluemix_notm}}. 
* Puoi avere 1 o più cluster Kubernetes in un'organizzazione. 
* La raccolta dei log è abilitata automaticamente quando crei un cluster Kubernetes. 
* Un cluster Kubernetes è indipendente dagli spazi {{site.data.keyword.Bluemix_notm}}. Tuttavia, i dati di log di un cluster e le relative risorse sono associati a uno spazio {{site.data.keyword.Bluemix_notm}}.
* I dati di log vengono raccolti per un'applicazione appena il pod viene distribuito.
* Per analizzare i dati di log per un cluster, devi accedere ai dashboard Kibana per la regione di cloud pubblico dove viene creato il cluster.

Prima di creare un cluster, tramite l'[interfaccia utente {{site.data.keyword.Bluemix_notm}}](../../../containers/cs_cluster.html#cs_cluster_ui) o tramite la [riga di comando](../../../containers/cs_cluster.html#cs_cluster_cli), devi eseguire l'accesso a una regione, un account, un'organizzazione e uno spazio {{site.data.keyword.Bluemix_notm}} specifici. Lo spazio dove hai eseguito l'accesso è quello in cui vengono raccolti i dati di registrazione per il cluster e le relative risorse.

Per impostazione predefinita, vengono raccolte le informazioni inserite dai processi di contenitore in stdout (output standard) e stderr (errore standard). L'invio di informazioni a stdout e stderr è la convenzione Docker standard per esporre le informazioni di un contenitore. 

Se inoltri i dati di log di un'applicazione che viene eseguita in un contenitore al raccoglitore di log Docker in formato JSON, puoi cercare nei dati di log e analizzarli in Kibana utilizzando campi JSON. Per ulteriori informazioni, vedi [Configurazione di campi personalizzati come campi di ricerca Kibana](logging_containers_ov.html#send_data_in_json).

**Nota:** quando lavori con un cluster Kubernetes, gli spazi dei nomi *ibm-system* e *kube-system* sono riservati. Non creare, eliminare, modificare o cambiare le autorizzazioni delle risorse disponibili in tali spazi dei nomi. L'uso dei log per questi spazi dei nomi è riservato a {{site.data.keyword.IBM_notm}}.


## Raccolta dei log per un contenitore gestito da Bluemix
{: #logging_containers_ov_logs_collected}

La seguente figura mostra una vista di alto livello della registrazione per {{site.data.keyword.containershort}}:

![Panoramica dei componenti di alto livello per i contenitori distribuiti in un'infrastruttura cloud gestita da {{site.data.keyword.Bluemix_notm}}](images/container_bmx.gif "Panoramica dei componenti di alto livello per i contenitori distribuiti in un'infrastruttura cloud gestita da {{site.data.keyword.Bluemix_notm}}")

Per impostazione predefinita, i seguenti log sono raccolti per un contenitore distribuito nell'infrastruttura cloud gestita da {{site.data.keyword.Bluemix_notm}}:

<table>
  <caption>Tabella 2. Log raccolti per i contenitori distribuiti nell'infrastruttura cloud gestita da Bluemix</caption>
  <tbody>
    <tr>
      <th align="center">Log</th>
      <th align="center">Descrizione</th>
    </tr>
    <tr>
      <td align="left" width="30%">/var/log/messages</td>
      <td align="left" width="70%"> Per impostazione predefinita, i messaggi Docker vengono archiviati nella cartella /var/log/messages del contenitore. Questo log include i messaggi di sistema.
      </td>
    </tr>
    <tr>
      <td align="left">./docker.log</td>
      <td align="left">Questo log è il log Docker. <br> Il file di log Docker non è memorizzato come file interno di un contenitore, ma viene raccolto comunque. Questo file di log viene raccolto per impostazione predefinita poiché è la convenzione Docker standard per esporre le informazioni stdout (output standard) e stderr (errore standard) per il contenitore. Vengono raccolte le informazioni inserite in stdout o stderr dai processi del contenitore.
      </td>
     </tr>
  </tbody>
</table>

Per raccogliere ulteriori log, aggiungi la variabile di ambiente **LOG_LOCATIONS** con un percorso al file di log quando crei il contenitore. Puoi aggiungere più file di log separandoli con le virgole. Per ulteriori informazioni, vedi [Raccolta di dati di log non predefiniti da un contenitore](logging_containers_other_logs.html#logging_containers_collect_data).


##  Configurazione di campi personalizzati come campi di ricerca Kibana 
{: #send_data_in_json}

Per impostazione predefinita, la registrazione è abilitata automaticamente per i contenitori. Ogni voce nel file di log Docker viene visualizzata in Kibana nel campo `message`.Se hai bisogno di filtrare e analizzare i tuoi dati in Kibana utilizzando uno specifico campo che fa parte della voce di log del contenitore, configura la tua applicazione per inviare un output in formato JSON valido.

Tieni conto delle seguenti informazioni:

* Per i contenitori distribuiti in un cluster Kubernetes, registra il messaggio in formato JSON in stdout (output standard) e stderr (errore standard).

    Ciascun campo disponibile nel messaggio viene analizzato al tipo di campo che corrisponde al suo valore. Ad esempio, ciascun campo nel seguente messaggio JSON:
    
    ```
    {"field1":"string type",
        "field2":123,
        "field3":false,
        "field4":"4567"
    }
    ```
    
    è disponibile come un campo che puoi utilizzare per attività di filtro e ricerca:
    
    * `field1` viene analizzato come `field1_str` di tipo stringa.
    * `field2` viene analizzato come `field1_int` di tipo numero intero.
    * `field3` viene analizzato come `field3_bool` di tipo booleano.
    * `field4` viene analizzato come `field4_str` di tipo stringa.
    
* Per i contenitori distribuiti nell'infrastruttura cloud gestita da {{site.data.keyword.Bluemix_notm}}, completa la seguente procedura per analizzare le voci di log del contenitore in singoli campi:

    1. Registra il messaggio in un file. 
    2. Aggiungi il file di log all'elenco di log non predefiniti che sono disponibili per l'analisi da un contenitore. Per ulteriori informazioni, vedi [Raccolta di dati di log non predefiniti da un contenitore](logging_containers_other_logs.html#logging_containers_collect_data). 
    
   Se registri il messaggio in un file, e viene determinato che un messaggio è in JSON valido, i campi vengono analizzati e vengono creati dei nuovi campi per ciascun campo nel messaggio. Solo i valori di campo di tipo stringa sono disponibili per il filtro e l'ordinamento in Kibana


## Visualizzazione dei log del contenitore per un contenitore in esecuzione in un cluster Kubernetes
{: #logging_containers_ov_methods_view_kube}

Puoi visualizzare i log più recenti per un contenitore in un pod Kubernetes utilizzando uno qualsiasi dei seguenti metodi:

* Visualizza i log tramite l'interfaccia utente Kubernetes. Per ciascun pod, puoi operarne la selezione e accedere ai suoi log. Per ulteriori informazioni,
vedi [Dashboard interfaccia utente web ![(Icona link esterno)](../../../icons/launch-glyph.svg "Icona link esterno")](https://kubernetes.io/docs/tasks/access-application-cluster/web-ui-dashboard/){: new_window}.

* Visualizza i log utilizzando il comando CLI Kubernetes [kubectl logs ![(Icona link esterno)](../../../icons/launch-glyph.svg "Icona link esterno")](http://vishh.github.io/docs/user-guide/kubectl/kubectl_logs/){: new_window}. 

Per visualizzare i log a lungo termine, puoi utilizzare Kibana. Controlla le informazioni [Conservazione log](logging_containers_ov.html#logging_containers_ov_log_retention) per conoscere le politiche dei periodi di conservazione dei dati.



## Visualizzazione dei log del contenitore per un contenitore gestito da Bluemix
{: #logging_containers_ov_methods_view_bmx}

Puoi visualizzare i log più recenti per un contenitore distribuito nell'infrastruttura cloud gestita da {{site.data.keyword.Bluemix_notm}} utilizzando uno qualsiasi dei seguenti metodi:

* Visualizza i log tramite l'interfaccia utente {{site.data.keyword.Bluemix_notm}} per monitorare l'attività più recente del contenitore.
    
    Puoi visualizzare, filtrare e analizzare i log attraverso la scheda **Monitoraggio e log** disponibile per ogni contenitore. Per ulteriori informazioni, vedi [Analisi dei log dal dashboard Bluemix](../logging_view_dashboard.html#analyzing_logs_bmx_ui).
    
    
* Visualizza i log utilizzando la CLI {site.data.keyword.containershort}}. Utilizza i comandi per gestire i log a livello di programmazione.
    
    Puoi visualizzare, filtrare e analizzare i log attraverso l'interfaccia riga di comando utilizzando il comando **cf ic logs**. Per ulteriori informazioni, vedi [Analisi dei log dall'interfaccia riga di comando](../logging_view_cli.html#analyzing_logs_cli).


## Analisi dei log del contenitore
{: #logging_containers_ov_methods}

Per analizzare i dati dei log del contenitore, usa Kibana per eseguire delle attività di analisi avanzate. Puoi utilizzare Kibana, una piattaforma di analisi e visualizzazione open source, per monitorare, ricercare, analizzare e visualizzare i tuoi dati in una varietà di grafici, ad esempio, diagrammi e tabelle. Per ulteriori informazioni, vedi [Analisi dei log in Kibana](../kibana4/analyzing_logs_Kibana.html#analyzing_logs_Kibana).


## Conservazione log
{: #logging_containers_ov_log_retention}

Tieni conto delle seguenti informazioni sulla conservazione dei log:

* Viene memorizzato un massimo di 1 GB per spazio di dati al giorno. I log che superano questo limite di 1 GB vengono eliminati. Le assegnazioni dei limiti vengono reimpostate ogni giorno alle
00:30 UTC. 

    Puoi incrementare la tua assegnazione contattando il supporto. Nel ticket di supporto, includi il tuo ID dello spazio per la richiesta di incremento dell'attestazione, la nuova dimensione e il motivo della richiesta.

* Sono ricercabili fino a 7 GB di dati per un massimo di 7 giorni. Viene eseguito il rollover (la prima voce inserita è la prima a essere eliminata) dei dati di log quando vengono raggiunti i 7 GB di dati o vengono superati i 7 giorni

## Esercitazione: analizza i log in Kibana per un'applicazione distribuita in un cluster Kubernetes
{: #tutorial1}

Per informazioni su come utilizzare Kibana per analizzare i log di un contenitore distribuito in un cluster Kubernetes, vedi [Esercitazione: analizza i log in Kibana per un'applicazione distribuita in un cluster Kubernetes](tutorials/kibana_tutorial_1.html#kibana_tutorial_1).


