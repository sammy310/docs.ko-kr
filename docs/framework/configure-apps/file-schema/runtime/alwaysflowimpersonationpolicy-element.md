---
description: '다음에 대 한 자세한 정보: <alwaysFlowImpersonationPolicy> 요소'
title: <alwaysFlowImpersonationPolicy> 요소
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/alwaysFlowImpersonationPolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#alwaysFlowImpersonationPolicy
helpviewer_keywords:
- alwaysFlowImpersonationPolicy element
- <alwaysFlowImpersonationPolicy> element
ms.assetid: ee622801-9e46-470b-85ab-88c4b1dd2ee1
ms.openlocfilehash: 5ee8e763eddb810143522ce9e6df780ee77c26c3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99719372"
---
# <a name="alwaysflowimpersonationpolicy-element"></a><span data-ttu-id="ea065-103">\<alwaysFlowImpersonationPolicy> 요소</span><span class="sxs-lookup"><span data-stu-id="ea065-103">\<alwaysFlowImpersonationPolicy> Element</span></span>

<span data-ttu-id="ea065-104">가장을 수행하는 방법과 관계없이 Windows ID가 항상 비동기 지점 간을 흐르도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ea065-104">Specifies that the Windows identity always flows across asynchronous points, regardless of how impersonation was performed.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<alwaysFlowImpersonationPolicy>**\  
  
## <a name="syntax"></a><span data-ttu-id="ea065-105">구문</span><span class="sxs-lookup"><span data-stu-id="ea065-105">Syntax</span></span>  
  
```xml  
<alwaysFlowImpersonationPolicy
  enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ea065-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="ea065-106">Attributes and Elements</span></span>  

 <span data-ttu-id="ea065-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ea065-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ea065-108">특성</span><span class="sxs-lookup"><span data-stu-id="ea065-108">Attributes</span></span>  
  
|<span data-ttu-id="ea065-109">attribute</span><span class="sxs-lookup"><span data-stu-id="ea065-109">Attribute</span></span>|<span data-ttu-id="ea065-110">설명</span><span class="sxs-lookup"><span data-stu-id="ea065-110">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="ea065-111">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="ea065-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="ea065-112">Windows id가 비동기 요소를 통과 하는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ea065-112">Indicates whether the Windows identity flows across asynchronous points.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="ea065-113">enabled 특성</span><span class="sxs-lookup"><span data-stu-id="ea065-113">enabled Attribute</span></span>  
  
|<span data-ttu-id="ea065-114">값</span><span class="sxs-lookup"><span data-stu-id="ea065-114">Value</span></span>|<span data-ttu-id="ea065-115">설명</span><span class="sxs-lookup"><span data-stu-id="ea065-115">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="ea065-116">와 같은 관리 되는 메서드를 통해 가장을 수행 하지 않는 한, Windows id는 비동기 요소를 통해 전달 되지 않습니다 <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A> .</span><span class="sxs-lookup"><span data-stu-id="ea065-116">The Windows identity does not flow across asynchronous points, unless the impersonation is performed through managed methods such as <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A>.</span></span> <span data-ttu-id="ea065-117">기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="ea065-117">This is the default.</span></span>|  
|`true`|<span data-ttu-id="ea065-118">Windows id는 가장이 수행 된 방법에 관계 없이 항상 비동기 요소를 통해 흐릅니다.</span><span class="sxs-lookup"><span data-stu-id="ea065-118">The Windows identity always flows across asynchronous points, regardless of how impersonation was performed.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ea065-119">자식 요소</span><span class="sxs-lookup"><span data-stu-id="ea065-119">Child Elements</span></span>  

 <span data-ttu-id="ea065-120">없음</span><span class="sxs-lookup"><span data-stu-id="ea065-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ea065-121">부모 요소</span><span class="sxs-lookup"><span data-stu-id="ea065-121">Parent Elements</span></span>  
  
|<span data-ttu-id="ea065-122">요소</span><span class="sxs-lookup"><span data-stu-id="ea065-122">Element</span></span>|<span data-ttu-id="ea065-123">설명</span><span class="sxs-lookup"><span data-stu-id="ea065-123">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="ea065-124">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="ea065-124">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="ea065-125">어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="ea065-125">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ea065-126">설명</span><span class="sxs-lookup"><span data-stu-id="ea065-126">Remarks</span></span>  

 <span data-ttu-id="ea065-127">.NET Framework 버전 1.0 및 1.1에서는 Windows id가 비동기 시점 간에 이동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ea065-127">In the .NET Framework versions 1.0 and 1.1, the Windows identity does not flow across asynchronous points.</span></span> <span data-ttu-id="ea065-128">.NET Framework 버전 2.0에는 <xref:System.Threading.ExecutionContext> 현재 실행 중인 스레드에 대 한 정보를 포함 하는 개체가 있으며,이 개체는 응용 프로그램 도메인 내의 비동기 요소를 통해 흐릅니다.</span><span class="sxs-lookup"><span data-stu-id="ea065-128">In the .NET Framework version 2.0, there is an <xref:System.Threading.ExecutionContext> object that contains information about the currently executing thread, and flows it across asynchronous points within an application domain.</span></span> <span data-ttu-id="ea065-129">는 <xref:System.Security.Principal.WindowsIdentity> 비동기 요소를 통해 전달 되는 정보의 일부로도 전달 됩니다 .이 경우에는 및와 같은 관리 되는 메서드를 사용 하 여, <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A> 네이티브 메서드에 대 한 플랫폼 호출과 같은 다른 방법을 사용 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ea065-129">The <xref:System.Security.Principal.WindowsIdentity> also flows as part of the information that flows across the asynchronous points, provided the impersonation was achieved using managed methods such as <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A> and not through other means such as platform invoke to native methods.</span></span> <span data-ttu-id="ea065-130">이 요소는 가장이 달성 된 방법에 관계 없이 Windows id가 비동기 시점 간에 이동 하도록 지정 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea065-130">This element is used to specify that the Windows identity does flow across asynchronous points, regardless of how the impersonation was achieved.</span></span>  
  
 <span data-ttu-id="ea065-131">다른 두 가지 방법으로이 기본 동작을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea065-131">You can alter this default behavior in two other ways:</span></span>  
  
1. <span data-ttu-id="ea065-132">스레드 단위로 관리 코드에서</span><span class="sxs-lookup"><span data-stu-id="ea065-132">In managed code on a per-thread basis.</span></span>  
  
     <span data-ttu-id="ea065-133"><xref:System.Threading.ExecutionContext> <xref:System.Security.SecurityContext> <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType> , 또는 메서드를 사용 하 여 및 설정을 수정 하 여 스레드 단위로 흐름을 억제할 수 있습니다 <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType> <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="ea065-133">You can suppress the flow on a per-thread basis by modifying the <xref:System.Threading.ExecutionContext> and <xref:System.Security.SecurityContext> settings by using the <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>, <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType>, or <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> method.</span></span>  
  
2. <span data-ttu-id="ea065-134">관리 되지 않는 호스팅 인터페이스를 호출 하 여 CLR (공용 언어 런타임)을 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea065-134">In the call to the unmanaged hosting interface to load the common language runtime (CLR).</span></span>  
  
     <span data-ttu-id="ea065-135">단순한 관리 되는 실행 파일 대신 관리 되지 않는 호스팅 인터페이스를 사용 하 여 CLR을 로드 하는 경우 [CorBindToRuntimeEx 함수](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) 함수 호출에서 특수 플래그를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea065-135">If an unmanaged hosting interface (instead of a simple managed executable) is used to load the CLR, you can specify a special flag in the call to the [CorBindToRuntimeEx Function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) function.</span></span> <span data-ttu-id="ea065-136">전체 프로세스에 대 한 호환성 모드를 사용 하도록 설정 하려면 `flags` [CorBindToRuntimeEx 함수](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) 에 대 한 매개 변수를로 설정 `STARTUP_ALWAYSFLOW_IMPERSONATION` 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea065-136">To enable the compatibility mode for the entire process, set the `flags` parameter for [CorBindToRuntimeEx Function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) to `STARTUP_ALWAYSFLOW_IMPERSONATION`.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="ea065-137">구성 파일</span><span class="sxs-lookup"><span data-stu-id="ea065-137">Configuration File</span></span>  

 <span data-ttu-id="ea065-138">.NET Framework 응용 프로그램에서이 요소는 응용 프로그램 구성 파일에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea065-138">In a .NET Framework application, this element can be used only in the application configuration file.</span></span>  
  
 <span data-ttu-id="ea065-139">ASP.NET 응용 프로그램의 경우 \Microsoft.NET\Framework\vx.x.xxxx 디렉터리에 있는 aspnet.config 파일에서 가장 흐름을 구성할 수 있습니다 \<Windows Folder> .</span><span class="sxs-lookup"><span data-stu-id="ea065-139">For an ASP.NET application, the impersonation flow can be configured in the aspnet.config file found in the \<Windows Folder>\Microsoft.NET\Framework\vx.x.xxxx directory.</span></span>  
  
 <span data-ttu-id="ea065-140">ASP.NET는 기본적으로 다음 구성 설정을 사용 하 여 aspnet.config 파일에서 가장 흐름을 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea065-140">ASP.NET by default disables the impersonation flow in the aspnet.config file by using the following configuration settings:</span></span>  
  
```xml
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
      <alwaysFlowImpersonationPolicy enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="ea065-141">ASP.NET에서 대신 가장의 흐름을 허용 하려면 다음 구성 설정을 명시적으로 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea065-141">In ASP.NET, if you want to allow the flow of impersonation instead, you must explicitly use the following configuration settings:</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="false"/>  
      <alwaysFlowImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="example"></a><span data-ttu-id="ea065-142">예제</span><span class="sxs-lookup"><span data-stu-id="ea065-142">Example</span></span>  

 <span data-ttu-id="ea065-143">다음 예제에서는 관리 되는 메서드가 아닌를 통해 가장을 사용 하는 경우에도 Windows id가 비동기 시점에서 흐르도록 지정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ea065-143">The following example shows how to specify that the Windows identity flows across asynchronous points, even when the impersonation is achieved through means other than managed methods.</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <alwaysFlowImpersonationPolicy enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ea065-144">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ea065-144">See also</span></span>

- [<span data-ttu-id="ea065-145">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="ea065-145">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="ea065-146">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="ea065-146">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="ea065-147">\<legacyImpersonationPolicy> 요소</span><span class="sxs-lookup"><span data-stu-id="ea065-147">\<legacyImpersonationPolicy> Element</span></span>](legacyimpersonationpolicy-element.md)
