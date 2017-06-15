---

copyright:
  years: 2017

Lastupdated: "2017-05-25"

---


{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:screen: .screen}

# Analisando as métricas de contêiner por meio do console do Bluemix
{: #analyzing_metrics_bmx_ui}

No {{site.data.keyword.Bluemix}}, é possível visualizar e analisar métricas por meio da guia *Monitoramento* que está disponível para contêineres do Docker que são implementados em uma infraestrutura em nuvem gerenciada pelo {{site.data.keyword.Bluemix_notm}}.{:shortdesc}

{{site.data.keyword.Bluemix_notm}} Público oferece recursos de monitoramento integrados. 

Considere as informações a seguir sobre disponibilidade de métricas para retenção de análise e dados:

* No {{site.data.keyword.Bluemix_notm}} Public, as métricas são armazenadas por 7 dias por padrão. 
* É possível armazenar até 1 GB de dados por dia. 
* Por padrão, as métricas que estão disponíveis para análise no console do {{site.data.keyword.Bluemix_notm}} incluem dados para as últimas 24 horas.

**Dica:** use o Grafana para analisar dados para um período customizado que precede as últimas 24 horas.


##  Navegando para as métricas de um contêiner do Docker que é gerenciado no Bluemix
{: #launch_metrics_tab_bmx_ui_containers}

Para ver as métricas para um contêiner do Docker que é implementado na infraestrutura em Nuvem gerenciada pelo {{site.data.keyword.Bluemix_notm}}, conclua as etapas a seguir:

1. No painel Apps, clique no contêiner único ou no grupo de contêiner. 
    
2. Na página de detalhes do app, clique em **Monitoramento e Logs**.

3. Selecione **Monitoramento** na guia.
    
    Na guia **Monitoramento**, é possível visualizar as métricas para seu contêiner.
