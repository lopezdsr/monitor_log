---

copyright:
  years: 2016, 2017
lastupdated: "2017-02-06"


{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}


# Filtrando seus logs do app Cloud Foundry por ID da instância no Kibana
{: #logging_kibana_instance_id}

Visualize e filtre logs da instância do {{site.data.keyword.Bluemix_notm}} pelo ID da instância (instance_id) de seu app no painel do Kibana. É possível acessar o painel do Kibana na guia **Logs** para seu app Cloud Foundry. 
{:shortdesc}

Conclua as tarefas a seguir para visualizar e filtrar seus logs do app Cloud Foundry por instance_id no painel do Kibana:

1. Acesse a guia **Logs** de seu app Cloud Foundry. 

    1. Clique no nome do app no painel **Apps** do {{site.data.keyword.Bluemix_notm}}.
    2. Clique na guia **Logs**. 
    
    Os logs para seu app são exibidos.

2. Acesse o painel do Kibana para seu app. Clique em **Visualização avançada** ![Link da visualização avançada](images/logging_advanced_view.jpg "Link da visualização avançada"). O painel do Kibana é exibido.

3. No painel do Kibana, clique no ícone **Acessar padrão salvo**; ![Ícone Acessar padrão salvo](images/logging_default_dash.jpg "Ícone Acessar padrão salvo") para exibir todos os logs para um espaço. Na janela **TODOS OS EVENTOS**, clique no ícone de seta à direita para mostrar todos os campos. 

    ![Janela Todos os eventos com ícone de seta à direita](images/logging_all_events_no_fields.jpg "Janela Todos os eventos com ícone de seta à direita")

4. Na área de janela **Campos**, selecione **application_id** e **instance_id** para exibir os campos application_id e instance_id na janela **TODOS OS EVENTOS**.

    ![Janela Todos os eventos com os campos application_id e instance_id selecionados](images/logging_all_events_app_instance_select.jpg "Janela Todos os eventos com os campos application_id e instance_id selecionados")

5. Na janela **TODOS OS EVENTOS**, clique em uma linha de evento de log para exibir os detalhes para esse evento. Escolha um evento que exiba o instance_id que você deseja filtrar.

    ![Janela Todos os eventos exibindo detalhes para um evento de log selecionado](images/logging_selected_log_event.jpg "Janela Todos os eventos exibindo detalhes para um evento de log selecionado")

6. Inclua um filtro para incluir ou excluir informações sobre um ID de app. 

    * Para incluir um filtro que inclua informações sobre um ID do aplicativo específico, clique no ícone de **Lupa** ![Ícone de Lupa](images/logging_magnifying_glass.jpg) na linha application_id da tabela. 
    
           ![Condição do filtro para o campo application_id](images/logging_application_id_filter.jpg "Condição do filtro para o campo application_id")
    
    * Para incluir um filtro que exclua informações sobre um ID do aplicativo específico, clique no ícone de **Exclusão** ![Ícone de Exclusão](images/logging_exclusion_icon.png) na linha application_id da tabela. 
    
           ![Condição do filtro para excluir um ID do aplicativo](images/logging_application_id_exclude_filter.jpg "Condição do filtro para excluir um ID do aplicativo")
    
    Uma nova condição do filtro é incluída no painel do Kibana.
 

7. Inclua um filtro para incluir ou excluir informações sobre um ID da instância do app. 

    * Para incluir um filtro que inclua informações sobre um ID da instância específico, clique no ícone de **Lupa** ![Ícone de lupa](images/logging_magnifying_glass.jpg "Ícone de lupa") na linha instance_id da tabela. 

    ![Condição do filtro para o campo instance_id](images/logging_instance_id_filter.jpg "Condição do filtro para o campo instance_id")

     * Para incluir um filtro que exclua informações sobre um ID da instância específico, clique no ícone de **Exclusão** ![Ícone de exclusão](images/logging_exclusion_icon.png "Ícone de exclusão") na linha instance_id da tabela. 
    
           ![Condição do filtro para excluir um ID da instância](images/logging_application_instance_id_exclude_filter.jpg "Condição do filtro para excluir um ID da instância")
    
    Uma nova condição do filtro é incluída no painel do Kibana.

9. Salve o painel. Quando concluir a criação de seu filtro, clique no ícone **Salvar** ![Ícone Salvar](images/logging_save.jpg "Ícone Salvar") e insira um nome para seu painel. 

    **Nota:** se você tentar salvar um painel com um nome contendo espaços em branco, ele não será salvo. Insira um nome sem espaços e clique no ícone **Salvar**.

    ![Salvar nome do painel](images/logging_save_dashboard.jpg "Salvar nome do painel").

Você criou um painel que filtra suas entradas de log por instance_id. É possível carregar seu painel salvo a qualquer momento clicando no ícone **Pasta** ![Ícone Pasta](images/logging_folder.jpg "Ícone Pasta") e selecionando seu painel por nome. 
