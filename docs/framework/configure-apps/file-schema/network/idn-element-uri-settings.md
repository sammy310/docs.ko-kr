---
title: <idn> 요소(URI 설정)
ms.date: 03/30/2017
ms.assetid: 16c8e869-1791-4cf5-9244-3d3c738f60ec
ms.openlocfilehash: 2d2729f9120d6b6fe673904ad2bf6d005ddf5469
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61705118"
---
# <a name="idn-element-uri-settings"></a>\<idn > 요소 (Uri 설정)
다국어 도메인 이름 (IDN) 구문 분석 된 도메인 이름에 적용 됩니다 지정 합니다.  
  
## <a name="schema-hierarchy"></a>스키마 계층 구조  
 [\<configuration> 요소](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
  
 [\<Uri > 요소 (Uri 설정)](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)  
  
 [\<idn>](../../../../../docs/framework/configure-apps/file-schema/network/idn-element-uri-settings.md)  
  
## <a name="syntax"></a>구문  
  
```xml  
<idn  
  enabled="All|AllExceptIntranet|None"  
/>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|**요소**|**설명**|  
|-----------------|---------------------|  
|`enabled`|도메인 이름에 적용 되는 다국어 도메인 이름 (IDN) 구문 분석 하는 경우 기본값은 none을 지정 합니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|**요소**|**설명**|  
|-----------------|---------------------|  
|[uri](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)|.NET Framework uniform resource identifier (Uri)를 사용 하 여 표현 하는 웹 주소를 처리 하는 방법을 지정 하는 설정을 포함 합니다.|  
  
## <a name="remarks"></a>설명  
 기존 <xref:System.Uri> 클래스는.NET Framework 3.5에서 확장 되었습니다. 3.0 SP1 및 2.0 SP1 식별자 IRI (International Resource) 및 이름을 IDN (Internationalized Domain)를 지원 합니다. IRI 및 IDN 구체적으로 설정 하지 않으면 현재 사용자가.NET Framework 2.0 동작에서 표시 되지 것입니다 지원 합니다. 이 덕분에 .NET Framework 이전 버전과의 애플리케이션 호환성이 제공됩니다.  
  
 Iri 지원을 사용 하는 다음 두 변경이 필요 합니다.  
  
1. .NET Framework 2.0 디렉터리 아래에 있는 machine.config 파일에 다음 줄을 추가 합니다.  
  
    ```xml  
    <section name="uri" type="System.Configuration.UriSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
    ```  
  
2. 다국어 도메인 이름 (IDN) 구문 분석 된 도메인 이름에 적용할 것인지와 IRI 구문 분석 규칙을 적용 해야 하는지 여부를 지정 합니다. 이 설정은 machine.config 또는 app.config 파일에서 지정할 수 있습니다.  
  
 세 가지 idn 관련 값을 사용 하는 DNS 서버에 따라 가지가 있습니다.  
  
- idn 사용 = All  
  
     이 값은 모든 유니코드 도메인 이름을 해당하는 Punycode 항목(IDN 이름)으로 변환합니다.  
  
- 사용 하도록 설정 하는 idn AllExceptIntranet =  
  
     이 값은 Punycode 항목 (IDN 이름)을 사용 하려면 로컬 인트라넷에 없는 모든 유니코드 도메인 이름을 변환 합니다. 이 경우를 처리 하기 위해 로컬 인트라넷에 있는 국가별 이름을 인트라넷에 사용 되는 DNS 서버가 유니코드 이름 확인을 지원 해야 합니다.  
  
- idn 사용 = 없음  
  
     이 값은 Punycode를 사용하도록 어떠한 유니코드 도메인 이름도 변환하지 않습니다. .NET Framework 2.0 동작을 사용 하 여 일치 하는 기본 값입니다.  
  
 IDN을 사용하면 도메인 이름의 모든 유니코드 레이블이 해당 Punycode 문자로 변환됩니다. Punycode 이름에는 ASCII 문자만 사용되며 항상 xn-- 접두사로 시작합니다. 대부분의 DNS 서버는 ASCII 문자만 지원하므로(RFC 3940 참조) 이렇게 해야 인터넷에서 기존 DNS 서버를 지원할 수 있습니다.  
  
### <a name="configuration-files"></a>구성 파일  
 이 요소는 응용 프로그램 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.  
  
## <a name="example"></a>예제  
  
### <a name="description"></a>설명  
 다음 예제에서 사용 하는 구성을 보여 줍니다는 <xref:System.Uri> IRI 구문 분석 및 IDN 이름이 지원 되는 클래스입니다.  
  
### <a name="code"></a>코드  
  
```xml  
<configuration>  
  <uri>  
    <idn enabled="All" />  
    <iriParsing enabled="true" />  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a>참고자료

- <xref:System.Configuration.IdnElement?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- [네트워크 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
