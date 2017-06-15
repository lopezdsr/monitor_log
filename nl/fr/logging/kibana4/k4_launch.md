---

copyright:
  years: 2015, 2017

lastupdated: "2017-05-22"

---


{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:screen: .screen}


# Accès au tableau de bord Kibana
{: #k4_launch}

Vous pouvez lancer Kibana depuis l'interface utilisateur {{site.data.keyword.Bluemix}} ou directement depuis un navigateur Web.
{:shortdesc}

Lancez Kibana depuis {{site.data.keyword.Bluemix_notm}} pour visualiser et analyser des données en contexte sur la ressource à partir de laquelle vous lancez Kibana. Par exemple, vous pouvez lancer Kibana sur vos journaux d'application CF spécifiques et dans le contexte de cette application spécifique.
    
Lancez Kibana depuis un lien de navigateur direct si vous souhaitez voir les données de journal agrégées à partir des services d'un espace {{site.data.keyword.Bluemix_notm}} fourni. La requête utilisée pour filtrer les données affichées dans le tableau de bord extrait des entrées de journal pour un espace dans l'organisation {{site.data.keyword.Bluemix_notm}}. Les informations de journal affichées par Kibana incluent des enregistrements pour toutes les ressources déployées dans l'espace de l'organisation {{site.data.keyword.Bluemix_notm}} à laquelle vous êtes connecté. 

Le tableau suivant recense les ressources et la méthode de navigation prise en charge pour lancer Kibana :

<table>
<caption>Tableau 1. Liste des ressources et des méthodes de navigation prises en charge. </caption>
  <tr>
    <th>Ressource</th>
    <th>Accès au tableau de bord Kibana depuis le tableau de bord Bluemix</th>
    <th>Accès au tableau de bord Kibana depuis un navigateur Web</th>
  <tr>
  <tr>
    <td>Application CF</td>
    <td>Oui</td>
    <td>Oui</td>
  <tr>  
  <tr>
    <td>Conteneur déployé dans un cluster Kubernetes</td>
    <td>Non</td>
    <td>Oui</td>
  <tr>  
  <tr>
    <td>Conteneur déployé dans une infrastructure de cloud gérée par {{site.data.keyword.Bluemix_notm}}</td>
    <td>Oui</td>
    <td>Oui</td>
  <tr>  
</table>

Pour plus d'informations sur Kibana, reportez-vous au manuel [Kibana User Guide ![Icône de lien externe](../../../icons/launch-glyph.svg "Icône de lien externe")](https://www.elastic.co/guide/en/kibana/4.1/index.html){: new_window}.
    

##  Accès au tableau de bord Kibana depuis le tableau de bord Bluemix
{: #launch_Kibana_from_bluemix}

La requête utilisée pour filtrer les données affichées dans Kibana extrait les entrées de journal pour {{site.data.keyword.Bluemix_notm}} l'application CF ou le conteneur depuis lequel vous lancez Kibana.

Pour consulter les journaux d'une application Cloud Foundry ou d'un conteneur Docker dans Kibana, procédez comme suit :

1. Connectez-vous à {{site.data.keyword.Bluemix_notm}}, puis cliquez sur le nom de l'application ou du conteneur dans le tableau de bord {{site.data.keyword.Bluemix_notm}}. 
    
2. Ouvrez l'onglet des journaux dans l'interface utilisateur {{site.data.keyword.Bluemix_notm}}.

    * Pour les applications CF, cliquez sur **Journaux** dans la barre de navigation. 
    * Dans le cas de conteneurs déployés dans une infrastructure de cloud gérée par {{site.data.keyword.Bluemix_notm}}, sélectionnez **Surveillance et journaux** dans la barre de navigation, puis cliquez sur l'onglet **Journalisation**. 
    
        L'onglet Journaux s'affiche.  

3. Cliquez sur **Vue avancée**. Le tableau de bord Kibana s'ouvre.

    Par défaut, la page **Discover** (Reconnaître) est chargée avec le canevas d'index par défaut et un filtre temporel est défini sur les 30 dernières secondes. La requête de recherche est configurée pour porter sur toutes les entrées concernant votre application CF ou votre conteneur Docker.

    Si la page Discover n'affiche aucune entrée de journal, ajustez le sélecteur de période. Pour plus d'informations, voir [Configuration d'un filtre temporel](logging_kibana_set_time_filter.html#set_time_filter).


##  Accès au tableau de bord Kibana depuis un navigateur Web
{: #launch_Kibana_from_browser}

La requête utilisée pour filtrer les données affichées dans Kibana extrait les entrées de journal pour un espace dans l'organisation {{site.data.keyword.Bluemix_notm}}. Les informations de journal affichées par Kibana incluent des enregistrements pour toutes les ressources déployées dans l'espace de l'organisation {{site.data.keyword.Bluemix_notm}} à laquelle vous êtes connecté.

Procédez comme suit pour lancer Kibana depuis un navigateur :

1. Accédez à l'URL [https://logging.<span class="keyword" data-hd-keyref="DomainName">nom_domaine</span>](https://logging.{DomainName}) pour vous connecter à l'interface utilisateur de Kibana.
    
    Par exemple 
      
        <table>
          <caption>Tableau 1. URL pour lancement de Kibana  </caption>
           <tr>
            <th>Région</th>
            <th>URL</th>
          </tr>
          <tr>
            <td>Sud des États-Unis</td>
            <td>https://logging.ng.bluemix.net/ </td>
          </tr>
          <tr>
            <td>Royaume-Uni</td>
            <td>https://logging.eu-gb.bluemix.net/ </td>
          </tr>
        </table>

    Si la page Discover n'affiche aucune entrée de journal, ajustez le sélecteur de période. Pour plus d'informations, voir [Configuration d'un filtre temporel](logging_kibana_set_time_filter.html#set_time_filter).


