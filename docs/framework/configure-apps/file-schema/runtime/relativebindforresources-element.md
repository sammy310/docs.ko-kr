---
description: '다음에 대 한 자세한 정보: <relativeBindForResources> 요소'
title: <relativeBindForResources> 요소
ms.date: 03/30/2017
helpviewer_keywords:
- RelativeBindForResources element
- <relativeBindForResources> element
ms.assetid: 846ffa47-7257-4ce3-8cac-7ff627e0e34f
ms.openlocfilehash: f08d8f8a8fc4bb14d28762254dca99788d44a858
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99712924"
---
# <a name="relativebindforresources-element"></a><span data-ttu-id="69678-103">\<relativeBindForResources> 요소</span><span class="sxs-lookup"><span data-stu-id="69678-103">\<relativeBindForResources> Element</span></span>

<span data-ttu-id="69678-104">위성 어셈블리에 대한 프로브를 최적화합니다.</span><span class="sxs-lookup"><span data-stu-id="69678-104">Optimizes the probe for satellite assemblies.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<relativeBindForResources>**  
  
## <a name="syntax"></a><span data-ttu-id="69678-105">구문</span><span class="sxs-lookup"><span data-stu-id="69678-105">Syntax</span></span>  
  
```xml
<relativeBindForResources
   enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="69678-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="69678-106">Attributes and Elements</span></span>  

 <span data-ttu-id="69678-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="69678-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="69678-108">특성</span><span class="sxs-lookup"><span data-stu-id="69678-108">Attributes</span></span>  
  
|<span data-ttu-id="69678-109">attribute</span><span class="sxs-lookup"><span data-stu-id="69678-109">Attribute</span></span>|<span data-ttu-id="69678-110">설명</span><span class="sxs-lookup"><span data-stu-id="69678-110">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="69678-111">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="69678-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="69678-112">공용 언어 런타임에서 위성 어셈블리에 대 한 프로브를 최적화할지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="69678-112">Specifies whether the common language runtime optimizes the probe for satellite assemblies.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="69678-113">enabled 특성</span><span class="sxs-lookup"><span data-stu-id="69678-113">enabled Attribute</span></span>  
  
|<span data-ttu-id="69678-114">값</span><span class="sxs-lookup"><span data-stu-id="69678-114">Value</span></span>|<span data-ttu-id="69678-115">설명</span><span class="sxs-lookup"><span data-stu-id="69678-115">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="69678-116">런타임은 위성 어셈블리에 대 한 프로브를 최적화 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="69678-116">The runtime does not optimize the probe for satellite assemblies.</span></span> <span data-ttu-id="69678-117">기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="69678-117">This is the default value.</span></span>|  
|`true`|<span data-ttu-id="69678-118">런타임은 위성 어셈블리에 대 한 프로브를 최적화 합니다.</span><span class="sxs-lookup"><span data-stu-id="69678-118">The runtime optimizes the probe for satellite assemblies.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="69678-119">자식 요소</span><span class="sxs-lookup"><span data-stu-id="69678-119">Child Elements</span></span>  

 <span data-ttu-id="69678-120">없음</span><span class="sxs-lookup"><span data-stu-id="69678-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="69678-121">부모 요소</span><span class="sxs-lookup"><span data-stu-id="69678-121">Parent Elements</span></span>  
  
|<span data-ttu-id="69678-122">요소</span><span class="sxs-lookup"><span data-stu-id="69678-122">Element</span></span>|<span data-ttu-id="69678-123">설명</span><span class="sxs-lookup"><span data-stu-id="69678-123">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="69678-124">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="69678-124">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="69678-125">런타임 초기화 옵션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="69678-125">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="69678-126">설명</span><span class="sxs-lookup"><span data-stu-id="69678-126">Remarks</span></span>  

 <span data-ttu-id="69678-127">일반적으로 [리소스 패키징 및 배포](../../../resources/packaging-and-deploying-resources-in-desktop-apps.md) 항목에 설명 된 대로 리소스에 대 한 프로브를 리소스 관리자 합니다.</span><span class="sxs-lookup"><span data-stu-id="69678-127">In general, Resource Manager probes for resources, as documented in the [Packaging and Deploying Resources](../../../resources/packaging-and-deploying-resources-in-desktop-apps.md) topic.</span></span> <span data-ttu-id="69678-128">즉, 지역화 된 특정 버전의 리소스를 리소스 관리자 검색할 때 전역 어셈블리 캐시에서 응용 프로그램의 코드 베이스에 있는 문화권별 폴더를 찾고 위성 어셈블리에 대 한 Windows Installer을 쿼리 한 다음 이벤트를 발생 시킬 수 있습니다 <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="69678-128">This means that when Resource Manager probes for a particular localized version of a resource, it may look in the global assembly cache, look in a culture-specific folder in the application's code base, query Windows Installer for satellite assemblies, and raise the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event.</span></span> <span data-ttu-id="69678-129">`<relativeBindForResources>`요소는 위성 어셈블리를 리소스 관리자 프로브 하는 방법을 최적화 합니다.</span><span class="sxs-lookup"><span data-stu-id="69678-129">The `<relativeBindForResources>` element optimizes the way in which Resource Manager probes for satellite assemblies.</span></span> <span data-ttu-id="69678-130">다음 조건에서 리소스를 검색할 때 성능을 향상 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69678-130">It can improve performance when probing for resources under the following conditions:</span></span>  
  
- <span data-ttu-id="69678-131">위성 어셈블리가 코드 어셈블리와 동일한 위치에 배포 되는 경우</span><span class="sxs-lookup"><span data-stu-id="69678-131">When the satellite assembly is deployed in the same location as the code assembly.</span></span> <span data-ttu-id="69678-132">즉, 코드 어셈블리가 전역 어셈블리 캐시에 설치 된 경우 위성 어셈블리도 여기에 설치 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="69678-132">In other words, if the code assembly is installed in the global assembly cache, the satellite assemblies must also be installed there.</span></span> <span data-ttu-id="69678-133">코드 어셈블리가 응용 프로그램의 코드 베이스에 설치 된 경우에는 코드 베이스의 문화권별 폴더에도 위성 어셈블리를 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="69678-133">If the code assembly is installed in the application's code base, the satellite assemblies must also be installed in a culture-specific folder in the code base.</span></span>  
  
- <span data-ttu-id="69678-134">Windows Installer 사용 되지 않거나 위성 어셈블리의 요청 시 설치에 드물게 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="69678-134">When Windows Installer is not used or is used only rarely for on-demand installation of satellite assemblies.</span></span>  
  
- <span data-ttu-id="69678-135">응용 프로그램 코드가 이벤트를 처리 하지 않는 경우 <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="69678-135">When application code does not handle the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event.</span></span>  
  
 <span data-ttu-id="69678-136">요소의 특성을 설정 하 여 다음과 `enabled` `<relativeBindForResources>` `true` 같이 위성 어셈블리에 대 한 리소스 관리자 프로브를 최적화 합니다.</span><span class="sxs-lookup"><span data-stu-id="69678-136">Setting the `enabled` attribute of the `<relativeBindForResources>` element to `true` optimizes Resource Manager's probe for satellite assemblies as follows:</span></span>  
  
- <span data-ttu-id="69678-137">부모 코드 어셈블리의 위치를 사용 하 여 위성 어셈블리를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="69678-137">It uses the location of the parent code assembly to probe for the satellite assembly.</span></span>  
  
- <span data-ttu-id="69678-138">위성 어셈블리에 대 한 Windows Installer를 쿼리하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="69678-138">It does not query Windows Installer for satellite assemblies.</span></span>  
  
- <span data-ttu-id="69678-139">이벤트를 발생 시 키 지 않습니다 <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="69678-139">It does not raise the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69678-140">참조</span><span class="sxs-lookup"><span data-stu-id="69678-140">See also</span></span>

- [<span data-ttu-id="69678-141">리소스 패키징 및 배포</span><span class="sxs-lookup"><span data-stu-id="69678-141">Packaging and Deploying Resources</span></span>](../../../resources/packaging-and-deploying-resources-in-desktop-apps.md)
- [<span data-ttu-id="69678-142">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="69678-142">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="69678-143">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="69678-143">Configuration File Schema</span></span>](../index.md)
