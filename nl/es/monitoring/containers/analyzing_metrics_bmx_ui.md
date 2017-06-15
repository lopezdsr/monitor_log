---

copyright:
  years: 2017

lastupdated: "2017-05-25"

---


{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:screen: .screen}

# Análisis de métricas de contenedor desde la consola de Bluemix
{: #analyzing_metrics_bmx_ui}

En {{site.data.keyword.Bluemix}}, tiene la posibilidad de visualizar y analizar métricas a través del separador *Supervisión* que está disponible para contenedores Docker desplegados en una infraestructura de nube gestionada de {{site.data.keyword.Bluemix_notm}}.  {:shortdesc}

{{site.data.keyword.Bluemix_notm}} Public ofrece funcionalidades integradas de supervisión.  

Considere la siguiente información sobre la disponibilidad de las métricas para realizar análisis y sobre la retención de datos: 

* En {{site.data.keyword.Bluemix_notm}} Public, de forma predeterminada, las métricas se almacenan durante 7 días.  
* Puede almacenar hasta 1 GB de datos por día. 
* De forma predeterminada, las métricas que están disponibles para su análisis desde la consola de {{site.data.keyword.Bluemix_notm}} incluyen datos correspondientes a las últimas 24 horas.

**Sugerencia: ** Utilice Grafana para analizar los datos de un periodo de tiempo personalizado que preceda a las últimas 24 horas. 


##  Navegación a métricas de un contenedor Docker que se gestiona en Bluemix
{: #launch_metrics_tab_bmx_ui_containers}

Para ver las métricas para un contenedor Docker desplegado en una infraestructura de nube gestionada de {{site.data.keyword.Bluemix_notm}}, complete los siguientes pasos: 

1. En el panel de control Apps, pulse en un contenedor o grupo de contenedores. 
    
2. En la página de detalles de la app, pulse **Supervisión y registros**.

3. Seleccione el separador **Supervisión**. 
    
    Desde el separador **Supervisión** visualice las métricas para su contenedor. 
