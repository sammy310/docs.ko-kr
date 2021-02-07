---
description: '다음에 대 한 자세한 정보: <webRequestModules> 요소 (네트워크 설정)'
title: <webRequestModules> 요소(네트워크 설정)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/webRequestModules
- http://schemas.microsoft.com/.NetConfiguration/v2.0#webRequestModules
helpviewer_keywords:
- webRequestModules element
- <webRequestModules> element
ms.assetid: 1263de11-3e0a-4f94-97c9-710b2ae53817
ms.openlocfilehash: 851aec2bf38910239874cb5792239a48de6efb70
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99698429"
---
# <a name="webrequestmodules-element-network-settings"></a>\<webRequestModules> 요소(네트워크 설정)

네트워크 호스트의 정보를 요청 하는 데 사용할 모듈을 지정 합니다.  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;\<webRequestModules>  
  
## <a name="syntax"></a>구문  
  
```xml  
<webRequestModules>
</webRequestModules>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  

 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  

 없음  
  
### <a name="child-elements"></a>자식 요소  
  
|**요소**|**설명**|  
|-----------------|---------------------|  
|[add](add-element-for-webrequestmodules-network-settings.md)|응용 프로그램에 사용자 지정 웹 요청 모듈을 추가 합니다.|  
|[clear](clear-element-for-webrequestmodules-network-settings.md)|응용 프로그램에서 등록 된 모든 웹 요청 모듈을 제거 합니다.|  
|[remove](remove-element-for-webrequestmodules-network-settings.md)|응용 프로그램에서 사용자 지정 웹 요청 모듈을 제거 합니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|**요소**|**설명**|  
|-----------------|---------------------|  
|[system.net](system-net-element-network-settings.md)|.NET Framework의 네트워크 연결 방법을 지정하는 설정을 포함합니다.|  
  
## <a name="remarks"></a>설명  

 `webRequestModules` 요소는 <xref:System.Net.WebRequest> 클래스의 하위 클래스를 등록하여 네트워크 호스트로의 정보 요청을 처리합니다. 웹 요청 모듈은 인터페이스를 구현 해야 합니다 <xref:System.Net.IWebRequestCreate> .  
  
 .NET Framework에는, 및로 시작 하는 Uri에 대 한 웹 요청 모듈이 포함 되어 있습니다 `http://` `https://` `file://` . 구성 파일에서 사용자 지정 모듈을 등록 하 여 기본 모듈만 재정의할 수 있습니다.  
  
## <a name="configuration-files"></a>구성 파일  

 이 요소는 애플리케이션 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.  
  
## <a name="example"></a>예제  

 다음 예제에서는 기본 HTTP 모듈을 등록 합니다. Version 및 PublicKeyToken의 값을 지정 된 모듈의 올바른 값으로 바꾸어야 합니다.  
  
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
