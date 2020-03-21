---
title: <alwaysFlowImpersonationPolicy> 요소
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/alwaysFlowImpersonationPolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#alwaysFlowImpersonationPolicy
helpviewer_keywords:
- alwaysFlowImpersonationPolicy element
- <alwaysFlowImpersonationPolicy> element
ms.assetid: ee622801-9e46-470b-85ab-88c4b1dd2ee1
ms.openlocfilehash: 7c8ac37932a528ff0f000cbaab49124dec51b88c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154485"
---
# <a name="alwaysflowimpersonationpolicy-element"></a>\<alwaysFlow사칭정책> 요소
가장을 수행하는 방법과 관계없이 Windows ID가 항상 비동기 지점 간을 흐르도록 지정합니다.  
  
[**\<구성>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<런타임>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<항상흐름사칭정책>**\  
  
## <a name="syntax"></a>구문  
  
```xml  
<alwaysFlowImpersonationPolicy
  enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|attribute|Description|  
|---------------|-----------------|  
|`enabled`|필수 특성입니다.<br /><br /> Windows ID가 비동기 지점을 가로질러 흐르는지 여부를 나타냅니다.|  
  
## <a name="enabled-attribute"></a>enabled 특성  
  
|값|Description|  
|-----------|-----------------|  
|`false`|와 같은 <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A>관리되는 메서드를 통해 가장이 수행되지 않는 한 Windows ID는 비동기 지점에서 흐르지 않습니다. 이것이 기본값입니다.|  
|`true`|Windows ID는 가장이 수행된 방식에 관계없이 항상 비동기 지점을 가로질러 흐릅니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|Description|  
|-------------|-----------------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`runtime`|어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.|  
  
## <a name="remarks"></a>설명  
 .NET Framework 버전 1.0 및 1.1에서 Windows ID는 비동기 지점에서 흐르지 않습니다. .NET Framework 버전 2.0에는 현재 <xref:System.Threading.ExecutionContext> 실행 중인 스레드에 대한 정보가 포함된 개체가 있으며 응용 프로그램 도메인 내의 비동기 지점을 통해 흐릅니다. <xref:System.Security.Principal.WindowsIdentity> 또한 비동기 지점을 가로질러 흐르는 정보의 일부로 흐르며, 플랫폼이 네이티브 메서드로 호출하는 것과 같은 다른 수단이 아닌 관리되는 메서드를 <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A> 사용하여 가장을 달성한 경우. 이 요소는 가장이 달성된 방식에 관계없이 Windows ID가 비동기 지점에서 흐르도록 지정하는 데 사용됩니다.  
  
 이 기본 동작은 다음 두 가지 방법으로 변경할 수 있습니다.  
  
1. 스레드별로 관리 되는 코드에서 입니다.  
  
     <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>을 <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType>사용하여 <xref:System.Threading.ExecutionContext> 및 <xref:System.Security.SecurityContext> 설정을 수정하여 스레드별로 흐름을 억제할 수 있습니다. <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType>  
  
2. 관리되지 않는 호스팅 인터페이스에 대한 호출에서 공통 언어 런타임(CLR)을 로드합니다.  
  
     CLR을 로드하는 데 관리되지 않는 호스팅 인터페이스(간단한 관리 실행 가능) 대신사용하는 경우 [CorBindToRuntimeEx 함수](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) 호출에서 특수 플래그를 지정할 수 있습니다. 전체 프로세스에 대한 호환성 모드를 사용하려면 `flags` [CorBindToRuntimeEx 함수에](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) 대한 매개 변수를 로 `STARTUP_ALWAYSFLOW_IMPERSONATION`설정합니다.  
  
## <a name="configuration-file"></a>구성 파일  
 .NET Framework 응용 프로그램에서이 요소는 응용 프로그램 구성 파일에서만 사용할 수 있습니다.  
  
 ASP.NET 응용 프로그램의 경우 \<가장 흐름은 Windows 폴더>\Microsoft.NET\Framework\vx.xxxx 디렉터리에서 발견된 aspnet.config 파일에서 구성할 수 있습니다.  
  
 ASP.NET 기본적으로 다음 구성 설정을 사용하여 aspnet.config 파일에서 가장 흐름을 사용하지 않도록 설정합니다.  
  
```xml
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
      <alwaysFlowImpersonationPolicy enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
 ASP.NET 대신 가장 흐름을 허용하려면 다음 구성 설정을 명시적으로 사용해야 합니다.  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="false"/>  
      <alwaysFlowImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="example"></a>예제  
 다음 예제에서는 관리되는 메서드 이외의 수단을 통해 가장이 달성되는 경우에도 Windows ID가 비동기 지점을 가로질러 흐르도록 지정하는 방법을 보여 주며, 이 중 에서다.  
  
```xml  
<configuration>  
  <runtime>  
    <alwaysFlowImpersonationPolicy enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>참고 항목

- [런타임 설정 스키마](index.md)
- [구성 파일 스키마](../index.md)
- [\<레거시 사칭정책> 요소](legacyimpersonationpolicy-element.md)
