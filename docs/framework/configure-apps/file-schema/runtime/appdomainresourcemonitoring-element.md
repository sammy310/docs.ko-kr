---
title: <appDomainResourceMonitoring> 요소
ms.date: 03/30/2017
helpviewer_keywords:
- appDomainResourceMonitoring element
- <appDomainResourceMonitoring> element
ms.assetid: 02119ab6-1e91-448e-97ad-e7b2e5c4bbbd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ad0ae023215eeb1f42f9351369ee77d41d537b88
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2019
ms.locfileid: "66487733"
---
# <a name="appdomainresourcemonitoring-element"></a>\<appDomainResourceMonitoring > 요소
프로세스의 수명 동안 프로세스의 모든 애플리케이션 도메인에서 통계를 수집하도록 런타임에 명령합니다.  
  
 \<configuration>  
\<runtime>  
\<appDomainResourceMonitoring>  
  
## <a name="syntax"></a>구문  
  
```xml  
<appDomainResourceMonitoring    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|`enabled`|필수 특성입니다.<br /><br /> 런타임에 응용 프로그램 도메인 리소스 모니터링에 대 한 통계 수집 여부를 지정 합니다.|  
  
## <a name="enabled-attribute"></a>enabled 특성  
  
|값|설명|  
|-----------|-----------------|  
|`true`|응용 프로그램 도메인 리소스 모니터링에 대 한 통계가 수집 됩니다.|  
|`false`|응용 프로그램 도메인 리소스 모니터링에 대 한 통계 수집 되지 않습니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`runtime`|어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.|  
  
## <a name="remarks"></a>설명  
 응용 프로그램 도메인 리소스 모니터링을 호스팅하는 관리 되는 응용 프로그램 도메인 클래스를 통해 사용할 수 [ICLRAppDomainResourceMonitor](../../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md) 인터페이스 및 Windows (ETW) 용 이벤트 추적 합니다. 모니터링을 사용 하면 프로세스의 수명에 대 한 프로세스의 모든 응용 프로그램 도메인에 대 한 통계가 수집 됩니다.  
  
 관리 코드에서 모니터링을 사용 하려면 사용 된 <xref:System.AppDomain.MonitoringIsEnabled%2A> 속성입니다.  
  
 이 구성 요소가 이상.NET Framework 4에만 사용할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 응용 프로그램 도메인 리소스 모니터링을 사용 하도록 설정 하는 방법을 보여 줍니다.  
  
```xml  
<configuration>  
   <runtime>  
      <appDomainResourceMonitoring enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>참고자료

- <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType>
- [런타임 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [구성 파일 스키마](../../../../../docs/framework/configure-apps/file-schema/index.md)
