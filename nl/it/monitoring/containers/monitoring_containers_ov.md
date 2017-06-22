---

copyright:
  years: 2015, 2017

lastupdated: "2017-05-26"

---


{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:screen: .screen}


# Monitoraggio del servizio IBM Bluemix Container
{: #monitoring_bmx_containers_ov}

In {{site.data.keyword.Bluemix}}, le metriche del contenitore vengono raccolte automaticamente dall'esterno del contenitore, senza dover installare e conservare gli agent nel contenitore. Puoi utilizzare Grafana per visualizzare le metriche del contenitore. Puoi anche utilizzare l'interfaccia utente Kubernetes per visualizzare le metriche per i nodi (lavori) e i pod.
{:shortdesc}

## Raccolta delle metriche per un contenitore che viene eseguito in un cluster Kubernetes
{: #metrics_containers_kube_ov}

In {{site.data.keyword.Bluemix_notm}}, quando distribuisci le applicazioni in un cluster Kubernetes, tieni conto delle seguenti informazioni:

* In un account {{site.data.keyword.Bluemix_notm}}, puoi avere 1 o più organizzazioni.
* Ciascuna organizzazione può avere 1 o più spazi {{site.data.keyword.Bluemix_notm}}.
* Puoi avere 1 o più cluster Kubernetes in un'organizzazione.
* La raccolta delle metriche è abilitata automaticamente quando crei un cluster Kubernetes.
* Un cluster Kubernetes è indipendente dagli spazi {{site.data.keyword.Bluemix_notm}}. Tuttavia, le metriche raccolte per un cluster e le relative risorse sono associate a uno spazio {{site.data.keyword.Bluemix_notm}}.
* Le metriche vengono raccolte per un contenitore appena il pod viene distribuito.
* Puoi visualizzare le metriche in Grafana o nell'interfaccia utente Kubernetes.
* Per visualizzare i dati di metrica per un cluster, devi configurare i dashboard Grafana per la regione di cloud pubblico dove viene creato il cluster.

Prima di creare un cluster, tramite l'interfaccia utente {{site.data.keyword.Bluemix_notm}} o tramite la riga di comando, devi eseguire l'accesso a una regione, un account, un'organizzazione e uno spazio {{site.data.keyword.Bluemix_notm}} specifici. Lo spazio dove hai eseguito l'accesso è quello in cui vengono raccolti i dati di metrica per il cluster e le relative risorse.

La seguente figura mostra una vista di alto livello del monitoraggio per {{site.data.keyword.containershort}}:

![Panoramica dei componenti di alto livello per i contenitori distribuiti in un cluster Kubernetes](images/monitoring_kube.gif "Panoramica dei componenti di alto livello per i contenitori distribuiti in un cluster Kubernetes")

Il crawler è un processo che è in esecuzione nell'host e che esegue il monitoraggio senza agent per le metriche. Il crawler raccoglie costantemente le seguenti metriche da tutti i contenitori per impostazione predefinita:

<table>
  <caption>Tabella 1. Metriche acquisite per impostazione predefinita</caption>
  <tr>
    <th>Tipo di metrica</th>
    <th>Nome della metrica</th>
    <th>Descrizione</th>
  </tr>
  <tr>
    <td>Memoria</td>
    <td>*memory_current*</td>
    <td>Questa metrica notifica i byte di memoria che il contenitore sta attualmente utilizzando. </td>
  </tr>
  <tr>
    <td>Memoria</td>
    <td>*memory_limit*</td>
    <td>Questa metrica notifica la quantità di memoria di cui un contenitore può eseguire lo swap su disco rispetto ai limiti massimo e minimo impostati per un pod.<br> <br>Per impostazione predefinita, i pod vengono eseguiti con dei limiti di memoria illimitati. Un pod può consumare tanta memoria quanta ne è presente sul lavoro dove è in esecuzione. Quando distribuisci un pod, puoi impostare dei limiti alla quantità di memoria che un pod può utilizzare. </td>
  </tr>
  <tr>
    <td>CPU</td>
    <td>*cpu_usage*</td>
    <td>Questa metrica notifica i nanosecondi di tempo della CPU tra tutti i core. <br><br>Quando l'utilizzo della CPU è elevato, potresti riscontrare dei ritardi. Un utilizzo elevato della CPU indica una potenza di elaborazione insufficiente.</td>
  </tr>
  <tr>
    <td>CPU</td>
    <td>*cpu_usage_pct*</td>
    <td>Questa metrica notifica il tempo della CPU utilizzato come una percentuale della capacità della CPU. <br><br>Quando la percentuale dell'utilizzo della CPU è elevata, potresti riscontrare dei ritardi. Un utilizzo elevato della CPU indica una potenza di elaborazione insufficiente.</td>
  </tr>
  <tr>
    <td>CPU</td>
    <td>*cpu_num_cores*</td>
    <td>Questa metrica notifica il numero di core CPU disponibili per il contenitore.</td>
  </tr>
</table>


## Raccolta delle metriche per un contenitore gestito in Bluemix
{: #metrics_containers_bmx_ov}

La seguente figura mostra una vista di alto livello del monitoraggio per {{site.data.keyword.containershort}}:

![Panoramica dei componenti di alto livello per i contenitori distribuiti in un'infrastruttura cloud gestita da {{site.data.keyword.Bluemix_notm}}](images/monitoring_bmx.gif "Panoramica dei componenti di alto livello per i contenitori distribuiti in un'infrastruttura cloud gestita da {{site.data.keyword.Bluemix_notm}}")

Il crawler raccoglie costantemente le seguenti metriche da tutti i contenitori per impostazione predefinita:

* CPU
* Memoria
* Informazioni di rete


## Monitoraggio delle metriche per un contenitore che viene eseguito in un cluster Kubernetes
{: #monitoring_metrics_kube}

Le metriche vengono raccolte e visualizzate sia nell'interfaccia utente Kubernetes che in Grafana:

* Utilizza Grafana, una piattaforma di analisi e virtualizzazione open source, per monitorare, ricercare, analizzare e visualizzare le tue metriche in una varietà di grafici, ad esempio diagrammi e tabelle.
 
    Puoi avviare Grafana da un browser. Per ulteriori informazioni, vedi [Passaggio al dashboard Grafana da un browser web](../grafana/navigating_grafana.html#launch_grafana_from_browser).
    
* Utilizza l'interfaccia utente Kubernetes per visualizzare le metriche per i nodi e i pod. Per ulteriori informazioni,
vedi [Dashboard interfaccia utente web ![(Icona link esterno)](../../../icons/launch-glyph.svg "Icona link esterno")](https://kubernetes.io/docs/tasks/access-application-cluster/web-ui-dashboard/){: new_window}.


## Monitoraggio delle metriche per un contenitore gestito in Bluemix
{: #monitoring_metrics_bmx}

Le metriche vengono raccolte e visualizzate sia nell'interfaccia utente {{site.data.keyword.Bluemix_notm}} che in Grafana:

* Utilizza Grafana, una piattaforma di analisi e virtualizzazione open source, per monitorare, ricercare, analizzare e visualizzare le tue metriche in una varietà di grafici, ad esempio diagrammi e tabelle.
 
    Puoi avviare Grafana dalla IU {{site.data.keyword.Bluemix_notm}} o da un browser. Per ulteriori informazioni, vedi [Passaggio al dashboard Grafana](../grafana/navigating_grafana.html#navigating_grafana).
    

* Utilizza l'interfaccia utente {{site.data.keyword.Bluemix_notm}} per visualizzare le metriche più recenti.

    Per visualizzare le metriche nell'interfaccia utente {{site.data.keyword.Bluemix_notm}}, vedi [Analisi delle metriche per la console Bluemix](analyzing_metrics_bmx_ui.html#analyzing_metrics_bmx_ui).


## Conservazione delle metriche
{: #metrics_retention}

Viene raccolto fino a un punto dati al minuto. Le metriche del contenitore che non sono state scritte per 7 giorni vengono eliminate.
    

