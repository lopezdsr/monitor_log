---

copyright:
  years: 2015, 2017

lastupdated: "2017-05-22"

---


{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:screen: .screen}


# Kibana ダッシュボードへのナビゲート
{: #k4_launch}

Kibana は、{{site.data.keyword.Bluemix}} UI から、または Web ブラウザーから直接、起動できます。
{:shortdesc}

{{site.data.keyword.Bluemix_notm}} から Kibana を起動して、Kibana を起動したリソースに応じてデータを表示し、分析します。例えば、特定の CF アプリのログがその特定のアプリに応じて表示されるように Kibana を起動できます。
    
提供される {{site.data.keyword.Bluemix_notm}} スペース内でサービスから集計されたログ・データを表示する場合は、直接ブラウザー・リンクから Kibana を起動します。ダッシュボードに表示されるデータをフィルター操作するために使用される照会によって、{{site.data.keyword.Bluemix_notm}} 組織内のスペースのログ項目が取り出されます。Kibana に表示されるログ情報には、ログインしている {{site.data.keyword.Bluemix_notm}} 組織のスペース内にデプロイされているすべてのリソースに関するレコードが含まれます。 

次の表に、リソースと、Kibana を起動するためのサポートされているナビゲーション方法をリストします。

<table>
<caption>表 1. リソースおよびサポートされているナビゲーション方法のリスト</caption>
  <tr>
    <th>リソース</th>
    <th>Bluemix ダッシュボードから Kibana ダッシュボードへのナビゲート</th>
    <th>Web ブラウザーから Kibana ダッシュボードへのナビゲート</th>
  <tr>
  <tr>
    <td>CF アプリ</td>
    <td>はい</td>
    <td>はい</td>
  <tr>  
  <tr>
    <td>Kubernetes クラスターにデプロイされたコンテナー</td>
    <td>いいえ</td>
    <td>はい</td>
  <tr>  
  <tr>
    <td>{{site.data.keyword.Bluemix_notm}} 管理のクラウド・インフラストラクチャーにデプロイされたコンテナー</td>
    <td>はい</td>
    <td>はい</td>
  <tr>  
</table>

Kibana について詳しくは、「[Kibana User Guide ![外部リンク・アイコン](../../../icons/launch-glyph.svg "外部リンク・アイコン")](https://www.elastic.co/guide/en/kibana/4.1/index.html){: new_window}」を参照してください。
    

##  Bluemix ダッシュボードから Kibana ダッシュボードへのナビゲート
{: #launch_Kibana_from_bluemix}

Kibana で表示されるデータをフィルタリングするために使用される照会によって、Kibana を起動した {{site.data.keyword.Bluemix_notm}} CF アプリまたはコンテナーのログ項目を取得します。

Cloud Foundry アプリケーションまたは Docker コンテナーのログを Kibana で表示するには、以下のステップを実行します。

1. {{site.data.keyword.Bluemix_notm}} にログインし、{{site.data.keyword.Bluemix_notm}} ダッシュボードでアプリ名またはコンテナーをクリックします。 
    
2. {{site.data.keyword.Bluemix_notm}} UI でログ・タブを開きます。

    * CF アプリの場合、ナビゲーション・バーの**「ログ」**をクリックします。 
    * {{site.data.keyword.Bluemix_notm}} が管理するクラウド・インフラストラクチャーにデプロイされたコンテナーの場合、ナビゲーション・バーで**「モニターおよびログ」**を選択してから、**「ロギング」**タブをクリックします。 
    
        「ログ」タブが開きます。  

3. **「拡張ビュー」**をクリックします。Kibana ダッシュボードが開きます。

    デフォルトでは、**「Discover」**ページは、デフォルトの索引パターンが選択され、時間フィルターが過去 30 秒に設定された状態でロードされます。検索照会は、CF アプリまたは Docker コンテナーのすべての項目に突き合わせるように設定されます。

    「Discover」ページでログ項目が表示されない場合は、時間ピッカーを調整します。詳しくは、『[時間フィルターの設定](logging_kibana_set_time_filter.html#set_time_filter)』を参照してください。


##  Web ブラウザーから Kibana ダッシュボードへのナビゲート
{: #launch_Kibana_from_browser}

Kibana に表示されるデータをフィルター操作するために使用される照会によって、{{site.data.keyword.Bluemix_notm}} 組織内のスペースのログ項目が取り出されます。Kibana に表示されるログ情報には、ログインしている {{site.data.keyword.Bluemix_notm}} 組織のスペース内にデプロイされているすべてのリソースに関するレコードが含まれます。

以下のステップを実行して、ブラウザーから Kibana を起動します。

1. Kibana ユーザー・インターフェースにログインするため、[https://logging.<span class="keyword" data-hd-keyref="DomainName">DomainName</span>](https://logging.{DomainName}) を開きます。
    
    以下に例を示します。 
      
        <table>
          <caption>表 1. Kibana を起動するための URL </caption>
           <tr>
            <th>地域</th>
            <th>URL</th>
          </tr>
          <tr>
            <td>米国南部</td>
            <td>https://logging.ng.bluemix.net/ </td>
          </tr>
          <tr>
            <td>英国</td>
            <td>https://logging.eu-gb.bluemix.net/ </td>
          </tr>
        </table>

    「Discover」ページでログ項目が表示されない場合は、時間ピッカーを調整します。詳しくは、『[時間フィルターの設定](logging_kibana_set_time_filter.html#set_time_filter)』を参照してください。


