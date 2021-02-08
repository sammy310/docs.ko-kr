---
description: '다음에 대 한 자세한 정보:: <add><entries>'
title: <entries>의 <add>
ms.date: 03/30/2017
ms.assetid: 3af4805b-dc72-4f68-b168-da4fba8c6170
ms.openlocfilehash: 0be24fb9d2327d411368dd05afc21156dfaf3d3a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99803973"
---
# <a name="add-of-entries"></a><span data-ttu-id="70db2-103">\<entries>의 \<add></span><span class="sxs-lookup"><span data-stu-id="70db2-103">\<add> of \<entries></span></span>

<span data-ttu-id="70db2-104">이전에 정의된 클라이언트 엔드포인트에 필터를 매핑하는 라우팅 항목을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="70db2-104">Represents a routing entry that maps a filter to a client endpoint that was previously defined.</span></span> <span data-ttu-id="70db2-105">이 필터와 일치하는 메시지가 해당 대상으로 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="70db2-105">Messages matching this filter will be sent to this destination.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<filterTables>**](filtertables.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<filterTable>**](filtertable.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<entries>**](entries.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="70db2-106">구문</span><span class="sxs-lookup"><span data-stu-id="70db2-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="70db2-107">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="70db2-107">Attributes and Elements</span></span>  

 <span data-ttu-id="70db2-108">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="70db2-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="70db2-109">특성</span><span class="sxs-lookup"><span data-stu-id="70db2-109">Attributes</span></span>  
  
|<span data-ttu-id="70db2-110">attribute</span><span class="sxs-lookup"><span data-stu-id="70db2-110">Attribute</span></span>|<span data-ttu-id="70db2-111">설명</span><span class="sxs-lookup"><span data-stu-id="70db2-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="70db2-112">backupList</span><span class="sxs-lookup"><span data-stu-id="70db2-112">backupList</span></span>|<span data-ttu-id="70db2-113">엔드포인트의 백업 목록에 대한 참조를 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="70db2-113">A string that specifies a reference to a backup list of endpoints.</span></span>|  
|<span data-ttu-id="70db2-114">엔드포인트(endpoint)</span><span class="sxs-lookup"><span data-stu-id="70db2-114">endpoint</span></span>|<span data-ttu-id="70db2-115">ph x="1" /&gt; 특성에 의해 지정된 필터와 일치하는 메시지를 수신할 클라이언트 엔드포인트에 대한 참조를 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="70db2-115">A string that specifies a reference to a client endpoint that will receive messages that match the filter specified by the `filterName` attribute.</span></span>|  
|<span data-ttu-id="70db2-116">filterName</span><span class="sxs-lookup"><span data-stu-id="70db2-116">filterName</span></span>|<span data-ttu-id="70db2-117">필터 요소에 대한 참조를 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="70db2-117">A string that specifies a reference to a filter element.</span></span>|  
|<span data-ttu-id="70db2-118">priority</span><span class="sxs-lookup"><span data-stu-id="70db2-118">priority</span></span>|<span data-ttu-id="70db2-119">이 항목의 우선 순위를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="70db2-119">An integer that specifies the priority of this entry.</span></span><br /><br /> <span data-ttu-id="70db2-120">라우팅 테이블의 항목은 우선 순위를 기준으로 평가되며 0이 가장 낮은 우선 순위입니다.</span><span class="sxs-lookup"><span data-stu-id="70db2-120">Entries in the routing table will be evaluated based on priority, with 0 being the lowest priority.</span></span> <span data-ttu-id="70db2-121">특정 우선 순위를 갖는 모든 항목은 동시에 평가되며 현재 우선 순위에 대해 일치하는 항목이 없는 경우 다음 우선 순위가 평가됩니다.</span><span class="sxs-lookup"><span data-stu-id="70db2-121">All entries for a specific priority are evaluated simultaneously, if no matching entry is found for the current priority, the next priority level will be evaluated.</span></span><br /><br /> <span data-ttu-id="70db2-122">이 값은 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="70db2-122">This value is optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="70db2-123">자식 요소</span><span class="sxs-lookup"><span data-stu-id="70db2-123">Child Elements</span></span>  

 <span data-ttu-id="70db2-124">없음</span><span class="sxs-lookup"><span data-stu-id="70db2-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="70db2-125">부모 요소</span><span class="sxs-lookup"><span data-stu-id="70db2-125">Parent Elements</span></span>  
  
|<span data-ttu-id="70db2-126">요소</span><span class="sxs-lookup"><span data-stu-id="70db2-126">Element</span></span>|<span data-ttu-id="70db2-127">설명</span><span class="sxs-lookup"><span data-stu-id="70db2-127">Description</span></span>|  
|-------------|-----------------|  
|[\<routing>](routing.md)|<span data-ttu-id="70db2-128">라우팅 매핑 항목을 포함하는 구성 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="70db2-128">A configuration section that contains routing mapping entries.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="70db2-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="70db2-129">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement?displayProperty=nameWithType>
