---
title: <performanceCounter> 요소 (네트워크 설정)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/performanceCounters
- http://schemas.microsoft.com/.NetConfiguration/v2.0#performanceCounters
helpviewer_keywords:
- performanceCounter element
- <performanceCounter> element
ms.assetid: 3afa1586-e1b8-473d-8985-c3fc90cf561b
ms.openlocfilehash: 30c5cd07c92a8fc3c340cab0ff9ae74e940c0c12
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59210934"
---
# <a name="performancecounter-element-network-settings"></a><span data-ttu-id="a2190-102">\<performanceCounter > 요소 (네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="a2190-102">\<performanceCounter> Element (Network Settings)</span></span>
<span data-ttu-id="a2190-103">네트워킹 성능 카운터를 사용할지 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2190-103">Enables or disables networking performance counters.</span></span>  
  
 <span data-ttu-id="a2190-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="a2190-104">\<configuration></span></span>  
<span data-ttu-id="a2190-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="a2190-105">\<system.net></span></span>  
<span data-ttu-id="a2190-106">\<settings></span><span class="sxs-lookup"><span data-stu-id="a2190-106">\<settings></span></span>  
<span data-ttu-id="a2190-107">\<performanceCounters></span><span class="sxs-lookup"><span data-stu-id="a2190-107">\<performanceCounters></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2190-108">구문</span><span class="sxs-lookup"><span data-stu-id="a2190-108">Syntax</span></span>  
  
```xml  
<performanceCounters  
  enabled="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a2190-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="a2190-109">Attributes and Elements</span></span>  
 <span data-ttu-id="a2190-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a2190-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a2190-111">특성</span><span class="sxs-lookup"><span data-stu-id="a2190-111">Attributes</span></span>  
  
|<span data-ttu-id="a2190-112">특성</span><span class="sxs-lookup"><span data-stu-id="a2190-112">Attribute</span></span>|<span data-ttu-id="a2190-113">설명</span><span class="sxs-lookup"><span data-stu-id="a2190-113">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="a2190-114">네트워킹 성능 카운터 사용 되는지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2190-114">Specifies whether the networking performance counters are enabled.</span></span> <span data-ttu-id="a2190-115">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="a2190-115">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a2190-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="a2190-116">Child Elements</span></span>  
 <span data-ttu-id="a2190-117">없음</span><span class="sxs-lookup"><span data-stu-id="a2190-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a2190-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="a2190-118">Parent Elements</span></span>  
  
|<span data-ttu-id="a2190-119">요소</span><span class="sxs-lookup"><span data-stu-id="a2190-119">Element</span></span>|<span data-ttu-id="a2190-120">설명</span><span class="sxs-lookup"><span data-stu-id="a2190-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a2190-121">설정</span><span class="sxs-lookup"><span data-stu-id="a2190-121">settings</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|<span data-ttu-id="a2190-122"><xref:System.Net> 네임스페이스에 대한 기본 네트워크 옵션을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="a2190-122">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a2190-123">설명</span><span class="sxs-lookup"><span data-stu-id="a2190-123">Remarks</span></span>  
 <span data-ttu-id="a2190-124">이 요소는 응용 프로그램 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2190-124">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
 <span data-ttu-id="a2190-125">네트워킹 성능 카운터를 사용하려면 구성 파일에서 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2190-125">Networking performance counters need to be enabled in the configuration file to be used.</span></span> <span data-ttu-id="a2190-126">구성 파일의 단일 설정을 통해 모든 네트워킹 성능 카운터를 사용하거나 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="a2190-126">All networking performance counters are enabled or disabled with a single setting in the configuration file.</span></span> <span data-ttu-id="a2190-127">개별 네트워킹 성능 카운터를 사용하거나 사용하지 않도록 설정할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a2190-127">Individual networking performance counters cannot be enabled or disabled.</span></span> <span data-ttu-id="a2190-128">특정 네트워킹 성능 카운터에 대 한 자세한 내용은 참조 하세요. [네트워킹 성능 카운터](../../../../../docs/framework/debug-trace-profile/performance-counters.md#networking)합니다.</span><span class="sxs-lookup"><span data-stu-id="a2190-128">For more information on the specific networking performance counters, see [Networking Performance Counters](../../../../../docs/framework/debug-trace-profile/performance-counters.md#networking).</span></span>  
  
 <span data-ttu-id="a2190-129">기본값은 해당 네트워킹 성능 카운터가 비활성화 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a2190-129">The default value is that networking performance counters are disabled.</span></span>  
  
 <span data-ttu-id="a2190-130">합니다 <xref:System.Net.Configuration.PerformanceCountersElement.Enabled%2A?displayProperty=nameWithType> 속성의 현재 값을 가져오는 데 사용할 수는 **사용 하도록 설정** 해당 구성 파일에서 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="a2190-130">The <xref:System.Net.Configuration.PerformanceCountersElement.Enabled%2A?displayProperty=nameWithType> property can be used to get the current value of the **enabled** attribute from applicable configuration files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a2190-131">예제</span><span class="sxs-lookup"><span data-stu-id="a2190-131">Example</span></span>  
 <span data-ttu-id="a2190-132">다음 예제에서는 구성 하는 방법의 <xref:System.Net> 및 관련 네트워킹 성능 카운터를 사용 하도록 설정 하려면 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="a2190-132">The following example shows how to configure the <xref:System.Net> and related namespaces to enable networking performance counters.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <settings>  
      <performanceCounters  
        enabled="true"  
      />  
    </settings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a2190-133">참고자료</span><span class="sxs-lookup"><span data-stu-id="a2190-133">See also</span></span>

- <xref:System.Net.Configuration.PerformanceCountersElement?displayProperty=nameWithType>
- <xref:System.Net.Configuration.PerformanceCountersElement.Enabled%2A?displayProperty=nameWithType>
- [<span data-ttu-id="a2190-134">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="a2190-134">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
- [<span data-ttu-id="a2190-135">네트워킹 성능 카운터</span><span class="sxs-lookup"><span data-stu-id="a2190-135">Networking Performance Counters</span></span>](../../../../../docs/framework/debug-trace-profile/performance-counters.md#networking)
