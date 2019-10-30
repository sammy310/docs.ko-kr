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
ms.openlocfilehash: 06e91ea6989dcdf0b2a179e7d6ce79b8d9aaff03
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73118347"
---
# <a name="alwaysflowimpersonationpolicy-element"></a><span data-ttu-id="9fb73-102">\<alwaysFlowImpersonationPolicy > 요소</span><span class="sxs-lookup"><span data-stu-id="9fb73-102">\<alwaysFlowImpersonationPolicy> Element</span></span>
<span data-ttu-id="9fb73-103">가장을 수행하는 방법과 관계없이 Windows ID가 항상 비동기 지점 간을 흐르도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9fb73-103">Specifies that the Windows identity always flows across asynchronous points, regardless of how impersonation was performed.</span></span>  
  
<span data-ttu-id="9fb73-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="9fb73-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="9fb73-105">&nbsp; &nbsp;[ **\<runtime >** ](runtime-element.md) </span><span class="sxs-lookup"><span data-stu-id="9fb73-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="9fb73-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<alwaysFlowImpersonationPolicy >** </span><span class="sxs-lookup"><span data-stu-id="9fb73-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<alwaysFlowImpersonationPolicy>**</span></span>\  
  
## <a name="syntax"></a><span data-ttu-id="9fb73-107">구문</span><span class="sxs-lookup"><span data-stu-id="9fb73-107">Syntax</span></span>  
  
```xml  
<alwaysFlowImpersonationPolicy    
  enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9fb73-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="9fb73-108">Attributes and Elements</span></span>  
 <span data-ttu-id="9fb73-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9fb73-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9fb73-110">특성</span><span class="sxs-lookup"><span data-stu-id="9fb73-110">Attributes</span></span>  
  
|<span data-ttu-id="9fb73-111">특성</span><span class="sxs-lookup"><span data-stu-id="9fb73-111">Attribute</span></span>|<span data-ttu-id="9fb73-112">설명</span><span class="sxs-lookup"><span data-stu-id="9fb73-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="9fb73-113">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="9fb73-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="9fb73-114">Windows id가 비동기 요소를 통과 하는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9fb73-114">Indicates whether the Windows identity flows across asynchronous points.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="9fb73-115">enabled 특성</span><span class="sxs-lookup"><span data-stu-id="9fb73-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="9fb73-116">값</span><span class="sxs-lookup"><span data-stu-id="9fb73-116">Value</span></span>|<span data-ttu-id="9fb73-117">설명</span><span class="sxs-lookup"><span data-stu-id="9fb73-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="9fb73-118"><xref:System.Security.Principal.WindowsIdentity.Impersonate%2A>와 같은 관리 되는 메서드를 통해 가장이 수행 되지 않는 한 Windows id는 비동기 요소를 통해 전달 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9fb73-118">The Windows identity does not flow across asynchronous points, unless the impersonation is performed through managed methods such as <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A>.</span></span> <span data-ttu-id="9fb73-119">기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="9fb73-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="9fb73-120">Windows id는 가장이 수행 된 방법에 관계 없이 항상 비동기 요소를 통해 흐릅니다.</span><span class="sxs-lookup"><span data-stu-id="9fb73-120">The Windows identity always flows across asynchronous points, regardless of how impersonation was performed.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9fb73-121">자식 요소</span><span class="sxs-lookup"><span data-stu-id="9fb73-121">Child Elements</span></span>  
 <span data-ttu-id="9fb73-122">없음.</span><span class="sxs-lookup"><span data-stu-id="9fb73-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9fb73-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="9fb73-123">Parent Elements</span></span>  
  
|<span data-ttu-id="9fb73-124">요소</span><span class="sxs-lookup"><span data-stu-id="9fb73-124">Element</span></span>|<span data-ttu-id="9fb73-125">설명</span><span class="sxs-lookup"><span data-stu-id="9fb73-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="9fb73-126">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="9fb73-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="9fb73-127">어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="9fb73-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9fb73-128">주의</span><span class="sxs-lookup"><span data-stu-id="9fb73-128">Remarks</span></span>  
 <span data-ttu-id="9fb73-129">.NET Framework 버전 1.0 및 1.1에서는 Windows id가 비동기 시점 간에 이동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9fb73-129">In the .NET Framework versions 1.0 and 1.1, the Windows identity does not flow across asynchronous points.</span></span> <span data-ttu-id="9fb73-130">.NET Framework 버전 2.0에는 현재 실행 중인 스레드에 대 한 정보를 포함 하는 <xref:System.Threading.ExecutionContext> 개체가 있으며,이 개체는 응용 프로그램 도메인 내의 비동기 요소를 통해 흐릅니다.</span><span class="sxs-lookup"><span data-stu-id="9fb73-130">In the .NET Framework version 2.0, there is an <xref:System.Threading.ExecutionContext> object that contains information about the currently executing thread, and flows it across asynchronous points within an application domain.</span></span> <span data-ttu-id="9fb73-131"><xref:System.Security.Principal.WindowsIdentity>는 비동기 요소를 통해 전달 되는 정보의 일부로도 전달 됩니다. 가장을 사용 하는 경우에는 <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A>와 같은 관리 되는 메서드를 사용 하는 것이 아니라 네이티브 메서드에 대 한 플랫폼 호출과 같은 다른 방법이 아닌를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fb73-131">The <xref:System.Security.Principal.WindowsIdentity> also flows as part of the information that flows across the asynchronous points, provided the impersonation was achieved using managed methods such as <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A> and not through other means such as platform invoke to native methods.</span></span> <span data-ttu-id="9fb73-132">이 요소는 가장이 달성 된 방법에 관계 없이 Windows id가 비동기 시점 간에 이동 하도록 지정 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fb73-132">This element is used to specify that the Windows identity does flow across asynchronous points, regardless of how the impersonation was achieved.</span></span>  
  
 <span data-ttu-id="9fb73-133">다른 두 가지 방법으로이 기본 동작을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fb73-133">You can alter this default behavior in two other ways:</span></span>  
  
1. <span data-ttu-id="9fb73-134">스레드 단위로 관리 코드에서</span><span class="sxs-lookup"><span data-stu-id="9fb73-134">In managed code on a per-thread basis.</span></span>  
  
     <span data-ttu-id="9fb73-135"><xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>, <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType>또는 <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> 메서드를 사용 하 여 <xref:System.Threading.ExecutionContext>를 수정 하 고 설정을 <xref:System.Security.SecurityContext> 하 여 스레드 단위로 흐름을 억제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fb73-135">You can suppress the flow on a per-thread basis by modifying the <xref:System.Threading.ExecutionContext> and <xref:System.Security.SecurityContext> settings by using the <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>, <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType>, or <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> method.</span></span>  
  
2. <span data-ttu-id="9fb73-136">관리 되지 않는 호스팅 인터페이스를 호출 하 여 CLR (공용 언어 런타임)을 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fb73-136">In the call to the unmanaged hosting interface to load the common language runtime (CLR).</span></span>  
  
     <span data-ttu-id="9fb73-137">단순한 관리 되는 실행 파일 대신 관리 되지 않는 호스팅 인터페이스를 사용 하 여 CLR을 로드 하는 경우 [CorBindToRuntimeEx 함수](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) 함수 호출에서 특수 플래그를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fb73-137">If an unmanaged hosting interface (instead of a simple managed executable) is used to load the CLR, you can specify a special flag in the call to the [CorBindToRuntimeEx Function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) function.</span></span> <span data-ttu-id="9fb73-138">전체 프로세스에 대해 호환 모드를 사용 하도록 설정 하려면 [CorBindToRuntimeEx 함수의](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) `flags` 매개 변수를 `STARTUP_ALWAYSFLOW_IMPERSONATION`로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fb73-138">To enable the compatibility mode for the entire process, set the `flags` parameter for [CorBindToRuntimeEx Function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) to `STARTUP_ALWAYSFLOW_IMPERSONATION`.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="9fb73-139">구성 파일</span><span class="sxs-lookup"><span data-stu-id="9fb73-139">Configuration File</span></span>  
 <span data-ttu-id="9fb73-140">.NET Framework 응용 프로그램에서이 요소는 응용 프로그램 구성 파일에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fb73-140">In a .NET Framework application, this element can be used only in the application configuration file.</span></span>  
  
 <span data-ttu-id="9fb73-141">ASP.NET 응용 프로그램의 경우 \Microsoft.NET\Framework\vx.x.xxxx 디렉터리 > \<Windows 폴더에 있는 aspnet .config 파일에서 가장 흐름을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fb73-141">For an ASP.NET application, the impersonation flow can be configured in the aspnet.config file found in the \<Windows Folder>\Microsoft.NET\Framework\vx.x.xxxx directory.</span></span>  
  
 <span data-ttu-id="9fb73-142">ASP.NET는 기본적으로 다음 구성 설정을 사용 하 여 aspnet 파일에서 가장 흐름을 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fb73-142">ASP.NET by default disables the impersonation flow in the aspnet.config file by using the following configuration settings:</span></span>  
  
```xml
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
      <alwaysFlowImpersonationPolicy enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="9fb73-143">ASP.NET에서 대신 가장의 흐름을 허용 하려면 다음 구성 설정을 명시적으로 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fb73-143">In ASP.NET, if you want to allow the flow of impersonation instead, you must explicitly use the following configuration settings:</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="false"/>  
      <alwaysFlowImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="example"></a><span data-ttu-id="9fb73-144">예제</span><span class="sxs-lookup"><span data-stu-id="9fb73-144">Example</span></span>  
 <span data-ttu-id="9fb73-145">다음 예제에서는 관리 되는 메서드가 아닌를 통해 가장을 사용 하는 경우에도 Windows id가 비동기 시점에서 흐르도록 지정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9fb73-145">The following example shows how to specify that the Windows identity flows across asynchronous points, even when the impersonation is achieved through means other than managed methods.</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <alwaysFlowImpersonationPolicy enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="9fb73-146">참조</span><span class="sxs-lookup"><span data-stu-id="9fb73-146">See also</span></span>

- [<span data-ttu-id="9fb73-147">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="9fb73-147">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="9fb73-148">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="9fb73-148">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="9fb73-149">\<legacyImpersonationPolicy > 요소</span><span class="sxs-lookup"><span data-stu-id="9fb73-149">\<legacyImpersonationPolicy> Element</span></span>](legacyimpersonationpolicy-element.md)
