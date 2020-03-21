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
# <a name="alwaysflowimpersonationpolicy-element"></a><span data-ttu-id="faf4a-102">\<alwaysFlow사칭정책> 요소</span><span class="sxs-lookup"><span data-stu-id="faf4a-102">\<alwaysFlowImpersonationPolicy> Element</span></span>
<span data-ttu-id="faf4a-103">가장을 수행하는 방법과 관계없이 Windows ID가 항상 비동기 지점 간을 흐르도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="faf4a-103">Specifies that the Windows identity always flows across asynchronous points, regardless of how impersonation was performed.</span></span>  
  
<span data-ttu-id="faf4a-104">[**\<구성>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="faf4a-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="faf4a-105">&nbsp;&nbsp;[**\<런타임>**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="faf4a-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="faf4a-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<항상흐름사칭정책>**</span><span class="sxs-lookup"><span data-stu-id="faf4a-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<alwaysFlowImpersonationPolicy>**</span></span>\  
  
## <a name="syntax"></a><span data-ttu-id="faf4a-107">구문</span><span class="sxs-lookup"><span data-stu-id="faf4a-107">Syntax</span></span>  
  
```xml  
<alwaysFlowImpersonationPolicy
  enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="faf4a-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="faf4a-108">Attributes and Elements</span></span>  
 <span data-ttu-id="faf4a-109">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="faf4a-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="faf4a-110">특성</span><span class="sxs-lookup"><span data-stu-id="faf4a-110">Attributes</span></span>  
  
|<span data-ttu-id="faf4a-111">attribute</span><span class="sxs-lookup"><span data-stu-id="faf4a-111">Attribute</span></span>|<span data-ttu-id="faf4a-112">Description</span><span class="sxs-lookup"><span data-stu-id="faf4a-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="faf4a-113">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="faf4a-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="faf4a-114">Windows ID가 비동기 지점을 가로질러 흐르는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="faf4a-114">Indicates whether the Windows identity flows across asynchronous points.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="faf4a-115">enabled 특성</span><span class="sxs-lookup"><span data-stu-id="faf4a-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="faf4a-116">값</span><span class="sxs-lookup"><span data-stu-id="faf4a-116">Value</span></span>|<span data-ttu-id="faf4a-117">Description</span><span class="sxs-lookup"><span data-stu-id="faf4a-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="faf4a-118">와 같은 <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A>관리되는 메서드를 통해 가장이 수행되지 않는 한 Windows ID는 비동기 지점에서 흐르지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="faf4a-118">The Windows identity does not flow across asynchronous points, unless the impersonation is performed through managed methods such as <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A>.</span></span> <span data-ttu-id="faf4a-119">이것이 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="faf4a-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="faf4a-120">Windows ID는 가장이 수행된 방식에 관계없이 항상 비동기 지점을 가로질러 흐릅니다.</span><span class="sxs-lookup"><span data-stu-id="faf4a-120">The Windows identity always flows across asynchronous points, regardless of how impersonation was performed.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="faf4a-121">자식 요소</span><span class="sxs-lookup"><span data-stu-id="faf4a-121">Child Elements</span></span>  
 <span data-ttu-id="faf4a-122">없음</span><span class="sxs-lookup"><span data-stu-id="faf4a-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="faf4a-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="faf4a-123">Parent Elements</span></span>  
  
|<span data-ttu-id="faf4a-124">요소</span><span class="sxs-lookup"><span data-stu-id="faf4a-124">Element</span></span>|<span data-ttu-id="faf4a-125">Description</span><span class="sxs-lookup"><span data-stu-id="faf4a-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="faf4a-126">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="faf4a-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="faf4a-127">어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="faf4a-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="faf4a-128">설명</span><span class="sxs-lookup"><span data-stu-id="faf4a-128">Remarks</span></span>  
 <span data-ttu-id="faf4a-129">.NET Framework 버전 1.0 및 1.1에서 Windows ID는 비동기 지점에서 흐르지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="faf4a-129">In the .NET Framework versions 1.0 and 1.1, the Windows identity does not flow across asynchronous points.</span></span> <span data-ttu-id="faf4a-130">.NET Framework 버전 2.0에는 현재 <xref:System.Threading.ExecutionContext> 실행 중인 스레드에 대한 정보가 포함된 개체가 있으며 응용 프로그램 도메인 내의 비동기 지점을 통해 흐릅니다.</span><span class="sxs-lookup"><span data-stu-id="faf4a-130">In the .NET Framework version 2.0, there is an <xref:System.Threading.ExecutionContext> object that contains information about the currently executing thread, and flows it across asynchronous points within an application domain.</span></span> <span data-ttu-id="faf4a-131"><xref:System.Security.Principal.WindowsIdentity> 또한 비동기 지점을 가로질러 흐르는 정보의 일부로 흐르며, 플랫폼이 네이티브 메서드로 호출하는 것과 같은 다른 수단이 아닌 관리되는 메서드를 <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A> 사용하여 가장을 달성한 경우.</span><span class="sxs-lookup"><span data-stu-id="faf4a-131">The <xref:System.Security.Principal.WindowsIdentity> also flows as part of the information that flows across the asynchronous points, provided the impersonation was achieved using managed methods such as <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A> and not through other means such as platform invoke to native methods.</span></span> <span data-ttu-id="faf4a-132">이 요소는 가장이 달성된 방식에 관계없이 Windows ID가 비동기 지점에서 흐르도록 지정하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="faf4a-132">This element is used to specify that the Windows identity does flow across asynchronous points, regardless of how the impersonation was achieved.</span></span>  
  
 <span data-ttu-id="faf4a-133">이 기본 동작은 다음 두 가지 방법으로 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="faf4a-133">You can alter this default behavior in two other ways:</span></span>  
  
1. <span data-ttu-id="faf4a-134">스레드별로 관리 되는 코드에서 입니다.</span><span class="sxs-lookup"><span data-stu-id="faf4a-134">In managed code on a per-thread basis.</span></span>  
  
     <span data-ttu-id="faf4a-135"><xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>을 <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType>사용하여 <xref:System.Threading.ExecutionContext> 및 <xref:System.Security.SecurityContext> 설정을 수정하여 스레드별로 흐름을 억제할 수 있습니다. <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="faf4a-135">You can suppress the flow on a per-thread basis by modifying the <xref:System.Threading.ExecutionContext> and <xref:System.Security.SecurityContext> settings by using the <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>, <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType>, or <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> method.</span></span>  
  
2. <span data-ttu-id="faf4a-136">관리되지 않는 호스팅 인터페이스에 대한 호출에서 공통 언어 런타임(CLR)을 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="faf4a-136">In the call to the unmanaged hosting interface to load the common language runtime (CLR).</span></span>  
  
     <span data-ttu-id="faf4a-137">CLR을 로드하는 데 관리되지 않는 호스팅 인터페이스(간단한 관리 실행 가능) 대신사용하는 경우 [CorBindToRuntimeEx 함수](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) 호출에서 특수 플래그를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="faf4a-137">If an unmanaged hosting interface (instead of a simple managed executable) is used to load the CLR, you can specify a special flag in the call to the [CorBindToRuntimeEx Function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) function.</span></span> <span data-ttu-id="faf4a-138">전체 프로세스에 대한 호환성 모드를 사용하려면 `flags` [CorBindToRuntimeEx 함수에](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) 대한 매개 변수를 로 `STARTUP_ALWAYSFLOW_IMPERSONATION`설정합니다.</span><span class="sxs-lookup"><span data-stu-id="faf4a-138">To enable the compatibility mode for the entire process, set the `flags` parameter for [CorBindToRuntimeEx Function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) to `STARTUP_ALWAYSFLOW_IMPERSONATION`.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="faf4a-139">구성 파일</span><span class="sxs-lookup"><span data-stu-id="faf4a-139">Configuration File</span></span>  
 <span data-ttu-id="faf4a-140">.NET Framework 응용 프로그램에서이 요소는 응용 프로그램 구성 파일에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="faf4a-140">In a .NET Framework application, this element can be used only in the application configuration file.</span></span>  
  
 <span data-ttu-id="faf4a-141">ASP.NET 응용 프로그램의 경우 \<가장 흐름은 Windows 폴더>\Microsoft.NET\Framework\vx.xxxx 디렉터리에서 발견된 aspnet.config 파일에서 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="faf4a-141">For an ASP.NET application, the impersonation flow can be configured in the aspnet.config file found in the \<Windows Folder>\Microsoft.NET\Framework\vx.x.xxxx directory.</span></span>  
  
 <span data-ttu-id="faf4a-142">ASP.NET 기본적으로 다음 구성 설정을 사용하여 aspnet.config 파일에서 가장 흐름을 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="faf4a-142">ASP.NET by default disables the impersonation flow in the aspnet.config file by using the following configuration settings:</span></span>  
  
```xml
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
      <alwaysFlowImpersonationPolicy enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="faf4a-143">ASP.NET 대신 가장 흐름을 허용하려면 다음 구성 설정을 명시적으로 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="faf4a-143">In ASP.NET, if you want to allow the flow of impersonation instead, you must explicitly use the following configuration settings:</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="false"/>  
      <alwaysFlowImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="example"></a><span data-ttu-id="faf4a-144">예제</span><span class="sxs-lookup"><span data-stu-id="faf4a-144">Example</span></span>  
 <span data-ttu-id="faf4a-145">다음 예제에서는 관리되는 메서드 이외의 수단을 통해 가장이 달성되는 경우에도 Windows ID가 비동기 지점을 가로질러 흐르도록 지정하는 방법을 보여 주며, 이 중 에서다.</span><span class="sxs-lookup"><span data-stu-id="faf4a-145">The following example shows how to specify that the Windows identity flows across asynchronous points, even when the impersonation is achieved through means other than managed methods.</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <alwaysFlowImpersonationPolicy enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="faf4a-146">참고 항목</span><span class="sxs-lookup"><span data-stu-id="faf4a-146">See also</span></span>

- [<span data-ttu-id="faf4a-147">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="faf4a-147">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="faf4a-148">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="faf4a-148">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="faf4a-149">\<레거시 사칭정책> 요소</span><span class="sxs-lookup"><span data-stu-id="faf4a-149">\<legacyImpersonationPolicy> Element</span></span>](legacyimpersonationpolicy-element.md)
