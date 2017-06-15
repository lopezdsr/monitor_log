---

copyright:
  years: 2015, 2017

lastupdated: "2017-05-22"

---


{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:screen: .screen}


# Kibana 대시보드로 이동
{: #k4_launch}

{{site.data.keyword.Bluemix}} UI에서 또는 웹 브라우저에서 직접 Kibana를 실행할 수 있습니다.
{:shortdesc}

{{site.data.keyword.Bluemix_notm}}에서 Kibana를 실행하여 Kibana를 실행하는 리소스에 대한 컨텍스트에서 데이터를 보고 분석하십시오. 예를 들면, Kibana에서 특정 앱의 컨텍스트로 특정 CF 앱 로그를 시작할 수 있습니다. 
    
제공된 {{site.data.keyword.Bluemix_notm}} 영역 내 서비스에서 수집된 로그 데이터를 보려면 직접 브라우저 링크에서 Kibana를 실행하십시오. 대시보드에 표시되는 데이터를 필터링하는 데 사용되는 조회는 {{site.data.keyword.Bluemix_notm}} 조직에서 영역의 로그 항목을 검색합니다. Kibana에 표시되는 로그 정보에는 로그인한 {{site.data.keyword.Bluemix_notm}} 조직의 영역 내에 배치된 모든 리소스에 대한 레코드가 포함됩니다. 

다음 표에는 리소스와 Kibana 시작에 지원되는 이동 방법이 나열되어 있습니다. 

<table>
<caption>표 1. 리소스 및 지원되는 이동 방법의 목록</caption>
  <tr>
    <th>리소스</th>
    <th>Bluemix 대시보드에서 Kibana 대시보드로 이동</th>
    <th>웹 브라우저에서 Kibana 대시보드로 이동</th>
  <tr>
  <tr>
    <td>CF 앱</td>
    <td>예</td>
    <td>예</td>
  <tr>  
  <tr>
    <td>Kubernetes 클러스터에 배치된 컨테이너</td>
    <td>아니오</td>
    <td>예</td>
  <tr>  
  <tr>
    <td>{{site.data.keyword.Bluemix_notm}} 관리 클라우드 인프라에 배치된 컨테이너</td>
    <td>예</td>
    <td>예</td>
  <tr>  
</table>

Kibana에 대한 자세한 정보는 [Kibana 사용자 안내서 ![외부 링크 아이콘](../../../icons/launch-glyph.svg "외부 링크 아이콘")](https://www.elastic.co/guide/en/kibana/4.1/index.html){: new_window}를 참조하십시오.
    

##  Bluemix 대시보드에서 Kibana 대시보드로 이동
{: #launch_Kibana_from_bluemix}

Kibana에 표시된 데이터를 필터링하는 데 사용되는 조회를 통해 Kibana를 시작할 {{site.data.keyword.Bluemix_notm}} CF 앱 또는 컨테이너의 로그 항목을 검색합니다.

Kibana에서 Cloud Foundry 애플리케이션 또는 Docker 컨테이너의 로그를 보려면 다음 단계를 수행하십시오.

1. {{site.data.keyword.Bluemix_notm}}에 로그인한 다음 {{site.data.keyword.Bluemix_notm}} 대시보드에서 앱 이름 또는 컨테이너를 클릭하십시오. 
    
2. {{site.data.keyword.Bluemix_notm}} UI에서 로그 탭을 여십시오.

    * CF 앱의 경우 탐색줄에서 **로그**를 클릭하십시오. 
    * {{site.data.keyword.Bluemix_notm}} 관리 클라우드 인프라에 배치된 컨테이너의 경우, 탐색줄에서 **모니터링 및 로그**를 선택한 후 **로깅** 탭을 클릭하십시오.  
    
         로그 탭이 열립니다.  

3. **고급 보기**를 클릭하십시오. Kibana 대시보드가 열립니다. 

    기본적으로 **검색** 페이지는 기본 색인 패턴이 선택되고 시간 필터가 지난 30초로 설정되어 로드됩니다. 검색 조회는 CF 앱 또는 Docker 컨테이너의 모든 항목과 일치하도록 설정됩니다.

    검색 페이지에서 로그 항목을 표시하지 않으면 시간 선택 도구를 조정하십시오. 자세한 정보는 [시간 필터 설정](logging_kibana_set_time_filter.html#set_time_filter)을 참조하십시오.


##  웹 브라우저에서 Kibana 대시보드로 이동
{: #launch_Kibana_from_browser}

Kibana에 표시되는 데이터를 필터링하는 데 사용되는 조회는 {{site.data.keyword.Bluemix_notm}} 조직에서 영역의 로그 항목을 검색합니다. Kibana에 표시되는 로그 정보에는 로그인한 {{site.data.keyword.Bluemix_notm}} 조직의 영역 내에 배치된 모든 리소스에 대한 레코드가 포함됩니다.

브라우저에서 Kibana를 시작하려면 다음 단계를 완료하십시오. 

1. [https://logging.<span class="keyword" data-hd-keyref="DomainName">DomainName</span>](https://logging.{DomainName})을 열어 Kibana 사용자 인터페이스에 로그인하십시오. 
    
    예를 들어, 다음과 같습니다. 
      
        <table>
          <caption>표 1. Kibana 시작 URL</caption>
           <tr>
            <th>지역</th>
            <th>URL</th>
          </tr>
          <tr>
            <td>미국 남부</td>
            <td>https://logging.ng.bluemix.net/</td>
          </tr>
          <tr>
            <td>영국</td>
            <td>https://logging.eu-gb.bluemix.net/</td>
          </tr>
        </table>

    검색 페이지에서 로그 항목을 표시하지 않으면 시간 선택 도구를 조정하십시오. 자세한 정보는 [시간 필터 설정](logging_kibana_set_time_filter.html#set_time_filter)을 참조하십시오.


