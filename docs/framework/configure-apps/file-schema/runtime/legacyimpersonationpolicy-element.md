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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c39ee551dde19d87a75403f3db7433d1ef829f3b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704637"
---
# <a name="legacyimpersonationpolicy-element"></a>\<legacyImpersonationPolicy > 요소
현재 스레드의 실행 컨텍스트 흐름 설정과 관계없이 Windows ID가 비동기 지점 간을 흐르지 않도록 지정합니다.  
  
 \<configuration>  
\<runtime>  
\<legacyImpersonationPolicy>  
  
## <a name="syntax"></a>구문  
  
```xml  
<legacyImpersonationPolicy    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|`enabled`|필수 특성입니다.<br /><br /> 지정 합니다 <xref:System.Security.Principal.WindowsIdentity> 에 관계 없이 비동기 지점 간을 흐르지 않는 <xref:System.Threading.ExecutionContext> 흐름 현재 스레드에 설정 합니다.|  
  
## <a name="enabled-attribute"></a>enabled 특성  
  
|값|설명|  
|-----------|-----------------|  
|`false`|<xref:System.Security.Principal.WindowsIdentity> 흐름에 따라 비동기 지점 간을 <xref:System.Threading.ExecutionContext> 흐름 현재 스레드에 대 한 설정입니다. 이 값이 기본값입니다.|  
|`true`|<xref:System.Security.Principal.WindowsIdentity> 에 관계 없이 비동기 지점 간을 흐르지 않는 <xref:System.Threading.ExecutionContext> 흐름 현재 스레드에 설정 합니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`runtime`|어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.|  
  
## <a name="remarks"></a>설명  
 .NET Framework 버전 1.0 및 1.1의 <xref:System.Security.Principal.WindowsIdentity> 사용자 정의 된 모든 비동기 지점 간을 흐르지 않습니다. .NET framework 버전 2.0부터는 <xref:System.Threading.ExecutionContext> 현재 실행 중인 스레드 및 해당 하는 방법에 대 한 정보가 들어 있는 개체 응용 프로그램 도메인 내에서 비동기 지점 간을 흐르도록 합니다. <xref:System.Security.Principal.WindowsIdentity> 이 실행 컨텍스트에 포함 되 고 따라서도 비동기 지점 간을 흐르도록, 가장 컨텍스트 있으면 하는 흐름을 의미 합니다.  
  
 .NET Framework 2.0부터 사용할 수는 `<legacyImpersonationPolicy>` 지정 하는 요소 <xref:System.Security.Principal.WindowsIdentity> 비동기 지점 간을 흐르지 않습니다.  
  
> [!NOTE]
>  CLR (공용 언어 런타임)는 Win32 함수를 직접 호출을 통해 관리 되지 않는 코드와 같은 플랫폼을 통해 관리 되는 코드 외부에서 수행 된 가장의 관리 되는 코드만 사용 하 여 수행 되는 작업 호출이 가장 인식 합니다. 관리 되는 <xref:System.Security.Principal.WindowsIdentity> 경우가 아니면 개체 비동기 지점 간을 이동할 수는 `alwaysFlowImpersonationPolicy` 요소를 설정한로 (`<alwaysFlowImpersonationPolicy enabled="true"/>`). 설정 된 `alwaysFlowImpersonationPolicy` 요소를 true로 Windows id 가장을 수행 하는 방법에 관계 없이 비동기 지점 간을 항상 전달 되도록 지정 합니다. 자세한 내용은 관리 되지 않는 흐름에 대 한 정보 가장 비동기 지점 간을 [ \<alwaysFlowImpersonationPolicy > 요소](../../../../../docs/framework/configure-apps/file-schema/runtime/alwaysflowimpersonationpolicy-element.md)합니다.  
  
 다른 두 가지 방법으로이 기본 동작을 변경할 수 있습니다.  
  
1. 스레드별 기준 관리 되는 코드입니다.  
  
     스레드별 기준 흐름을 수정 하 여 무시할 수 있습니다는 <xref:System.Threading.ExecutionContext> 및 <xref:System.Security.SecurityContext> 사용 하 여 설정 합니다 <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>, <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType> 또는 <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> 메서드.  
  
2. 로드 된 CLR (공용 언어 런타임) 관리 되지 않는 호스팅 인터페이스를 호출 합니다.  
  
     관리 되지 않는 호스팅 인터페이스 (대신 간단한 관리 되는 실행 파일)를 사용 하 여 CLR을 로드 하, 경우에 대 한 호출에서 특수 플래그를 지정할 수 있습니다 합니다 [CorBindToRuntimeEx 함수](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) 함수입니다. 전체 프로세스에 대 한 호환성 모드를 사용 하려면 다음을 설정 합니다 `flags` 에 대 한 매개 변수 [CorBindToRuntimeEx 함수](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) STARTUP_LEGACY_IMPERSONATION를 합니다.  
  
 자세한 내용은 참조는 [ \<alwaysFlowImpersonationPolicy > 요소](../../../../../docs/framework/configure-apps/file-schema/runtime/alwaysflowimpersonationpolicy-element.md)합니다.  
  
## <a name="configuration-file"></a>구성 파일  
 .NET Framework 응용 프로그램에서이 요소는 응용 프로그램 구성 파일에만 사용할 수 있습니다.  
  
 ASP.NET 응용 프로그램에서 가장 흐름이 있는 aspnet.config 파일에서 구성할 수 있습니다는 \<Windows 폴더 > \Microsoft.NET\Framework\vx.x.xxxx 디렉터리입니다.  
  
 기본적으로 ASP.NET에는 다음 구성 설정을 사용 하 여 aspnet.config 파일에서 가장 흐름을 비활성화 합니다.  
  
``` xml
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
      <alwaysFlowImpersonationPolicy enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
 ASP.NET에서 가장의 흐름을 대신 허용 하려면 다음 구성 설정을 사용 해야 합니다 명시적으로.  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="false"/>  
      <alwaysFlowImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="example"></a>예제  
 다음 예제에서는 비동기 지점 간을 Windows id를 전달 하지 않는 레거시 동작을 지정 하는 방법을 보여 줍니다.  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>참고자료

- [런타임 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [구성 파일 스키마](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [\<alwaysFlowImpersonationPolicy > 요소](../../../../../docs/framework/configure-apps/file-schema/runtime/alwaysflowimpersonationpolicy-element.md)
