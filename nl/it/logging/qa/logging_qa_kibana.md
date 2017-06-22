---

copyright:
  years: 2015, 2017

lastupdated: "2017-05-22"

---


{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:screen: .screen}


# Domande frequenti (FAQ) per Kibana
{: #logging_qa_kibana}

Queste sono le risposte alle domandi comuni sull'utilizzo delle funzionalità di registrazione {{site.data.keyword.Bluemix}}. {:shortdesc}

* [Cosa posso fare se non posso visualizzare i dati nella pagina Rileva in Kibana ](logging_qa_kibana.html#logging_qa_no_data_discover_kibana)
* [Cosa posso fare se ricevo un'eccezione di autenticazione ](logging_qa_kibana.html#logging_qa_no_data_dashboard_kibana)
* [Come avvio Kibana 3](logging_qa_kibana.html#logging_qa_kibana3)
* [Perché vedo il simbolo ? accanto ai campi nella pagina Rileva in Kibana](logging_qa_kibana.html#logging_qa_kibana_question)

## Cosa posso fare se non posso visualizzare i dati nella pagina Rileva in Kibana
{: #logging_qa_no_data_discover_kibana}

Esistono vari scenari per cui potresti non visualizzare i dati in Kibana:

1. Quando avvii Kibana, potresti non visualizzare alcun dato nella pagina Rileva. Ricevi il seguente messaggio: **Nessun risultato trovato.**. 
2. Potresti star utilizzando la pagina Rileva in Kibana. Tuttavia, dopo un breve periodo di tempo, ricevi il messaggio: **Nessun risultato trovato.** quando tenti di eseguire un'attività in Kibana.

Per risolvere questo problema, completa la seguente procedura:

1. Controlla che il *Selezionatore di tempo* sia configurato nella pagina Rileva e aumenta il periodo di tempo. 

    **Nota**: per impostazione predefinita, in {{site.data.keyword.Bluemix_notm}}, il *Selezionatore di tempo* è configurato per mostrare i dati degli ultimi 15 minuti.

    Per ulteriori informazioni su come impostare il *Selezionatore di tempo*, vedi [Configurazione di un filtro temporale](../kibana4/k4_filter_logs.html#set_time_filter).
       
2. Fai clic sulla lente di ingrandimento ubicata nella barra di ricerca della pagina *Rileva*. I dati della pagina vengono aggiornati in base alla query di ricerca predefinita.

    In alternativa, puoi impostare un periodo di *Aggiornamento automatico*.

    **Nota**: per impostazione predefinita, in {{site.data.keyword.Bluemix_notm}}, il periodo di *Aggiornamento automatico* è impostato su **DISATTIVO**.
    
    Per ulteriori informazioni su come abilitarlo, vedi [Aggiornamento automatico dei dati](../kibana4/logging_kibana_analize_logs_interactively.html#kibana_discover_view_refresh_interval).



## Cosa posso fare se ricevo un'eccezione di autenticazione
{: #logging_qa_no_data_dashboard_kibana}

Quando non puoi visualizzare i dati nelle tue visualizzazioni in una pagina Dashboard e ricevi il messaggio di errore: **Errore: Eccezione di autorizzazione.**, controlla le tue autorizzazioni per visualizzare i dati in ogni visualizzazione.

Considera le seguenti informazioni:
Puoi configurare una o più visualizzazioni in una pagina Dashboard. Quando la pagina Dashboard effettua una richiesta per raccogliere i dati visualizzati tramite queste visualizzazioni, viene emessa solo una richiesta per tutte le visualizzazioni. Se non disponi delle autorizzazioni per visualizzare i dati per una delle visualizzazioni, l'intera richiesta ha esito negativo.

Per risolvere questo problema, completa la seguente procedura:

1. Identifica le visualizzazioni per cui non disponi delle autorizzazioni.

    1. Fai clic sull'icona *matita* di una visualizzazione nella pagina *Dashboard*. Viene aperta la visualizzazione nella pagina *Visualizza*. In alternativa, nella pagina *Visualizza*, carica una visualizzazione. 
    2. Verifica di poter visualizzare i dati.
    
    Ripeti questi passi per ogni visualizzazione.

2. Richiedi l'accesso per visualizzare i dati per le visualizzazioni all'amministratore cloud.

3. Crea una nuova pagina Dashboard che esclude le visualizzazioni per cui non hai le autorizzazioni mentre hai concesso l'accesso a visualizzare i dati per le visualizzazioni che stanno provocando il problema. 

    Se condividi il Dashboard, non eliminare le visualizzazioni finché questo problema impedirà ad altri membri del team di utilizzare lo stesso dashboard.

## Come avvio Kibana 3
{: #logging_qa_kibana3}

**Nota:** Kibana 3 è obsoleto.

Puoi avviare Kibana 3 da un browser.

Completa il seguente passo per avviare Kibana 3 da un browser:

1. Apri [https://logmet.<span class="keyword" data-hd-keyref="DomainName">DomainName</span>](https://logmet.{DomainName}) per accedere all'interfaccia utente Kibana.
    
2. Seleziona la versione di Kibana che desideri utilizzare per analizzare i tuoi log.
    * Seleziona **Kibana 4** per lavorare con Kibana 4. Viene aperta la pagina Rileva. Per ulteriori informazioni, vedi [logging_kibana_analize_logs_interactively.html#kibana_analize_logs_interactively).
    * Seleziona la scheda **Kibana 3** per lavorare con Kibana 3. Viene aperto il dashboard Kibana predefinito. Per ulteriori informazioni sull'utilizzo di Kibana per analizzare i tuoi log, vedi [Analisi dei log in Kibana 3 (Obsoleto)](../logging_view_kibana3.html#analyzing_logs_Kibana3). Per ulteriori informazioni sulla personalizzazione di un dashboard Kibana 3, vedi [questo post del blog ![Icona link esterno](../../../icons/launch-glyph.svg "Icona link esterno")](https://www.ibm.com/blogs/bluemix/2015/09/creating-custom-kibana-dashboard-in-bluemix/).
     

## Perché vedo il simbolo ? accanto ai campi nella pagina Rileva in Kibana
{: #logging_qa_kibana_question}

Quando apri la pagina Rileva in Kibana, potresti vedere un `?` accanto ai campi elencati nella sezione dei campi disponibili invece del carattere `t`. Quando ricarichi l'elenco di campi, il tipo di campi viene analizzato e `?` viene sostituito dal carattere `t`. Per ulteriori informazioni, vedi [Ricaricamento dell'elenco di campi](../kibana4/logging_kibana_analize_logs_interactively.html#kibana_discover_view_reload_fields).



