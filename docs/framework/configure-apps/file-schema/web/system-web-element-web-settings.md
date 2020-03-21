---
title: <system.web> 요소(웹 설정)
ms.date: 03/30/2017
helpviewer_keywords:
- Web.config configuration file [ASP.NET]
- system.Web element
- <system.Web> element
- ASP.NET configuration system
- configuration files [ASP.NET]
ms.assetid: 24c4cf4f-ad32-42b2-b040-8e4549e2855e
ms.openlocfilehash: b37b05bdf90630251cbfcf86751243a3a8b77663
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152843"
---
# <a name="systemweb-element-web-settings"></a>\<system.web> 요소(웹 설정)
ASP.NET 호스팅 계층이 프로세스 전체 동작을 관리하는 방법에 대한 정보를 포함합니다.  
  
[**\<구성>**](../configuration-element.md)  
&nbsp;&nbsp;**\<system.web>**  
  
## <a name="syntax"></a>구문  
  
```xml  
<system.web>  
</system.web>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  

다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  

없음  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|Description|  
|-------------|-----------------|  
|[\<애플리케이션풀>](applicationpool-element-web-settings.md)|aspnet.config 파일에서 IIS 응용 프로그램 풀에 대한 구성 설정을 지정합니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|Description|  
|-------------|-----------------|  
|[\<구성>](../configuration-element.md)|공통 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소를 지정합니다.|  
  
## <a name="remarks"></a>설명  

`system.web` .NET Framework `applicationPool` 3.5 SP1을 사용하여 요소와 자식 요소가 .NET 프레임워크에 추가되었습니다. 통합 모드에서 IIS 7.0 이상 버전을 실행하는 경우 이 요소 조합을 사용하면 ASP.NET 스레드를 관리하는 방법과 iIS 응용 프로그램 풀에서 호스팅될 때 요청을 큐에 대기하는 방법을 구성할 수 ASP.NET. 클래식 또는 ISAPI 모드에서 IIS 7.0 이상 버전을 실행하면 이러한 설정은 무시됩니다.  
  
## <a name="example"></a>예제  

다음 예제에서는 iis 응용 프로그램 풀에서 ASP.NET 호스트될 때 aspnet.config 파일에서 프로세스 ASP.NET 동작을 구성하는 방법을 보여 주며, 이 예제에서는 이 예제에서는 IIS가 통합 모드에서 실행중이며 응용 프로그램이 .NET Framework 3.5 SP1 또는 이후 버전을 사용하고 있다고 가정합니다. 이 동작은 .NET Framework 3.5 SP1 보다 이전의 .NET Framework 버전에서는 발생하지 않습니다. 예제의 값은 기본값입니다.  
  
```xml  
<configuration>  
  <system.web>  
    <applicationPool
        maxConcurrentRequestsPerCPU="5000"
        maxConcurrentThreadsPerCPU="0"
        requestQueueLimit="5000" />  
  </system.web>  
</configuration>  
```  
  
## <a name="element-information"></a>요소 정보  
  
|||  
|-|-|  
|네임스페이스||  
|Schema Name||  
|유효성 검사 파일||  
|비어 있을 수 있습니다.||  
  
## <a name="see-also"></a>참고 항목

- [\<응용 프로그램풀> 요소(웹 설정)](applicationpool-element-web-settings.md)
