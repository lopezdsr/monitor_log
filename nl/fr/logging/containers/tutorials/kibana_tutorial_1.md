---

copyright:
  years: 2015, 2017

lastupdated: "2017-05-23"

---


{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:screen: .screen}


# Analyse dans Kibana des journaux d'une application déployée dans un cluster Kubernetes
{: #kibana_tutorial_1}

Familiarisez-vous avec Kibana. Découvrez comment rechercher et analyser des journaux de conteneurs pour une application déployée dans un cluster Kubernetes.
{:shortdesc}

**Remarque :** Pour suivre ce tutoriel, exécutez les tutoriels des différentes étapes associées.

## Prérequis
{: #prereq}

1. Etre membre ou propriétaire d'un compte Bluemix et disposer des autorisations de création de clusters Kubernetes, de déploiement d'applications dans des clusters, et d'interrogation des journaux Bluemix pour analyse avancée dans Kibana.

2. Disposer d'une session de terminal depuis laquelle vous pouvez gérer le cluster Kubernetes et déployer des applications depuis la ligne de commande. Les exemples de ce tutoriel se réfèrent à un système Ubuntu Linux.

3. [Installez les interfaces CLI](../../../../containers/cs_cli_install.html#cs_cli_install_steps) dans votre système Ubuntu afin de gérer le service IBM Bluemix Container depuis la ligne de commande. 


## Etape 1 : Configuration et mise en route de Kubernetes dans Bluemix
{: #step1}

Procédez comme suit :

1. [Créez un cluster Kubernetes](../../../../containers/cs_cluster.html#cs_cluster_ui).

2. [Configurez le contexte de cluster](../../../../containers/cs_cli_install.html#cs_cli_configure) dans un terminal Linux. Une fois le contexte défini, vous pouvez gérer le cluster Kubernetes et déployer l'application dans ce cluster.

## Etape 2 : Déploiement d'une application dans le cluster Kubernetes
{: #step2}

Déployez et exécutez un exemple d'application dans le cluster Kubernetes. [Exécutez les tâches de la leçon 1](../../../../containers/cs_tutorials.html#cs_apps_tutorial).

L'application est une application node js Hello World :

```
var express = require('express')
var app = express()

app.get('/', function(req, res) {
  res.send('Hello world! Votre application est en opération dans un cluster !\n')
})
app.listen(8080, function() {
  console.log('L'exemple d'application est à l'écoute sur le port 8080.')
})
```

Lorsque l'application est déployée, le collecte de journaux est automatiquement activée pour les entrées de journal envoyées par l'application vers les flux stdout (sortie standard) et stderr (erreur standard). 

Dans cet exemple d'application, lorsque vous testez votre application dans un navigateur, l'application consigne dans stdout le message suivant : `L'exemple d'application est à l'écoute sur le port 8080.`


## Etape 3 : Analyse des données de journal dans Kibana
{: #step3}

1. Lancez Kibana depuis un navigateur.  

    Pour analyser les données de journal pour un cluster, vous devez accéder à Kibana dans la région cloud Public où le cluster a été créé. 
    
    Choisissez l'URL correcte en fonction de la région où vous avez créé le cluster Kubernetes à l'étape précédente :

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
           <tr>
             <td>Francfort</td>
             <td>https://logging.eu-de.bluemix.net/ </td>
           </tr>
    </table>
    
    Ensuite, à partir d'un navigateur, lancez l'URL pour ouvrir Kibana.
    
2. Sur la page **Discover**(Reconnaître), examinez les événements qui sont affichés. 

    L'exemple d'application Hello-World génère un seul événement.
    
    ![Page Discover dans Kibana](images/sampleapp_2.gif "Page Discover dans Kibana")
    
    La section *Zones disponibles* affiche la liste des zones que vous pouvez utiliser pour définir de nouvelles requêtes ou pour filtrer les entrées dans le tableau affiché sur la page.
    
    Le tableau suivant répertorie les zones communes que vous pouvez utiliser pour définir de nouvelles requêtes de recherche. Il comprend également des exemples de valeurs correspondant à l'événement généré par l'exemple d'application :
    
     <table>
              <caption>Tableau 2. Zones communes aux journaux de conteneurs </caption>
               <tr>
                <th align="center">Zone</th>
                <th align="center">Description</th>
                <th align="center">Exemple</th>
              </tr>
              <tr>
                <td>*docker.container_id_str*</td>
                <td> La valeur de cette zone correspond à l'identificateur global unique du conteneur qui exécute l'application dans une nacelle du cluster Kubernetes.</td>
                <td></td>
              </tr>
              <tr>
                <td>*ibm-containers.region_str*</td>
                <td>La valeur de cette zone correspond à la région {{site.data.keyword.Bluemix_notm}} où l'entrée de journal est collectée.</td>
                <td>us-south</td>
              </tr>
              <tr>
                <td>*kubernetes.container_name_str*</td>
                <td>La valeur de cette zone indique le nom du conteneur.</td>
                <td>hello-world-deployment</td>
              </tr>
              <tr>
                <td>*kubernetes.host*</td>
                <td>La valeur de cette zone indique l'adresse IP publique disponible pour accès à l'application depuis Internet. </td>
                <td>xxx.xx.xxx.xxx</td>
              </tr>
              <tr>
                <td>*kubernetes.labels.label_name*</td>
                <td>Les zones de libellé sont facultatives. Vous pouvez ne pas les utiliser ou en utiliser plusieurs. Chaque libellé débute par le préfixe `kubernetes.labels.`, suivi du *label_name* (nom du libellé). </td>
                <td>Dans l'exemple d'application, vous pouvez observer 2 libellés : <br>* *kubernetes.labels.pod-template-hash_str* = 3355293961 <br>* *kubernetes.labels.run_str* =	hello-world-deployment  </td>
              </tr>
              <tr>
                <td>*kubernetes.namespace_name_str*</td>
                <td>La valeur de cette zone indique l'espace de nom Kubernetes sous lequel la nacelle s'exécute. </td>
                <td>default</td>
              </tr>
              <tr>
                <td>*kubernetes.pod_id_str*</td>
                <td>La valeur de cette zone correspond à l'identificateur global unique de la nacelle dans laquelle le conteneur s'exécute.</td>
                <td>d695f346-xxxx-xxxx-xxxx-aab0b50f7315</td>
              </tr>
              <tr>
                <td>*kubernetes.pod_name_str*</td>
                <td>La valeur de cette zone indique le nom de la capsule.</td>
                <td>hello-world-deployment-3xxxxxxx1-xxxxx8</td>
              </tr>
              <tr>
                <td>*message*</td>
                <td>Message complet consigné par l'application.</td>
                <td>L'exemple d'application est à l'écoute sur le port 8080.</td>
              </tr>
        </table>
    
    
    
3. Filtrez les données sur la page *Discover* (Reconnaître).  

    Dans le tableau, vous pouvez observer toutes les entrées disponibles pour une analyse. Les entrées répertoriées découlent de la requête de recherche affichée dans la barre *Rechercher*. Vous pouvez utiliser le caractère `*` afin d'afficher toutes les entrées correspondant à la période configurée pour la page. 
    
    Par exemple, pour filtrer les entrées par espace de nom Kubernetes, modifiez la requête dans la barre *Rechercher*. Ajoutez un filtre basé sur la zone personnalisée *kubernetes.namespace_name_str*:
    
    1. Dans la section **Zones disponibles**, sélectionnez la zone *kubernetes.namespace_name_str*. Un sous-ensemble des valeurs disponibles pour la zone est affiché.    
    
    2. Sélectionnez la valeur **default**. Il s'agit de l'espace de nom où vous avez déployé dans une étape antérieure l'exemple d'application.
    
        Après avoir sélectionné la valeur, un filtre est ajouté à la *Barre de recherche* et le tableau n'affiche plus que les entrées correspondant au critère que vous venez de sélectionner.     
    
    ![Filtre de recherche de l'espace de nom Kubernetes par défaut](images/sampleapp_k4_1.gif "Filtre de recherche de l'espace de nom Kubernetes par défaut")
    
    Vous pouvez sélectionner le symbole d'édition du filtre pour modifier le nom de l'espace de nom à rechercher.   
    
    ![Actions disponibles pour un filtre](images/sampleapp_k4_1.gif "Actions disponibles pour un filtre")
    
    La requête suivante est affichée :
    
    ```{
        "query": {
          "match": {
            "kubernetes.namespace_name_str": {
              "query": "default",
              "type": "phrase"
            }
          }
        }
      }
    ```
    
    Pour rechercher des entrées dans un espace de nom différent (par exemple, *mynamespace1*), modifiez comme suit la requête :
    
    ```{
        "query": {
          "match": {
            "kubernetes.namespace_name_str": {
              "query": "mynamespace1",
              "type": "phrase"
            }
          }
        }
      }
    ```
    

    Si vous ne voyez pas de données, essayez de changer le filtre temporel. Pour plus d'informations, voir [Définition d'un filtre temporel](../../kibana4/k4_filter_logs.html#set_time_filter).
    


Pour plus d'informations, voir [Filtrage des journaux dans Kibana](../../kibana4/k4_filter_logs.html#k4_filter_logs).

