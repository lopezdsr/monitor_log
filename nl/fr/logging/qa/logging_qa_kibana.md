---

copyright:
  years: 2015, 2017

lastupdated: "2017-05-22"

---


{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:screen: .screen}


# Foire aux questions concernant Kibana
{: #logging_qa_kibana}

Ci-après figurent des réponses sur des questions fréquentes concernant l'utilisation des fonctionnalités de journalisation de {{site.data.keyword.Bluemix}}. {:shortdesc}

* [Comment procéder si je ne vois pas de données dans la page Discover de Kibana ?](logging_qa_kibana.html#logging_qa_no_data_discover_kibana)
* [Que faire en cas de renvoi d'une exception d'authentification ?](logging_qa_kibana.html#logging_qa_no_data_dashboard_kibana)
* [Comment lancer Kibana 3 ?](logging_qa_kibana.html#logging_qa_kibana3)
* [Pourquoi le symbole ? s'affiche-t-il en regard de zones sur la page Kibana Discover ?](logging_qa_kibana.html#logging_qa_kibana_question)

## Comment procéder si je ne vois pas de données dans la page Discover de Kibana ?
{: #logging_qa_no_data_discover_kibana}

Il se peut que vous ne puissiez pas voir de données dans Kibana sous différents scénarios :

1. Lorsque vous lancez Kibana, il se peut que vous ne voyiez pas de données dans la page Discover. Vous recevez alors le message suivant : **No results found.** (Aucun résultat trouvé) . 
2. Il se peut que vous travailliez sur la page Discover dans Kibana. Toutefois, après un bref délai, vous recevez le message : **No results found.** (Aucun résultat trouvé) lorsque vous essayez d'effectuer une tâche dans Kibana.

Pour résoudre ce problème, procédez comme suit :

1. Vérifiez le *sélecteur de période* défini sur la page Discover et rallongez la période. 

    **Remarque **: par défaut, dans {{site.data.keyword.Bluemix_notm}}, le *sélecteur de période* est configuré pour afficher les données des 15 dernières minutes.

    Pour plus d'informations sur la définition du *Sélecteur de période*, voir [Définition d'un sélecteur de période](../kibana4/k4_filter_logs.html#set_time_filter).
       
2. Cliquez sur la loupe située dans la barre de recherche de la page *Discover*. Les données de la page sont actualisées compte tenu de la requête de recherche par défaut.

    Vous pouvez également définir une période d'*actualisation automatique*.

    **Remarque **: par défaut, dans {{site.data.keyword.Bluemix_notm}}, la période d'*actualisation automatique* est configurée sur **OFF** (désactivée).
    
    Pour plus d'informations sur son activation, voir [Actualisation automatique des données](../kibana4/logging_kibana_analize_logs_interactively.html#kibana_discover_view_refresh_interval).



## Que faire en cas de renvoi d'une exception d'authentification ?
{: #logging_qa_no_data_dashboard_kibana}

Lorsque vous ne pouvez pas voir de données affichées dans vos visualisations sur une page du tableau de bord et que vous rencontrez le message d'erreur : **Error: Authorization Exception.** (Erreur : exception d'autorisation), vérifiez que vous disposez des autorisations nécessaires pour voir les données dans chaque visualisation.

Prenez en compte les informations suivantes :
vous pouvez configurer une ou plusieurs visualisations dans une page du tableau de bord. Lorsque la page du tableau de bord demande de collecter les données affichées via ces visualisations, une seule requête est soumise pour toutes les visualisations. Si vous n'êtes pas autorisé à examiner les données d'une de ces visualisations, la requête complète échoue.

Pour résoudre ce problème, procédez comme suit :

1. Identifiez les visualisations pour lesquelles vous ne disposez pas d'autorisations.

    1. Cliquez sur l'icône en forme de *crayon* d'une visualisation sur la page *Dashboard* (Tableau de bord). La visualisation s'ouvre dans la page *Visualize* (Visualiser). Vous pouvez aussi charger une visualisation dans la page *Visualize*. 
    2. Vérifiez que vous pouvez voir des données.
    
    Répétez ces étapes pour chaque visualisation.

2. Demandez à votre administrateur de cloud de vous accorder un accès aux données de ces visualisations.

3. Créez une nouvelle page de tableau de bord excluant les visualisations pour lesquelles une autorisation d'accès aux données ne vous a pas été octroyée et qui causent le problème. 

    Si vous partagez le tableau de bord, ne supprimez pas de visualisations car ceci affecterait d'autres membres de l'équipe qui utilisent le même tableau de bord.

## Comment lancer Kibana 3
{: #logging_qa_kibana3}

**Remarque :** la version Kibana 3 est obsolète.

Vous pouvez lancer Kibana 3 depuis un navigateur.

Procédez comme suit pour lancer Kibana 3 depuis un navigateur :

1. Ouvrez [https://logmet.<span class="keyword" data-hd-keyref="DomainName">NomDomaine</span>](https://logmet.{DomainName}) pour vous connecter à l'interface utilisateur Kibana.
    
2. Sélectionnez la version Kibana à utiliser pour analyser vos journaux.
    * Sélectionnez l'onglet **Kibana 4** si vous désirez utiliser cette version. La page Discovery (Reconnaissance) s'ouvre. Pour plus d'informations, voir [logging_kibana_analize_logs_interactively.html#kibana_analize_logs_interactively).
    * Sélectionnez l'onglet **Kibana 3** si vous désirez utiliser cette version. Le tableau de bord Kibana par défaut s'ouvre. Pour plus d'informations sur l'utilisation de Kibana 3 pour analyser vos journaux, voir [Analyse de journaux dans Kibana 3 (Obsolète)](../logging_view_kibana3.html#analyzing_logs_Kibana3). Pour plus d'informations sur la personnalisation d'un tableau de bord Kibana 3, voir cet [article de blogue ![Icône de lien externe](../../../icons/launch-glyph.svg "Icône de lien externe")](https://www.ibm.com/blogs/bluemix/2015/09/creating-custom-kibana-dashboard-in-bluemix/).
     

## Pourquoi le symbole ? s'affiche-t-il sur la page Kibana Discover ?
{: #logging_qa_kibana_question}

Lorsque vous ouvrez la page Discover dans Kibana, vous pourriez rencontrer un signe `?` en regard de zones répertoriées comme disponibles au lieu du caractère `t`. Lorsque vous rechargez la liste des zones, le type des zones est analysé et le signe `?` est remplacé par le caractère `t`. Pour plus d'informations, voir [Rechargement de la liste de zones](../kibana4/logging_kibana_analize_logs_interactively.html#kibana_discover_view_reload_fields).



