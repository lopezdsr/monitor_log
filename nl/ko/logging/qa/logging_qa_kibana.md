---

copyright:
  years: 2015, 2017

lastupdated: "2017-05-22"

---


{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:screen: .screen}


# Kibana FAQ
{: #logging_qa_kibana}

다음은 {{site.data.keyword.Bluemix}} 로깅 기능을 사용하는 데 대한 일반적인 질문의 응답입니다.
{:shortdesc}

* [Kibana의 검색 페이지에 데이터를 표시할 수 없으면 어떻게 합니까?](logging_qa_kibana.html#logging_qa_no_data_discover_kibana)
* [인증 예외가 발생하면 어떻게 합니까?](logging_qa_kibana.html#logging_qa_no_data_dashboard_kibana)
* [Kibana 3 시작 방법](logging_qa_kibana.html#logging_qa_kibana3)
* [Kibana 검색 페이지에서 ? 기호가 표시되는 이유](logging_qa_kibana.html#logging_qa_kibana_question)

## Kibana의 검색 페이지에 데이터를 표시할 수 없으면 어떻게 합니까?
{: #logging_qa_no_data_discover_kibana}

Kibana에 데이터가 표시되지 않을 수 있는 시나리오는 다음과 같이 다양합니다.

1. Kibana를 시작할 때 검색 페이지에 데이터가 표시되지 않을 수 있습니다. **결과를 찾을 수 없습니다.**라는 메시지가 표시됩니다. 
2. Kibana의 검색 페이지에서 작업 중일 수 있습니다. 그러나 Kibana에서 태스크를 수행할 때 정렬 기간이 지나고 나면 **결과를 찾을 수 없습니다.**라는 메시지가 표시됩니다.

이 문제점을 해결하려면 다음 단계를 완료하십시오.

1. 검색 페이지에 설정된 *시간 선택도구*를 확인하고 기간을 늘리십시오. 

    **참고**: 기본적으로 {{site.data.keyword.Bluemix_notm}}에서 지난 5분 동안의 데이터를 표시하도록 *시간 선택도구*가 설정됩니다.

    *시간 선택도구*를 설정하는 방법에 대한 자세한 정보는 [시간 필터 설정](../kibana4/k4_filter_logs.html#set_time_filter)을 참조하십시오.
       
2. *검색* 페이지 검색 표시줄에 있는 돋보기를 클릭하십시오. 기본 검색 조회를 기반으로 페이지 데이터를 새로 고칩니다.

    또는 *자동으로 새로 고치기* 기간을 설정할 수 있습니다.

    **참고**: 기본적으로 {{site.data.keyword.Bluemix_notm}}에서 *자동으로 새로 고치기* 기간은 **OFF**로 설정됩니다.
    
    사용하는 방법에 대한 자세한 정보는 [자동으로 데이터 새로 고치기](../kibana4/logging_kibana_analize_logs_interactively.html#kibana_discover_view_refresh_interval)를 참조하십시오.



## 인증 예외가 발생하면 어떻게 합니까?
{: #logging_qa_no_data_dashboard_kibana}

대시보드 페이지에서 시각화에 표시된 데이터를 볼 수 없고 **오류: 인증 예외** 오류 메시지가 표시되면 각 시각화에서 데이터를 볼 권한을 확인하십시오.

다음 정보를 고려하십시오.
대시보드 페이지에서 하나 이상의 시각화를 구성할 수 있습니다. 대시보드 페이지에서 해당 시각화를 통해 표시된 데이터를 수집하도록 요청하면 모든 시각화에 대해 하나의 요청만 발행됩니다. 시각화 중 하나의 데이터를 볼 권한이 없으면 전체 요청이 실패합니다.

이 문제점을 해결하려면 다음 단계를 완료하십시오.

1. 권한이 없는 시각화를 식별하십시오.

    1. *대시보드* 페이지에서 시각화의 *연필* 아이콘을 클릭하십시오. *시각화* 페이지에 시각화가 열립니다. 또는 *시각화* 페이지에서 한 시각화를 로드하십시오. 
    2. 데이터를 볼 수 있는지 확인하십시오.
    
    각 시각화에 대해 이 단계를 반복하십시오.

2. 클라우드 관리자에서 해당 시각화의 데이터를 볼 액세스 권한을 요청하십시오.

3. 문제점을 초래하는 시각화에서 데이터를 볼 액세스 권한이 부여되는 동안 권한이 없는 시각화를 제외하는 새 대시보드 페이지를 작성하십시오. 

    대시보드를 공유하는 경우 시각화가 동일한 대시보드를 사용하는 다른 팀 구성원에 영향을 미치므로 시각화를 삭제하지 마십시오.

## Kibana 3 시작 방법
{: #logging_qa_kibana3}

**참고:** Kibana 3은 더 이상 사용되지 않습니다.

Kibana 3은 브라우저에서 시작할 수 있습니다. 

브라우저에서 Kibana 3을 시작하려면 다음 단계를 완료하십시오. 

1. Kibana 사용자 인터페이스에 로그인하려면 [https://logmet.<span class="keyword" data-hd-keyref="DomainName">DomainName</span>](https://logmet.{DomainName})을 여십시오. 
    
2. 로그를 분석하는 데 사용할 Kibana의 버전을 선택하십시오.
    * **Kibana 4** 탭을 선택하여 Kibana 4로 작업하십시오. 검색 페이지가 열립니다. 자세한 정보는 [logging_kibana_analize_logs_interactively.html#kibana_analize_logs_interactively)를 참조하십시오.
    * **Kibana 3** 탭을 선택하여 Kibana 3으로 작업하십시오. 기본 Kibana 대시보드가 열립니다. Kibana 3을 사용하여 로그를 분석하는 데 대한 정보는 [Kibana 3에서 로그 분석(더 이상 사용되지 않음)](../logging_view_kibana3.html#analyzing_logs_Kibana3)을 참조하십시오. Kibana 3 대시보드 사용자 정의에 대한 자세한 정보는 [이 블로그 포스트 ![외부 링크 아이콘](../../../icons/launch-glyph.svg "외부 링크 아이콘")](https://www.ibm.com/blogs/bluemix/2015/09/creating-custom-kibana-dashboard-in-bluemix/)를 참조하십시오.
     

## Kibana 검색 페이지에서 ? 기호가 표시되는 이유
{: #logging_qa_kibana_question}

Kibana에서 검색 페이지를 열었을 때 문자 `t` 대신 `?`가 사용 가능한 필드 섹션에 나열된 필드 옆에 표시됩니다. 필드 목록을 다시 로드하면 필드 유형이 분석되며 `?`가 문자 `t`로 대체됩니다. 자세한 정보는 [필드 목록 다시 로드](../kibana4/logging_kibana_analize_logs_interactively.html#kibana_discover_view_reload_fields)를 참조하십시오. 



