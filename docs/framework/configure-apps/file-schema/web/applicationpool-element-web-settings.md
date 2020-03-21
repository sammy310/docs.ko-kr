---
title: <applicationPool> 요소(웹 설정)
ms.date: 03/30/2017
helpviewer_keywords:
- applicationPool element
- <applicationPool> element
ms.assetid: 46d1baaa-e343-4639-b70d-2a43a9f62b2a
ms.openlocfilehash: 6feaa801610fa0ffbbf47575f25aff29fa46a66c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152856"
---
# <a name="applicationpool-element-web-settings"></a>\<applicationPool> 요소(웹 설정)
ASP.NET 응용 프로그램이 IIS 7.0 또는 이후 버전의 통합 모드에서 실행중인 경우 ASP.NET 프로세스 전체 동작을 관리하는 데 사용되는 구성 설정을 지정합니다.  
  
> [!IMPORTANT]
> 이 요소와 지원되는 기능은 ASP.NET 응용 프로그램이 IIS 7.0 이상 버전에서 호스팅되는 경우에만 작동합니다.  
  
[**\<구성>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<system.web>**](system-web-element-web-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<애플리케이션풀>**  
  
## <a name="syntax"></a>구문  
  
```xml  
<applicationPool
    maxConcurrentRequestsPerCPU="5000"
    maxConcurrentThreadsPerCPU="0"
    requestQueueLimit="5000" />  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  

다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|attribute|Description|  
|---------------|-----------------|  
|`maxConcurrentRequestsPerCPU`|CPU당 허용할 ASP.NET 동시 요청 수를 지정합니다.|  
|`maxConcurrentThreadsPerCPU`|각 CPU에 대한 응용 프로그램 풀에 대해 실행할 수 있는 동시 스레드 수를 지정합니다. 이렇게 하면 CPU당 요청을 제공하는 데 사용할 수 있는 관리되는 스레드 수를 제한할 수 있으므로 ASP.NET 동시성을 제어하는 다른 방법이 제공됩니다. 기본적으로 이 설정은 0이므로 clR 스레드 풀은 만들 수 있는 스레드 수도 제한되지만 ASP.NET CPU당 만들 수 있는 스레드 수를 제한하지 않습니다.|  
|`requestQueueLimit`|단일 프로세스에서 ASP.NET 동안 큐에 대기할 수 있는 최대 요청 수를 지정합니다. 둘 이상의 ASP.NET 응용 프로그램이 단일 응용 프로그램 풀에서 실행되는 경우 응용 프로그램 풀의 모든 응용 프로그램에 대해 발생하는 누적 요청 집합이 이 설정의 적용을 받습니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|Description|  
|-------------|-----------------|  
|[\<system.web>](system-web-element-web-settings.md)|ASP.NET 호스트 응용 프로그램과 상호 작용하는 방법에 대한 정보를 포함합니다.|  
  
## <a name="remarks"></a>설명  

통합 모드에서 IIS 7.0 또는 이후 버전을 실행하는 경우 이 요소 조합을 사용하면 응용 프로그램이 IIS 응용 프로그램 풀에서 호스팅될 때 ASP.NET 스레드 및 큐 요청을 관리하는 방법을 구성할 수 있습니다. IIS 6을 실행하거나 클래식 모드 또는 ISAPI 모드에서 IIS 7.0을 실행하면 이러한 설정이 무시됩니다.  
  
이 `applicationPool` 설정은 .NET Framework의 특정 버전에서 실행되는 모든 응용 프로그램 풀에 적용됩니다. 설정은 aspnet.config 파일에 포함되어 있습니다. .NET Framework의 버전 2.0 및 4.0에 대해 이 파일버전이 있습니다. (.NET 프레임워크의 버전 3.0 및 3.5는 버전 2.0과 aspnet.config 파일을 공유합니다.)  
  
> [!IMPORTANT]
> Windows 7에서 IIS 7.0을 실행하는 경우 모든 응용 프로그램 풀에 대해 별도의 aspnet.config 파일을 구성할 수 있습니다. 이렇게 하면 각 응용 프로그램 풀에 대한 스레드의 성능을 조정할 수 있습니다.  
  
설정의 `maxConcurrentRequestsPerCPU` 경우 .NET Framework 4의 기본 설정인 "5000"은 실제로 CPU당 5,000개 이상의 요청이 있는 경우가 아니면 ASP.NET 의해 제어되는 요청 제한을 효과적으로 해제합니다. 기본 설정은 CPU당 동시성을 자동으로 관리하기 위해 CLR 스레드 풀에 따라 달라집니다. 비동기 요청 처리를 광범위하게 사용하거나 네트워크 I/O에서 장기 실행 요청이 많이 차단된 응용 프로그램은 .NET Framework 4에서 증가된 기본 제한의 이점을 누릴 수 있습니다. 0으로 설정하면 `maxConcurrentRequestsPerCPU` ASP.NET 요청을 처리하기 위해 관리되는 스레드의 사용이 해제됩니다. 응용 프로그램이 IIS 응용 프로그램 풀에서 실행되면 요청이 IIS I/O 스레드에 유지되므로 IIS 스레드 설정에 의해 동시화가 제한됩니다.  
  
`requestQueueLimit`설정은 ASP.NET 응용 프로그램의 web.config 파일에 설정된 [processModel](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7w2sway1(v=vs.100)) 요소의 `requestQueueLimit`특성과 동일한 방식으로 작동합니다. 그러나 aspnet.config 파일의 `requestQueueLimit` 설정은 `requestQueueLimit` Web.config 파일의 설정을 재정의합니다. 즉, 두 특성이 모두 설정된 경우(기본적으로 true) `requestQueueLimit` aspnet.config 파일의 설정이 우선합니다.  
  
## <a name="example"></a>예제  

다음 예제에서는 다음과 같은 상황에서 aspnet.config 파일에서 프로세스 전체의 동작을 구성하는 ASP.NET 방법을 보여 주며 다음과 같은 경우를 보여 주며 있습니다.  
  
- 응용 프로그램은 IIS 7.0 응용 프로그램 풀에서 호스팅됩니다.  
  
- IIS 7.0이 통합 모드에서 실행되고 있습니다.  
  
- 응용 프로그램이 .NET Framework 3.5 SP1 또는 이후 버전을 사용하고 있습니다.  
  
예제의 값은 기본값입니다.  
  
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

- [\<system.web> 요소(웹 설정)](system-web-element-web-settings.md)
