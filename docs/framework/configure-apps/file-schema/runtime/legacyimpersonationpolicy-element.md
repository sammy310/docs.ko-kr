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
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154106"
---
# <a name="legacyimpersonationpolicy-element"></a><span data-ttu-id="d029b-102">\<레거시 사칭정책> 요소</span><span class="sxs-lookup"><span data-stu-id="d029b-102">\<legacyImpersonationPolicy> Element</span></span>
<span data-ttu-id="d029b-103">현재 스레드의 실행 컨텍스트 흐름 설정과 관계없이 Windows ID가 비동기 지점 간을 흐르지 않도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d029b-103">Specifies that the Windows identity does not flow across asynchronous points, regardless of the flow settings for the execution context on the current thread.</span></span>  
  
<span data-ttu-id="d029b-104">[**\<구성>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="d029b-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="d029b-105">&nbsp;&nbsp;[**\<런타임>**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="d029b-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="d029b-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<레거시 사칭정책>**</span><span class="sxs-lookup"><span data-stu-id="d029b-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<legacyImpersonationPolicy>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d029b-107">구문</span><span class="sxs-lookup"><span data-stu-id="d029b-107">Syntax</span></span>  
  
```xml  
<legacyImpersonationPolicy
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d029b-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="d029b-108">Attributes and Elements</span></span>  
 <span data-ttu-id="d029b-109">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d029b-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d029b-110">특성</span><span class="sxs-lookup"><span data-stu-id="d029b-110">Attributes</span></span>  
  
|<span data-ttu-id="d029b-111">attribute</span><span class="sxs-lookup"><span data-stu-id="d029b-111">Attribute</span></span>|<span data-ttu-id="d029b-112">Description</span><span class="sxs-lookup"><span data-stu-id="d029b-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="d029b-113">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="d029b-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="d029b-114">현재 스레드의 <xref:System.Security.Principal.WindowsIdentity> <xref:System.Threading.ExecutionContext> 흐름 설정에 관계없이 비동기 지점에서 흐르지 않도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d029b-114">Specifies that the <xref:System.Security.Principal.WindowsIdentity> does not flow across asynchronous points, regardless of the <xref:System.Threading.ExecutionContext> flow settings on the current thread.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="d029b-115">enabled 특성</span><span class="sxs-lookup"><span data-stu-id="d029b-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="d029b-116">값</span><span class="sxs-lookup"><span data-stu-id="d029b-116">Value</span></span>|<span data-ttu-id="d029b-117">Description</span><span class="sxs-lookup"><span data-stu-id="d029b-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="d029b-118"><xref:System.Security.Principal.WindowsIdentity>현재 스레드의 <xref:System.Threading.ExecutionContext> 흐름 설정에 따라 비동기 지점에 걸쳐 흐릅니다.</span><span class="sxs-lookup"><span data-stu-id="d029b-118"><xref:System.Security.Principal.WindowsIdentity> flows across asynchronous points depending upon the <xref:System.Threading.ExecutionContext> flow settings for the current thread.</span></span> <span data-ttu-id="d029b-119">이것이 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="d029b-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="d029b-120"><xref:System.Security.Principal.WindowsIdentity>현재 스레드의 <xref:System.Threading.ExecutionContext> 흐름 설정에 관계없이 비동기 지점에서 흐르지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d029b-120"><xref:System.Security.Principal.WindowsIdentity> does not flow across asynchronous points, regardless of the <xref:System.Threading.ExecutionContext> flow settings on the current thread.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d029b-121">자식 요소</span><span class="sxs-lookup"><span data-stu-id="d029b-121">Child Elements</span></span>  
 <span data-ttu-id="d029b-122">없음</span><span class="sxs-lookup"><span data-stu-id="d029b-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d029b-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="d029b-123">Parent Elements</span></span>  
  
|<span data-ttu-id="d029b-124">요소</span><span class="sxs-lookup"><span data-stu-id="d029b-124">Element</span></span>|<span data-ttu-id="d029b-125">Description</span><span class="sxs-lookup"><span data-stu-id="d029b-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="d029b-126">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="d029b-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="d029b-127">어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="d029b-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d029b-128">설명</span><span class="sxs-lookup"><span data-stu-id="d029b-128">Remarks</span></span>  
 <span data-ttu-id="d029b-129">.NET Framework 버전 1.0 및 1.1에서는 사용자 정의 비동기 지점에서 흐르지 <xref:System.Security.Principal.WindowsIdentity> 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d029b-129">In the .NET Framework versions 1.0 and 1.1, the <xref:System.Security.Principal.WindowsIdentity> does not flow across any user-defined asynchronous points.</span></span> <span data-ttu-id="d029b-130">.NET Framework 버전 2.0부터 현재 <xref:System.Threading.ExecutionContext> 실행 중인 스레드에 대한 정보가 포함된 개체가 있으며 응용 프로그램 도메인 내의 비동기 지점을 통해 흐릅니다.</span><span class="sxs-lookup"><span data-stu-id="d029b-130">Starting with the .NET Framework version 2.0, there is an <xref:System.Threading.ExecutionContext> object that contains information about the currently executing thread, and it flows across asynchronous points within an application domain.</span></span> <span data-ttu-id="d029b-131">는 <xref:System.Security.Principal.WindowsIdentity> 이 실행 컨텍스트에 포함되므로 비동기 지점을 가로질러 흐릅니다.</span><span class="sxs-lookup"><span data-stu-id="d029b-131">The <xref:System.Security.Principal.WindowsIdentity> is included in this execution context and therefore also flows across the asynchronous points, which means that if an impersonation context exists, it will flow as well.</span></span>  
  
 <span data-ttu-id="d029b-132">.NET Framework 2.0부터 시작하여 `<legacyImpersonationPolicy>` 요소를 사용하여 비동기 <xref:System.Security.Principal.WindowsIdentity> 지점에서 흐르지 않도록 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d029b-132">Starting with the .NET Framework 2.0, you can use the `<legacyImpersonationPolicy>` element to specify that  <xref:System.Security.Principal.WindowsIdentity> does not flow across asynchronous points.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d029b-133">공통 언어 런타임(CLR)은 관리되지 않는 코드에 대한 플랫폼 호출 또는 Win32 함수에 대한 직접 호출과 같이 관리 코드 외부에서 수행되는 가장이 아닌 관리 코드만 사용하여 수행되는 가장 작업을 인식합니다.</span><span class="sxs-lookup"><span data-stu-id="d029b-133">The common language runtime (CLR) is aware of impersonation operations performed using only managed code, not of impersonation performed outside of managed code, such as through platform invoke to unmanaged code or through direct calls to Win32 functions.</span></span> <span data-ttu-id="d029b-134">요소가 <xref:System.Security.Principal.WindowsIdentity> true()로`<alwaysFlowImpersonationPolicy enabled="true"/>`설정되지 않은 경우 관리되는 개체만 비동기 지점을 가로질러 흐를 수 있습니다. `alwaysFlowImpersonationPolicy`</span><span class="sxs-lookup"><span data-stu-id="d029b-134">Only managed <xref:System.Security.Principal.WindowsIdentity> objects can flow across asynchronous points, unless the `alwaysFlowImpersonationPolicy` element has been set to true (`<alwaysFlowImpersonationPolicy enabled="true"/>`).</span></span> <span data-ttu-id="d029b-135">`alwaysFlowImpersonationPolicy` 요소를 true로 설정하면 가장이 수행된 방식에 관계없이 Windows ID가 항상 비동기 지점에서 흐르도록 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="d029b-135">Setting the `alwaysFlowImpersonationPolicy` element to true specifies that the Windows identity always flows across asynchronous points, regardless of how impersonation was performed.</span></span> <span data-ttu-id="d029b-136">비동기 포인트에서 관리되지 않는 가장을 흐르는 방법에 대한 자세한 내용은 [ \<alwaysFlow사칭정책> 요소를](alwaysflowimpersonationpolicy-element.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d029b-136">For more information on flowing unmanaged impersonation across asynchronous points, see [\<alwaysFlowImpersonationPolicy> Element](alwaysflowimpersonationpolicy-element.md).</span></span>  
  
 <span data-ttu-id="d029b-137">이 기본 동작은 다음 두 가지 방법으로 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d029b-137">You can alter this default behavior in two other ways:</span></span>  
  
1. <span data-ttu-id="d029b-138">스레드별로 관리 되는 코드에서 입니다.</span><span class="sxs-lookup"><span data-stu-id="d029b-138">In managed code on a per-thread basis.</span></span>  
  
     <span data-ttu-id="d029b-139"><xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>을 <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType> 사용하여 <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> <xref:System.Threading.ExecutionContext> 및 <xref:System.Security.SecurityContext> 설정을 수정하여 스레드별로 흐름을 억제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d029b-139">You can suppress the flow on a per-thread basis by modifying the <xref:System.Threading.ExecutionContext> and <xref:System.Security.SecurityContext> settings by using the <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>, <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType> or <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> method.</span></span>  
  
2. <span data-ttu-id="d029b-140">관리되지 않는 호스팅 인터페이스에 대한 호출에서 공통 언어 런타임(CLR)을 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="d029b-140">In the call to the unmanaged hosting interface to load the common language runtime (CLR).</span></span>  
  
     <span data-ttu-id="d029b-141">CLR을 로드하는 데 관리되지 않는 호스팅 인터페이스(간단한 관리 실행 가능) 대신사용하는 경우 [CorBindToRuntimeEx 함수](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) 호출에서 특수 플래그를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d029b-141">If an unmanaged hosting interface (instead of a simple managed executable) is used to load the CLR, you can specify a special flag in the call to the [CorBindToRuntimeEx Function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) function.</span></span> <span data-ttu-id="d029b-142">전체 프로세스에 대한 호환성 모드를 사용하려면 `flags` [CorBindToRuntimeEx 함수에](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) 대한 매개 변수를 STARTUP_LEGACY_IMPERSONATION 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d029b-142">To enable the compatibility mode for the entire process, set the `flags` parameter for [CorBindToRuntimeEx Function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) to STARTUP_LEGACY_IMPERSONATION.</span></span>  
  
 <span data-ttu-id="d029b-143">자세한 내용은 [ \<항상흐름 사칭정책> 요소를](alwaysflowimpersonationpolicy-element.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d029b-143">For more information, see the [\<alwaysFlowImpersonationPolicy> Element](alwaysflowimpersonationpolicy-element.md).</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="d029b-144">구성 파일</span><span class="sxs-lookup"><span data-stu-id="d029b-144">Configuration File</span></span>  
 <span data-ttu-id="d029b-145">.NET Framework 응용 프로그램에서이 요소는 응용 프로그램 구성 파일에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d029b-145">In a .NET Framework application, this element can be used only in the application configuration file.</span></span>  
  
 <span data-ttu-id="d029b-146">ASP.NET 응용 프로그램의 경우 \<가장 흐름은 Windows 폴더>\Microsoft.NET\Framework\vx.xxxx 디렉터리에서 발견된 aspnet.config 파일에서 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d029b-146">For an ASP.NET application, the impersonation flow can be configured in the aspnet.config file found in the \<Windows Folder>\Microsoft.NET\Framework\vx.x.xxxx directory.</span></span>  
  
 <span data-ttu-id="d029b-147">ASP.NET 기본적으로 다음 구성 설정을 사용하여 aspnet.config 파일에서 가장 흐름을 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d029b-147">ASP.NET by default disables the impersonation flow in the aspnet.config file by using the following configuration settings:</span></span>  
  
``` xml
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
      <alwaysFlowImpersonationPolicy enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="d029b-148">ASP.NET 대신 가장 흐름을 허용하려면 다음 구성 설정을 명시적으로 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d029b-148">In ASP.NET, if you want to allow the flow of impersonation instead, you must explicitly use the following configuration settings:</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="false"/>  
      <alwaysFlowImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="example"></a><span data-ttu-id="d029b-149">예제</span><span class="sxs-lookup"><span data-stu-id="d029b-149">Example</span></span>  
 <span data-ttu-id="d029b-150">다음 예제에서는 비동기 지점에서 Windows ID를 흐르지 않는 레거시 동작을 지정하는 방법을 보여 주며 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d029b-150">The following example shows how to specify the legacy behavior that does not flow the Windows identity across asynchronous points.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d029b-151">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d029b-151">See also</span></span>

- [<span data-ttu-id="d029b-152">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="d029b-152">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="d029b-153">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="d029b-153">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="d029b-154">\<alwaysFlow사칭정책> 요소</span><span class="sxs-lookup"><span data-stu-id="d029b-154">\<alwaysFlowImpersonationPolicy> Element</span></span>](alwaysflowimpersonationpolicy-element.md)
