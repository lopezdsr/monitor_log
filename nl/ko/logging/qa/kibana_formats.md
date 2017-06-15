---

copyright:
  years: 2015, 2017

lastupdated: "2017-05-23"

---


{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:screen: .screen}

# Kibana 로그 형식
{: #kibana_formats}

*검색* 페이지에 각 로그 항목의 여러 필드를 표시하도록 Kibana를 구성할 수 있습니다.
{:shortdesc}



## Cloud Foundry 애플리케이션에 대한 Kibana 로그 형식
{: #kibana_log_format_cf}

*검색* 페이지에 각 로그 항목의 다음 필드를 표시하도록 Kibana를 구성할 수 있습니다. 

| 필드  | 설명 |
|-------|-------------|
| @timestamp | `yyyy-MM-ddTHH:mm:ss:SS-0500`  <br> 로그된 이벤트의 시간입니다. <br> 시간소인은 밀리초 단위까지 정의됩니다.  |
| @version | 이벤트의 버전입니다. |
| ALCH_TENANT_ID | {{site.data.keyword.Bluemix_notm}} 영역의 ID입니다. |
| \_id | 로그 문서의 고유 ID입니다. |
| \_index | 로그 항목의 색인입니다. |
| \_type | 로그 유형(예: *syslog*)입니다. |
| app_name | {{site.data.keyword.Bluemix_notm}} 애플리케이션의 이름입니다. |
| application_id | {{site.data.keyword.Bluemix_notm}} 애플리케이션의 고유 ID입니다. |
| host | 로그 데이터를 생성한 애플리케이션의 이름입니다. |
| instance_id | 로그 데이터를 생성한 애플리케이션 인스턴스의 인스턴스 ID입니다. |
| loglevel | 로그된 이벤트의 심각도입니다. |
| message | 컴포넌트에서 발행하는 메시지. <br> 메시지는 컨텍스트에 따라 달라집니다. |
| message_type | 로그 메시지가 기록되는 스트림. <br> * **OUT**은 stdout 스트림을 나타냅니다. <br> * **ERR**는 stderr 스트림을 나타냅니다. |
| org_id | {{site.data.keyword.Bluemix_notm}} 조직의 고유 ID입니다. |
| org_name | 앱이 스테이징된 {{site.data.keyword.Bluemix_notm}} 조직의 이름입니다. |
| origin | 이벤트가 시작되는 컴포넌트입니다. |
| source_id | 로그를 생성하는 컴포넌트. <br> 다음 목록에서는 각 컴포넌트의 로그에 대해 설명합니다.<br> * **API**: 앱 상태 변경을 요청하는 API 호출에 대해 로깅된 응답니다. <br> * **APP**: 앱에서 로깅된 응답니다. <br> * **CELL**: 앱이 시작, 중지 또는 충돌한 시기를 표시하는 Diego 셀의 로깅된 응답입니다. <br> * **LGR**: 로깅 프로세스의 문제점을 표시하는 loggregator의 로깅된 응답입니다. <br> * **RTR**: HTTP 요청을 앱에 라우팅할 때 라우터에서 로깅된 응답입니다. <br> * **SSH**: `cf ssh` 명령을 사용하여 앱 컨테이너에 액세스할 때 Diego 셀에서 로깅된 응답입니다. <br> * **STG**: 앱이 스테이징되거나 다시 스테이징될 때 DEA(Droplet Execution Agent) 또는 Diego 셀에서 로그된 응답입니다. |
| space_name | 앱이 스테이징된 {{site.data.keyword.Bluemix_notm}} 영역의 이름입니다. |
| timestamp | 로그된 이벤트의 시간입니다. 시간소인은 밀리초 단위까지 정의됩니다.  |
{: caption="표 1. CF 앱의 필드" caption-side="top"}



## Bluemix 관리 인프라에 배치된 Docker 컨테이너의 Kibana 로그 형식
{: #kibana_log_format_containers}

*검색* 페이지에 각 로그 항목의 다음 필드를 표시하도록 Kibana를 구성할 수 있습니다. 

| 필드  | 설명 |
|-------|-------------|
| @timestamp | `yyyy-MM-ddTHH:mm:ss:SS-0500`  <br> 로그된 이벤트의 시간입니다. <br> 시간소인은 밀리초 단위까지 정의됩니다.  |
| @version | 이벤트의 버전입니다. |
| ALCH_TENANT_ID | {{site.data.keyword.Bluemix_notm}} 영역의 ID입니다. |
| \_id | 로그 문서의 고유 ID입니다. |
| \_index | 로그 항목의 색인입니다. |
| \_type | 로그의 유형(예: *logs*)입니다. |
| group_id | 그룹 ID<br> * 단일 컨테이너의 경우 값은 **0000**입니다. <br> * 컨테이너 그룹의 경우 값은 그룹의 GUID 입니다.  |
| host | 컨테이너가 실행되는 호스트 이름입니다. |
| instance | 단일 컨테이너의 인스턴스 GUID 입니다. 컨테이너 그룹의 인스턴스 ID 목록입니다.|
| log | 간단한 메시지입니다. |
| message | 전체 메시지입니다. |
| path | 로그가 컨테이너 내부에 있는 경로 및 로그 이름입니다. |
| stream | 로그의 유형을 지정합니다(stdout, stderr). |
| time | 이벤트 발생 날짜 및 시간입니다. 시간소인은 밀리초 단위까지 정의됩니다. |
| timestamp | 로깅된 이벤트의 날짜 및 시간입니다. 시간소인은 밀리초 단위까지 정의됩니다.  |
{: caption="표 2. Docker 컨테이너의 필드" caption-side="top"}

## Kubernetes 클러스터에 배치된 Docker 컨테이너의 Kibana 로그 형식
{: #kibana_log_format_containers_kubernetes}

*검색* 페이지에서 각 로그 항목에 대해 다음 필드를 표시하도록 Kibana를 구성할 수 있습니다. 이러한 필드는 {{site.data.keyword.IBM}}에 의해 설정되며 메시지 데이터에 포함됩니다.  

| 필드  | 설명 | 기타 정보 |
|-------|-------------|---------------------------|
| @timestamp | `yyyy-MM-ddTHH:mm:ss:SS-0500`  <br> 로그된 이벤트의 시간입니다. <br> 시간소인은 밀리초 단위까지 정의됩니다.  | |
| @version | 이벤트의 버전입니다. | |
| ALCH_TENANT_ID | {{site.data.keyword.Bluemix_notm}} 영역의 ID입니다. | |
| \_id | 로그 문서의 고유 ID 입니다. | |
| \_index | 로그 항목의 색인입니다. | |
| \_score |  |  |
| \_type | 로그의 유형(예: *logs*)입니다. | |
| crn_str | 로그의 소스에 대한 정보입니다. | 기본적으로, 이 필드는 {{site.data.keyword.IBM_notm}}에 의해 설정됩니다. <br> **참고**: 로그 메시지를 유효한 JSON 형식으로 전송하며 필드 중 하나의 이름이 `crn`인 경우 이 필드의 값을 메시지에 설정된 값을 겹쳐씁니다.  |  
| docker.container_id_str | 포드에서 실행 중인 컨테이너의 GUID입니다. | |
| ibm-containers.account_str | {{site.data.keyword.Bluemix_notm}} 계정의 GUID입니다.  |  |
| ibm-containers.cluster_id_str | Kubernetes 클러스터의 GUID입니다.  |  |
| ibm-containers.cluster_type_str |  | {{site.data.keyword.IBM_notm}} 내부용으로 예약된 값입니다. |
| ibm-containers.region_str | {{site.data.keyword.Bluemix_notm}}의 지역입니다.  |  |
| kubernetes.container_name_str | 앱이 배치된 컨테이너의 이름입니다.  |  |
| kubernetes.host | 컨테이너가 실행 중인 작업자의 공인 IP 주소입니다. |  |
| kubernetes.labels.*example_label_name*\_str | 포드와 같은 Kubernetes 오브젝트에 연결하는 키-값 쌍입니다. | Kubernetes 오브젝트에 연결하는 각 레이블은 Kibana에서 표시되는 로그 항목에 필드로 나열됩니다. <br> 레이블은 0개 이상 보유할 수 있습니다. |
| kubernetes.namespace_name_str | 컨테이너가 배치된 Kubernetes 네임스페이스입니다. |  |
| kubernetes.pod_id_str | 컨테이너가 배치된 포드의 GUID입니다. |  |
| kubernetes.pod_name_str | 포드의 이름입니다. |  |
| message | 전체 메시지입니다. | 유효한 JSON 형식화된 메시지를 전송하는 경우 각 필드는 Kibana에서 개별적으로 구문 분석되어 표시됩니다.  |
| stream_str |  | {{site.data.keyword.IBM_notm}} 내부용으로 예약된 값입니다. |
|tag_str |  | {{site.data.keyword.IBM_notm}} 내부용으로 예약된 값입니다. |
{: caption="표 3. Docker 컨테이너의 필드" caption-side="top"}


## Message Hub의 Kibana 로그 형식
{: #kibana_log_format_messagehub}

*검색* 페이지에 각 로그 항목의 다음 필드를 표시하도록 Kibana를 구성할 수 있습니다. 

| 필드  | 설명 |
|-------|-------------|
| @timestamp | `yyyy-MM-ddTHH:mm:ss:SS-0500`  <br> 로그된 이벤트의 시간입니다. <br> 시간소인은 밀리초 단위까지 정의됩니다.  |
| @version | 이벤트의 버전입니다. |
| ALCH_TENANT_ID | {{site.data.keyword.Bluemix_notm}} 영역의 ID입니다. |
| \_id | 로그 문서의 고유 ID 입니다. |
| \_index | 로그 항목의 색인입니다. |
| \_type | 로그 유형(예: *syslog*)입니다. |
| loglevel | 로깅된 이벤트의 심각도입니다(예: **Info**). |
| module | 이 필드는 **MessageHub**로 설정됩니다. |
{: caption="표 4. 메시지 허브 이벤트의 필드" caption-side="top"}

로그 항목의 예:

```
March 8th 2017, 17:15:16.454	

message:
    Creating topic ABC
@version:
    1
@timestamp:
    March 8th 2017, 17:15:16.454
loglevel:
    Info
module:
    MessageHub
ALCH_TENANT_ID:
    3d8d2eae-f3f0-44f6-9717-126113a00b51
&#95;id:
    AVqu6vJl1zcfr8KYMI95
&#95;type:
    logs
&#95;index:
    logstash-2017.03.08
```
