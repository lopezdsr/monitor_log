---

copyright:
  years: 2015, 2017

lastupdated: "2017-05-19"

---


{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:screen: .screen}

# Análisis avanzado de registros con Kibana
{:#analyzing_logs_Kibana}

En {{site.data.keyword.Bluemix}}, puede utilizar Kibana, una plataforma de visualización y análisis de código abierto, para supervisar, buscar, analizar y visualizar datos en diversos gráficos, como diagramas y tablas. Utilice Kibana para realizar tareas avanzadas de análisis.
{:shortdesc}

Kibana es una interfaz basada en navegador con la que puede analizar datos de forma interactiva y personalizar paneles de control que luego puede utilizar para analizar datos de registro y realizar tareas avanzadas de gestión. Para obtener más información, consulte la [Guía del usuario de Kibana ![Icono de enlace externo](../../../icons/launch-glyph.svg "Icono de enlace externo")](https://www.elastic.co/guide/en/kibana/4.1/index.html){: new_window}.

Los datos que muestran una página de Kibana están restringidos por una búsqueda. El conjunto de datos predeterminado se define mediante un patrón de índice preconfigurado. Para filtrar la información, puede añadir nuevas consultas de búsqueda y aplicar filtros al conjunto de datos predeterminado. Luego puede guardar la búsqueda para reutilizarla en el futuro. 

Kibana incluye varias páginas que puede utilizar para analizar los registros:

| Página de Kibana | Descripción |
|-------------|-------------|
| Descubrir | Utilice esta página para definir búsquedas y analizar los registros de forma interactiva a través de una tabla y un histograma. |
| Visualizar | Utilice esta página para crear visualizaciones, como gráficos y tablas, que puede utilizar para analizar los datos de registro y comparara los resultados.  |
| Panel de control | Utilice esta página para analizar los registros a través de recopilaciones de visualizaciones y búsquedas guardadas.  |
{: caption="Tabla 1. Páginas de Kibana" caption-side="top"}

**Nota:** Sólo puede analizar 1 día completa cada vez mediante la página Visualizar o la página Panel de control, aunque puede retroceder 7 días. Los datos del registro se guardan de forma predeterminada durante 7 días. 

| Página de Kibana | Información sobre periodo de tiempo |
|-------------|-------------------------|
| Descubrir | Analizar datos correspondientes a un máximo de 7 días. |
| Visualizar | Analizar datos correspondientes a un periodo de 24 horas. <br> Puede filtrar los datos de registro durante un periodo personalizado que comprenda 24 horas.  |
| Panel de control | Analizar datos correspondientes a un periodo de 24 horas. <br> Puede filtrar los datos de registro durante un periodo personalizado que comprenda 24 horas. <br> El selector de tiempo que defina se aplica a todas las visualizaciones que se incluyen en el panel de control. |
{: caption="Tabla 2. Información sobre periodo de tiempo" caption-side="top"}

Por ejemplo, así es cómo puede utilizar Kibana para que muestre información sobre una app CF o un contenedor del espacio en diversas páginas:

## Navegación al panel de control de Kibana
{: #launch_Kibana}

Puede iniciar Kibana de cualquiera de estas formas:

* Desde {{site.data.keyword.Bluemix_notm}}

    Puede iniciar los registros específicos de la app CF en Kibana, dentro del contexto de la app específica.
    
    Puede iniciar registros de un contenedor Docker específico en Kibana, dentro del contexto de dicho contenedor en concreto. Esta característica únicamente se aplica a contenedores desplegados en la infraestructura de nube gestionada de {{site.data.keyword.Bluemix_notm}}. 
    
    Para las apps CF, la consulta que se utiliza para filtrar los datos disponibles para análisis en Kibana recupera las entradas de registro de la aplicación Cloud Foundry. La información de registro que muestra Kibana de forma predeterminada está relacionada con una sola aplicación Cloud Foundry y todas sus instancias. 
    
    Para contenedores, la consulta que se utiliza para filtrar los datos disponibles para análisis en Kibana recupera las entradas de registro de todas las instancias del contenedor. La información de registro que muestra Kibana de forma predeterminada está relacionada con un solo contenedor o con un grupo de contenedores y todas sus instancias. 
    
    Para obtener más información, consulte [Navegación al panel de control de Kibana desde el panel de control de Bluemix](k4_launch.html#launch_Kibana_from_bluemix).

* Desde un enlace directo del navegador

    Puede iniciar Kibana para que los datos que ve agreguen registros de servicios de un espacio de {{site.data.keyword.Bluemix_notm}} especificado.
    
    La consulta que se utiliza para filtrar los datos que aparecen en el panel de control recupera las entradas de registro correspondientes a un espacio de la organización {{site.data.keyword.Bluemix_notm}}. La información de registro que muestra Kibana incluye registros correspondientes a todos los recursos desplegados dentro del espacio de la organización {{site.data.keyword.Bluemix_notm}} en la que ha iniciado la sesión. 
    
    Para obtener más información, consulte [Navegación al panel de control de Kibana desde un navegador web](k4_launch.html#launch_Kibana_from_browser).
    
    Cuando inicie Kibana desde un navegador, puede elegir entre trabajar con Kibana 4 o Kibana 3. **Nota:** Kibana 3 está en desuso. Para obtener información sobre cómo utilizar Kibana 3 para analizar registros, consulte [Análisis de registros en Kibana 3 (en desuso)](../logging_view_kibana3.html#analyzing_logs_Kibana3).


## Análisis de datos de forma interactiva
{: #analyze_discover}

En la página Descubrir, puede definir nuevas consultas de búsqueda y aplicar filtros por consulta. Los datos de registro se muestran en una tabla y un histograma. Puede utilizar estas visualizaciones para analizar los datos de forma interactiva. Para obtener más información, consulte [Análisis interactivo de registros en Kibana](logging_kibana_analize_logs_interactively.html#kibana_analize_logs_interactively).

Puede configurar filtros desde campos de registro, por ejemplo message_type e instance_ID, y definir un periodo de tiempo. Puede habilitar o inhabilitar dinámicamente estos filtros. La tabla y el histograma mostrarán las entradas de registro que cumplan la consulta y los criterios de filtro que habilite. Para obtener más información, consulte [Filtrado de registros en Kibana](k4_filter_logs.html#k4_filter_logs).

## Análisis de datos mediante su visualización
{: #analyze_visualize}
    
En la página Visualizar, puede definir nuevas consultas de búsqueda y visualizaciones.

Para analizar los datos, puede crear visualizaciones basadas en una búsqueda existente o en una búsqueda nueva. Kibana incluye distintos tipos de visualizaciones, como tabla, tendencias e histograma, que puede utilizar para analizar la información. El objetivo de cada visualización varía. Algunas visualizaciones se organizan en filas que proporcionan los resultados de una o varias consultas. Otras visualizaciones muestran documentos o información personalizada. Los datos de una visualización se pueden dejar fijos o modificar si una se actualiza una consulta de búsqueda. Puede incluir la visualización en una página web o puede compartirla. Para obtener más información, consulte [Análisis de registros mediante visualizaciones](logging_kibana_visualizations.html#logging_kibana_visualizations).

## Análisis de datos en un panel de control
{: #analyze_dashboard}

En la página Panel de control, puede personalizar, guardar y compartir varias visualizaciones y búsquedas simultáneamente. 

Puede añadir, eliminar y cambiar la disposición de las visualizaciones del panel de control. Para obtener más información, consulte [Análisis de registros en Kibana mediante un panel de control](logging_kibana_analize_logs_dashboard.html#kibana_analize_logs_dashboard).
    
Después de personalizar un panel de control de Kibana, puede analizar los datos a través de sus visualizaciones y guardarlos para volverlos a utilizar en el futuro. Para obtener más información, consulte [Cómo guardar un panel de control de Kibana](logging_kibana_analize_logs_dashboard.html#k4_dashboard_save).

En Kibana, también hay una página *Valores* que puede utilizar para configurar Kibana y para guardar, suprimir, exportar e importar búsquedas, visualizaciones y paneles de control.


