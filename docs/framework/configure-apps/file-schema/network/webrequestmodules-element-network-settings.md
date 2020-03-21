---
title: <webRequestModules> 요소(네트워크 설정)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/webRequestModules
- http://schemas.microsoft.com/.NetConfiguration/v2.0#webRequestModules
helpviewer_keywords:
- webRequestModules element
- <webRequestModules> element
ms.assetid: 1263de11-3e0a-4f94-97c9-710b2ae53817
ms.openlocfilehash: 7f2805283f89e6165d336b3e593d34054e02115d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154545"
---
# <a name="webrequestmodules-element-network-settings"></a>\<webRequestModules> 요소 (네트워크 설정)
네트워크 호스트에서 정보를 요청하는 데 사용할 모듈을 지정합니다.  
  
[**\<구성>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;\<웹리퀘스트모듈>  
  
## <a name="syntax"></a>구문  
  
```xml  
<webRequestModules>
</webRequestModules>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
 없음  
  
### <a name="child-elements"></a>자식 요소  
  
|**요소**|**설명**|  
|-----------------|---------------------|  
|[추가](add-element-for-webrequestmodules-network-settings.md)|응용 프로그램에 사용자 지정 웹 요청 모듈을 추가합니다.|  
|[명확한](clear-element-for-webrequestmodules-network-settings.md)|등록된 모든 웹 요청 모듈을 응용 프로그램에서 제거합니다.|  
|[제거](remove-element-for-webrequestmodules-network-settings.md)|응용 프로그램에서 사용자 지정 웹 요청 모듈을 제거합니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|**요소**|**설명**|  
|-----------------|---------------------|  
|[system.net](system-net-element-network-settings.md)|.NET Framework의 네트워크 연결 방법을 지정하는 설정을 포함합니다.|  
  
## <a name="remarks"></a>설명  
 `webRequestModules` 요소는 <xref:System.Net.WebRequest> 클래스의 하위 클래스를 등록하여 네트워크 호스트로의 정보 요청을 처리합니다. 웹 요청 모듈은 <xref:System.Net.IWebRequestCreate> 인터페이스를 구현해야 합니다.  
  
 .NET 프레임워크에는 `http://`에서 `https://`로 시작하는 URI에 대한 웹 `file://`요청 모듈이 포함됩니다. 구성 파일에 사용자 지정 모듈을 등록해야만 기본 모듈을 재정의할 수 있습니다.  
  
## <a name="configuration-files"></a>구성 파일  
 이 요소는 애플리케이션 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 예제는 기본 HTTP 모듈을 등록합니다. 버전 및 PublicKeyToken의 값을 지정된 모듈의 올바른 값으로 바꿔야 합니다.  
  
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
- <xref:System.Net.IWebRequestCreate>
- [네트워크 설정 스키마](index.md)
