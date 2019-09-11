---
title: <entries>의 <add>
ms.date: 03/30/2017
ms.assetid: 3af4805b-dc72-4f68-b168-da4fba8c6170
ms.openlocfilehash: 23b0a825ea593f85ade870d5b93367571eaa3ec0
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850514"
---
# <a name="add-of-entries"></a><span data-ttu-id="c7808-102">\<\<항목 > 추가 ></span><span class="sxs-lookup"><span data-stu-id="c7808-102">\<add> of \<entries></span></span>
<span data-ttu-id="c7808-103">이전에 정의된 클라이언트 엔드포인트에 필터를 매핑하는 라우팅 항목을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c7808-103">Represents a routing entry that maps a filter to a client endpoint that was previously defined.</span></span> <span data-ttu-id="c7808-104">이 필터와 일치하는 메시지가 해당 대상으로 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7808-104">Messages matching this filter will be sent to this destination.</span></span>  
  
<span data-ttu-id="c7808-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="c7808-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="c7808-106">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="c7808-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="c7808-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<라우팅 >** ](routing.md)</span><span class="sxs-lookup"><span data-stu-id="c7808-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)</span></span>\
<span data-ttu-id="c7808-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<filterTables >** ](filtertables.md)</span><span class="sxs-lookup"><span data-stu-id="c7808-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<filterTables>**](filtertables.md)</span></span>\
<span data-ttu-id="c7808-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<filterTable >** ](filtertable.md)</span><span class="sxs-lookup"><span data-stu-id="c7808-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<filterTable>**](filtertable.md)</span></span>\
<span data-ttu-id="c7808-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<항목 >** ](entries.md)</span><span class="sxs-lookup"><span data-stu-id="c7808-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<entries>**](entries.md)</span></span>\
<span data-ttu-id="c7808-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> 추가**</span><span class="sxs-lookup"><span data-stu-id="c7808-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7808-112">구문</span><span class="sxs-lookup"><span data-stu-id="c7808-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c7808-113">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="c7808-113">Attributes and Elements</span></span>  
 <span data-ttu-id="c7808-114">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c7808-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c7808-115">특성</span><span class="sxs-lookup"><span data-stu-id="c7808-115">Attributes</span></span>  
  
|<span data-ttu-id="c7808-116">특성</span><span class="sxs-lookup"><span data-stu-id="c7808-116">Attribute</span></span>|<span data-ttu-id="c7808-117">설명</span><span class="sxs-lookup"><span data-stu-id="c7808-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c7808-118">backupList</span><span class="sxs-lookup"><span data-stu-id="c7808-118">backupList</span></span>|<span data-ttu-id="c7808-119">엔드포인트의 백업 목록에 대한 참조를 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="c7808-119">A string that specifies a reference to a backup list of endpoints.</span></span>|  
|<span data-ttu-id="c7808-120">엔드포인트(endpoint)</span><span class="sxs-lookup"><span data-stu-id="c7808-120">endpoint</span></span>|<span data-ttu-id="c7808-121">`filterName` 특성에 의해 지정된 필터와 일치하는 메시지를 수신할 클라이언트 엔드포인트에 대한 참조를 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="c7808-121">A string that specifies a reference to a client endpoint that will receive messages that match the filter specified by the `filterName` attribute.</span></span>|  
|<span data-ttu-id="c7808-122">filterName</span><span class="sxs-lookup"><span data-stu-id="c7808-122">filterName</span></span>|<span data-ttu-id="c7808-123">필터 요소에 대한 참조를 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="c7808-123">A string that specifies a reference to a filter element.</span></span>|  
|<span data-ttu-id="c7808-124">priority</span><span class="sxs-lookup"><span data-stu-id="c7808-124">priority</span></span>|<span data-ttu-id="c7808-125">이 항목의 우선 순위를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="c7808-125">An integer that specifies the priority of this entry.</span></span><br /><br /> <span data-ttu-id="c7808-126">라우팅 테이블의 항목은 우선 순위를 기준으로 평가되며 0이 가장 낮은 우선 순위입니다.</span><span class="sxs-lookup"><span data-stu-id="c7808-126">Entries in the routing table will be evaluated based on priority, with 0 being the lowest priority.</span></span> <span data-ttu-id="c7808-127">특정 우선 순위를 갖는 모든 항목은 동시에 평가되며 현재 우선 순위에 대해 일치하는 항목이 없는 경우 다음 우선 순위가 평가됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7808-127">All entries for a specific priority are evaluated simultaneously, if no matching entry is found for the current priority, the next priority level will be evaluated.</span></span><br /><br /> <span data-ttu-id="c7808-128">이 값은 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="c7808-128">This value is optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c7808-129">자식 요소</span><span class="sxs-lookup"><span data-stu-id="c7808-129">Child Elements</span></span>  
 <span data-ttu-id="c7808-130">없음</span><span class="sxs-lookup"><span data-stu-id="c7808-130">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c7808-131">부모 요소</span><span class="sxs-lookup"><span data-stu-id="c7808-131">Parent Elements</span></span>  
  
|<span data-ttu-id="c7808-132">요소</span><span class="sxs-lookup"><span data-stu-id="c7808-132">Element</span></span>|<span data-ttu-id="c7808-133">Description</span><span class="sxs-lookup"><span data-stu-id="c7808-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c7808-134">\<routing></span><span class="sxs-lookup"><span data-stu-id="c7808-134">\<routing></span></span>](routing.md)|<span data-ttu-id="c7808-135">라우팅 매핑 항목을 포함하는 구성 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="c7808-135">A configuration section that contains routing mapping entries.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c7808-136">참고자료</span><span class="sxs-lookup"><span data-stu-id="c7808-136">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement?displayProperty=nameWithType>
