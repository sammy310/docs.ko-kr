---
title: <relativeBindForResources> 요소
ms.date: 03/30/2017
helpviewer_keywords:
- RelativeBindForResources element
- <relativeBindForResources> element
ms.assetid: 846ffa47-7257-4ce3-8cac-7ff627e0e34f
ms.openlocfilehash: 6a418fc546313b74bb965a0b223eca9c2e5acc08
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73115793"
---
# <a name="relativebindforresources-element"></a><span data-ttu-id="91606-102">\<런타임은 relativebindforresources> 요소가 > 요소</span><span class="sxs-lookup"><span data-stu-id="91606-102">\<relativeBindForResources> Element</span></span>
<span data-ttu-id="91606-103">위성 어셈블리에 대한 프로브를 최적화합니다.</span><span class="sxs-lookup"><span data-stu-id="91606-103">Optimizes the probe for satellite assemblies.</span></span>  
  
<span data-ttu-id="91606-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="91606-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="91606-105">&nbsp; &nbsp;[ **\<runtime >** ](runtime-element.md) </span><span class="sxs-lookup"><span data-stu-id="91606-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="91606-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<런타임은 relativebindforresources> 요소가 >**</span><span class="sxs-lookup"><span data-stu-id="91606-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<relativeBindForResources>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91606-107">구문</span><span class="sxs-lookup"><span data-stu-id="91606-107">Syntax</span></span>  
  
```xml
<relativeBindForResources    
   enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="91606-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="91606-108">Attributes and Elements</span></span>  
 <span data-ttu-id="91606-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="91606-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="91606-110">특성</span><span class="sxs-lookup"><span data-stu-id="91606-110">Attributes</span></span>  
  
|<span data-ttu-id="91606-111">특성</span><span class="sxs-lookup"><span data-stu-id="91606-111">Attribute</span></span>|<span data-ttu-id="91606-112">설명</span><span class="sxs-lookup"><span data-stu-id="91606-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="91606-113">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="91606-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="91606-114">공용 언어 런타임에서 위성 어셈블리에 대 한 프로브를 최적화할지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="91606-114">Specifies whether the common language runtime optimizes the probe for satellite assemblies.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="91606-115">enabled 특성</span><span class="sxs-lookup"><span data-stu-id="91606-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="91606-116">값</span><span class="sxs-lookup"><span data-stu-id="91606-116">Value</span></span>|<span data-ttu-id="91606-117">설명</span><span class="sxs-lookup"><span data-stu-id="91606-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="91606-118">런타임은 위성 어셈블리에 대 한 프로브를 최적화 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="91606-118">The runtime does not optimize the probe for satellite assemblies.</span></span> <span data-ttu-id="91606-119">이 설정은 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="91606-119">This is the default value.</span></span>|  
|`true`|<span data-ttu-id="91606-120">런타임은 위성 어셈블리에 대 한 프로브를 최적화 합니다.</span><span class="sxs-lookup"><span data-stu-id="91606-120">The runtime optimizes the probe for satellite assemblies.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="91606-121">자식 요소</span><span class="sxs-lookup"><span data-stu-id="91606-121">Child Elements</span></span>  
 <span data-ttu-id="91606-122">없음.</span><span class="sxs-lookup"><span data-stu-id="91606-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="91606-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="91606-123">Parent Elements</span></span>  
  
|<span data-ttu-id="91606-124">요소</span><span class="sxs-lookup"><span data-stu-id="91606-124">Element</span></span>|<span data-ttu-id="91606-125">설명</span><span class="sxs-lookup"><span data-stu-id="91606-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="91606-126">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="91606-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="91606-127">런타임 초기화 옵션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="91606-127">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="91606-128">주의</span><span class="sxs-lookup"><span data-stu-id="91606-128">Remarks</span></span>  
 <span data-ttu-id="91606-129">일반적으로 [리소스 패키징 및 배포](../../../resources/packaging-and-deploying-resources-in-desktop-apps.md) 항목에 설명 된 대로 리소스에 대 한 프로브를 리소스 관리자 합니다.</span><span class="sxs-lookup"><span data-stu-id="91606-129">In general, Resource Manager probes for resources, as documented in the [Packaging and Deploying Resources](../../../resources/packaging-and-deploying-resources-in-desktop-apps.md) topic.</span></span> <span data-ttu-id="91606-130">즉, 지역화 된 특정 버전의 리소스를 리소스 관리자 검색할 때 전역 어셈블리 캐시에서 응용 프로그램의 코드 베이스에 있는 문화권별 폴더를 찾고 위성 어셈블리에 대 한 Windows Installer을 쿼리 한 다음이를 발생 시킬 수 있습니다. 이벤트를 <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> 합니다.</span><span class="sxs-lookup"><span data-stu-id="91606-130">This means that when Resource Manager probes for a particular localized version of a resource, it may look in the global assembly cache, look in a culture-specific folder in the application's code base, query Windows Installer for satellite assemblies, and raise the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event.</span></span> <span data-ttu-id="91606-131">`<relativeBindForResources>` 요소는 위성 어셈블리를 리소스 관리자 프로브 하는 방법을 최적화 합니다.</span><span class="sxs-lookup"><span data-stu-id="91606-131">The `<relativeBindForResources>` element optimizes the way in which Resource Manager probes for satellite assemblies.</span></span> <span data-ttu-id="91606-132">다음 조건에서 리소스를 검색할 때 성능을 향상 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91606-132">It can improve performance when probing for resources under the following conditions:</span></span>  
  
- <span data-ttu-id="91606-133">위성 어셈블리가 코드 어셈블리와 동일한 위치에 배포 되는 경우</span><span class="sxs-lookup"><span data-stu-id="91606-133">When the satellite assembly is deployed in the same location as the code assembly.</span></span> <span data-ttu-id="91606-134">즉, 코드 어셈블리가 전역 어셈블리 캐시에 설치 된 경우 위성 어셈블리도 여기에 설치 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="91606-134">In other words, if the code assembly is installed in the global assembly cache, the satellite assemblies must also be installed there.</span></span> <span data-ttu-id="91606-135">코드 어셈블리가 응용 프로그램의 코드 베이스에 설치 된 경우에는 코드 베이스의 문화권별 폴더에도 위성 어셈블리를 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="91606-135">If the code assembly is installed in the application's code base, the satellite assemblies must also be installed in a culture-specific folder in the code base.</span></span>  
  
- <span data-ttu-id="91606-136">Windows Installer 사용 되지 않거나 위성 어셈블리의 요청 시 설치에 드물게 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="91606-136">When Windows Installer is not used or is used only rarely for on-demand installation of satellite assemblies.</span></span>  
  
- <span data-ttu-id="91606-137">응용 프로그램 코드가 <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> 이벤트를 처리 하지 않는 경우</span><span class="sxs-lookup"><span data-stu-id="91606-137">When application code does not handle the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event.</span></span>  
  
 <span data-ttu-id="91606-138">`<relativeBindForResources>` 요소의 `enabled` 특성을 `true`로 설정 하면 다음과 같이 위성 어셈블리에 대 한 리소스 관리자 프로브를 최적화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91606-138">Setting the `enabled` attribute of the `<relativeBindForResources>` element to `true` optimizes Resource Manager's probe for satellite assemblies as follows:</span></span>  
  
- <span data-ttu-id="91606-139">부모 코드 어셈블리의 위치를 사용 하 여 위성 어셈블리를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="91606-139">It uses the location of the parent code assembly to probe for the satellite assembly.</span></span>  
  
- <span data-ttu-id="91606-140">위성 어셈블리에 대 한 Windows Installer를 쿼리하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="91606-140">It does not query Windows Installer for satellite assemblies.</span></span>  
  
- <span data-ttu-id="91606-141"><xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> 이벤트를 발생 시 키 지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="91606-141">It does not raise the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91606-142">참조</span><span class="sxs-lookup"><span data-stu-id="91606-142">See also</span></span>

- [<span data-ttu-id="91606-143">리소스 패키징 및 배포</span><span class="sxs-lookup"><span data-stu-id="91606-143">Packaging and Deploying Resources</span></span>](../../../resources/packaging-and-deploying-resources-in-desktop-apps.md)
- [<span data-ttu-id="91606-144">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="91606-144">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="91606-145">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="91606-145">Configuration File Schema</span></span>](../index.md)
