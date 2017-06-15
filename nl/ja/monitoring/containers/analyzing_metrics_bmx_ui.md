---

copyright:
  years: 2017

lastupdated: "2017-05-25"

---


{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:screen: .screen}

# Bluemix コンソールからのコンテナー・メトリックの分析
{: #analyzing_metrics_bmx_ui}

{{site.data.keyword.Bluemix}} では、{{site.data.keyword.Bluemix_notm}} が管理するクラウド・インフラストラクチャーにデプロイされた Docker コンテナーに対して使用可能な*「モニタリング」*タブを使用して、メトリックの表示および分析を行うことができます。
{:shortdesc}

{{site.data.keyword.Bluemix_notm}} Public は、統合モニタリング機能を提供します。 

分析およびデータ保存に関するメトリック可用性についての以下の情報を考慮してください。

* {{site.data.keyword.Bluemix_notm}} Public では、メトリックはデフォルトで 7 日間保管されます。 
* 1 日当たり 1 GB までのデータを保管できます。 
* デフォルトでは、{{site.data.keyword.Bluemix_notm}} コンソールから分析用に使用可能なメトリックには、過去 24 時間のデータが含まれます。

**ヒント:** 過去 24 時間より前のカスタム期間のデータを分析するには、Grafana を使用してください。


##  Bluemix で管理されている Docker コンテナーのメトリックへのナビゲート
{: #launch_metrics_tab_bmx_ui_containers}

{{site.data.keyword.Bluemix_notm}} が管理するクラウド・インフラストラクチャーにデプロイされた Docker コンテナーのメトリックを表示するには、以下の手順を実行します。

1. 「アプリ」ダッシュボードで単一コンテナーまたはコンテナー・グループをクリックします。 
    
2. アプリ詳細ページで**「モニターおよびログ (Monitoring and Logs)」**をクリックします。

3. **「モニタリング」**タブを選択します。
    
    **「モニタリング」**タブではコンテナーのメトリックを表示できます。
