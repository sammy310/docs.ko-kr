---
title: <performanceCounter> 요소(네트워크 설정)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/performanceCounters
- http://schemas.microsoft.com/.NetConfiguration/v2.0#performanceCounters
helpviewer_keywords:
- performanceCounter element
- <performanceCounter> element
ms.assetid: 3afa1586-e1b8-473d-8985-c3fc90cf561b
ms.openlocfilehash: 05aac6c1ed3c04bce263a45cafdb9bec906bd75b
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/21/2019
ms.locfileid: "69664055"
---
# <a name="performancecounter-element-network-settings"></a><span data-ttu-id="889a6-102">\<performanceCounter > 요소 (네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="889a6-102">\<performanceCounter> Element (Network Settings)</span></span>
<span data-ttu-id="889a6-103">네트워킹 성능 카운터를 사용 하거나 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="889a6-103">Enables or disables networking performance counters.</span></span>  
  
 <span data-ttu-id="889a6-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="889a6-104">\<configuration></span></span>  
<span data-ttu-id="889a6-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="889a6-105">\<system.net></span></span>  
<span data-ttu-id="889a6-106">\<settings></span><span class="sxs-lookup"><span data-stu-id="889a6-106">\<settings></span></span>  
<span data-ttu-id="889a6-107">\<performanceCounters></span><span class="sxs-lookup"><span data-stu-id="889a6-107">\<performanceCounters></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="889a6-108">구문</span><span class="sxs-lookup"><span data-stu-id="889a6-108">Syntax</span></span>  
  
```xml  
<performanceCounters  
  enabled="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="889a6-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="889a6-109">Attributes and Elements</span></span>  
 <span data-ttu-id="889a6-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="889a6-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="889a6-111">특성</span><span class="sxs-lookup"><span data-stu-id="889a6-111">Attributes</span></span>  
  
|<span data-ttu-id="889a6-112">특성</span><span class="sxs-lookup"><span data-stu-id="889a6-112">Attribute</span></span>|<span data-ttu-id="889a6-113">Description</span><span class="sxs-lookup"><span data-stu-id="889a6-113">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="889a6-114">네트워킹 성능 카운터의 사용 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="889a6-114">Specifies whether the networking performance counters are enabled.</span></span> <span data-ttu-id="889a6-115">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="889a6-115">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="889a6-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="889a6-116">Child Elements</span></span>  
 <span data-ttu-id="889a6-117">없음</span><span class="sxs-lookup"><span data-stu-id="889a6-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="889a6-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="889a6-118">Parent Elements</span></span>  
  
|<span data-ttu-id="889a6-119">요소</span><span class="sxs-lookup"><span data-stu-id="889a6-119">Element</span></span>|<span data-ttu-id="889a6-120">설명</span><span class="sxs-lookup"><span data-stu-id="889a6-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="889a6-121">settings</span><span class="sxs-lookup"><span data-stu-id="889a6-121">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="889a6-122"><xref:System.Net> 네임스페이스에 대한 기본 네트워크 옵션을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="889a6-122">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="889a6-123">설명</span><span class="sxs-lookup"><span data-stu-id="889a6-123">Remarks</span></span>  
 <span data-ttu-id="889a6-124">이 요소는 응용 프로그램 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="889a6-124">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
 <span data-ttu-id="889a6-125">네트워킹 성능 카운터를 사용하려면 구성 파일에서 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="889a6-125">Networking performance counters need to be enabled in the configuration file to be used.</span></span> <span data-ttu-id="889a6-126">구성 파일의 단일 설정을 통해 모든 네트워킹 성능 카운터를 사용하거나 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="889a6-126">All networking performance counters are enabled or disabled with a single setting in the configuration file.</span></span> <span data-ttu-id="889a6-127">개별 네트워킹 성능 카운터를 사용하거나 사용하지 않도록 설정할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="889a6-127">Individual networking performance counters cannot be enabled or disabled.</span></span> <span data-ttu-id="889a6-128">특정 네트워킹 성능 카운터에 대 한 자세한 내용은 [네트워킹 성능 카운터](../../../debug-trace-profile/performance-counters.md#networking)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="889a6-128">For more information on the specific networking performance counters, see [Networking Performance Counters](../../../debug-trace-profile/performance-counters.md#networking).</span></span>  
  
 <span data-ttu-id="889a6-129">기본값은 네트워킹 성능 카운터를 사용 하지 않도록 설정 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="889a6-129">The default value is that networking performance counters are disabled.</span></span>  
  
 <span data-ttu-id="889a6-130">속성을 사용 하 여 적용 가능한 구성 파일에서 활성화 된 특성의 현재 값을 가져올 수 있습니다. <xref:System.Net.Configuration.PerformanceCountersElement.Enabled%2A?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="889a6-130">The <xref:System.Net.Configuration.PerformanceCountersElement.Enabled%2A?displayProperty=nameWithType> property can be used to get the current value of the **enabled** attribute from applicable configuration files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="889a6-131">예제</span><span class="sxs-lookup"><span data-stu-id="889a6-131">Example</span></span>  
 <span data-ttu-id="889a6-132">다음 예제에서는 <xref:System.Net> 및 관련 네임 스페이스를 구성 하 여 네트워킹 성능 카운터를 사용 하도록 설정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="889a6-132">The following example shows how to configure the <xref:System.Net> and related namespaces to enable networking performance counters.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="889a6-133">참고자료</span><span class="sxs-lookup"><span data-stu-id="889a6-133">See also</span></span>

- <xref:System.Net.Configuration.PerformanceCountersElement?displayProperty=nameWithType>
- <xref:System.Net.Configuration.PerformanceCountersElement.Enabled%2A?displayProperty=nameWithType>
- [<span data-ttu-id="889a6-134">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="889a6-134">Network Settings Schema</span></span>](index.md)
- [<span data-ttu-id="889a6-135">네트워킹 성능 카운터</span><span class="sxs-lookup"><span data-stu-id="889a6-135">Networking Performance Counters</span></span>](../../../debug-trace-profile/performance-counters.md#networking)
