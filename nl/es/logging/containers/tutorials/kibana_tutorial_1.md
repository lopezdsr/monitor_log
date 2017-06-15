---

copyright:
  years: 2015, 2017

lastupdated: "2017-05-23"

---


{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:screen: .screen}


# Análisis de registros en Kibana para una app desplegada en un clúster Kubernetes
{: #kibana_tutorial_1}

Empiece hoy mismo a trabajar con Kibana. Aprenda a buscar y analizar los registros de contenedor de una app desplegada en un clúster Kubernetes. {:shortdesc}

**Nota:** Para completar esta guía de aprendizaje, complete las otras guías de aprendizaje enlazadas desde los distintos pasos. 

## Requisitos previos
{: #prereq}

1. Debe ser un miembro o un propietario de una cuenta Bluemix con permisos para crear clústeres Kubernetes, desplegar apps en clústeres y realizar consultas en los registros de Bluemix para un análisis avanzado en Kibana. 

2. Tener una sesión de terminal desde la que gestionar el clúster Kubernetes y desplegar apps desde la línea de mandatos. Los ejemplos en esta guía de aprendizaje se proporcionan para un sistema Ubuntu Linux. 

3. [Instalar los plugins de interfaz de línea de mandatos](../../../../containers/cs_cli_install.html#cs_cli_install_steps) en su sistema Ubuntu para gestionar el servicio IBM Bluemix Container desde la línea de mandatos.  


## Paso 1: Preparar y ejecutar un clúster Kubernetes en Bluemix
{: #step1}

Siga estos pasos:

1. [Crear un clúster Kubernetes](../../../../containers/cs_cluster.html#cs_cluster_ui).

2. [Configurar el contexto del clúster](../../../../containers/cs_cli_install.html#cs_cli_configure) en un terminal Linux. Después de haber configurado el contexto, podrá gestionar el clúster Kubernetes y desplegar la aplicación en dicho clúster Kubernetes. 

## Paso 2: Desplegar una app en el clúster Kubernetes 
{: #step2}

Desplegar y ejecutar una app de ejemplo en el clúster Kubernetes. [Complete los pasos de la lección 1](../../../../containers/cs_tutorials.html#cs_apps_tutorial).

La app es una app node.js Hello World: 

```
var express = require('express')
var app = express()

app.get('/', function(req, res) {
  res.send('Hello world! Your app is up and running in a cluster!\n')
})
app.listen(8080, function() {
  console.log('Sample app is listening on port 8080.')
})
```

Cuando se despliega la app, la recopilación del registro se habilita de forma automática para todas las entradas de registro que envíe la app a stdout (salida estándar) y stderr (error estándar).  

En esta app de ejemplo, cuando prueba la app en un navegador, la app escribe en la salida estándar el siguiente mensaje: `Sample app is listening on port 8080.`


## Paso 3: Analizar datos de registro en Kibana
{: #step3}

1. Inicie Kibana desde un navegador.  

    Para analizar los datos de registro para un clúster, debe acceder a Kibana en la región Pública de la nube en la que se ha creado el clúster.  
    
    Elija el URL correcto de acuerdo a la región en la que creó el clúster Kubernetes en el paso anterior: 

    <table>
      <caption>Tabla 1. URL para iniciar Kibana  </caption>
        <tr>
          <th>Región</th>
          <th>URL</th>
         </tr>
         <tr>
           <td>EE.UU. sur</td>
           <td>https://logging.ng.bluemix.net/ </td>
          </tr>
          <tr>
            <td>Reino Unido</td>
            <td>https://logging.eu-gb.bluemix.net/ </td>
           </tr>
           <tr>
             <td>Frankfurt</td>
             <td>https://logging.eu-de.bluemix.net/ </td>
           </tr>
    </table>
    
    A continuación, desde un navegador, inicie el URL para abrir Kibana. 
    
2. En la página **Descubrir**, mire los sucesos que se visualizan.  

    La aplicación Hello-World genera un suceso. 
    
    ![Página Descubrir en Kibana](images/sampleapp_2.gif "Página Descubrir en Kibana")
    
    En la sección *Campos disponibles*, puede ver una lista de campos para utilizar para definir nuevas consultas o para filtrar las entradas que aparecen listadas en la tabla que se visualiza en la página. 
    
    En la siguiente tabla se muestra una lista de campos comunes que puede utilizar para definir nuevas consultas de búsquedas. En la tabla también se incluyen valores de ejemplo que corresponden al suceso que la app de ejemplo genera: 
    
     <table>
              <caption>Tabla 2. Campos comunes para registros de contenedor </caption>
               <tr>
                <th align="center">Campo</th>
                <th align="center">Descripción</th>
                <th align="center">Ejemplo</th>
              </tr>
              <tr>
                <td>*docker.container_id_str*</td>
                <td> El valor de este campo corresponde al GUID del contenedor que ejecuta la app en un pod del clúster Kubernetes. </td>
                <td></td>
              </tr>
              <tr>
                <td>*ibm-containers.region_str*</td>
                <td>El valor de este campo corresponde a la región de {{site.data.keyword.Bluemix_notm}} en la que se recopila esta entrada de registro. </td>
                <td>us-south</td>
              </tr>
              <tr>
                <td>*kubernetes.container_name_str*</td>
                <td>El valor de este campo informa sobre el nombre del contenedor.</td>
                <td>hello-world-deployment</td>
              </tr>
              <tr>
                <td>*kubernetes.host*</td>
                <td>El valor de este campo informe sobre la IP pública que está disponible para acceder a la app desde internet. </td>
                <td>xxx.xx.xxx.xxx</td>
              </tr>
              <tr>
                <td>*kubernetes.labels.label_name*</td>
                <td>Los campos de etiqueta son opcionales. Puede haber o no haber etiquetas. Cada etiqueta empieza con el prefijo `kubernetes.labels.` seguido por *nombre_etiqueta*. </td>
                <td>En la app de ejemplo, puede ver dos etiquetas: <br>* *kubernetes.labels.pod-template-hash_str* = 3355293961 <br>* *kubernetes.labels.run_str* =	hello-world-deployment  </td>
              </tr>
              <tr>
                <td>*kubernetes.namespace_name_str*</td>
                <td>El valor de este campo informa sobre el espacio de nombres de Kubernetes donde está el pod en ejecución. </td>
                <td>default</td>
              </tr>
              <tr>
                <td>*kubernetes.pod_id_str*</td>
                <td>El valor de este campo corresponde al GUID del pod donde se ejecuta el contenedor. </td>
                <td>d695f346-xxxx-xxxx-xxxx-aab0b50f7315</td>
              </tr>
              <tr>
                <td>*kubernetes.pod_name_str*</td>
                <td>El valor de este campo informa sobre el nombre de pod. </td>
                <td>hello-world-deployment-3xxxxxxx1-xxxxx8</td>
              </tr>
              <tr>
                <td>*message*</td>
                <td>Se trata el mensaje completo que registra la aplicación. </td>
                <td>Sample app is listening on port 8080.</td>
              </tr>
        </table>
    
    
    
3. Filtrar datos en la página *Descubrir*.   

    En la tabla podrá ver todas las entradas disponibles para ser analizadas. Las entradas que se listan corresponden a la consulta de búsqueda que se visualiza en la barra *Buscar*. `*` es el carácter que se utiliza para visualizar todas las entradas del periodo de tiempo configurado para la página.  
    
    Por ejemplo, para filtrar datos según el espacio de nombres de Kubernetes, modifique la barra de consulta *Buscar*. Añada un filtro en base al campo personalizado *kubernetes.namespace_name_str*:
    
    1. En la sección **Campos disponibles**, seleccione el campo *kubernetes.namespace_name_str*. Se visualizará un subconjunto de valores disponibles para el campo.     
    
    2. Seleccione el valor **default**. Este es el espacio de nombres donde en el paso anterior se desplegó la app de ejemplo. 
    
        Después de seleccionar el valor, se añade un filtro a la barra *Buscar* para que la tabla visualice únicamente las entradas que coincidan con el criterio que acaba de seleccionar.      
    
    ![Filtrar para buscar según el espacio de nombres Kubernetes default](images/sampleapp_k4_1.gif "Filtrar para buscar según el espacio de nombres Kubernetes default")
    
    Puede seleccionar el símbolo de edición del filtro para modificar el nombre del espacio de nombres que busca.    
    
    ![Acciones disponibles para un filtro](images/sampleapp_k4_1.gif "Acciones disponibles para un filtro")
    
    Se visualiza la siguiente consulta: 
    
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
    
    Para buscar entradas en un espacio de nombres diferente como, por ejemplo, *mynamespace1*, modifique la consulta: 
    
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
    

    Si no ve ningún dato, intente cambiar el filtro de tiempo. Para obtener más información, consulte [Establecimiento de un filtro de tiempo](../../kibana4/k4_filter_logs.html#set_time_filter).
    


Para obtener más información, consulte [Filtrado de registros en Kibana](../../kibana4/k4_filter_logs.html#k4_filter_logs).

