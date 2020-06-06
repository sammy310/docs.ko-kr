---
title: <legacyImpersonationPolicy> 요소
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#legacyImpersonationPolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/legacyImpersonationPolicy
helpviewer_keywords:
- <legacyImpersonationPolicy> element
- legacyImpersonationPolicy element
ms.assetid: 6e00af10-42f3-4235-8415-1bb2db78394e
ms.openlocfilehash: 5e43ead278ecd4049014f4000a2f056b2190f7e5
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154106"
---
# <a name="legacyimpersonationpolicy-element"></a>\<legacyImpersonationPolicy> 요소
현재 스레드의 실행 컨텍스트 흐름 설정과 관계없이 Windows ID가 비동기 지점 간을 흐르지 않도록 지정합니다.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<legacyImpersonationPolicy>**  
  
## <a name="syntax"></a>구문  
  
```xml  
<legacyImpersonationPolicy
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|attribute|Description|  
|---------------|-----------------|  
|`enabled`|필수 특성입니다.<br /><br /> <xref:System.Security.Principal.WindowsIdentity>현재 스레드의 흐름 설정에 관계 없이가 비동기 요소를 통해 이동 하지 않도록 지정 합니다 <xref:System.Threading.ExecutionContext> .|  
  
## <a name="enabled-attribute"></a>enabled 특성  
  
|값|Description|  
|-----------|-----------------|  
|`false`|<xref:System.Security.Principal.WindowsIdentity><xref:System.Threading.ExecutionContext>현재 스레드에 대 한 흐름 설정에 따라 비동기 요소를 통해 흐릅니다. 기본값입니다.|  
|`true`|<xref:System.Security.Principal.WindowsIdentity>는 현재 스레드의 흐름 설정에 관계 없이 비동기 요소를 통해 이동 하지 않습니다 <xref:System.Threading.ExecutionContext> .|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|Description|  
|-------------|-----------------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`runtime`|어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.|  
  
## <a name="remarks"></a>설명  
 .NET Framework 버전 1.0 및 1.1에서은 <xref:System.Security.Principal.WindowsIdentity> 사용자가 정의한 비동기 시점 간에 이동 하지 않습니다. .NET Framework 버전 2.0부터 <xref:System.Threading.ExecutionContext> 현재 실행 중인 스레드에 대 한 정보를 포함 하는 개체가 있으며 응용 프로그램 도메인 내의 비동기 요소를 통해 흐릅니다. 는 <xref:System.Security.Principal.WindowsIdentity> 이 실행 컨텍스트에 포함 되어 있으므로 비동기 지점만 전달 됩니다. 즉, 가장 컨텍스트가 있는 경우에도 흐릅니다.  
  
 .NET Framework 2.0부터 요소를 사용 하 여 `<legacyImpersonationPolicy>` <xref:System.Security.Principal.WindowsIdentity> 가 비동기 요소 간에 이동 하지 않도록 지정할 수 있습니다.  
  
> [!NOTE]
> CLR (공용 언어 런타임)은 관리 코드를 사용 하 여 수행 되는 가장 작업을 인식 합니다. 예를 들어 비관리 코드에 대 한 플랫폼 호출 또는 Win32 함수에 대 한 직접 호출을 통해 관리 코드 외부에서 수행 되는 가장이 아닙니다. <xref:System.Security.Principal.WindowsIdentity> `alwaysFlowImpersonationPolicy` 요소가 true ()로 설정 되지 않은 경우 관리 되는 개체만 비동기 요소를 통해 흐를 수 있습니다 `<alwaysFlowImpersonationPolicy enabled="true"/>` . 요소를 `alwaysFlowImpersonationPolicy` true로 설정 하면 가장 수행 된 방법에 관계 없이 Windows id가 항상 비동기 요소를 통해 이동 합니다. 비동기 시점에서 관리 되지 않는 가장을 이동 하는 방법에 대 한 자세한 내용은 [ \<alwaysFlowImpersonationPolicy> 요소](alwaysflowimpersonationpolicy-element.md)를 참조 하세요.  
  
 다른 두 가지 방법으로이 기본 동작을 변경할 수 있습니다.  
  
1. 스레드 단위로 관리 코드에서  
  
     <xref:System.Threading.ExecutionContext> <xref:System.Security.SecurityContext> <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType> , 또는 메서드를 사용 하 여 및 설정을 수정 하 여 스레드 단위로 흐름을 억제할 수 있습니다 <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType> <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> .  
  
2. 관리 되지 않는 호스팅 인터페이스를 호출 하 여 CLR (공용 언어 런타임)을 로드 합니다.  
  
     단순한 관리 되는 실행 파일 대신 관리 되지 않는 호스팅 인터페이스를 사용 하 여 CLR을 로드 하는 경우 [CorBindToRuntimeEx 함수](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) 함수 호출에서 특수 플래그를 지정할 수 있습니다. 전체 프로세스에 대해 호환 모드를 사용 하도록 설정 하려면 `flags` [CorBindToRuntimeEx 함수](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) 에 대 한 매개 변수를 STARTUP_LEGACY_IMPERSONATION 설정 합니다.  
  
 자세한 내용은 [ \<alwaysFlowImpersonationPolicy> 요소](alwaysflowimpersonationpolicy-element.md)를 참조 하세요.  
  
## <a name="configuration-file"></a>구성 파일  
 .NET Framework 응용 프로그램에서이 요소는 응용 프로그램 구성 파일에만 사용할 수 있습니다.  
  
 ASP.NET 응용 프로그램의 경우 \Microsoft.NET\Framework\vx.x.xxxx 디렉터리에 있는 aspnet .config 파일에서 가장 흐름을 구성할 수 있습니다 \<Windows Folder> .  
  
 ASP.NET는 기본적으로 다음 구성 설정을 사용 하 여 aspnet 파일에서 가장 흐름을 사용 하지 않도록 설정 합니다.  
  
``` xml
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
      <alwaysFlowImpersonationPolicy enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
 ASP.NET에서 대신 가장의 흐름을 허용 하려면 다음 구성 설정을 명시적으로 사용 해야 합니다.  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="false"/>  
      <alwaysFlowImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="example"></a>예제  
 다음 예제에서는 비동기 시점에서 Windows id를 전달 하지 않는 레거시 동작을 지정 하는 방법을 보여 줍니다.  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>참고 항목

- [런타임 설정 스키마](index.md)
- [구성 파일 스키마](../index.md)
- [\<alwaysFlowImpersonationPolicy>요소인](alwaysflowimpersonationpolicy-element.md)
