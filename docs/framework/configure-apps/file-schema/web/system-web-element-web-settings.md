---
description: '자세한 정보: <system.web> 요소 (웹 설정)'
title: <system.web> 요소(웹 설정)
ms.date: 03/30/2017
helpviewer_keywords:
- Web.config configuration file [ASP.NET]
- system.Web element
- <system.Web> element
- ASP.NET configuration system
- configuration files [ASP.NET]
ms.assetid: 24c4cf4f-ad32-42b2-b040-8e4549e2855e
ms.openlocfilehash: 2adcd3eba1eb6d67bcb4dc82243cd70d31d64fe9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99681905"
---
# <a name="systemweb-element-web-settings"></a>\<system.web> 요소(웹 설정)

ASP.NET 호스팅 계층이 프로세스 전체 동작을 관리 하는 방법에 대 한 정보를 포함 합니다.  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;**\<system.web>**  
  
## <a name="syntax"></a>구문  
  
```xml  
<system.web>  
</system.web>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  

다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  

없음  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<applicationPool>](applicationpool-element-web-settings.md)|aspnet.config 파일의 IIS 응용 프로그램 풀에 대 한 구성 설정을 지정 합니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<configuration>](../configuration-element.md)|공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용 하는 모든 구성 파일의 루트 요소를 지정 합니다.|  
  
## <a name="remarks"></a>설명  

`system.web`요소와 해당 자식 `applicationPool` 요소가 .NET Framework 3.5 s p 1의 .NET Framework에 추가 되었습니다. 통합 모드에서 IIS 7.0 이상 버전을 실행 하는 경우이 요소 조합을 사용 하면 ASP.NET에서 스레드를 관리 하는 방법 및 ASP.NET가 IIS 응용 프로그램 풀에서 호스팅되는 경우 요청을 큐에 대기 하는 방법을 구성할 수 있습니다. 클래식 또는 ISAPI 모드에서 IIS 7.0 이상 버전을 실행 하는 경우 이러한 설정은 무시 됩니다.  
  
## <a name="example"></a>예제  

다음 예제에서는 ASP.NET가 IIS 응용 프로그램 풀에서 호스팅될 때 aspnet.config 파일에서 ASP.NET 프로세스 전체 동작을 구성 하는 방법을 보여 줍니다. 이 예제에서는 IIS가 통합 모드로 실행 중이 고 응용 프로그램에서 .NET Framework 3.5 SP1 이상 버전을 사용 하 고 있다고 가정 합니다. 이 동작은 .NET Framework 3.5 s p 1 이전의 .NET Framework 버전에서 발생 하지 않습니다. 이 예제의 값은 기본값입니다.  
  
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
|비워 둘 수 있음||  
  
## <a name="see-also"></a>참고 항목

- [\<applicationPool> 요소 (웹 설정)](applicationpool-element-web-settings.md)
