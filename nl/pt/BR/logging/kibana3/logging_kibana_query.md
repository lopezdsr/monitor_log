---

copyright:
  years: 2016, 2017
lastupdated: "2017-02-02"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}


# Filtrando seus logs do app Cloud Foundry com consultas no Kibana
{: #logging_kibana_query}

Use o Kibana para criar consultas para procurar termos chave em seus logs e filtrar por esses termos. Com o Kibana, é possível comparar as consultas visualmente no painel. É possível acessar o painel do Kibana na guia **Logs** para seu app Cloud Foundry. 
{:shortdesc}

Conclua as tarefas a seguir para criar uma consulta para seus logs do app Cloud Foundry no painel do Kibana:

1. Acesse a guia **Logs** de seu app Cloud Foundry. 

    1. Clique no nome do app no painel **Apps** do {{site.data.keyword.Bluemix_notm}}.
    2. Clique na guia **Logs**. 
    
    Os logs para seu app são exibidos.

2. Acesse o painel do Kibana para seu app. Clique em **Visualização avançada** ![Link da visualização avançada](images/logging_advanced_view.jpg "Link da visualização avançada"). O painel do Kibana é exibido.

3. No painel do Kibana, clique em **CONSULTA** ![Ícone de consulta](images/logging_query.jpg "Ícone de consulta") para exibir o campo. Ao acessar o Kibana para visualizar seus logs do app na guia **Logs** para seu app, uma consulta é criada para mostrar todos os logs para o application_id de seu app.
	
    Para editar sua consulta, clique no campo **CONSULTA** e insira um termo de procura.

    * Para procurar por uma palavra-chave ou parte de uma palavra-chave, insira uma palavra, seguida por um símbolo curinga \*; por exemplo, `Java*`. 
	* Para procurar por uma frase específica, insira essa frase entre aspas duplas; por exemplo, `"Java/1.8.0"`.
	* Para criar procuras mais complexas, é possível usar os termos lógicos AND e OR; por exemplo, `"Java/1.8.0" OR "Java/1.7.0"`.
	* Para procurar por um valor em um campo específico, insira sua procura no formato a seguir: *log_field_name:search_term*; por exemplo, `instance_id:1`.
	* Para procurar por um intervalo de valores para um campo de log específico, insira sua procura no formato a seguir: *log_field_name:[start_of_range TO end_of_range]*; por exemplo, `instance_id:[1 TO 2]`.

4. Se você desejar comparar os resultados de duas consultas separadas, será possível incluir outro termo de consulta em seu painel. Para incluir outra consulta, clique no ícone **+** no final do campo **CONSULTA**.

    ![Campo de Consulta](images/logging_query_field.jpg "Campo de Consulta")
	
    Um novo campo **CONSULTA** que contém o curinga \* é exibido. Essa consulta instrui o Kibana a incluir todas as entradas.
	
    ![Campo de consulta adicional](images/logging_additional_query_field.jpg "Campo de consulta adicional")
	
    O painel é atualizado com os resultados de sua nova consulta. A área de janela **EVENTOS POR HORÁRIO** exibe uma representação gráfica para ambas as consultas, junto com o número de termos para cada consulta entre parênteses. 
	
    ![Painel exibindo gráfico para ambas as consultas](images/logging_dashboard_queries.jpg "Painel exibindo gráfico para ambas as consultas")
	
5. Clique no novo campo **CONSULTA** para editar seu conteúdo e incluir uma condição de consulta; por exemplo, `instance_id:1`. Use a área de janela **EVENTOS POR HORÁRIO** para comparar os resultados de suas consultas.

    ![Painel exibindo gráfico para ambas as consultas](images/logging_dashboard_queries2.jpg "Painel exibindo gráfico para ambas as consultas")

6. Para excluir uma consulta, mova o mouse sobre o campo **CONSULTA** que você deseja excluir para revelar o ícone de **exclusão**. Clique no ícone de **exclusão**.

    ![Campo de consulta com ícone de exclusão](images/logging_delete_query.jpg "Campo de consulta com ícone de exclusão")

7. Para salvar esse painel com um nome reconhecível, clique no ícone **Salvar** ![Ícone Salvar](images/logging_save.jpg "Ícone Salvar") e insira um nome para seu painel. 

    **Nota:** se você tentar salvar um painel com um nome contendo espaços em branco, ele não será salvo. Insira um nome sem espaços e clique no ícone **Salvar**.

    ![Salvar nome do painel](images/logging_save_dashboard.jpg "Salvar nome do painel")


