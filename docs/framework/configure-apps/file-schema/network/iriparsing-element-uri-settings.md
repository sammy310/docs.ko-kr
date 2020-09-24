---
title: <iriParsing> 요소(URI 설정)
ms.date: 03/30/2017
ms.assetid: 953d0b53-445e-41f9-b302-77c4030852ce
ms.openlocfilehash: ec2610e47957d5560bc7f51e0641afc9ba60c814
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91158892"
---
# <a name="iriparsing-element-uri-settings"></a>\<iriParsing> 요소(URI 설정)

IRI(International Resource Identifier) 구문 분석이 <xref:System.Uri>에 적용되는지와 IRI 구문 분석 규칙을 적용해야 하는지 지정합니다.  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<uri>**](uri-element-uri-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<iriParsing>**  
  
## <a name="syntax"></a>구문  
  
```xml  
<iriParsing  
  enabled="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  

 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|**요소**|**설명**|  
|-----------------|---------------------|  
|`enabled`|IRI 구문 분석이 사용 되는지 여부를 지정 합니다. 기본값은 `false`입니다.|  
  
### <a name="child-elements"></a>자식 요소  

 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|**요소**|**설명**|  
|-----------------|---------------------|  
|[uri](uri-element-uri-settings.md)|.NET Framework Uri (uniform resource identifier)를 사용 하 여 표현 된 웹 주소를 처리 하는 방법을 지정 하는 설정을 포함 합니다.|  
  
## <a name="remarks"></a>설명  

 <xref:System.Uri>.NET Framework 3.5에서 기존 클래스가 확장 되었습니다. 3.0 SP1 및 2.0 s p 1은 IRI (국가별 리소스 식별자) 및 IDN (다국어 도메인 이름)에 대 한 지원을 제공 합니다. 현재 사용자가 IRI 및 IDN 지원을 특별히 사용 하도록 설정 하지 않으면 .NET Framework 2.0 동작의 변경 내용이 표시 되지 않습니다. 이 덕분에 .NET Framework 이전 버전과의 애플리케이션 호환성이 제공됩니다.  
  
 IRI에 대 한 지원을 사용 하도록 설정 하려면 다음 두 가지 변경이 필요 합니다.  
  
1. .NET Framework 2.0 디렉터리 아래의 machine.config 파일에 다음 줄을 추가 합니다.  
  
    ```xml  
    <section name="uri" type="System.Configuration.UriSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
    ```  
  
2. IRI 구문 분석 규칙을 적용할지 여부를 지정 합니다. 이 설정은 machine.config 또는 app.config 파일에서 지정할 수 있습니다.  
  
 IRI 구문 분석 (iriParsing 분석 사용 =)을 사용 하면 `true` RFC 3987의 최신 IRI 규칙에 따라 정규화 및 문자 검사를 수행 합니다. 기본값은 이며 `false` rfc 2396 및 rfc 3986 (IPv6 리터럴의 경우)에 따라 정규화 및 문자 검사를 수행 합니다.  
  
### <a name="configuration-files"></a>구성 파일  

 이 요소는 애플리케이션 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.  
  
## <a name="example"></a>예제  
  
### <a name="description"></a>설명  

 다음 예제에서는 <xref:System.Uri> 클래스에서 IRI 구문 분석 및 IDN 이름을 지원 하기 위해 사용 하는 구성을 보여 줍니다.  
  
### <a name="code"></a>코드  
  
```xml  
<configuration>  
  <uri>  
    <idn enabled="All" />  
    <iriParsing enabled="true" />  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a>참조

- <xref:System.Configuration.IriParsingElement?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- [네트워크 설정 스키마](index.md)
