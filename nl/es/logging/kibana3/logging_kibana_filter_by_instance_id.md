---

copyright:
  years: 2016, 2017
lastupdated: "2017-02-06"


{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}


# Filtrado de registros de apps de Cloud Foundry por ID de instancia en Kibana
{: #logging_kibana_instance_id}

Puede ver y filtrar registros de instancia de {{site.data.keyword.Bluemix_notm}} por ID de instancia (instance_id) de una app en el panel de control de Kibana. Puede acceder al panel de control de Kibana desde el separador **Registros** de la app de Cloud Foundry. 
{:shortdesc}

Lleve a cabo las tareas siguientes para ver y filtrar los registros de la app de Cloud Foundry por instance_id en el panel de control de Kibana:

1. Acceda al separador **Registros** de la app de Cloud Foundry. 

    1. Pulse el nombre de la app en el panel de control **Apps** de {{site.data.keyword.Bluemix_notm}}.
    2. Pulse el separador **Registros**. 
    
    Se muestran los registros de la app.

2. Acceso al panel de control de Kibana para su app. Pulse **Vista avanzada** ![Enlace Vista avanzada](images/logging_advanced_view.jpg "Enlace Vista avanzada"). Se visualiza el panel de control de Kibana.

3. En el panel de control de Kibana, pulse el icono **Ir a valor predeterminado guardado**; ![Icono Ir a valor predeterminado guardado](images/logging_default_dash.jpg "Icono Ir a valor predeterminado guardado") para ver todos los registros correspondientes a un espacio. En la ventana **TODOS LOS SUCESOS**, pulse el icono de flecha hacia la derecha para mostrar todos los campos. 

    ![Ventana Todos los sucesos con icono de flecha hacia la derecha](images/logging_all_events_no_fields.jpg "Ventana Todos los sucesos con icono de flecha hacia la derecha")

4. En el panel **Campos**, seleccione **application_id** e **instance_id** para visualizar los campos application_id e instance_id en la ventana **TODOS LOS SUCESOS**.

    ![Ventana Todos los sucesos con los campos application_id e instance_id seleccionados](images/logging_all_events_app_instance_select.jpg "Ventana Todos los sucesos con los campos application_id e instance_id seleccionados")

5. En la ventana **TODOS LOS SUCESOS**, pulse una fila de suceso de registro para ver los detalles de dicho suceso. Elija un suceso que muestre el instance_id que desea filtrar.

    ![Ventana Todos los sucesos que muestra detalles del suceso de registro seleccionado](images/logging_selected_log_event.jpg "Ventana Todos los sucesos que muestra detalles del suceso de registro seleccionado")

6. Añada un filtro para incluir o excluir información sobre un ID de app. 

    * Para añadir un filtro que incluya información sobre un determinado ID de aplicación, pulse el icono **Lupa** ![icono Lupa](images/logging_magnifying_glass.jpg) en la fila application_id de la tabla. 
    
           ![Condición de filtro para el campo application_id](images/logging_application_id_filter.jpg "Condición de filtro para el campo application_id")
    
    * Para añadir un filtro que excluya información sobre un determinado ID de aplicación, pulse el icono **Exclusión** ![icono de exclusión](images/logging_exclusion_icon.png) en la fila application_id de la tabla. 
    
           ![Condición de filtro para excluir un ID de aplicación](images/logging_application_id_exclude_filter.jpg "Condición de filtro para excluir un ID de aplicación")
    
    Se añade una nueva condición de filtro al panel de control de Kibana.
 

7. Añada un filtro para incluir o excluir información sobre un ID de instancia de app. 

    * Para añadir un filtro que incluya información sobre un determinado ID de instancia, pulse el icono **Lupa** ![Icono Lupa](images/logging_magnifying_glass.jpg "Icono Lupa") en la fila instance_id de la tabla. 

    ![Condición de filtro para el campo instance_id](images/logging_instance_id_filter.jpg "Condición de filtro para el campo instance_id")

     * Para añadir un filtro que excluya información sobre un determinado ID de instancia, pulse el icono **Exclusión** ![Icono Exclusión](images/logging_exclusion_icon.png "Icono Exclusión") en la fila instance_id de la tabla. 
    
           ![Condición de filtro para excluir un ID de instancia](images/logging_application_instance_id_exclude_filter.jpg "Condición de filtro para excluir un ID de instancia")
    
    Se añade una nueva condición de filtro al panel de control de Kibana.

9. Guarde el panel de control. Cuando haya terminado de crear los filtros, pulse el icono **Guardar** ![Icono Guardar](images/logging_save.jpg "Icono Guardar") y escriba un nombre para el panel de control. 

    **Nota:** si intenta guardar un panel de control con un nombre que contenga espacios en blanco, no se guardará. Escriba un nombre sin espacios y pulse el icono **Guardar**.

    ![Guardar nombre del panel de control](images/logging_save_dashboard.jpg "Guardar nombre del panel de control").

Ha creado un panel de control que filtra las entradas de registro por instance_id. Puede cargar el panel de control que ha guardado en cualquier momento pulsando el icono **Carpeta** ![Icono Carpeta](images/logging_folder.jpg "Icono Carpeta") y seleccionando el panel de control por nombre. 
