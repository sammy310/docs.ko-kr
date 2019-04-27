---
title: <entries>의 <add>
ms.date: 03/30/2017
ms.assetid: 3af4805b-dc72-4f68-b168-da4fba8c6170
ms.openlocfilehash: 1324803d7c0f127cfee9eadebff2672955780eda
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61673643"
---
# <a name="add-of-entries"></a><span data-ttu-id="5222e-102">\<추가 >의 \<항목 ></span><span class="sxs-lookup"><span data-stu-id="5222e-102">\<add> of \<entries></span></span>
<span data-ttu-id="5222e-103">이전에 정의된 클라이언트 엔드포인트에 필터를 매핑하는 라우팅 항목을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5222e-103">Represents a routing entry that maps a filter to a client endpoint that was previously defined.</span></span> <span data-ttu-id="5222e-104">이 필터와 일치하는 메시지가 해당 대상으로 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="5222e-104">Messages matching this filter will be sent to this destination.</span></span>  
  
 <span data-ttu-id="5222e-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="5222e-105">\<system.serviceModel></span></span>  
<span data-ttu-id="5222e-106">\<라우팅 ></span><span class="sxs-lookup"><span data-stu-id="5222e-106">\<routing></span></span>  
<span data-ttu-id="5222e-107">\<filterTables></span><span class="sxs-lookup"><span data-stu-id="5222e-107">\<filterTables></span></span>  
<span data-ttu-id="5222e-108">\<filterTable></span><span class="sxs-lookup"><span data-stu-id="5222e-108">\<filterTable></span></span>  
<span data-ttu-id="5222e-109">\<entries></span><span class="sxs-lookup"><span data-stu-id="5222e-109">\<entries></span></span>  
<span data-ttu-id="5222e-110">\<add></span><span class="sxs-lookup"><span data-stu-id="5222e-110">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5222e-111">구문</span><span class="sxs-lookup"><span data-stu-id="5222e-111">Syntax</span></span>  
  
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
  
```csharp  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5222e-112">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="5222e-112">Attributes and Elements</span></span>  
 <span data-ttu-id="5222e-113">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5222e-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5222e-114">특성</span><span class="sxs-lookup"><span data-stu-id="5222e-114">Attributes</span></span>  
  
|<span data-ttu-id="5222e-115">특성</span><span class="sxs-lookup"><span data-stu-id="5222e-115">Attribute</span></span>|<span data-ttu-id="5222e-116">설명</span><span class="sxs-lookup"><span data-stu-id="5222e-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5222e-117">backupList</span><span class="sxs-lookup"><span data-stu-id="5222e-117">backupList</span></span>|<span data-ttu-id="5222e-118">엔드포인트의 백업 목록에 대한 참조를 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="5222e-118">A string that specifies a reference to a backup list of endpoints.</span></span>|  
|<span data-ttu-id="5222e-119">엔드포인트(endpoint)</span><span class="sxs-lookup"><span data-stu-id="5222e-119">endpoint</span></span>|<span data-ttu-id="5222e-120">`filterName` 특성에 의해 지정된 필터와 일치하는 메시지를 수신할 클라이언트 엔드포인트에 대한 참조를 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="5222e-120">A string that specifies a reference to a client endpoint that will receive messages that match the filter specified by the `filterName` attribute.</span></span>|  
|<span data-ttu-id="5222e-121">filterName</span><span class="sxs-lookup"><span data-stu-id="5222e-121">filterName</span></span>|<span data-ttu-id="5222e-122">필터 요소에 대한 참조를 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="5222e-122">A string that specifies a reference to a filter element.</span></span>|  
|<span data-ttu-id="5222e-123">priority</span><span class="sxs-lookup"><span data-stu-id="5222e-123">priority</span></span>|<span data-ttu-id="5222e-124">이 항목의 우선 순위를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="5222e-124">An integer that specifies the priority of this entry.</span></span><br /><br /> <span data-ttu-id="5222e-125">라우팅 테이블의 항목은 우선 순위를 기준으로 평가되며 0이 가장 낮은 우선 순위입니다.</span><span class="sxs-lookup"><span data-stu-id="5222e-125">Entries in the routing table will be evaluated based on priority, with 0 being the lowest priority.</span></span> <span data-ttu-id="5222e-126">특정 우선 순위를 갖는 모든 항목은 동시에 평가되며 현재 우선 순위에 대해 일치하는 항목이 없는 경우 다음 우선 순위가 평가됩니다.</span><span class="sxs-lookup"><span data-stu-id="5222e-126">All entries for a specific priority are evaluated simultaneously, if no matching entry is found for the current priority, the next priority level will be evaluated.</span></span><br /><br /> <span data-ttu-id="5222e-127">이 값은 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="5222e-127">This value is optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5222e-128">자식 요소</span><span class="sxs-lookup"><span data-stu-id="5222e-128">Child Elements</span></span>  
 <span data-ttu-id="5222e-129">없음</span><span class="sxs-lookup"><span data-stu-id="5222e-129">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5222e-130">부모 요소</span><span class="sxs-lookup"><span data-stu-id="5222e-130">Parent Elements</span></span>  
  
|<span data-ttu-id="5222e-131">요소</span><span class="sxs-lookup"><span data-stu-id="5222e-131">Element</span></span>|<span data-ttu-id="5222e-132">설명</span><span class="sxs-lookup"><span data-stu-id="5222e-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5222e-133">\<routing></span><span class="sxs-lookup"><span data-stu-id="5222e-133">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="5222e-134">라우팅 매핑 항목을 포함하는 구성 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="5222e-134">A configuration section that contains routing mapping entries.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5222e-135">참고자료</span><span class="sxs-lookup"><span data-stu-id="5222e-135">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement?displayProperty=nameWithType>
