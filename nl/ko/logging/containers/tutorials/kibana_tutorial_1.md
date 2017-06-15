---

copyright:
  years: 2015, 2017

lastupdated: "2017-05-23"

---


{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:screen: .screen}


# Kubernetes 클러스터에 배치된 앱에 대한 Kibana에서의 로그 분석
{: #kibana_tutorial_1}

Kibana를 시작하십시오. Kubernetes 클러스터에 배치된 앱에 대한 컨테이너 로그를 검색하고 분석하는 방법을 학습하십시오.
{:shortdesc}

**참고:** 이 튜토리얼을 완료하려면 여러 단계에 링크된 튜토리얼을 완료하십시오. 

## 전제조건
{: #prereq}

1. Kubernetes 클러스터를 작성하고, 클러스터에 앱을 배치하고, Kibana에서의 고급 분석을 위해 Bluemix에서 로그를 조회할 수 있는 권한을 가진 Bluemix 계정의 구성원 또는 소유자입니다. 

2. Kubernetes 클러스터를 관리하고 명령행에서 앱을 배치할 수 있는 터미널 세션이 있습니다. 이 튜토리얼의 예는 Ubuntu Linux 시스템에 대해 제공된 예입니다. 

3. IBM Bluemix 컨테이너 서비스를 명령행에서 관리하기 위해 Ubuntu 시스템에 [CLI 플러그인을 설치하십시오](../../../../containers/cs_cli_install.html#cs_cli_install_steps).  


## 1단계: Bluemix에서 Kubernetes 시작 및 실행
{: #step1}

다음 단계를 수행하십시오. 

1. [Kubernetes 클러스터를 작성하십시오](../../../../containers/cs_cluster.html#cs_cluster_ui). 

2. Linux 터미널에서 [클러스터 컨텍스트를 설정하십시오](../../../../containers/cs_cli_install.html#cs_cli_configure). 컨텍스트가 설정되면 Kubernetes 클러스터를 관리하고 Kubernetes 클러스터에 애플리케이션을 배치할 수 있습니다. 

## 2단계: Kubernetes 클러스터에 앱 배치
{: #step2}

Kubernetes 클러스터에 샘플 앱을 배치하고 실행하십시오. [학습 1의 단계를 완료하십시오](../../../../containers/cs_tutorials.html#cs_apps_tutorial). 

앱은 Hello World node js 앱입니다. 

```
var express = require('express')
var app = express()

app.get('/', function(req, res) {
  res.send('Hello world! Your app is up and running in a cluster!\n')
})
app.listen(8080, function() {
  console.log('Sample app is listening on port 8080.')
})
```

앱이 배치되면 앱에서 stdout(표준 출력) 및 stderr(표준 오류)로 전송하는 로그 항목에 대해 로그 수집이 자동으로 사용으로 설정됩니다.  

이 샘플 앱에서는 브라우저에서 이 앱을 테스트할 때 앱이 stdout에 다음 메시지를 기록합니다: `Sample app is listening on port 8080.`


## 3단계: Kibana에서 로그 데이터 분석
{: #step3}

1. 브라우저에서 Kibana를 시작하십시오.  

    클러스터의 로그 데이터를 분석하려면 클러스터가 작성된 클라우드 퍼블릭 지역에 액세스해야 합니다.  
    
    이전 단계에서 Kubernetes 클러스터를 작성한 지역에 따라 올바른 URL을 선택하십시오. 

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
           <tr>
             <td>프랑크푸르트</td>
             <td>https://logging.eu-de.bluemix.net/</td>
           </tr>
    </table>
    
    그 후, 브라우저에서 해당 URL을 사용하여 Kibana를 여십시오. 
    
2. **검색** 페이지에서 표시되는 이벤트를 살펴보십시오.  

    샘플 Hello-World 애플리케이션은 하나의 이벤트를 생성합니다. 
    
    ![Kibana의 검색 페이지](images/sampleapp_2.gif "Kibana의 검색 페이지")
    
    *사용 가능한 필드* 섹션에서는 새 조회를 정의하는 데 사용할 수 있는 필드의 목록을 보거나 페이지에 표시된 테이블에 나열된 항목을 필터링할 수 있습니다. 
    
    다음 표에는 새 검색 조회를 정의하는 데 사용할 수 있는 공통 필드가 나열되어 있습니다. 이 표에는 샘플 앱에서 생성하는 이벤트에 해당하는 샘플 값도 포함되어 있습니다. 
    
     <table>
              <caption>표 2. 컨테이너 로그의 공통 필드</caption>
               <tr>
                <th align="center">필드 </th>
                <th align="center">설명</th>
                <th align="center">예</th>
              </tr>
              <tr>
                <td>*docker.container_id_str*</td>
                <td> 이 필드의 값은 Kubernetes 클러스터의 포드에서 앱을 실행하는 컨테이너의 GUID에 해당합니다. </td>
                <td></td>
              </tr>
              <tr>
                <td>*ibm-containers.region_str*</td>
                <td>이 필드의 값은 로그 항목이 수집된 {{site.data.keyword.Bluemix_notm}} 지역에 해당합니다. </td>
                <td>us-south</td>
              </tr>
              <tr>
                <td>*kubernetes.container_name_str*</td>
                <td>이 필드의 값은 컨테이너의 이름을 알립니다. </td>
                <td>hello-world-deployment</td>
              </tr>
              <tr>
                <td>*kubernetes.host*</td>
                <td>이 필드의 값은 인터넷에서 이 앱에 액세스하기 위해 사용할 수 있는 공인 IP를 알립니다. </td>
                <td>xxx.xx.xxx.xxx</td>
              </tr>
              <tr>
                <td>*kubernetes.labels.label_name*</td>
                <td>레이블 필드는 선택사항입니다. 레이블은 0개 이상 보유할 수 있습니다. 각 레이블은 `kubernetes.labels.`로 시작하며 그 뒤에는 *label_name*이 붙습니다. </td>
                <td>샘플 앱에서는 2개의 레이블을 볼 수 있습니다. <br>* *kubernetes.labels.pod-template-hash_str* = 3355293961 <br>* *kubernetes.labels.run_str* =	hello-world-deployment </td>
              </tr>
              <tr>
                <td>*kubernetes.namespace_name_str*</td>
                <td>이 필드의 값은 포드가 실행 중인 Kubernetes 네임스페이스를 알립니다. </td>
                <td>기본값</td>
              </tr>
              <tr>
                <td>*kubernetes.pod_id_str*</td>
                <td>이 필드의 값은 컨테이너가 실행되는 포드의 GUID에 해당합니다. </td>
                <td>d695f346-xxxx-xxxx-xxxx-aab0b50f7315</td>
              </tr>
              <tr>
                <td>*kubernetes.pod_name_str*</td>
                <td>이 필드의 값은 포드 이름을 알립니다. </td>
                <td>hello-world-deployment-3xxxxxxx1-xxxxx8</td>
              </tr>
              <tr>
                <td>*message*</td>
                <td>이 메시지는 애플리케이션에서 로그한 전체 메시지입니다. </td>
                <td>Sample app is listening on port 8080.</td>
              </tr>
        </table>
    
    
    
3. *검색* 페이지의 데이터를 필터링하십시오.   

    테이블에서는 분석하는 데 사용 가능한 모든 항목을 볼 수 있습니다. 나열되는 항목은 *검색* 막대에 표시되는 검색 조회에 해당합니다. `*`는 페이지에 대해 구성된 기간 내의 모든 항목을 표시하는 데 사용되는 문자입니다.  
    
    예를 들어, Kubernetes 네임스페이스로 데이터를 필터링하려면 *검색* 막대 조회를 수정하십시오. 사용자 정의 필드 *kubernetes.namespace_name_str*을 기반으로 하는 필터를 추가하십시오. 
    
    1. **사용 가능한 필드** 섹션에서 필드 *kubernetes.namespace_name_str*을 선택하십시오. 필드에 대해 사용 가능한 값의 서브세트가 표시됩니다.     
    
    2. 값 **default**를 선택하십시오. 이는 이전 단계에서 샘플 앱에 배치한 네임스페이스입니다. 
    
        값을 선택하면 *검색 막대*에 필터가 표시되며 방금 선택한 기준과 일치하는 항목만 테이블에 표시됩니다.      
    
    ![기본 Kubernetes 네임스페이스에 대한 검색으로 필터링](images/sampleapp_k4_1.gif "기본 Kubernetes 네임스페이스에 대한 검색으로 필터링")
    
    필터의 편집 기호를 선택하여 검색하는 네임스페이스 이름을 수정할 수 있습니다.    
    
    ![필터에 대해 사용 가능한 조치](images/sampleapp_k4_1.gif "필터에 대해 사용 가능한 조치")
    
    다음 조회가 표시됩니다. 
    
    ```{
        "query": {
          "match": {
            "kubernetes.namespace_name_str": {
              "query": "default",
              "type": "phrase"
            }
          }
        }
      }
    ```
    
    *mynamespace1*과 같은 별도의 네임스페이스의 항목을 검색하려면 조회를 수정하십시오. 
    
    ```{
        "query": {
          "match": {
            "kubernetes.namespace_name_str": {
              "query": "mynamespace1",
              "type": "phrase"
            }
          }
        }
      }
    ```
    

    데이터가 표시되지 않는 경우에는 시간 필터를 변경해 보십시오. 자세한 정보는 [시간 필터 설정](../../kibana4/k4_filter_logs.html#set_time_filter)을 참조하십시오.
    


자세한 정보는 [Kibana에서 로그 필터링](../../kibana4/k4_filter_logs.html#k4_filter_logs)을 참조하십시오.

