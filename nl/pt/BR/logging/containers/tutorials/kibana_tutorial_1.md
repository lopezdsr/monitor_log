---

copyright:
  years: 2015, 2017

Lastupdated: "2017-05-23"

---


{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:screen: .screen}


# Analisar logs no Kibana para um app que é implementado em um cluster do Kubernetes
{: #kibana_tutorial_1}

Comece com Kibana. Aprenda a procurar e analisar logs do contêiner para um app que é implementado em um cluster do Kubernetes.
{:shortdesc}

**Nota:** para concluir este tutorial, conclua as tutoriais que estão vinculados nas diferentes etapas.

## Pré-requisito
{: #prereq}

1. Seja um membro ou um proprietário de uma conta do Bluemix com permissões para criar clusters do Kubernetes, implemente apps em clusters e consulte os logs no Bluemix para análise avançada no Kibana.

2. Tenha uma sessão de terminal da qual seja possível gerenciar o cluster do Kubernetes e implementar apps por meio da linha de comandos. Os exemplos neste tutorial são fornecidos para um sistema Ubuntu Linux.

3. [Instale os plug-ins da CLI](../../../../containers/cs_cli_install.html#cs_cli_install_steps) em seu sistema Ubuntu para gerenciar o serviço IBM Bluemix Container por meio da linha de comandos. 


## Etapa 1: deixar o Kubernetes funcionamento no Bluemix
{: #step1}

Conclua
as etapas a seguir:

1. [Criar um Kubernetes cluster](../../../../containers/cs_cluster.html#cs_cluster_ui).

2. [Configure o contexto do cluster](../../../../containers/cs_cli_install.html#cs_cli_configure) em um terminal Linux. Após o contexto ser configurado, é possível gerenciar o cluster do Kubernetes e implementar o aplicativo no cluster do Kubernetes.

## Etapa 2: implementar um aplicativo no cluster do Kubernetes
{: #step2}

Implemente e execute um aplicativo de amostra no cluster do Kubernetes. [Conclua as etapas para a lição 1](../../../../containers/cs_tutorials.html#cs_apps_tutorial).

O app é um app Hello World node js:

```
var express = require('express')
var app = express()

app.get('/', function(req, res) {
  Res.send (' Hello world! Your app is up and running in a cluster!\n')
})
App.listen (8080, function () {
  console.log('Sample app is listening on port 8080.')
})
```

Quando o app é implementado, a coleção de logs é ativada automaticamente para quaisquer entradas de log que são enviadas pelo app para stdout (saída padrão) e stderr (erro padrão). 

Nesse aplicativo de amostra, quando você testa seu app em um navegador, o app grava no stdout a mensagem a seguir: `Sample app is listening on port 8080.`


## Etapa 3: analisar dados do log no Kibana
{: #step3}

1. Ativar Kibana de um navegador. 

    Para analisar dados do log para um cluster, deve-se acessar o Kibana na região Pública de nuvem na qual o cluster é criado. 
    
    Escolha a URL correta com base na região na qual você criou o cluster do Kubernetes na etapa anterior:

    <table>
      <caption>Tabela 1.  URLs para ativar Kibana  </caption>
        <tr>
          <th>Região</th>
          <th>Url</th>
         </tr>
         <tr>
           <td>Sul dos EUA</td>
           <td>Https://logging.ng.bluemix.net/ </td>
          </tr>
          <tr>
            <td>Reino Unido</td>
            <td>Https://logging.eu-gb.bluemix.net/ </td>
           </tr>
           <tr>
             <td>Frankfurt</td>
             <td>Https://logging.eu-de.bluemix.net/ </td>
           </tr>
    </table>
    
    Em seguida, em um navegador, ative a URL para abrir o Kibana.
    
2. Na página **Descobrir**, consulte os eventos que são exibidos. 

    O aplicativo Hello-World de amostra gera um evento.
    
    ![Página Descobrir
no Kibana](images/sampleapp_2.gif "Página Descobrir no Kibana")
    
    Na seção *Campos disponíveis*, é possível ver a lista de campos que podem ser usados para definir novas consultas ou filtrar as entradas listadas na tabela exibida na página.
    
    A tabela a seguir lista os campos comuns que podem ser usados para definir novas consultas de procura. A tabela também inclui valores de amostra que correspondem ao evento que é gerado pelo aplicativo de amostra:
    
     <table>
              <caption>Tabela 2. Campos comuns para logs do contêiner</caption>
               <tr>
                <th align="center">Campo</th>
                <th align="center">Descrição</th>
                <th align="center">Exemplo</th>
              </tr>
              <tr>
                <td>*docker.container_id_str*</td>
                <td> O valor desse campo corresponde ao GUID do contêiner que executa o app em um pod do cluster do Kubernetes.</td>
                <td></td>
              </tr>
              <tr>
                <td>*ibm-containers.region_str*</td>
                <td>O valor desse campo corresponde à região do {{site.data.keyword.Bluemix_notm}} na qual a entrada de log é coletada.</td>
                <td>us-south</td>
              </tr>
              <tr>
                <td>*kubernetes.container_name_str*</td>
                <td>O valor desse campo informa sobre o nome do contêiner.</td>
                <td>Olá a implementação mundial</td>
              </tr>
              <tr>
                <td>*kubernetes.host*</td>
                <td>O valor desse campo informa sobre o IP público que está disponível para acessar o app na Internet.</td>
                <td>Xxx.xx.xxx.xxx</td>
              </tr>
              <tr>
                <td>*kubernetes.labels.label_name*</td>
                <td>Os campos Rótulo são opcionais. É possível ter 0 ou mais rótulos. Cada rótulo inicia com o prefixo `kubernetes.labels.` Seguido pelo *label_name*. </td>
                <td>No app de amostra, é possível ver 2 rótulos: <br>* * kubernetes.labels.pod-template-hash_str* = 3355293961 <br>* *kubernetes.labels.run_str* =	hello-world-deployment  </td>
              </tr>
              <tr>
                <td>*Kubernetes.namespace_name_str*</td>
                <td>O valor desse campo informa sobre o namespace do Kubernetes no qual o módulo está em execução. </td>
                <td>Padrão</td>
              </tr>
              <tr>
                <td>*kubernetes.pod_id_str*</td>
                <td>O valor desse campo corresponde ao GUID do pod no qual o contêiner é executado. </td>
                <td>D695f346-xxxx-xxxx-xxxx-aab0b50f7315</td>
              </tr>
              <tr>
                <td>*kubernetes.pod_name_str*</td>
                <td>O valor desse campo informa sobre o nome do pod.</td>
                <td>Olá mundo a implementação 3xxxxxxx1-xxxxx8</td>
              </tr>
              <tr>
                <td>*mensagem*</td>
                <td>Esta é a mensagem integral registrada pelo aplicativo.</td>
                <td>O aplicativo de amostra está atendendo na porta 8080.</td>
              </tr>
        </table>
    
    
    
3. Filtrar dados no *Descobrir* página.  

    Na tabela, é possível ver todas as entradas que estão disponíveis para análise. As entradas que estão listados correspondem à consulta de procura que é exibida na barra *Procurar*.`*` é o caractere usado para exibir todas as entradas dentro do período de tempo configurado para a página. 
    
    Por exemplo, para filtrar os dados por namespace do Kubernetes, modifique a consulta da barra de *Procura*. Inclua um filtro com base no campo customizado *kubernetes.namespace_name_str*:
    
    1. Na seção **Campos disponíveis**, selecione o campo *kubernetes.namespace_name_str*. Um subconjunto de valores disponíveis para o campo é exibido.    
    
    2. Selecione o valor **padrão**. Esse é o namespace no qual você implementou em uma etapa anterior o mesmo app.
    
        Depois de selecionar o valor, um filtro é incluído na *Barra de procura* e a tabela exibe somente as entradas que correspondem aos critérios que você acabou de selecionar.     
    
    ![Filtre para procurar o namespace padrão do Kubernetes](images/sampleapp_k4_1.gif "Filtre para procurar o namespace padrão do Kubernetes")
    
    É possível selecionar o símbolo de edição do filtro para modificar o nome do namespace procurado.   
    
    ![Ações que estão disponíveis para um filtro](images/sampleapp_k4_1.gif "Ações que estão disponíveis para um filtro")
    
    A consulta a seguir exibe:
    
    ```{
        "query": {
          "Corresponder": {
            "Kubernetes.namespace_name_str": {
              "query": "default",
              "type": "phrase"
            }
          }
        }
      }
    ```
    
    Para procurar entradas em um namespace diferente, como *mynamespace1*, modifique a consulta:
    
    ```{
        "query": {
          "Corresponder": {
            "Kubernetes.namespace_name_str": {
              "query": "mynamespace1",
              "type": "phrase"
            }
          }
        }
      }
    ```
    

    Se não for possível ver nenhum dado, tente mudar o filtro de tempo. Para obter mais informações, consulte [Configurando um filtro de tempo](../../kibana4/k4_filter_logs.html#set_time_filter).
    


Para obter mais informações, consulte [Filtrando logs no Kibana](../../kibana4/k4_filter_logs.html#k4_filter_logs).

