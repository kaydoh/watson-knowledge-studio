---

copyright:
  years: 2015, 2018
lastupdated: "2018-04-04"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:tip: .tip}
{:pre: .pre}
{:codeblock: .codeblock}
{:screen: .screen}
{:javascript: .ph data-hd-programlang='javascript'}
{:java: .ph data-hd-programlang='java'}
{:python: .ph data-hd-programlang='python'}
{:swift: .ph data-hd-programlang='swift'}

이 문서는 {{site.data.keyword.knowledgestudiofull}} on {{site.data.keyword.cloud}}에 대한 문서입니다. 이전 {{site.data.keyword.knowledgestudioshort}} on {{site.data.keyword.IBM_notm}} Marketplace 버전에 대한 문서를 보려면 [이 링크 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")를 클릭하십시오](https://console.bluemix.net/docs/services/knowledge-studio/troubleshooting.html){: new_window}.
{: tip}

# 문제점 해결, 지원 및 FAQ
{: #troubleshooting}

{{site.data.keyword.IBM_notm}} 제품의 문제점을 격리하고 해결하기 위해 문제점 해결 및 지원 정보를 사용할 수 있습니다. 이 정보에는 {{site.data.keyword.knowledgestudiofull}}를 비롯한 {{site.data.keyword.IBM_notm}} 제품과 함께 제공된 문제점 판별 리소스의 사용에 대한 지시사항이 포함되어 있습니다.
{: shortdesc}

## 문제점 해결을 위한 기법
{: #ts_overview}

*문제점 해결*은 문제점을 해결하는 체계적인 접근법입니다. 문제점 해결의 목표는 특정 항목이 예상대로 작동하지 않는 이유와 문제점 해결 방법을 판별하는 것입니다. 특정한 공통 기법은 문제점 해결 작업에 도움을 줄 수 있습니다. 

문제점 해결 프로세스의 첫 번째 단계는 문제점을 완전하게 설명하는 것입니다. 문제점 설명은 사용자 및 {{site.data.keyword.IBM_notm}} 기술 지원 담당자가 문제점의 원인을 어디서부터 찾아야 하는지 알 수 있도록 도와줍니다. 이 단계에는 사용자 스스로 확인할 수 있는 기본 질문이 포함되어 있습니다. 

- 문제점의 증상은 무엇입니까? 
- 어디서 문제점이 발생합니까? 
- 언제 문제점이 발생합니까? 
- 어떤 조건에서 문제점이 발생합니까? 
- 문제점을 재현할 수 있습니까? 

일반적으로 이러한 질문에 응답하면 문제점이 잘 설명되며, 이는 문제점 해결로 이어집니다. 

### 문제점의 증상은 무엇입니까? 

문제점 설명을 시작할 때 가장 명백한 질문은 "문제점이 무엇입니까?"입니다. 이 질문은 단순해 보일 수 있으나, 사용자는 문제점을 보다 구체적으로 설명하는 여러 세부적인 질문으로 이 질문을 나눌 수 있습니다. 이러한 질문은 다음 질문을 포함할 수 있습니다. 

- 누가, 또는 무엇이 문제점을 보고합니까? 
- 오류 코드 및 메시지는 무엇입니까? 
- 시스템이 어떻게 실패합니까? 예를 들면, 실패의 유형이 루프, 정지, 충돌, 성능 저하 또는 올바르지 않은 결과 중 무엇입니까? 

### 어디서 문제점이 발생합니까? 

문제점이 시작된 위치를 판별하는 것이 항상 쉽지는 않지만, 이는 문제점 해결에서 가장 중요한 단계 중 하나입니다. 보고하는 컴포넌트와 실패한 컴포넌트 사이에 여러 기술 계층이 존재할 수 있습니다. 네트워크, 디스크, 드라이버는 문제점을 조사할 때 고려하는 컴포넌트 중 일부에 불과합니다. 

다음 질문은 문제점이 발생한 계층을 격리하기 위해 문제점 발생 위치에 집중하는 데 도움을 줍니다. 

- 문제점이 특정 플랫폼 또는 운영 체제에서만 발생합니까? 아니면 여러 플랫폼 또는 운영 체제에서 공통적으로 발생합니까? 
- 현재 환경 및 구성이 지원됩니까? 
- 모든 사용자에게 문제점이 발생합니까? 
- (멀티 사이트 설치의 경우) 모든 사이트에서 문제점이 발생합니까? 

한 계층이 문제점을 보고한다고 해서 반드시 해당 계층이 문제점의 원인이라고 단정할 수는 없습니다. 문제점이 발생한 위치를 식별하는 작업의 일부는 문제점이 속한 환경을 이해하는 것입니다. 충분한 시간을 가지고 운영 체제와 버전, 모든 해당 소프트웨어와 버전 및 하드웨어 정보를 비롯한 문제점 환경을 완전히 설명하십시오. 지원되는 구성인 환경에서 실행 중인지 확인하십시오. 많은 문제점은 함께 실행되도록 설계되지 않았거나 함께 완전히 테스트되지 않은, 호환되지 않는 소프트웨어 레벨로 인해 발생할 수 있습니다. 

### 언제 문제점이 발생합니까? 

실패가 발생하기까지의 상세한 이벤트 타임라인을 작성하십시오. 특히 일회성 실패인 경우에는 반드시 이를 수행하십시오. 역순으로 작업하면 타임라인을 가장 쉽게 작성할 수 있습니다. 사용 가능한 로그와 정보를 통해 오류가 보고된 시간(가능한 한 밀리초 단위까지 정확하게)에서 시작하여 역순으로 작업하십시오. 일반적으로는 진단 로그에서 발견되는 첫 번째 의심스러운 이벤트까지만 조사하면 됩니다. 

상세한 이벤트 타임라인을 작성하려면 다음 질문에 응답하십시오. 

- 문제점이 낮 또는 밤의 특정 시간에만 발생합니까? 
- 문제점이 얼마나 자주 발생합니까? 
- 문제점이 보고되는 시점에 이르기까지 어떤 이벤트 시퀀스가 발생합니까? 
- 환경 변경(예: 소프트웨어나 하드웨어의 업그레이드 또는 설치) 후에 문제점이 발생합니까? 

이런 유형의 질문에 응답하면 문제점을 조사할 참조 정보의 틀을 잡을 수 있습니다. 

### 어떤 조건에서 문제점이 발생합니까? 

문제점 발생 시 실행 중이던 시스템과 애플리케이션을 아는 것은 문제점 해결의 중요한 부분입니다. 환경에 대한 다음과 같은 질문은 문제점의 근본 원인을 식별하는 데 도움을 줍니다. 

- 동일한 태스크가 수행될 때 문제점이 항상 발생합니까? 
- 문제점이 발생하려면 특정한 이벤트 시퀀스가 발생해야 합니까? 
- 다른 애플리케이션도 동시에 실패합니까? 

이러한 유형의 질문에 응답하면 문제점이 발생하는 환경을 설명하고 종속성을 입증하는 데 도움이 됩니다. 여러 문제점이 거의 동시에 발생했다고 해서 이러한 문제점이 반드시 연관되어 있는 것은 아니라는 점을 기억하십시오. 

### 문제점을 재현할 수 있습니까? 

문제점 해결 관점에서 이상적인 문제점은 재현 가능한 문제점입니다. 일반적으로 문제점을 재현할 수 있는 경우에는 조사할 때 더욱 다양한 도구 또는 프로시저를 선택할 수 있습니다. 따라서 재현할 수 있는 문제점은 종종 보다 쉽게 디버그하고 해결할 수 있습니다. 

그러나 재현할 수 있는 문제점에는 단점도 있습니다. 해당 문제점이 비즈니스에 중대한 영향을 주는 경우에는 재발하지 않도록 해야 한다는 것입니다. 가능한 경우에는 조사 중에 일반적으로 보다 나은 유연성 및 제어를 제공하는 테스트 또는 개발 환경에서 문제점을 재현하십시오. 

- 문제점을 테스트 시스템에서 재현할 수 있습니까? 
- 여러 사용자 또는 애플리케이션에 동일한 유형의 문제점이 발생합니까? 
- 하나의 명령, 명령 세트 또는 특정 애플리케이션을 실행하여 문제점을 재현할 수 있습니까? 

## AlchemyLanguage 모델 문제
{: #wks_ts_deployed_model_deleted}

### 문제점

AlchemyLanguage 모델을 배치할 수 없거나, 배치가 성공했으나 모델을 사용할 수 없습니다. 

### 증상

- 모델을 배치했으나 상태가 오류가 발생했음을 표시합니다. 
- 모델을 배치했으며 상태가 모델이 사용 가능함을 표시했으나 모델을 사용할 수 없습니다. 
- 모델이 성공적으로 배치되어 이전에는 작동했으나, 지금은 작동하지 않습니다. 

### 원인

다음 이벤트는 배치된 모델에 문제점을 발생시킬 수 있습니다. 

- {{site.data.keyword.alchemyapishort}} 키를 REST API 호출의 `apikey` 매개변수에 추가할 때 이를 잘못 입력하면 호출이 실패합니다. 이는 모델 ID의 경우에도 마찬가지입니다. 입력 오류를 방지하기 위해 모델 ID 및 API 키는 복사하여 붙여넣는 것이 좋습니다. 
- 유효하지 않거나 사용자 정의 모델을 배치할 권한이 없는 {{site.data.keyword.alchemyapishort}} 키를 제공하는 경우 배치 프로세스는 배치가 성공했음을 표시하지만 이 모델을 사용할 수는 없습니다. 
- {{site.data.keyword.Bluemix}}에서 {{site.data.keyword.alchemylanguageshort}}를 사용하는 중에 {{site.data.keyword.Bluemix_notm}}의 {{site.data.keyword.alchemyapishort}}와 연관된 모든 서비스 인스턴스를 삭제하면 해당 키를 참조하는 모든 배치된 모델이 서비스에서 제거됩니다. {{site.data.keyword.Bluemix_notm}}는 등록된 모델이 유효한 키와 연관되어 있는지 주기적으로 확인하며 그렇지 않은 모델은 삭제됩니다. 모델이 배치될 때 연관된 키가 삭제되면 모델의 상태가 `error`로 변경됩니다. 

### 문제점 해결

1. 배치 상태를 확인하십시오. 

    {{site.data.keyword.knowledgestudioshort}} 관리자로 로그인하십시오. **Model Management** > **Versions** 페이지에서 **Status** 열을 보고 배치한 모델의 상태를 확인하십시오. 

1. 모델의 배치 상태가 `error`이거나, 상태가 `available`이지만 사용하려고 하면 작동하지 않는 경우에는 **Undeploy**를 클릭하여 모델을 배치에서 철회하십시오. 
1. 모델을 다시 배치하십시오. 

    모델을 배치할 권한이 있는 유효한 {{site.data.keyword.alchemyapishort}} 키만 사용하고, 모델 ID 및 API 키를 API 호출에 매개변수로서 추가할 때는 복사하여 붙여넣으십시오. 

**관련 태스크**:

[기계 학습 모델을 {{site.data.keyword.IBM_notm}} {{site.data.keyword.alchemylanguageshort}}에 배치](/docs/services/watson-knowledge-studio/publish-ml.html#wks_mabluemix)

## 무료 계정을 작성할 수 없음
{: #wks_ts_free}

### 문제점

무료 계정을 작성하려고 하면 오류 메시지 `Error 331: We are unable to process your request. Please try again later or contact the {{site.data.keyword.IBM_notm}} Helpdesk.`가 표시됩니다. 

### 원인

{{site.data.keyword.knowledgestudioshort}}는 조직당 둘 이상의 무료 계정을 허용하지 않습니다. 

### 문제점 해결

조직에 포함되지 않는 계정을 작성하십시오. 

현재 계정을 무료 평가판으로 사용해야 하며 사용자 계정이 유료 계정과 연관되어 있는 경우에는 지원 티켓을 제출할 수 있습니다. 자세한 정보는 [{{site.data.keyword.IBM_notm}} 지원 센터에 문의하기](/docs/services/watson-knowledge-studio/troubleshooting.html#ts_contactingibmsupport)를 참조하십시오. 

현재 계정을 무료 평가판으로 사용해야 하며 사용자 계정이 유료 계정과 연관되어 있지 않은 경우에는 문제를 [{{site.data.keyword.IBM_notm}} developerWorks 답변](https://developer.ibm.com/answers/topics/wks/)에 게시하고 질문에 **WKS** 태그를 지정하십시오. 

## 애플리케이션에 액세스할 수 없음
{: #wks_ts_access}

사용자에게 {{site.data.keyword.knowledgestudioshort}}에 대한 액세스 권한을 부여하는 방법을 알아본 후 일반적인 액세스 문제를 해결하십시오. 

{{site.data.keyword.IBM_notm}} {{site.data.keyword.knowledgestudioshort}}의 인스턴스를 요청하려면 {{site.data.keyword.IBM_notm}} 사용자 등록 신임 정보가 있어야 합니다. 

### 관리자

각 {{site.data.keyword.knowledgestudioshort}} 인스턴스에는 연관된 관리자 역할이 있습니다. 애플리케이션을 사용하기 위해 처음으로 가입한 사용자에게 관리자 역할이 자동으로 부여됩니다. 관리자는 다른 사용자를 초대할 수 있습니다. 

다른 사용자를 애플리케이션 인스턴스에 초대하는 방법에 대한 정보는 [팀 구성](/docs/services/watson-knowledge-studio/team.html)을 참조하십시오. 

### 사람 어노테이터

다른 누군가의 {{site.data.keyword.knowledgestudioshort}} 인스턴스에 사람 어노테이터로서 초대받은 경우에는 이메일 초대장을 수신합니다. 먼저, 아직 {{site.data.keyword.IBM_notm}} 등록 신임 정보가 없는 경우에는 {{site.data.keyword.IBM_notm}}에 등록해야 합니다. {{site.data.keyword.IBM_notm}}에 등록하고 초대를 수락하면 인스턴스에 대한 액세스 권한이 부여됩니다. 그러나 액세스 권한이 부여된 후, 문서 어노테이션 작성을 시작하려면 먼저 인스턴스의 관리자 또는 프로젝트 관리자가 사용자를 작업공간에 추가하고 사용자에게 어노테이션 작성 태스크를 지정해야 합니다. 태스크가 지정되기 전까지는 {{site.data.keyword.knowledgestudioshort}} 인스턴스에서 어떤 조치도 수행할 수 없습니다. 문서에 어노테이션을 작성하려면 기준 실제값 편집기를 사용하십시오. 최상의 성능을 위해서는 Google Chrome 브라우저를 사용하십시오. 

기준 실제값 편집기 사용에 대한 도움말은 [문서에 어노테이션 작성](/docs/services/watson-knowledge-studio/user-guide.html)을 참조하십시오. 

## 시범 서비스: *시범*이란 무엇을 의미합니까?
{: #experimental}

시범 서비스에 대한 정보는 [{{site.data.keyword.Bluemix_notm}} 문서](/docs/services/index.html#experimental_services)를 참조하십시오. 시범 서비스의 전체 세부사항은 [{{site.data.keyword.Bluemix_notm}} 서비스 설명 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](http://www.ibm.com/software/sla/sladb.nsf/searchsaas/?searchview&searchorder=4&searchmax=0&query=IBM+Bluemix+Service+Description){: new_window}의 최신 버전을 참조하십시오. 

## 스토리지 공간 문제
{: #storage}

구독 플랜에 따라, 플랜에 대해 지정된 스토리지 한계에 도달하여 완료하려는 태스크를 수행할 수 없는 경우가 있습니다. 

### 증상

다음 태스크 중 하나를 수행하려 하는 경우 허용된 스토리지 공간을 초과했다는 메시지가 표시됩니다. 

- 문서 또는 사전 업로드
- 모델 또는 모델의 버전 배치
- 문서에 대해 프리어노테이터(pre-annotator) 실행

### 원인

조치를 진행하면 스토리지 한계에 도달하거나 이를 초과합니다. 

### 문제점 해결

스토리지 공간을 가장 많이 이용하는 항목은 기계 학습 모델 및 규칙 기반 모델입니다. 공간을 확보하려면 다음 조치를 수행하십시오. 

- 되돌리는 데 사용하지 않을 모델의 스냅샷 버전을 삭제하십시오. 
- 필요하지 않은 모든 모델을 삭제하십시오. 
- 모델이 삭제하기에는 너무 중요한 경우에는 더 큰 스토리지 공간 할당을 제공하는 플랜으로 플랜을 업그레이드하는 것을 고려하십시오. 

모델 또는 모델 버전을 제거한 후에는 오류 메시지를 발생시킨 조치를 재시도하기 전에 한 시간 동안 기다리십시오. 확보한 스토리지 공간을 다시 사용할 수 있게 되려면 최대 한 시간이 소요됩니다. 

사용자에게 Admin 역할이 지정되어 있으며 사용자가 프리미엄 또는 표준 계정을 보유하고 있는 경우에는 월별 청구 요금을 관리하기 위해 {{site.data.keyword.knowledgestudioshort}}의 Service Details 페이지에서 스토리지 한계를 설정할 수 있습니다. Service Details 페이지를 보고 스토리지 한계를 설정하려면 {{site.data.keyword.knowledgestudioshort}}의 맨 위 탐색줄에서 **설정** 아이콘을 클릭하고, **View/modify service details** 링크를 클릭한 후 **Set storage limit** 링크를 클릭하십시오.
{: tip}

## IBM 지원 센터에 문의하기
{: #ts_contactingibmsupport}

{{site.data.keyword.IBM_notm}} 지원 센터는 제품 결함에 대한 지원을 제공하고, FAQ에 응답하며, 사용자가 제품 관련 문제점을 해결하는 데 도움을 줍니다. 

### 시작하기 전에

먼저, 발생한 문제점에 대한 솔루션이 기록되어 있는지 확인하십시오. [{{site.data.keyword.IBM_notm}} 지원 포털 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://www.ibm.com/support/home/entry/portal){: new_window}에서 {{site.data.keyword.knowledgestudioshort}}를 검색하십시오. 기술 노트, {{site.data.keyword.IBM_notm}} Redbook 및 문서의 결과를 보려면 검색 결과 페이지에서 **Support** 탭을 클릭하십시오. 블로그 및 포럼 질문과 같은 {{site.data.keyword.IBM_notm}} developerWorks 커뮤니티의 결과를 보려면 **For developers** 탭을 클릭하십시오. 

[{{site.data.keyword.IBM_notm}} 지원 포털 ![외부 링크 아이콘 ](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://www.ibm.com/support/home/entry/portal){: new_window}을 검색하여 응답 또는 솔루션을 찾으려 시도한 후에는 {{site.data.keyword.IBM_notm}} 지원 센터에 문의할 수 있습니다. 받을 수 있는 지원의 유형은 서비스 유형에 따라 다릅니다. 

- **무료 사용제 사용자**

    개발자 커뮤니티의 동료 구성원들에게 질문하여 답변을 얻고 도움을 받으십시오. 개발자 커뮤니티에 대한 링크는 목차의 **개발자 커뮤니티** 절을 참조하십시오. 

- **유료 사용제 사용자**

    유료 사용제 사용자 또한 질문을 게시하거나 다른 사용자의 질문으로부터 배울 수 있습니다. 포럼은 모든 사용자가 사용할 수 있으며, 솔루션은 여기서부터 찾아보는 것이 좋습니다. 링크는 목차의 **개발자 커뮤니티** 절을 참조하십시오. 

    [{{site.data.keyword.IBM_notm}} Cloud 서비스 포털 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://watson.service-now.com/wcp){: new_window}에서 문제점 티켓을 제출하십시오. 

    > **참고:** {{site.data.keyword.IBM_notm}}에 문제점을 제출할 수 있는 권한이 있어야 합니다. 

### 프로시저

문제점에 대해 {{site.data.keyword.IBM_notm}} 지원 센터에 문의하려면 다음 작업을 수행하십시오. 

1. 문제점을 명확히 하고, 배경 정보를 수집한 후, 문제의 심각도를 판별하십시오. 
1. 가능한 경우 진단 정보를 수집하십시오. 
1. 문제점을 {{site.data.keyword.IBM_notm}} 지원 센터에 제출하십시오. 문의에 대한 세부사항은 [SaaS(Software as a Service) 지원 안내서 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://www-01.ibm.com/software/support/acceleratedvalue/SaaS_Handbook_V18.pdf){: new_window}를 참조하십시오. 
