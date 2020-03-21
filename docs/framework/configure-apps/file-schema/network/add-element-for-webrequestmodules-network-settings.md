---
title: webRequestModules의 <add> 요소(네트워크 설정)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/webRequestModules/add
- http://schemas.microsoft.com/.NetConfiguration/v2.0#add
helpviewer_keywords:
- <webRequestModules>, add element
- webRequestModules, add element
- add element, webRequestModules
- <add> element, webRequestModules
ms.assetid: 47ec4adc-f39f-4bcd-8680-1ec21fd26890
ms.openlocfilehash: f4edce948033478aab59a2aff61abadc55a327ce
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155026"
---
# <a name="add-element-for-webrequestmodules-network-settings"></a>\<웹 요청 모듈에 대한> 요소 추가 (네트워크 설정)
응용 프로그램에 사용자 지정 웹 요청 모듈을 추가합니다.  

[**\<구성>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<웹 리퍼모듈>**](webrequestmodules-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<>추가**

## <a name="syntax"></a>구문  
  
```xml  
<add
  prefix="URI prefix"
  type="type_fullname, assembly_fullname"
/>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|**특성**|**설명**|  
|-------------------|---------------------|  
|`prefix`|이 웹 요청 모듈에서 처리하는 요청에 대한 URI 접두사입니다.|  
|`type`|이 웹 요청 모듈을 <xref:System.Type.FullName%2A> 구현하는 쉼표로 구분된 정규화된 형식 이름(속성으로 표시됨)과 어셈블리 <xref:System.Reflection.Assembly.FullName%2A> 이름(속성으로 표시됨)입니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|**요소**|**설명**|  
|-----------------|---------------------|  
|[webRequestModules](webrequestmodules-element-network-settings.md)|네트워크 호스트에서 정보를 요청하는 데 사용할 모듈을 지정합니다.|  
  
## <a name="remarks"></a>설명  
 특성은 `prefix` 지정된 웹 요청 모듈을 사용하는 URI 접두사를 정의합니다. 웹 요청 모듈은 일반적으로 HTTP 또는 FTP와 같은 특정 프로토콜을 처리하도록 등록되지만 서버의 특정 서버 또는 경로에 대한 요청을 처리하도록 등록할 수 있습니다.  
  
 웹 요청 모듈은 URI 일치 접두사가 메서드에 <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> 전달될 때 만들어집니다.  
  
 특성의 `prefix` 값은 유효한 URI의 선행 문자여야 합니다. 예를 들어 `http` 또는 `http://www.contoso.com`입니다.
  
 특성의 `type` 값은 유효한 형식 이름과 쉼표로 구분된 해당 어셈블리 이름이어야 합니다.
  
## <a name="configuration-files"></a>구성 파일  
 이 요소는 애플리케이션 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 예제는 HTTP에 대한 사용자 지정 웹 요청 모듈을 등록합니다. 버전 및 PublicKeyToken의 값을 지정된 모듈의 올바른 값으로 바꿔야 합니다.  
  
```xml  
<configuration>  
  <system.net>  
    <webRequestModules>  
      <add prefix="http"  
           type="System.Net.HttpRequestCreator, System, Version=2.0.3600.0,  
           Culture=neutral, PublicKeyToken=b77a5c561934e089"  
      />  
    </webRequestModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Net.WebRequest>
- [네트워크 설정 스키마](index.md)
