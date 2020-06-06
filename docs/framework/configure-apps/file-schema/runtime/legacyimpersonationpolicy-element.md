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
# <a name="legacyimpersonationpolicy-element"></a><span data-ttu-id="4ddcc-102">\<legacyImpersonationPolicy> 요소</span><span class="sxs-lookup"><span data-stu-id="4ddcc-102">\<legacyImpersonationPolicy> Element</span></span>
<span data-ttu-id="4ddcc-103">현재 스레드의 실행 컨텍스트 흐름 설정과 관계없이 Windows ID가 비동기 지점 간을 흐르지 않도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddcc-103">Specifies that the Windows identity does not flow across asynchronous points, regardless of the flow settings for the execution context on the current thread.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<legacyImpersonationPolicy>**  
  
## <a name="syntax"></a><span data-ttu-id="4ddcc-104">구문</span><span class="sxs-lookup"><span data-stu-id="4ddcc-104">Syntax</span></span>  
  
```xml  
<legacyImpersonationPolicy
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4ddcc-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="4ddcc-105">Attributes and Elements</span></span>  
 <span data-ttu-id="4ddcc-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddcc-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4ddcc-107">특성</span><span class="sxs-lookup"><span data-stu-id="4ddcc-107">Attributes</span></span>  
  
|<span data-ttu-id="4ddcc-108">attribute</span><span class="sxs-lookup"><span data-stu-id="4ddcc-108">Attribute</span></span>|<span data-ttu-id="4ddcc-109">Description</span><span class="sxs-lookup"><span data-stu-id="4ddcc-109">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="4ddcc-110">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="4ddcc-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="4ddcc-111"><xref:System.Security.Principal.WindowsIdentity>현재 스레드의 흐름 설정에 관계 없이가 비동기 요소를 통해 이동 하지 않도록 지정 합니다 <xref:System.Threading.ExecutionContext> .</span><span class="sxs-lookup"><span data-stu-id="4ddcc-111">Specifies that the <xref:System.Security.Principal.WindowsIdentity> does not flow across asynchronous points, regardless of the <xref:System.Threading.ExecutionContext> flow settings on the current thread.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="4ddcc-112">enabled 특성</span><span class="sxs-lookup"><span data-stu-id="4ddcc-112">enabled Attribute</span></span>  
  
|<span data-ttu-id="4ddcc-113">값</span><span class="sxs-lookup"><span data-stu-id="4ddcc-113">Value</span></span>|<span data-ttu-id="4ddcc-114">Description</span><span class="sxs-lookup"><span data-stu-id="4ddcc-114">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="4ddcc-115"><xref:System.Security.Principal.WindowsIdentity><xref:System.Threading.ExecutionContext>현재 스레드에 대 한 흐름 설정에 따라 비동기 요소를 통해 흐릅니다.</span><span class="sxs-lookup"><span data-stu-id="4ddcc-115"><xref:System.Security.Principal.WindowsIdentity> flows across asynchronous points depending upon the <xref:System.Threading.ExecutionContext> flow settings for the current thread.</span></span> <span data-ttu-id="4ddcc-116">기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="4ddcc-116">This is the default.</span></span>|  
|`true`|<span data-ttu-id="4ddcc-117"><xref:System.Security.Principal.WindowsIdentity>는 현재 스레드의 흐름 설정에 관계 없이 비동기 요소를 통해 이동 하지 않습니다 <xref:System.Threading.ExecutionContext> .</span><span class="sxs-lookup"><span data-stu-id="4ddcc-117"><xref:System.Security.Principal.WindowsIdentity> does not flow across asynchronous points, regardless of the <xref:System.Threading.ExecutionContext> flow settings on the current thread.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4ddcc-118">자식 요소</span><span class="sxs-lookup"><span data-stu-id="4ddcc-118">Child Elements</span></span>  
 <span data-ttu-id="4ddcc-119">없음</span><span class="sxs-lookup"><span data-stu-id="4ddcc-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4ddcc-120">부모 요소</span><span class="sxs-lookup"><span data-stu-id="4ddcc-120">Parent Elements</span></span>  
  
|<span data-ttu-id="4ddcc-121">요소</span><span class="sxs-lookup"><span data-stu-id="4ddcc-121">Element</span></span>|<span data-ttu-id="4ddcc-122">Description</span><span class="sxs-lookup"><span data-stu-id="4ddcc-122">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="4ddcc-123">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="4ddcc-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="4ddcc-124">어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddcc-124">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4ddcc-125">설명</span><span class="sxs-lookup"><span data-stu-id="4ddcc-125">Remarks</span></span>  
 <span data-ttu-id="4ddcc-126">.NET Framework 버전 1.0 및 1.1에서은 <xref:System.Security.Principal.WindowsIdentity> 사용자가 정의한 비동기 시점 간에 이동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4ddcc-126">In the .NET Framework versions 1.0 and 1.1, the <xref:System.Security.Principal.WindowsIdentity> does not flow across any user-defined asynchronous points.</span></span> <span data-ttu-id="4ddcc-127">.NET Framework 버전 2.0부터 <xref:System.Threading.ExecutionContext> 현재 실행 중인 스레드에 대 한 정보를 포함 하는 개체가 있으며 응용 프로그램 도메인 내의 비동기 요소를 통해 흐릅니다.</span><span class="sxs-lookup"><span data-stu-id="4ddcc-127">Starting with the .NET Framework version 2.0, there is an <xref:System.Threading.ExecutionContext> object that contains information about the currently executing thread, and it flows across asynchronous points within an application domain.</span></span> <span data-ttu-id="4ddcc-128">는 <xref:System.Security.Principal.WindowsIdentity> 이 실행 컨텍스트에 포함 되어 있으므로 비동기 지점만 전달 됩니다. 즉, 가장 컨텍스트가 있는 경우에도 흐릅니다.</span><span class="sxs-lookup"><span data-stu-id="4ddcc-128">The <xref:System.Security.Principal.WindowsIdentity> is included in this execution context and therefore also flows across the asynchronous points, which means that if an impersonation context exists, it will flow as well.</span></span>  
  
 <span data-ttu-id="4ddcc-129">.NET Framework 2.0부터 요소를 사용 하 여 `<legacyImpersonationPolicy>` <xref:System.Security.Principal.WindowsIdentity> 가 비동기 요소 간에 이동 하지 않도록 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ddcc-129">Starting with the .NET Framework 2.0, you can use the `<legacyImpersonationPolicy>` element to specify that  <xref:System.Security.Principal.WindowsIdentity> does not flow across asynchronous points.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4ddcc-130">CLR (공용 언어 런타임)은 관리 코드를 사용 하 여 수행 되는 가장 작업을 인식 합니다. 예를 들어 비관리 코드에 대 한 플랫폼 호출 또는 Win32 함수에 대 한 직접 호출을 통해 관리 코드 외부에서 수행 되는 가장이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="4ddcc-130">The common language runtime (CLR) is aware of impersonation operations performed using only managed code, not of impersonation performed outside of managed code, such as through platform invoke to unmanaged code or through direct calls to Win32 functions.</span></span> <span data-ttu-id="4ddcc-131"><xref:System.Security.Principal.WindowsIdentity> `alwaysFlowImpersonationPolicy` 요소가 true ()로 설정 되지 않은 경우 관리 되는 개체만 비동기 요소를 통해 흐를 수 있습니다 `<alwaysFlowImpersonationPolicy enabled="true"/>` .</span><span class="sxs-lookup"><span data-stu-id="4ddcc-131">Only managed <xref:System.Security.Principal.WindowsIdentity> objects can flow across asynchronous points, unless the `alwaysFlowImpersonationPolicy` element has been set to true (`<alwaysFlowImpersonationPolicy enabled="true"/>`).</span></span> <span data-ttu-id="4ddcc-132">요소를 `alwaysFlowImpersonationPolicy` true로 설정 하면 가장 수행 된 방법에 관계 없이 Windows id가 항상 비동기 요소를 통해 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddcc-132">Setting the `alwaysFlowImpersonationPolicy` element to true specifies that the Windows identity always flows across asynchronous points, regardless of how impersonation was performed.</span></span> <span data-ttu-id="4ddcc-133">비동기 시점에서 관리 되지 않는 가장을 이동 하는 방법에 대 한 자세한 내용은 [ \<alwaysFlowImpersonationPolicy> 요소](alwaysflowimpersonationpolicy-element.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4ddcc-133">For more information on flowing unmanaged impersonation across asynchronous points, see [\<alwaysFlowImpersonationPolicy> Element](alwaysflowimpersonationpolicy-element.md).</span></span>  
  
 <span data-ttu-id="4ddcc-134">다른 두 가지 방법으로이 기본 동작을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ddcc-134">You can alter this default behavior in two other ways:</span></span>  
  
1. <span data-ttu-id="4ddcc-135">스레드 단위로 관리 코드에서</span><span class="sxs-lookup"><span data-stu-id="4ddcc-135">In managed code on a per-thread basis.</span></span>  
  
     <span data-ttu-id="4ddcc-136"><xref:System.Threading.ExecutionContext> <xref:System.Security.SecurityContext> <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType> , 또는 메서드를 사용 하 여 및 설정을 수정 하 여 스레드 단위로 흐름을 억제할 수 있습니다 <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType> <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="4ddcc-136">You can suppress the flow on a per-thread basis by modifying the <xref:System.Threading.ExecutionContext> and <xref:System.Security.SecurityContext> settings by using the <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>, <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType> or <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> method.</span></span>  
  
2. <span data-ttu-id="4ddcc-137">관리 되지 않는 호스팅 인터페이스를 호출 하 여 CLR (공용 언어 런타임)을 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddcc-137">In the call to the unmanaged hosting interface to load the common language runtime (CLR).</span></span>  
  
     <span data-ttu-id="4ddcc-138">단순한 관리 되는 실행 파일 대신 관리 되지 않는 호스팅 인터페이스를 사용 하 여 CLR을 로드 하는 경우 [CorBindToRuntimeEx 함수](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) 함수 호출에서 특수 플래그를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ddcc-138">If an unmanaged hosting interface (instead of a simple managed executable) is used to load the CLR, you can specify a special flag in the call to the [CorBindToRuntimeEx Function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) function.</span></span> <span data-ttu-id="4ddcc-139">전체 프로세스에 대해 호환 모드를 사용 하도록 설정 하려면 `flags` [CorBindToRuntimeEx 함수](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) 에 대 한 매개 변수를 STARTUP_LEGACY_IMPERSONATION 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddcc-139">To enable the compatibility mode for the entire process, set the `flags` parameter for [CorBindToRuntimeEx Function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) to STARTUP_LEGACY_IMPERSONATION.</span></span>  
  
 <span data-ttu-id="4ddcc-140">자세한 내용은 [ \<alwaysFlowImpersonationPolicy> 요소](alwaysflowimpersonationpolicy-element.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4ddcc-140">For more information, see the [\<alwaysFlowImpersonationPolicy> Element](alwaysflowimpersonationpolicy-element.md).</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="4ddcc-141">구성 파일</span><span class="sxs-lookup"><span data-stu-id="4ddcc-141">Configuration File</span></span>  
 <span data-ttu-id="4ddcc-142">.NET Framework 응용 프로그램에서이 요소는 응용 프로그램 구성 파일에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ddcc-142">In a .NET Framework application, this element can be used only in the application configuration file.</span></span>  
  
 <span data-ttu-id="4ddcc-143">ASP.NET 응용 프로그램의 경우 \Microsoft.NET\Framework\vx.x.xxxx 디렉터리에 있는 aspnet .config 파일에서 가장 흐름을 구성할 수 있습니다 \<Windows Folder> .</span><span class="sxs-lookup"><span data-stu-id="4ddcc-143">For an ASP.NET application, the impersonation flow can be configured in the aspnet.config file found in the \<Windows Folder>\Microsoft.NET\Framework\vx.x.xxxx directory.</span></span>  
  
 <span data-ttu-id="4ddcc-144">ASP.NET는 기본적으로 다음 구성 설정을 사용 하 여 aspnet 파일에서 가장 흐름을 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddcc-144">ASP.NET by default disables the impersonation flow in the aspnet.config file by using the following configuration settings:</span></span>  
  
``` xml
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
      <alwaysFlowImpersonationPolicy enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="4ddcc-145">ASP.NET에서 대신 가장의 흐름을 허용 하려면 다음 구성 설정을 명시적으로 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ddcc-145">In ASP.NET, if you want to allow the flow of impersonation instead, you must explicitly use the following configuration settings:</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="false"/>  
      <alwaysFlowImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="example"></a><span data-ttu-id="4ddcc-146">예제</span><span class="sxs-lookup"><span data-stu-id="4ddcc-146">Example</span></span>  
 <span data-ttu-id="4ddcc-147">다음 예제에서는 비동기 시점에서 Windows id를 전달 하지 않는 레거시 동작을 지정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4ddcc-147">The following example shows how to specify the legacy behavior that does not flow the Windows identity across asynchronous points.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4ddcc-148">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4ddcc-148">See also</span></span>

- [<span data-ttu-id="4ddcc-149">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="4ddcc-149">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="4ddcc-150">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="4ddcc-150">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="4ddcc-151">\<alwaysFlowImpersonationPolicy>요소인</span><span class="sxs-lookup"><span data-stu-id="4ddcc-151">\<alwaysFlowImpersonationPolicy> Element</span></span>](alwaysflowimpersonationpolicy-element.md)
