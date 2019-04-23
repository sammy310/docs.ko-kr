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
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59333992"
---
# <a name="legacyimpersonationpolicy-element"></a><span data-ttu-id="6ebc7-102">\<legacyImpersonationPolicy > 요소</span><span class="sxs-lookup"><span data-stu-id="6ebc7-102">\<legacyImpersonationPolicy> Element</span></span>
<span data-ttu-id="6ebc7-103">현재 스레드의 실행 컨텍스트 흐름 설정과 관계없이 Windows ID가 비동기 지점 간을 흐르지 않도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6ebc7-103">Specifies that the Windows identity does not flow across asynchronous points, regardless of the flow settings for the execution context on the current thread.</span></span>  
  
 <span data-ttu-id="6ebc7-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="6ebc7-104">\<configuration></span></span>  
<span data-ttu-id="6ebc7-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="6ebc7-105">\<runtime></span></span>  
<span data-ttu-id="6ebc7-106">\<legacyImpersonationPolicy></span><span class="sxs-lookup"><span data-stu-id="6ebc7-106">\<legacyImpersonationPolicy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ebc7-107">구문</span><span class="sxs-lookup"><span data-stu-id="6ebc7-107">Syntax</span></span>  
  
```xml  
<legacyImpersonationPolicy    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6ebc7-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="6ebc7-108">Attributes and Elements</span></span>  
 <span data-ttu-id="6ebc7-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6ebc7-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6ebc7-110">특성</span><span class="sxs-lookup"><span data-stu-id="6ebc7-110">Attributes</span></span>  
  
|<span data-ttu-id="6ebc7-111">특성</span><span class="sxs-lookup"><span data-stu-id="6ebc7-111">Attribute</span></span>|<span data-ttu-id="6ebc7-112">설명</span><span class="sxs-lookup"><span data-stu-id="6ebc7-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="6ebc7-113">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="6ebc7-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="6ebc7-114">지정 합니다 <xref:System.Security.Principal.WindowsIdentity> 에 관계 없이 비동기 지점 간을 흐르지 않는 <xref:System.Threading.ExecutionContext> 흐름 현재 스레드에 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ebc7-114">Specifies that the <xref:System.Security.Principal.WindowsIdentity> does not flow across asynchronous points, regardless of the <xref:System.Threading.ExecutionContext> flow settings on the current thread.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="6ebc7-115">enabled 특성</span><span class="sxs-lookup"><span data-stu-id="6ebc7-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="6ebc7-116">값</span><span class="sxs-lookup"><span data-stu-id="6ebc7-116">Value</span></span>|<span data-ttu-id="6ebc7-117">설명</span><span class="sxs-lookup"><span data-stu-id="6ebc7-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="6ebc7-118"><xref:System.Security.Principal.WindowsIdentity> 흐름에 따라 비동기 지점 간을 <xref:System.Threading.ExecutionContext> 흐름 현재 스레드에 대 한 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="6ebc7-118"><xref:System.Security.Principal.WindowsIdentity> flows across asynchronous points depending upon the <xref:System.Threading.ExecutionContext> flow settings for the current thread.</span></span> <span data-ttu-id="6ebc7-119">이 값이 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="6ebc7-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="6ebc7-120"><xref:System.Security.Principal.WindowsIdentity> 에 관계 없이 비동기 지점 간을 흐르지 않는 <xref:System.Threading.ExecutionContext> 흐름 현재 스레드에 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ebc7-120"><xref:System.Security.Principal.WindowsIdentity> does not flow across asynchronous points, regardless of the <xref:System.Threading.ExecutionContext> flow settings on the current thread.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6ebc7-121">자식 요소</span><span class="sxs-lookup"><span data-stu-id="6ebc7-121">Child Elements</span></span>  
 <span data-ttu-id="6ebc7-122">없음</span><span class="sxs-lookup"><span data-stu-id="6ebc7-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6ebc7-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="6ebc7-123">Parent Elements</span></span>  
  
|<span data-ttu-id="6ebc7-124">요소</span><span class="sxs-lookup"><span data-stu-id="6ebc7-124">Element</span></span>|<span data-ttu-id="6ebc7-125">설명</span><span class="sxs-lookup"><span data-stu-id="6ebc7-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="6ebc7-126">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="6ebc7-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="6ebc7-127">어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="6ebc7-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6ebc7-128">설명</span><span class="sxs-lookup"><span data-stu-id="6ebc7-128">Remarks</span></span>  
 <span data-ttu-id="6ebc7-129">.NET Framework 버전 1.0 및 1.1의 <xref:System.Security.Principal.WindowsIdentity> 사용자 정의 된 모든 비동기 지점 간을 흐르지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6ebc7-129">In the .NET Framework versions 1.0 and 1.1, the <xref:System.Security.Principal.WindowsIdentity> does not flow across any user-defined asynchronous points.</span></span> <span data-ttu-id="6ebc7-130">.NET framework 버전 2.0부터는 <xref:System.Threading.ExecutionContext> 현재 실행 중인 스레드 및 해당 하는 방법에 대 한 정보가 들어 있는 개체 응용 프로그램 도메인 내에서 비동기 지점 간을 흐르도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ebc7-130">Starting with the .NET Framework version 2.0, there is an <xref:System.Threading.ExecutionContext> object that contains information about the currently executing thread, and it flows across asynchronous points within an application domain.</span></span> <span data-ttu-id="6ebc7-131"><xref:System.Security.Principal.WindowsIdentity> 이 실행 컨텍스트에 포함 되 고 따라서도 비동기 지점 간을 흐르도록, 가장 컨텍스트 있으면 하는 흐름을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ebc7-131">The <xref:System.Security.Principal.WindowsIdentity> is included in this execution context and therefore also flows across the asynchronous points, which means that if an impersonation context exists, it will flow as well.</span></span>  
  
 <span data-ttu-id="6ebc7-132">.NET Framework 2.0부터 사용할 수는 `<legacyImpersonationPolicy>` 지정 하는 요소 <xref:System.Security.Principal.WindowsIdentity> 비동기 지점 간을 흐르지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6ebc7-132">Starting with the .NET Framework 2.0, you can use the `<legacyImpersonationPolicy>` element to specify that  <xref:System.Security.Principal.WindowsIdentity> does not flow across asynchronous points.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6ebc7-133">CLR (공용 언어 런타임)는 Win32 함수를 직접 호출을 통해 관리 되지 않는 코드와 같은 플랫폼을 통해 관리 되는 코드 외부에서 수행 된 가장의 관리 되는 코드만 사용 하 여 수행 되는 작업 호출이 가장 인식 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ebc7-133">The common language runtime (CLR) is aware of impersonation operations performed using only managed code, not of impersonation performed outside of managed code, such as through platform invoke to unmanaged code or through direct calls to Win32 functions.</span></span> <span data-ttu-id="6ebc7-134">관리 되는 <xref:System.Security.Principal.WindowsIdentity> 경우가 아니면 개체 비동기 지점 간을 이동할 수는 `alwaysFlowImpersonationPolicy` 요소를 설정한로 (`<alwaysFlowImpersonationPolicy enabled="true"/>`).</span><span class="sxs-lookup"><span data-stu-id="6ebc7-134">Only managed <xref:System.Security.Principal.WindowsIdentity> objects can flow across asynchronous points, unless the `alwaysFlowImpersonationPolicy` element has been set to true (`<alwaysFlowImpersonationPolicy enabled="true"/>`).</span></span> <span data-ttu-id="6ebc7-135">설정 된 `alwaysFlowImpersonationPolicy` 요소를 true로 Windows id 가장을 수행 하는 방법에 관계 없이 비동기 지점 간을 항상 전달 되도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ebc7-135">Setting the `alwaysFlowImpersonationPolicy` element to true specifies that the Windows identity always flows across asynchronous points, regardless of how impersonation was performed.</span></span> <span data-ttu-id="6ebc7-136">자세한 내용은 관리 되지 않는 흐름에 대 한 정보 가장 비동기 지점 간을 [ \<alwaysFlowImpersonationPolicy > 요소](../../../../../docs/framework/configure-apps/file-schema/runtime/alwaysflowimpersonationpolicy-element.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6ebc7-136">For more information on flowing unmanaged impersonation across asynchronous points, see [\<alwaysFlowImpersonationPolicy> Element](../../../../../docs/framework/configure-apps/file-schema/runtime/alwaysflowimpersonationpolicy-element.md).</span></span>  
  
 <span data-ttu-id="6ebc7-137">다른 두 가지 방법으로이 기본 동작을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ebc7-137">You can alter this default behavior in two other ways:</span></span>  
  
1. <span data-ttu-id="6ebc7-138">스레드별 기준 관리 되는 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="6ebc7-138">In managed code on a per-thread basis.</span></span>  
  
     <span data-ttu-id="6ebc7-139">스레드별 기준 흐름을 수정 하 여 무시할 수 있습니다는 <xref:System.Threading.ExecutionContext> 및 <xref:System.Security.SecurityContext> 사용 하 여 설정 합니다 <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>, <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType> 또는 <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> 메서드.</span><span class="sxs-lookup"><span data-stu-id="6ebc7-139">You can suppress the flow on a per-thread basis by modifying the <xref:System.Threading.ExecutionContext> and <xref:System.Security.SecurityContext> settings by using the <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>, <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType> or <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> method.</span></span>  
  
2. <span data-ttu-id="6ebc7-140">로드 된 CLR (공용 언어 런타임) 관리 되지 않는 호스팅 인터페이스를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ebc7-140">In the call to the unmanaged hosting interface to load the common language runtime (CLR).</span></span>  
  
     <span data-ttu-id="6ebc7-141">관리 되지 않는 호스팅 인터페이스 (대신 간단한 관리 되는 실행 파일)를 사용 하 여 CLR을 로드 하, 경우에 대 한 호출에서 특수 플래그를 지정할 수 있습니다 합니다 [CorBindToRuntimeEx 함수](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="6ebc7-141">If an unmanaged hosting interface (instead of a simple managed executable) is used to load the CLR, you can specify a special flag in the call to the [CorBindToRuntimeEx Function](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) function.</span></span> <span data-ttu-id="6ebc7-142">전체 프로세스에 대 한 호환성 모드를 사용 하려면 다음을 설정 합니다 `flags` 에 대 한 매개 변수 [CorBindToRuntimeEx 함수](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) STARTUP_LEGACY_IMPERSONATION를 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ebc7-142">To enable the compatibility mode for the entire process, set the `flags` parameter for [CorBindToRuntimeEx Function](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) to STARTUP_LEGACY_IMPERSONATION.</span></span>  
  
 <span data-ttu-id="6ebc7-143">자세한 내용은 참조는 [ \<alwaysFlowImpersonationPolicy > 요소](../../../../../docs/framework/configure-apps/file-schema/runtime/alwaysflowimpersonationpolicy-element.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6ebc7-143">For more information, see the [\<alwaysFlowImpersonationPolicy> Element](../../../../../docs/framework/configure-apps/file-schema/runtime/alwaysflowimpersonationpolicy-element.md).</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="6ebc7-144">구성 파일</span><span class="sxs-lookup"><span data-stu-id="6ebc7-144">Configuration File</span></span>  
 <span data-ttu-id="6ebc7-145">.NET Framework 응용 프로그램에서이 요소는 응용 프로그램 구성 파일에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ebc7-145">In a .NET Framework application, this element can be used only in the application configuration file.</span></span>  
  
 <span data-ttu-id="6ebc7-146">ASP.NET 응용 프로그램에서 가장 흐름이 있는 aspnet.config 파일에서 구성할 수 있습니다는 \<Windows 폴더 > \Microsoft.NET\Framework\vx.x.xxxx 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="6ebc7-146">For an ASP.NET application, the impersonation flow can be configured in the aspnet.config file found in the \<Windows Folder>\Microsoft.NET\Framework\vx.x.xxxx directory.</span></span>  
  
 <span data-ttu-id="6ebc7-147">기본적으로 ASP.NET에는 다음 구성 설정을 사용 하 여 aspnet.config 파일에서 가장 흐름을 비활성화 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ebc7-147">ASP.NET by default disables the impersonation flow in the aspnet.config file by using the following configuration settings:</span></span>  
  
``` xml
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
      <alwaysFlowImpersonationPolicy enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="6ebc7-148">ASP.NET에서 가장의 흐름을 대신 허용 하려면 다음 구성 설정을 사용 해야 합니다 명시적으로.</span><span class="sxs-lookup"><span data-stu-id="6ebc7-148">In ASP.NET, if you want to allow the flow of impersonation instead, you must explicitly use the following configuration settings:</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="false"/>  
      <alwaysFlowImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="example"></a><span data-ttu-id="6ebc7-149">예제</span><span class="sxs-lookup"><span data-stu-id="6ebc7-149">Example</span></span>  
 <span data-ttu-id="6ebc7-150">다음 예제에서는 비동기 지점 간을 Windows id를 전달 하지 않는 레거시 동작을 지정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6ebc7-150">The following example shows how to specify the legacy behavior that does not flow the Windows identity across asynchronous points.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="6ebc7-151">참고자료</span><span class="sxs-lookup"><span data-stu-id="6ebc7-151">See also</span></span>

- [<span data-ttu-id="6ebc7-152">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="6ebc7-152">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="6ebc7-153">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="6ebc7-153">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="6ebc7-154">\<alwaysFlowImpersonationPolicy > 요소</span><span class="sxs-lookup"><span data-stu-id="6ebc7-154">\<alwaysFlowImpersonationPolicy> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/alwaysflowimpersonationpolicy-element.md)
