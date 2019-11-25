---
title: schemeSettings의 <add> 요소(URI 설정)
ms.date: 03/30/2017
ms.assetid: 594a7b3b-af23-4cfa-b616-0b2dddb1a705
ms.openlocfilehash: ed40098e8d4c2d1298771e67a618b8d04f59c912
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/14/2019
ms.locfileid: "74087713"
---
# <a name="add-element-for-schemesettings-uri-settings"></a>schemeSettings에 대 한 > 요소 추가 \<(Uri 설정)
구성표 이름에 대 한 구성표 설정을 추가 합니다.  

[ **\<configuration>** ](../configuration-element.md)\
[ **\<uri >** ](uri-element-uri-settings.md) &nbsp;&nbsp;\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<schemeSettings >** ](schemesettings-element-uri-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**추가** >

## <a name="syntax"></a>구문  
  
```xml  
<add
  name="http|https"
  genericUriParserOptions="DontUnescapePathDotsAndSlashes"
/>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|name|이 설정이 적용 되는 체계 이름입니다. 유일 하 게 지원 되는 값은 name = "http" 및 name = "https"입니다.|  
  
## <a name="attribute-name-attribute"></a>{Attribute name} 특성도  
  
|값|설명|  
|-----------|-----------------|  
|genericUriParserOptions|이 스키마에 대 한 파서 옵션입니다. 유일 하 게 지원 되는 값은 genericUriParserOptions = "DontUnescapePathDotsAndSlashes"입니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<schemeSettings> 요소 (URI 설정)](schemesettings-element-uri-settings.md)|특정 체계에 대해 <xref:System.Uri>가 구문 분석되는 방법을 지정합니다.|  
  
## <a name="remarks"></a>주의  
 기본적으로 <xref:System.Uri?displayProperty=nameWithType> 클래스는 경로 압축을 실행 하기 전에 인코딩된 경로 구분 기호 비율을 이스케이프 해제 합니다. 이는 다음과 같은 공격에 대 한 보안 메커니즘으로 구현 되었습니다.  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 % 인코딩된 문자를 올바르게 처리 하지 않는 모듈에이 URI가 전달 되 면 서버에서 다음 명령을 실행 하 게 될 수 있습니다.  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 이러한 이유로, <xref:System.Uri?displayProperty=nameWithType> 클래스는 먼저 경로 구분 기호를 이스케이프 해제 한 후 경로 압축을 적용 합니다. 위의 악성 URL을 <xref:System.Uri?displayProperty=nameWithType> 클래스 생성자에 전달 하면 다음 URI가 생성 됩니다.  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 이 기본 동작은 특정 스키마에 대 한 schemeSettings 구성 옵션을 사용 하 여 인코딩된 경로 구분 기호를 이스케이프 해제 하지 않도록 수정할 수 있습니다.  
  
## <a name="configuration-files"></a>구성 파일  
 이 요소는 애플리케이션 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 http 체계의 백분율 인코딩된 경로 구분 기호를 이스케이프 하지 않도록 지원 하기 위해 <xref:System.Uri> 클래스에서 사용 하는 구성을 보여 줍니다.  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a>참조

- <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>
- <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>
- <xref:System.GenericUriParserOptions?displayProperty=nameWithType>
- <xref:System.Uri?displayProperty=nameWithType>
- [네트워크 설정 스키마](index.md)
