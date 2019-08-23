---
title: <entries>의 <add>
ms.date: 03/30/2017
ms.assetid: 3af4805b-dc72-4f68-b168-da4fba8c6170
ms.openlocfilehash: 690fd07159e07b7e037f7330b31fdcba423e80f9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920124"
---
# <a name="add-of-entries"></a><span data-ttu-id="8bd75-102">\<\<항목 > 추가 ></span><span class="sxs-lookup"><span data-stu-id="8bd75-102">\<add> of \<entries></span></span>
<span data-ttu-id="8bd75-103">이전에 정의된 클라이언트 엔드포인트에 필터를 매핑하는 라우팅 항목을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8bd75-103">Represents a routing entry that maps a filter to a client endpoint that was previously defined.</span></span> <span data-ttu-id="8bd75-104">이 필터와 일치하는 메시지가 해당 대상으로 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="8bd75-104">Messages matching this filter will be sent to this destination.</span></span>  
  
 <span data-ttu-id="8bd75-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="8bd75-105">\<system.serviceModel></span></span>  
<span data-ttu-id="8bd75-106">\<라우팅 ></span><span class="sxs-lookup"><span data-stu-id="8bd75-106">\<routing></span></span>  
<span data-ttu-id="8bd75-107">\<filterTables></span><span class="sxs-lookup"><span data-stu-id="8bd75-107">\<filterTables></span></span>  
<span data-ttu-id="8bd75-108">\<filterTable></span><span class="sxs-lookup"><span data-stu-id="8bd75-108">\<filterTable></span></span>  
<span data-ttu-id="8bd75-109">\<entries></span><span class="sxs-lookup"><span data-stu-id="8bd75-109">\<entries></span></span>  
<span data-ttu-id="8bd75-110">\<add></span><span class="sxs-lookup"><span data-stu-id="8bd75-110">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8bd75-111">구문</span><span class="sxs-lookup"><span data-stu-id="8bd75-111">Syntax</span></span>  
  
```xml  
<routing>
  <filterTables>
    <filterTable name="String">
      <entries>
        <add backupList="String"
             endpointName="String"
             filterName="String"
             priority="Integer" />
      </entries>
    </filterTable>
  </filterTables>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8bd75-112">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="8bd75-112">Attributes and Elements</span></span>  
 <span data-ttu-id="8bd75-113">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8bd75-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8bd75-114">특성</span><span class="sxs-lookup"><span data-stu-id="8bd75-114">Attributes</span></span>  
  
|<span data-ttu-id="8bd75-115">특성</span><span class="sxs-lookup"><span data-stu-id="8bd75-115">Attribute</span></span>|<span data-ttu-id="8bd75-116">Description</span><span class="sxs-lookup"><span data-stu-id="8bd75-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8bd75-117">backupList</span><span class="sxs-lookup"><span data-stu-id="8bd75-117">backupList</span></span>|<span data-ttu-id="8bd75-118">엔드포인트의 백업 목록에 대한 참조를 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="8bd75-118">A string that specifies a reference to a backup list of endpoints.</span></span>|  
|<span data-ttu-id="8bd75-119">엔드포인트(endpoint)</span><span class="sxs-lookup"><span data-stu-id="8bd75-119">endpoint</span></span>|<span data-ttu-id="8bd75-120">`filterName` 특성에 의해 지정된 필터와 일치하는 메시지를 수신할 클라이언트 엔드포인트에 대한 참조를 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="8bd75-120">A string that specifies a reference to a client endpoint that will receive messages that match the filter specified by the `filterName` attribute.</span></span>|  
|<span data-ttu-id="8bd75-121">filterName</span><span class="sxs-lookup"><span data-stu-id="8bd75-121">filterName</span></span>|<span data-ttu-id="8bd75-122">필터 요소에 대한 참조를 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="8bd75-122">A string that specifies a reference to a filter element.</span></span>|  
|<span data-ttu-id="8bd75-123">priority</span><span class="sxs-lookup"><span data-stu-id="8bd75-123">priority</span></span>|<span data-ttu-id="8bd75-124">이 항목의 우선 순위를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="8bd75-124">An integer that specifies the priority of this entry.</span></span><br /><br /> <span data-ttu-id="8bd75-125">라우팅 테이블의 항목은 우선 순위를 기준으로 평가되며 0이 가장 낮은 우선 순위입니다.</span><span class="sxs-lookup"><span data-stu-id="8bd75-125">Entries in the routing table will be evaluated based on priority, with 0 being the lowest priority.</span></span> <span data-ttu-id="8bd75-126">특정 우선 순위를 갖는 모든 항목은 동시에 평가되며 현재 우선 순위에 대해 일치하는 항목이 없는 경우 다음 우선 순위가 평가됩니다.</span><span class="sxs-lookup"><span data-stu-id="8bd75-126">All entries for a specific priority are evaluated simultaneously, if no matching entry is found for the current priority, the next priority level will be evaluated.</span></span><br /><br /> <span data-ttu-id="8bd75-127">이 값은 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="8bd75-127">This value is optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8bd75-128">자식 요소</span><span class="sxs-lookup"><span data-stu-id="8bd75-128">Child Elements</span></span>  
 <span data-ttu-id="8bd75-129">없음</span><span class="sxs-lookup"><span data-stu-id="8bd75-129">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8bd75-130">부모 요소</span><span class="sxs-lookup"><span data-stu-id="8bd75-130">Parent Elements</span></span>  
  
|<span data-ttu-id="8bd75-131">요소</span><span class="sxs-lookup"><span data-stu-id="8bd75-131">Element</span></span>|<span data-ttu-id="8bd75-132">Description</span><span class="sxs-lookup"><span data-stu-id="8bd75-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8bd75-133">\<routing></span><span class="sxs-lookup"><span data-stu-id="8bd75-133">\<routing></span></span>](routing.md)|<span data-ttu-id="8bd75-134">라우팅 매핑 항목을 포함하는 구성 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="8bd75-134">A configuration section that contains routing mapping entries.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8bd75-135">참고자료</span><span class="sxs-lookup"><span data-stu-id="8bd75-135">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement?displayProperty=nameWithType>
