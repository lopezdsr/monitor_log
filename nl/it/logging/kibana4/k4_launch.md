---

copyright:
  years: 2015, 2017

lastupdated: "2017-05-22"

---


{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:screen: .screen}


# Passaggio al dashboard Kibana
{: #k4_launch}

Puoi avviare Kibana dall'interfaccia utente {{site.data.keyword.Bluemix}} o direttamente da un browser web.
{:shortdesc}

Avvia Kibana da {{site.data.keyword.Bluemix_notm}} per visualizzare e analizzare i dati nel contesto della risorsa da cui avvii Kibana. Ad esempio, puoi eseguire l'avvio ai log della tua specifica applicazione CF in Kibana, nel contesto di quella specifica applicazione.
    
Avvia Kibana da un link diretto del browser se vuoi visualizzare i dati di log aggregati provenienti dai servizi all'interno di uno spazio {{site.data.keyword.Bluemix_notm}} specifico. La query che viene utilizzata per filtrare i dati visualizzati nel dashboard richiama le voci di log per uno spazio nell'organizzazione {{site.data.keyword.Bluemix_notm}}. Le informazioni di log visualizzate da Kibana includono i record per tutte le risorse che vengono distribuite all'interno dello spazio dell'organizzazione {{site.data.keyword.Bluemix_notm}} a cui sei connesso. 

La seguente tabella elenca le risorse e il metodo di navigazione supportato per avviare Kibana:

<table>
<caption>Tabella 1. Elenco di risorse e metodi di navigazione supportati.</caption>
  <tr>
    <th>Risorsa</th>
    <th>Passaggio al dashboard Kibana dal dashboard Bluemix</th>
    <th>Passaggio al dashboard Kibana da un browser web</th>
  <tr>
  <tr>
    <td>Applicazione CF</td>
    <td>Sì</td>
    <td>Sì</td>
  <tr>  
  <tr>
    <td>Contenitore distribuito in un cluster Kubernetes</td>
    <td>No</td>
    <td>Sì</td>
  <tr>  
  <tr>
    <td>Contenitore distribuito in un'infrastruttura cloud gestita da {{site.data.keyword.Bluemix_notm}}</td>
    <td>Sì</td>
    <td>Sì</td>
  <tr>  
</table>

Per ulteriori informazioni su Kibana, vedi [Kibana User Guide ![Icona link esterno](../../../icons/launch-glyph.svg "Icona link esterno")](https://www.elastic.co/guide/en/kibana/4.1/index.html){: new_window}.
    

##  Passaggio al dashboard Kibana dal dashboard Bluemix
{: #launch_Kibana_from_bluemix}

La query che viene utilizzata per filtrare i dati visualizzati in Kibana richiama le voci di log per l'applicazione CF o il contenitore {{site.data.keyword.Bluemix_notm}} da cui è stato avviato Kibana.

Per visualizzare i log di un'applicazione Cloud Foundry o un contenitore Docker in Kibana, completa la seguente procedura:

1. Accedi a {{site.data.keyword.Bluemix_notm}} e fai clic sul nome applicazione o sul contenitore dal dashboard {{site.data.keyword.Bluemix_notm}}. 
    
2. Apri la scheda del log nella IU {{site.data.keyword.Bluemix_notm}}.

    * Per le applicazioni CF, fai clic su **Log** nella barra di navigazione. 
    * Per i contenitori distribuiti nell'infrastruttura cloud gestita da {{site.data.keyword.Bluemix_notm}}, seleziona **Monitoraggio e log** nella barra di navigazione e fai quindi clic sulla scheda **Registrazione**. 
    
        Viene visualizzata la scheda Log.  

3. Fai clic su **Vista avanzata**. Viene aperto il dashboard Kibana.

    Per impostazione predefinita, la pagina **Ricerca** viene caricata con il modello di indice predefinito selezionato e un filtro temporale impostato sugli ultimi 30 secondi. La query di ricerca è configurata per corrispondere a tutte le voci per la tua applicazione CF o contenitore Docker.

    Se la pagina Rileva non mostra alcuna voce di log, modifica il selezionatore di tempo. Per ulteriori informazioni, vedi [Configurazione di un filtro temporale](logging_kibana_set_time_filter.html#set_time_filter).


##  Passaggio al dashboard Kibana da un browser web
{: #launch_Kibana_from_browser}

La query utilizzata per filtrare i dati visualizzati in Kibana richiama le voci di log per uno spazio nell'organizzazione {{site.data.keyword.Bluemix_notm}}. Le informazioni di log visualizzate da Kibana includono i record per tutte le risorse che vengono distribuite all'interno dello spazio dell'organizzazione {{site.data.keyword.Bluemix_notm}} a cui sei connesso.

Completa il seguente passo per avviare Kibana da un browser:

1. Apri [https://logging.<span class="keyword" data-hd-keyref="DomainName">NmeDominio</span>](https://logging.{DomainName}) per accedere all'interfaccia utente Kibana.
    
    Ad esempio, 
      
        <table>
          <caption>Tabella 1. URL per avviare Kibana </caption>
           <tr>
            <th>Regione</th>
            <th>URL</th>
          </tr>
          <tr>
            <td>Stati Uniti Sud</td>
            <td>https://logging.ng.bluemix.net/ </td>
          </tr>
          <tr>
            <td>Regno Unito</td>
            <td>https://logging.eu-gb.bluemix.net/ </td>
          </tr>
        </table>

    Se la pagina Rileva non mostra alcuna voce di log, modifica il selezionatore di tempo. Per ulteriori informazioni, vedi [Configurazione di un filtro temporale](logging_kibana_set_time_filter.html#set_time_filter).


