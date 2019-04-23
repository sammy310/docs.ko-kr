---
title: <gcServer> 요소
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/gcServer
- http://schemas.microsoft.com/.NetConfiguration/v2.0#gcServer
helpviewer_keywords:
- gcServer element
- <gcServer> element
ms.assetid: 8d25b80e-2581-4803-bd87-a59528e3cb03
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fd91cf0179ef9731c456b41fdc865e3eacdb33eb
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59132810"
---
# <a name="gcserver-element"></a><span data-ttu-id="282a9-102">\<gcServer > 요소</span><span class="sxs-lookup"><span data-stu-id="282a9-102">\<gcServer> Element</span></span>
<span data-ttu-id="282a9-103">공용 언어 런타임이 서버 가비지 컬렉션을 실행하는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="282a9-103">Specifies whether the common language runtime runs server garbage collection.</span></span>  
  
 <span data-ttu-id="282a9-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="282a9-104">\<configuration></span></span>  
<span data-ttu-id="282a9-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="282a9-105">\<runtime></span></span>  
<span data-ttu-id="282a9-106">\<gcServer></span><span class="sxs-lookup"><span data-stu-id="282a9-106">\<gcServer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="282a9-107">구문</span><span class="sxs-lookup"><span data-stu-id="282a9-107">Syntax</span></span>  
  
```xml  
<gcServer    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="282a9-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="282a9-108">Attributes and Elements</span></span>  
 <span data-ttu-id="282a9-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="282a9-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="282a9-110">특성</span><span class="sxs-lookup"><span data-stu-id="282a9-110">Attributes</span></span>  
  
|<span data-ttu-id="282a9-111">특성</span><span class="sxs-lookup"><span data-stu-id="282a9-111">Attribute</span></span>|<span data-ttu-id="282a9-112">설명</span><span class="sxs-lookup"><span data-stu-id="282a9-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="282a9-113">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="282a9-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="282a9-114">런타임이 서버 가비지 수집을 실행하는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="282a9-114">Specifies whether the runtime runs server garbage collection.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="282a9-115">enabled 특성</span><span class="sxs-lookup"><span data-stu-id="282a9-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="282a9-116">값</span><span class="sxs-lookup"><span data-stu-id="282a9-116">Value</span></span>|<span data-ttu-id="282a9-117">설명</span><span class="sxs-lookup"><span data-stu-id="282a9-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="282a9-118">서버 가비지 컬렉션을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="282a9-118">Does not run server garbage collection.</span></span> <span data-ttu-id="282a9-119">이 값이 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="282a9-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="282a9-120">서버 가비지 컬렉션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="282a9-120">Runs server garbage collection.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="282a9-121">자식 요소</span><span class="sxs-lookup"><span data-stu-id="282a9-121">Child Elements</span></span>  
 <span data-ttu-id="282a9-122">없음</span><span class="sxs-lookup"><span data-stu-id="282a9-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="282a9-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="282a9-123">Parent Elements</span></span>  
  
|<span data-ttu-id="282a9-124">요소</span><span class="sxs-lookup"><span data-stu-id="282a9-124">Element</span></span>|<span data-ttu-id="282a9-125">설명</span><span class="sxs-lookup"><span data-stu-id="282a9-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="282a9-126">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="282a9-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="282a9-127">어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="282a9-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="282a9-128">설명</span><span class="sxs-lookup"><span data-stu-id="282a9-128">Remarks</span></span>  
 <span data-ttu-id="282a9-129">CLR(공용 언어 런타임)에서는 두 가지 유형의 가비지 컬렉션을 지원합니다. 워크스테이션 가비지 컬렉션은 모든 시스템에서 사용할 수 있고, 서버 가비지 컬렉션은 다중 프로세서 시스템에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="282a9-129">The common language runtime (CLR) supports two types of garbage collection: workstation garbage collection, which is available on all systems, and server garbage collection, which is available on multiprocessor systems.</span></span> <span data-ttu-id="282a9-130">`<gcServer>` 요소를 사용하여 CLR에서 수행하는 가비지 수집 유형을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="282a9-130">You use the `<gcServer>` element to control the type of garbage collection the CLR performs.</span></span> <span data-ttu-id="282a9-131"><xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType> 속성을 사용하여 서버 가비지 수집이 사용하도록 설정되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="282a9-131">Use the <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType> property to determine if server garbage collection is enabled.</span></span>  
  
 <span data-ttu-id="282a9-132">단일 프로세서 컴퓨터의 경우 기본 워크스테이션 가비지 수집이 가장 빠른 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="282a9-132">For single-processor computers, the default workstation garbage collection should be the fastest option.</span></span> <span data-ttu-id="282a9-133">두 개의 프로세서가 있는 컴퓨터에는 워크스테이션 또는 서버를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="282a9-133">Either workstation or server can be used for two-processor computers.</span></span> <span data-ttu-id="282a9-134">세 개 이상 프로세서의 경우 서버 가비지 수집이 가장 빠른 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="282a9-134">Server garbage collection should be the fastest option for more than two processors.</span></span>  
  
 <span data-ttu-id="282a9-135">이 요소는 응용 프로그램 구성 파일에만 사용할 수 있습니다. 컴퓨터 구성 파일에 있는 경우 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="282a9-135">This element can be used only in the application configuration file; it is ignored if it is in the machine configuration file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="282a9-136">.NET Framework 4 및 이전 버전에서, 서버 가비지 수집이 사용되는 경우에는 동시 가비지 수집을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="282a9-136">In the .NET Framework 4 and earlier versions, concurrent garbage collection is not available when server garbage collection is enabled.</span></span> <span data-ttu-id="282a9-137">[!INCLUDE[net_v45](../../../../../includes/net-v45-md.md)]부터 서버 가비지 컬렉션이 동시에 이루어집니다.</span><span class="sxs-lookup"><span data-stu-id="282a9-137">Starting with the [!INCLUDE[net_v45](../../../../../includes/net-v45-md.md)], server garbage collection is concurrent.</span></span> <span data-ttu-id="282a9-138">비 동시 가비지 수집을 사용 하려면 설정 합니다 `<gcServer>` 요소를 `true` 하며 [ \<gcConcurrent > 요소](../../../../../docs/framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) 를 `false`.</span><span class="sxs-lookup"><span data-stu-id="282a9-138">To use non-concurrent server garbage collection, set the `<gcServer>` element to `true` and the [\<gcConcurrent> element](../../../../../docs/framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) to `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="282a9-139">예제</span><span class="sxs-lookup"><span data-stu-id="282a9-139">Example</span></span>  
 <span data-ttu-id="282a9-140">다음 예제에서는 서버 가비지 컬렉션을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="282a9-140">The following example enables server garbage collection.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <gcServer enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="282a9-141">참고자료</span><span class="sxs-lookup"><span data-stu-id="282a9-141">See also</span></span>

- <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType>
- [<span data-ttu-id="282a9-142">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="282a9-142">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="282a9-143">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="282a9-143">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="282a9-144">동시 가비지 수집을 사용 하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="282a9-144">To disable concurrent garbage collection</span></span>](gcconcurrent-element.md#to-disable-background-garbage-collection)
