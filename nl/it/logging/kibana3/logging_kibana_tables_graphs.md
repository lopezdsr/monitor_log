---

copyright:
  years: 2016, 2017
lastupdated: "2017-02-07"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}


# Creazione di tabelle e grafici dalle query in Kibana
{: #logging_kibana_tables_graphs}


Utilizza Kibana per creare grafici e tabelle di query per visualizzare i tuoi dati di log e confrontare i risultati. Puoi accedere al dashboard Kibana dalla scheda **Log** della tua applicazione Cloud Foundry. 
{:shortdesc}

Il dashboard Kibana si articola in una serie di righe, in cui ogni riga contiene uno o più pannelli. Puoi configurare i pannelli per visualizzare le rappresentazioni grafiche dei tuoi dati. Utilizza le query per determinare quali dati visualizzare. Per creare un grafico o una tabella, devi prima creare una riga vuota e quindi creare un pannello. Se accedi al dashboard Kibana dalla scheda **Log** della tua applicazione CF, il dashboard visualizza automaticamente due pannelli: un istogramma e una tabella.

Completa le seguenti attività per aggiungere un grafico o una tabella nel dashboard Kibana:

1. Per accedere alla scheda **Log** della tua applicazione Cloud Foundry, fai clic sul nome applicazione nella tabella **Applicazioni Cloud Foundry** del dashboard **Applicazioni** {{site.data.keyword.Bluemix_notm}}; fai quindi clic sulla scheda **Log**. Vengono visualizzati i log della tua applicazione.

2. Per accedere alla visualizzazione del dashboard Kibana per la tua applicazione, fai clic su **Vista avanzata** ![link Vista avanzata](images/logging_advanced_view.jpg "Advanced view link"). Viene visualizzato il dashboard Kibana.

3. Nel dashboard Kibana, scorri alla fine del dashboard e fai clic su **AGGIUNGI UNA RIGA** ![icona Aggiungi una riga](images/logging_add_row.jpg "Add a row icon") per creare una riga per il pannello che vuoi aggiungere. Viene visualizzato il riquadro Impostazioni dashboard. 
	
	![Riquadro Impostazioni dashboard](images/logging_dashboard_settings.jpg "Dashboard settings pane")
	
	Nel riquadro Aggiungi riga, immetti un nome per la riga nel campo **Titolo** e fai quindi clic su **Crea riga**. Viene aggiunta una nuova riga. Puoi regolare l'ordine delle righe facendo clic sulle icone **Freccia su** o **Freccia giù** accanto ai titoli delle righe. Una volta impostato l'ordine delle righe, fai clic su **Salva**. Viene creata una riga vuota nel dashboard Kibana.

4. Aggiungi un pannello facendo clic su **Aggiungi pannello alla riga vuota**. Viene visualizzato il riquadro Impostazioni riga.

    ![Riquadro Impostazioni riga](images/logging_row_settings.jpg "Row settings pane")
	
	Puoi scegliere diversi tipi di pannelli come **tabella**, **istogramma** o **termini** dall'elenco a discesa **Seleziona tipo di pannello**. Seleziona **termini** per creare un grafico a barre, un grafico a torta o una tabella basata sulle tue query. Nel riquadro Impostazioni riga viene visualizzata una serie di opzioni di configurazione.
	
	![Aggiunta di un pannello nel riquadro Impostazioni riga](images/logging_add_panel.jpg "Adding a panel in the row settings pane")
	
	Configura il pannello. Immetti un **Titolo** per la visualizzazione grafica. Seleziona la **Larghezza** del pannello dall'elenco a discesa; questo valore determina la larghezza del pannello all'interno del dashboard. Nella sezione Parametri, elimina il contenuto di **Campo** e immetti un campo di log valido, ad esempio `instance_id`. 

5. Nella sezione Opzioni di visualizzazione, seleziona **barra**, **torta** o **tabella** dall'elenco a discesa **Stile** per scegliere un grafico a barre, un grafico a torta o una tabella. Nella sezione Query, seleziona **selezionati** dall'elenco a discesa **Query** per utilizzare i dati di log delle tue query nel dashboard. Infine, fai clic su **Salva**. Il tuo nuovo pannello viene visualizzato nel dashboard.

	![Dashboard che visualizza il pannello con un grafico a barre](images/logging_bar_chart_panel.jpg "Dashboard displaying panel containing bar chart")
	
6. Per modificare questo pannello in modo che visualizzi una tabella, fai clic sull'icona **Configur** ![icona Configura](images/logging_dashboard_config_panel.jpg "Configure icon"). Viene visualizzato il riquadro Impostazioni termini. 

	![Riquadro Impostazioni termini](images/logging_terms_settings.jpg "Terms Settings pane")
	
	Fai clic sulla scheda **Panello**, quindi seleziona **tabella** dall'elenco a discesa **Stile**. Fai clic su **Salva** per aggiornare il pannello e ritornare al dashboard.

7. Aggiungi ulteriori righe e pannelli al tuo dashboard. Quando hai finito, salva le modifiche al dashboard facendo clic sull'icona **Salva**.

    **Nota:** un dashboard con un nome che contiene spazi vuoti non verrà salvato. Immetti un nome senza spazi e fai clic sull'icona **Salva**.

    ![Salva nome del dashboard](images/logging_save_dashboard.jpg "Save dashboard name").


