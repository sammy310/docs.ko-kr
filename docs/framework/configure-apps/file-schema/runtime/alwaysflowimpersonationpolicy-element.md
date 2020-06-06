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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154485"
---
# <a name="alwaysflowimpersonationpolicy-element"></a><span data-ttu-id="c9216-102">\<alwaysFlowImpersonationPolicy> 요소</span><span class="sxs-lookup"><span data-stu-id="c9216-102">\<alwaysFlowImpersonationPolicy> Element</span></span>
<span data-ttu-id="c9216-103">가장을 수행하는 방법과 관계없이 Windows ID가 항상 비동기 지점 간을 흐르도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c9216-103">Specifies that the Windows identity always flows across asynchronous points, regardless of how impersonation was performed.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<alwaysFlowImpersonationPolicy>**\  
  
## <a name="syntax"></a><span data-ttu-id="c9216-104">구문</span><span class="sxs-lookup"><span data-stu-id="c9216-104">Syntax</span></span>  
  
```xml  
<alwaysFlowImpersonationPolicy
  enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c9216-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="c9216-105">Attributes and Elements</span></span>  
 <span data-ttu-id="c9216-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c9216-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c9216-107">특성</span><span class="sxs-lookup"><span data-stu-id="c9216-107">Attributes</span></span>  
  
|<span data-ttu-id="c9216-108">attribute</span><span class="sxs-lookup"><span data-stu-id="c9216-108">Attribute</span></span>|<span data-ttu-id="c9216-109">Description</span><span class="sxs-lookup"><span data-stu-id="c9216-109">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="c9216-110">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="c9216-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="c9216-111">Windows id가 비동기 요소를 통과 하는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c9216-111">Indicates whether the Windows identity flows across asynchronous points.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="c9216-112">enabled 특성</span><span class="sxs-lookup"><span data-stu-id="c9216-112">enabled Attribute</span></span>  
  
|<span data-ttu-id="c9216-113">값</span><span class="sxs-lookup"><span data-stu-id="c9216-113">Value</span></span>|<span data-ttu-id="c9216-114">Description</span><span class="sxs-lookup"><span data-stu-id="c9216-114">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="c9216-115">와 같은 관리 되는 메서드를 통해 가장을 수행 하지 않는 한, Windows id는 비동기 요소를 통해 전달 되지 않습니다 <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A> .</span><span class="sxs-lookup"><span data-stu-id="c9216-115">The Windows identity does not flow across asynchronous points, unless the impersonation is performed through managed methods such as <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A>.</span></span> <span data-ttu-id="c9216-116">기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="c9216-116">This is the default.</span></span>|  
|`true`|<span data-ttu-id="c9216-117">Windows id는 가장이 수행 된 방법에 관계 없이 항상 비동기 요소를 통해 흐릅니다.</span><span class="sxs-lookup"><span data-stu-id="c9216-117">The Windows identity always flows across asynchronous points, regardless of how impersonation was performed.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c9216-118">자식 요소</span><span class="sxs-lookup"><span data-stu-id="c9216-118">Child Elements</span></span>  
 <span data-ttu-id="c9216-119">없음</span><span class="sxs-lookup"><span data-stu-id="c9216-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c9216-120">부모 요소</span><span class="sxs-lookup"><span data-stu-id="c9216-120">Parent Elements</span></span>  
  
|<span data-ttu-id="c9216-121">요소</span><span class="sxs-lookup"><span data-stu-id="c9216-121">Element</span></span>|<span data-ttu-id="c9216-122">Description</span><span class="sxs-lookup"><span data-stu-id="c9216-122">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="c9216-123">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="c9216-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="c9216-124">어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="c9216-124">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c9216-125">설명</span><span class="sxs-lookup"><span data-stu-id="c9216-125">Remarks</span></span>  
 <span data-ttu-id="c9216-126">.NET Framework 버전 1.0 및 1.1에서는 Windows id가 비동기 시점 간에 이동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c9216-126">In the .NET Framework versions 1.0 and 1.1, the Windows identity does not flow across asynchronous points.</span></span> <span data-ttu-id="c9216-127">.NET Framework 버전 2.0에는 <xref:System.Threading.ExecutionContext> 현재 실행 중인 스레드에 대 한 정보를 포함 하는 개체가 있으며,이 개체는 응용 프로그램 도메인 내의 비동기 요소를 통해 흐릅니다.</span><span class="sxs-lookup"><span data-stu-id="c9216-127">In the .NET Framework version 2.0, there is an <xref:System.Threading.ExecutionContext> object that contains information about the currently executing thread, and flows it across asynchronous points within an application domain.</span></span> <span data-ttu-id="c9216-128">는 <xref:System.Security.Principal.WindowsIdentity> 비동기 요소를 통해 전달 되는 정보의 일부로도 전달 됩니다 .이 경우에는 및와 같은 관리 되는 메서드를 사용 하 여, <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A> 네이티브 메서드에 대 한 플랫폼 호출과 같은 다른 방법을 사용 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c9216-128">The <xref:System.Security.Principal.WindowsIdentity> also flows as part of the information that flows across the asynchronous points, provided the impersonation was achieved using managed methods such as <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A> and not through other means such as platform invoke to native methods.</span></span> <span data-ttu-id="c9216-129">이 요소는 가장이 달성 된 방법에 관계 없이 Windows id가 비동기 시점 간에 이동 하도록 지정 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9216-129">This element is used to specify that the Windows identity does flow across asynchronous points, regardless of how the impersonation was achieved.</span></span>  
  
 <span data-ttu-id="c9216-130">다른 두 가지 방법으로이 기본 동작을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9216-130">You can alter this default behavior in two other ways:</span></span>  
  
1. <span data-ttu-id="c9216-131">스레드 단위로 관리 코드에서</span><span class="sxs-lookup"><span data-stu-id="c9216-131">In managed code on a per-thread basis.</span></span>  
  
     <span data-ttu-id="c9216-132"><xref:System.Threading.ExecutionContext> <xref:System.Security.SecurityContext> <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType> , 또는 메서드를 사용 하 여 및 설정을 수정 하 여 스레드 단위로 흐름을 억제할 수 있습니다 <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType> <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="c9216-132">You can suppress the flow on a per-thread basis by modifying the <xref:System.Threading.ExecutionContext> and <xref:System.Security.SecurityContext> settings by using the <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>, <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType>, or <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> method.</span></span>  
  
2. <span data-ttu-id="c9216-133">관리 되지 않는 호스팅 인터페이스를 호출 하 여 CLR (공용 언어 런타임)을 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9216-133">In the call to the unmanaged hosting interface to load the common language runtime (CLR).</span></span>  
  
     <span data-ttu-id="c9216-134">단순한 관리 되는 실행 파일 대신 관리 되지 않는 호스팅 인터페이스를 사용 하 여 CLR을 로드 하는 경우 [CorBindToRuntimeEx 함수](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) 함수 호출에서 특수 플래그를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9216-134">If an unmanaged hosting interface (instead of a simple managed executable) is used to load the CLR, you can specify a special flag in the call to the [CorBindToRuntimeEx Function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) function.</span></span> <span data-ttu-id="c9216-135">전체 프로세스에 대 한 호환성 모드를 사용 하도록 설정 하려면 `flags` [CorBindToRuntimeEx 함수](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) 에 대 한 매개 변수를로 설정 `STARTUP_ALWAYSFLOW_IMPERSONATION` 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9216-135">To enable the compatibility mode for the entire process, set the `flags` parameter for [CorBindToRuntimeEx Function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) to `STARTUP_ALWAYSFLOW_IMPERSONATION`.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="c9216-136">구성 파일</span><span class="sxs-lookup"><span data-stu-id="c9216-136">Configuration File</span></span>  
 <span data-ttu-id="c9216-137">.NET Framework 응용 프로그램에서이 요소는 응용 프로그램 구성 파일에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9216-137">In a .NET Framework application, this element can be used only in the application configuration file.</span></span>  
  
 <span data-ttu-id="c9216-138">ASP.NET 응용 프로그램의 경우 \Microsoft.NET\Framework\vx.x.xxxx 디렉터리에 있는 aspnet .config 파일에서 가장 흐름을 구성할 수 있습니다 \<Windows Folder> .</span><span class="sxs-lookup"><span data-stu-id="c9216-138">For an ASP.NET application, the impersonation flow can be configured in the aspnet.config file found in the \<Windows Folder>\Microsoft.NET\Framework\vx.x.xxxx directory.</span></span>  
  
 <span data-ttu-id="c9216-139">ASP.NET는 기본적으로 다음 구성 설정을 사용 하 여 aspnet 파일에서 가장 흐름을 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9216-139">ASP.NET by default disables the impersonation flow in the aspnet.config file by using the following configuration settings:</span></span>  
  
```xml
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
      <alwaysFlowImpersonationPolicy enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="c9216-140">ASP.NET에서 대신 가장의 흐름을 허용 하려면 다음 구성 설정을 명시적으로 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9216-140">In ASP.NET, if you want to allow the flow of impersonation instead, you must explicitly use the following configuration settings:</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="false"/>  
      <alwaysFlowImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="example"></a><span data-ttu-id="c9216-141">예제</span><span class="sxs-lookup"><span data-stu-id="c9216-141">Example</span></span>  
 <span data-ttu-id="c9216-142">다음 예제에서는 관리 되는 메서드가 아닌를 통해 가장을 사용 하는 경우에도 Windows id가 비동기 시점에서 흐르도록 지정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c9216-142">The following example shows how to specify that the Windows identity flows across asynchronous points, even when the impersonation is achieved through means other than managed methods.</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <alwaysFlowImpersonationPolicy enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c9216-143">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c9216-143">See also</span></span>

- [<span data-ttu-id="c9216-144">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="c9216-144">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="c9216-145">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="c9216-145">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="c9216-146">\<legacyImpersonationPolicy>요소인</span><span class="sxs-lookup"><span data-stu-id="c9216-146">\<legacyImpersonationPolicy> Element</span></span>](legacyimpersonationpolicy-element.md)
