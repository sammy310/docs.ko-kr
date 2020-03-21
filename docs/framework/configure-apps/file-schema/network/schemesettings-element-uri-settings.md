---
title: <schemeSettings> 요소(URI 설정)
ms.date: 03/30/2017
ms.assetid: 0ae45c6e-8c4c-4c0d-8b9f-a93824648890
ms.openlocfilehash: c745c90bb61b9ee393687d7f6db4fd11565c7dc7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154649"
---
# <a name="schemesettings-element-uri-settings"></a>\<schemeSettings> 요소 (URI 설정)
특정 체계에 대해 <xref:System.Uri>가 구문 분석되는 방법을 지정합니다.  
  
[**\<구성>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<우리>**](uri-element-uri-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<구성표설정>**  
  
## <a name="syntax"></a>구문  
  
```xml  
<schemeSettings>
</schemeSettings>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
 None  
  
### <a name="child-elements"></a>자식 요소  
  
|**요소**|**설명**|  
|-----------------|---------------------|  
|[추가](add-element-for-schemesettings-uri-settings.md)|구성표 이름에 대한 구성표 설정을 추가합니다.|  
|[명확한](clear-element-for-schemesettings-uri-settings.md)|모든 기존 구성표 설정을 지웁니다.|  
|[제거](remove-element-for-schemesettings-uri-settings.md)|구성표 이름에 대한 구성표 설정을 제거합니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|**요소**|**설명**|  
|-----------------|---------------------|  
|[Uri](uri-element-uri-settings.md)|.NET Framework에서 균일한 리소스 식별자(URIs)를 사용하여 표현된 웹 주소를 처리하는 방법을 지정하는 설정이 포함되어 있습니다.|  
  
## <a name="remarks"></a>설명  
 기본적으로 <xref:System.Uri?displayProperty=nameWithType> 클래스는 경로 압축을 실행하기 전에 인코딩된 경로 구분 기호%를 이스케이프해제합니다. 이 메커니즘은 다음과 같은 공격에 대한 보안 메커니즘으로 구현되었습니다.  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 이 URI가 인코딩된 문자를 올바르게 처리하지 않는 모듈로 전달되면 서버에서 다음 명령이 실행될 수 있습니다.  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 이러한 이유로 <xref:System.Uri?displayProperty=nameWithType> 클래스 첫 번째 un-escapes 경로 구분 기호 를 적용 하 고 경로 압축을 적용 합니다. 위의 악의적인 URL을 클래스 <xref:System.Uri?displayProperty=nameWithType> 생성자로 전달하면 다음 URI가 발생합니다.  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 이 기본 동작은 특정 구성표에 대한 schemeSettings 구성 옵션을 사용하여 이스케이프 해제 백% 인코딩된 경로 구분자를 사용하지 않도록 수정할 수 있습니다.  
  
## <a name="configuration-files"></a>구성 파일  
 이 요소는 애플리케이션 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 http 체계에 <xref:System.Uri> 대 한 백분율 인코딩된 경로 구분 자를 이스케이프 하지 를 지원 하기 위해 클래스에서 사용 하는 구성을 보여 주다.  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="element-information"></a>요소 정보  
  
|||
|-|-|  
|네임스페이스|시스템|  
|Schema Name||  
|유효성 검사 파일||  
|비어 있을 수 있습니다.||  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>
- <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>
- <xref:System.GenericUriParserOptions?displayProperty=nameWithType>
- <xref:System.Uri?displayProperty=nameWithType>
- [네트워크 설정 스키마](index.md)
