---
title: <Uri> 요소(URI 설정)
ms.date: 03/30/2017
ms.assetid: c22bab8b-477c-4ae4-8498-65ad409e0847
ms.openlocfilehash: 1f3573babd2e363a78f0ad454f0ba36c87ba6390
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61705111"
---
# <a name="uri-element-uri-settings"></a>\<Uri > 요소 (Uri 설정)
.NET Framework uniform resource identifier (Uri)를 사용 하 여 표현 하는 웹 주소를 처리 하는 방법을 지정 하는 설정을 포함 합니다.  
  
## <a name="schema-hierarchy"></a>스키마 계층 구조  
 [\<configuration> 요소](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
  
 [\<uri>](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)  
  
## <a name="syntax"></a>구문  
  
```xml  
<uri>  
</uri>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
 없음  
  
### <a name="child-elements"></a>자식 요소  
  
|**요소**|**설명**|  
|-----------------|---------------------|  
|[idn](../../../../../docs/framework/configure-apps/file-schema/network/idn-element-uri-settings.md)|IDN(Internationalized Domain Name) 구문 분석이 도메인 이름에 적용되는지 지정합니다.|  
|[iriParsing](../../../../../docs/framework/configure-apps/file-schema/network/iriparsing-element-uri-settings.md)|식별자 IRI (International Resource) 구문 분석에 적용 됩니다 지정 <xref:System.Uri> IRI 구문 분석 규칙을 적용 해야 하는지 여부입니다.|  
|[schemeSettings](../../../../../docs/framework/configure-apps/file-schema/network/schemesettings-element-uri-settings.md)|특정 체계에 대해 <xref:System.Uri>가 구문 분석되는 방법을 지정합니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|**요소**|**설명**|  
|-----------------|---------------------|  
|[configuration](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|모든 네임 스페이스에 대 한 설정을 포함합니다.|  
  
## <a name="remarks"></a>설명  
 `uri` 요소 멤버에 대 한 설정을 포함 합니다 <xref:System.Uri> 클래스에 의해 사용 되는 클래스는 <xref:System.Net> 네임 스페이스. 이 설정은 IRI 및 IDN에 대 한 지원을 구성 합니다.  
  
## <a name="example"></a>예제  
  
### <a name="description"></a>설명  
 다음 예제에서 사용 하는 구성을 보여 줍니다는 <xref:System.Uri> IRI 구문 분석 및 IDN 이름이 지원 되는 클래스입니다. 이 예제에서는 모든 스키마 설정을 지웁니다 및 http 체계에 대 한 백분율로 인코딩된 경로 구분 기호를 이스케이프 하지 않아도 되도록 하는 것에 대 한 지원을 추가 합니다.  
  
### <a name="code"></a>코드  
  
```xml  
<configuration>  
  <uri>  
    <idn enabled="All" />  
    <iriParsing enabled="true" />  
    <schemeSettings>  
      <clear/>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a>참고자료

- [네트워크 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
