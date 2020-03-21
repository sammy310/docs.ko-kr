---
title: <relativeBindForResources> 요소
ms.date: 03/30/2017
helpviewer_keywords:
- RelativeBindForResources element
- <relativeBindForResources> element
ms.assetid: 846ffa47-7257-4ce3-8cac-7ff627e0e34f
ms.openlocfilehash: cd49d424019a4e8422fee0ae16217d49cfc456b1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153908"
---
# <a name="relativebindforresources-element"></a><span data-ttu-id="22ab4-102">\<상대빈빈드포리소스> 요소</span><span class="sxs-lookup"><span data-stu-id="22ab4-102">\<relativeBindForResources> Element</span></span>
<span data-ttu-id="22ab4-103">위성 어셈블리에 대한 프로브를 최적화합니다.</span><span class="sxs-lookup"><span data-stu-id="22ab4-103">Optimizes the probe for satellite assemblies.</span></span>  
  
<span data-ttu-id="22ab4-104">[**\<구성>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="22ab4-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="22ab4-105">&nbsp;&nbsp;[**\<런타임>**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="22ab4-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="22ab4-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<상대빈빈드포리소>**</span><span class="sxs-lookup"><span data-stu-id="22ab4-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<relativeBindForResources>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22ab4-107">구문</span><span class="sxs-lookup"><span data-stu-id="22ab4-107">Syntax</span></span>  
  
```xml
<relativeBindForResources
   enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="22ab4-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="22ab4-108">Attributes and Elements</span></span>  
 <span data-ttu-id="22ab4-109">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="22ab4-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="22ab4-110">특성</span><span class="sxs-lookup"><span data-stu-id="22ab4-110">Attributes</span></span>  
  
|<span data-ttu-id="22ab4-111">attribute</span><span class="sxs-lookup"><span data-stu-id="22ab4-111">Attribute</span></span>|<span data-ttu-id="22ab4-112">Description</span><span class="sxs-lookup"><span data-stu-id="22ab4-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="22ab4-113">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="22ab4-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="22ab4-114">공통 언어 런타임이 위성 어셈블리에 대한 프로브를 최적화하는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="22ab4-114">Specifies whether the common language runtime optimizes the probe for satellite assemblies.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="22ab4-115">enabled 특성</span><span class="sxs-lookup"><span data-stu-id="22ab4-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="22ab4-116">값</span><span class="sxs-lookup"><span data-stu-id="22ab4-116">Value</span></span>|<span data-ttu-id="22ab4-117">Description</span><span class="sxs-lookup"><span data-stu-id="22ab4-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="22ab4-118">런타임은 위성 어셈블리에 대한 프로브를 최적화하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="22ab4-118">The runtime does not optimize the probe for satellite assemblies.</span></span> <span data-ttu-id="22ab4-119">이것은 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="22ab4-119">This is the default value.</span></span>|  
|`true`|<span data-ttu-id="22ab4-120">런타임은 위성 어셈블리에 대한 프로브를 최적화합니다.</span><span class="sxs-lookup"><span data-stu-id="22ab4-120">The runtime optimizes the probe for satellite assemblies.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="22ab4-121">자식 요소</span><span class="sxs-lookup"><span data-stu-id="22ab4-121">Child Elements</span></span>  
 <span data-ttu-id="22ab4-122">없음</span><span class="sxs-lookup"><span data-stu-id="22ab4-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="22ab4-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="22ab4-123">Parent Elements</span></span>  
  
|<span data-ttu-id="22ab4-124">요소</span><span class="sxs-lookup"><span data-stu-id="22ab4-124">Element</span></span>|<span data-ttu-id="22ab4-125">Description</span><span class="sxs-lookup"><span data-stu-id="22ab4-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="22ab4-126">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="22ab4-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="22ab4-127">런타임 초기화 옵션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="22ab4-127">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="22ab4-128">설명</span><span class="sxs-lookup"><span data-stu-id="22ab4-128">Remarks</span></span>  
 <span data-ttu-id="22ab4-129">일반적으로 리소스 관리자는 리소스 패키징 및 배포 항목에 설명된 대로 [리소스를 조사합니다.](../../../resources/packaging-and-deploying-resources-in-desktop-apps.md)</span><span class="sxs-lookup"><span data-stu-id="22ab4-129">In general, Resource Manager probes for resources, as documented in the [Packaging and Deploying Resources](../../../resources/packaging-and-deploying-resources-in-desktop-apps.md) topic.</span></span> <span data-ttu-id="22ab4-130">즉, Resource Manager가 특정 지역화된 버전의 리소스를 검색할 때 전역 어셈블리 캐시에서 보고, 응용 프로그램의 코드 베이스에서 문화권 별 폴더를 보고, 위성 어셈블리에 대한 Windows Installer를 <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> 쿼리하고, 이벤트를 발생시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22ab4-130">This means that when Resource Manager probes for a particular localized version of a resource, it may look in the global assembly cache, look in a culture-specific folder in the application's code base, query Windows Installer for satellite assemblies, and raise the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event.</span></span> <span data-ttu-id="22ab4-131">이 `<relativeBindForResources>` 요소는 리소스 관리자가 위성 어셈블리를 조사하는 방식을 최적화합니다.</span><span class="sxs-lookup"><span data-stu-id="22ab4-131">The `<relativeBindForResources>` element optimizes the way in which Resource Manager probes for satellite assemblies.</span></span> <span data-ttu-id="22ab4-132">다음 조건에서 리소스를 검색할 때 성능을 향상시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22ab4-132">It can improve performance when probing for resources under the following conditions:</span></span>  
  
- <span data-ttu-id="22ab4-133">위성 어셈블리가 코드 어셈블리와 동일한 위치에 배포되는 경우</span><span class="sxs-lookup"><span data-stu-id="22ab4-133">When the satellite assembly is deployed in the same location as the code assembly.</span></span> <span data-ttu-id="22ab4-134">즉, 코드 어셈블리가 전역 어셈블리 캐시에 설치된 경우 위성 어셈블리도 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="22ab4-134">In other words, if the code assembly is installed in the global assembly cache, the satellite assemblies must also be installed there.</span></span> <span data-ttu-id="22ab4-135">코드 어셈블리가 응용 프로그램의 코드 베이스에 설치된 경우 위성 어셈블리도 코드 베이스의 문화권 특정 폴더에 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="22ab4-135">If the code assembly is installed in the application's code base, the satellite assemblies must also be installed in a culture-specific folder in the code base.</span></span>  
  
- <span data-ttu-id="22ab4-136">Windows 설치 프로그램이 사용되지 않거나 위성 어셈블리의 온디맨드 설치에 거의 사용되지 않는 경우</span><span class="sxs-lookup"><span data-stu-id="22ab4-136">When Windows Installer is not used or is used only rarely for on-demand installation of satellite assemblies.</span></span>  
  
- <span data-ttu-id="22ab4-137">응용 프로그램 코드가 <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> 이벤트를 처리하지 않는 경우.</span><span class="sxs-lookup"><span data-stu-id="22ab4-137">When application code does not handle the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event.</span></span>  
  
 <span data-ttu-id="22ab4-138">요소의 `enabled` 특성을 설정하여 `true` 위성 어셈블리에 대한 리소스 관리자의 프로브를 다음과 같이 최적화합니다. `<relativeBindForResources>`</span><span class="sxs-lookup"><span data-stu-id="22ab4-138">Setting the `enabled` attribute of the `<relativeBindForResources>` element to `true` optimizes Resource Manager's probe for satellite assemblies as follows:</span></span>  
  
- <span data-ttu-id="22ab4-139">상위 코드 어셈블리의 위치를 사용하여 위성 어셈블리를 프로브합니다.</span><span class="sxs-lookup"><span data-stu-id="22ab4-139">It uses the location of the parent code assembly to probe for the satellite assembly.</span></span>  
  
- <span data-ttu-id="22ab4-140">위성 어셈블리에 대 한 Windows 설치 관리자를 쿼리 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="22ab4-140">It does not query Windows Installer for satellite assemblies.</span></span>  
  
- <span data-ttu-id="22ab4-141"><xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> 이벤트를 발생시키지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="22ab4-141">It does not raise the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22ab4-142">참고 항목</span><span class="sxs-lookup"><span data-stu-id="22ab4-142">See also</span></span>

- [<span data-ttu-id="22ab4-143">Packaging and Deploying Resources</span><span class="sxs-lookup"><span data-stu-id="22ab4-143">Packaging and Deploying Resources</span></span>](../../../resources/packaging-and-deploying-resources-in-desktop-apps.md)
- [<span data-ttu-id="22ab4-144">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="22ab4-144">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="22ab4-145">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="22ab4-145">Configuration File Schema</span></span>](../index.md)
