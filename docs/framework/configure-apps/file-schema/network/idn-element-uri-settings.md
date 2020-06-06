---
title: <idn> 요소(URI 설정)
ms.date: 03/30/2017
ms.assetid: 16c8e869-1791-4cf5-9244-3d3c738f60ec
ms.openlocfilehash: 533b2562f6e5c8d6c2bf452e56dff9a8bf8ab376
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "71698166"
---
# <a name="idn-element-uri-settings"></a>\<idn> 요소(URI 설정)

IDN (다국어 도메인 이름) 구문 분석이 도메인 이름에 적용 되는지 여부를 지정 합니다.
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<uri>**](uri-element-uri-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<idn>**  
  
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
|`enabled`|IDN (다국어 도메인 이름) 구문 분석이 도메인 이름에 적용 되는지 여부를 지정 합니다. 기본값은 none입니다.|  

### <a name="child-elements"></a>자식 요소

None
  
### <a name="parent-elements"></a>부모 요소

|**요소**|**설명**|  
|-----------------|---------------------|  
|[uri](uri-element-uri-settings.md)|.NET Framework Uri (uniform resource identifier)를 사용 하 여 표현 된 웹 주소를 처리 하는 방법을 지정 하는 설정을 포함 합니다.|  

## <a name="remarks"></a>설명

<xref:System.Uri>.NET Framework 3.5에서 기존 클래스가 확장 되었습니다. 3.0 SP1 및 2.0 s p 1은 IRI (국가별 리소스 식별자) 및 IDN (다국어 도메인 이름)을 지원 합니다. 현재 사용자가 IRI 및 IDN 지원을 특별히 사용 하도록 설정 하지 않으면 .NET Framework 2.0 동작의 변경 내용이 표시 되지 않습니다. 이 덕분에 .NET Framework 이전 버전과의 애플리케이션 호환성이 제공됩니다.

IRI에 대 한 지원을 사용 하도록 설정 하려면 다음 두 가지 변경이 필요 합니다.

1. Machine.config 파일의 .NET Framework 2.0 디렉터리 아래에 다음 줄을 추가 합니다.
  
    ```xml  
    <section name="uri" type="System.Configuration.UriSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
    ```  
  
2. IDN (다국어 도메인 이름) 구문 분석이 도메인 이름에 적용 되도록 할지 여부와 IRI 구문 분석 규칙을 적용할지 여부를 지정 합니다. 이 설정은 machine.config 또는 app.config 파일에서 지정할 수 있습니다.

 사용 되는 DNS 서버에 따라 IDN에 대해 다음과 같은 세 가지 값을 사용할 수 있습니다.

- idn 사용 = 모두  

     이 값은 모든 유니코드 도메인 이름을 해당하는 Punycode 항목(IDN 이름)으로 변환합니다.

- idn 사용 = AllExceptIntranet

     이 값은 해당 하는 Punycode (IDN 이름)를 사용 하도록 로컬 인트라넷에 없는 모든 유니코드 도메인 이름을 변환 합니다. 이 경우 로컬 인트라넷에서 국제 이름을 처리 하려면 인트라넷에 사용 되는 DNS 서버가 유니코드 이름 확인을 지원 해야 합니다.

- idn 사용 = 없음

     이 값은 Punycode를 사용하도록 어떠한 유니코드 도메인 이름도 변환하지 않습니다. 이 값은 .NET Framework 2.0 동작과 일치하는 기본값입니다.

 IDN을 사용하면 도메인 이름의 모든 유니코드 레이블이 해당 Punycode 문자로 변환됩니다. Punycode 이름에는 ASCII 문자만 사용되며 항상 xn-- 접두사로 시작합니다. 대부분의 DNS 서버는 ASCII 문자만 지원하므로(RFC 3940 참조) 이렇게 해야 인터넷에서 기존 DNS 서버를 지원할 수 있습니다.

### <a name="configuration-files"></a>구성 파일

이 요소는 애플리케이션 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.

## <a name="example"></a>예제

다음 예제에서는 <xref:System.Uri> 클래스에서 IRI 구문 분석 및 IDN 이름을 지원 하기 위해 사용 하는 구성을 보여 줍니다.

```xml
<configuration>
  <uri>
    <idn enabled="All" />
    <iriParsing enabled="true" />
  </uri>
</configuration>
```

## <a name="see-also"></a>참고 항목

- <xref:System.Configuration.IdnElement?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- [네트워크 설정 스키마](index.md)
