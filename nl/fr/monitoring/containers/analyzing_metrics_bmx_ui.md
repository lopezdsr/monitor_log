---

copyright:
  years: 2017

lastupdated: "2017-05-25"

---


{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:screen: .screen}

# Analyse des métriques de conteneur depuis la console Bluemix
{: #analyzing_metrics_bmx_ui}

Dans {{site.data.keyword.Bluemix}}, vous pouvez visualiser, filtrer et analyser des métriques via l'onglet *Surveillance* disponible pour les conteneurs Docker déployés dans une infrastructure de cloud gérée par {{site.data.keyword.Bluemix_notm}}.
{:shortdesc}

{{site.data.keyword.Bluemix_notm}} Public comporte des fonctions de surveillance intégrées. 

Prenez en compte les informations suivantes sur la disponibilité de métriques pour l'analyse et la conservation des données :

* Dans {{site.data.keyword.Bluemix_notm}} Public, les métriques sont conservées par défaut pendant 7 jours. 
* Vous pouvez stocker jusqu'à 1 Go de données par jour. 
* Par défaut, les métriques disponibles pour analyse depuis la console {{site.data.keyword.Bluemix_notm}} couvrent les données des dernières 24 heures.

**Conseil :** utilisez Grafana pour analyser les données d'une période personnalisée antérieure aux dernières 24 heures.


##  Accès aux métriques d'un conteneur Docker géré dans Bluemix
{: #launch_metrics_tab_bmx_ui_containers}

Pour examiner les métriques d'un conteneur Docker déployé dans l'infrastructure de cloud gérée par {{site.data.keyword.Bluemix_notm}}, procédez comme suit :

1. Dans le tableau de bord Applications, cliquez sur le nom du conteneur unique ou du groupe de conteneurs. 
    
2. Dans la page des informations d'application détaillées, cliquez sur **Surveillance et journaux**.

3. Sélectionnez l'onglet **Surveillance**.
    
    Depuis l'onglet **Surveillance**, vous pouvez examiner les métriques de votre conteneur.
