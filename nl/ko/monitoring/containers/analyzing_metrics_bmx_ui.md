---

copyright:
  years: 2017

lastupdated: "2017-05-25"

---


{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:screen: .screen}

# Bluemix 콘솔에서 컨테이너 메트릭 분석
{: #analyzing_metrics_bmx_ui}

{{site.data.keyword.Bluemix}}에서는 {{site.data.keyword.Bluemix_notm}} 관리 클라우드 인프라에 배치되는 Docker 컨테이너에서 사용 가능한 *모니터링* 탭을 통해 메트릭을 보고 분석할 수 있습니다.
{:shortdesc}

{{site.data.keyword.Bluemix_notm}} 퍼블릭에서는 통합 모니터링 기능을 제공합니다.  

분석 및 데이터 보존을 위한 메트릭 가용성에 대한 다음 정보를 고려하십시오. 

* {{site.data.keyword.Bluemix_notm}} 퍼블릭에서 메트릭은 기본적으로 7일 동안 저장됩니다.  
* 하루에 최대 1GB의 데이터를 저장할 수 있습니다. 
* 기본적으로 {{site.data.keyword.Bluemix_notm}} 콘솔에서 분석에 사용 가능한 메트릭에는 최근 24시간 동안의 데이터가 포함됩니다. 

**팁:** 최근 24시간보다 이전인 사용자 정의 기간의 데이터를 분석하려면 Grafana를 사용하십시오. 


##  Bluemix에서 관리되는 Docker 컨테이너의 메트릭으로 이동
{: #launch_metrics_tab_bmx_ui_containers}

{{site.data.keyword.Bluemix_notm}} 관리 클라우드 인프라에 배치된 Docker 컨테이너의 메트릭을 보려면 다음 단계를 완료하십시오. 

1. 앱 대시보드에서 단일 컨테이너 또는 컨테이너 그룹을 클릭하십시오. 
    
2. 앱 세부사항 페이지에서 **모니터링 및 로그**를 클릭하십시오.

3. **모니터링** 탭을 선택하십시오. 
    
    **모니터링** 탭에서는 컨테이너의 메트릭을 볼 수 있습니다. 
