---
title: <entries>
ms.date: 03/30/2017
ms.assetid: 202e430c-c1b9-4343-abe2-ac78c181a3b7
ms.openlocfilehash: 610ba29ec98f4b1f2a9b1db3542bcb3aefb46457
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925657"
---
# <a name="entries"></a><span data-ttu-id="0f178-101">\<entries></span><span class="sxs-lookup"><span data-stu-id="0f178-101">\<entries></span></span>
<span data-ttu-id="0f178-102">필터가 일치할 때 메시지를 보내기 위한 라우팅 필터와 대상 엔드포인트 간의 매핑을 포함하는 라우팅 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="0f178-102">A routing entry that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>  
  
 <span data-ttu-id="0f178-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="0f178-103">\<system.serviceModel></span></span>  
<span data-ttu-id="0f178-104">\<라우팅 ></span><span class="sxs-lookup"><span data-stu-id="0f178-104">\<routing></span></span>  
<span data-ttu-id="0f178-105">\<routingTables></span><span class="sxs-lookup"><span data-stu-id="0f178-105">\<routingTables></span></span>  
<span data-ttu-id="0f178-106">\<table></span><span class="sxs-lookup"><span data-stu-id="0f178-106">\<table></span></span>  
<span data-ttu-id="0f178-107">\<entries></span><span class="sxs-lookup"><span data-stu-id="0f178-107">\<entries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f178-108">구문</span><span class="sxs-lookup"><span data-stu-id="0f178-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0f178-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="0f178-109">Attributes and Elements</span></span>  
 <span data-ttu-id="0f178-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0f178-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0f178-111">특성</span><span class="sxs-lookup"><span data-stu-id="0f178-111">Attributes</span></span>  
 <span data-ttu-id="0f178-112">없음</span><span class="sxs-lookup"><span data-stu-id="0f178-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="0f178-113">자식 요소</span><span class="sxs-lookup"><span data-stu-id="0f178-113">Child Elements</span></span>  
  
|<span data-ttu-id="0f178-114">요소</span><span class="sxs-lookup"><span data-stu-id="0f178-114">Element</span></span>|<span data-ttu-id="0f178-115">설명</span><span class="sxs-lookup"><span data-stu-id="0f178-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0f178-116">\<필터></span><span class="sxs-lookup"><span data-stu-id="0f178-116">\<filters></span></span>](filters-of-routing.md)|<span data-ttu-id="0f178-117">이전에 정의된 클라이언트 엔드포인트에 필터를 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="0f178-117">Maps a filter to a client endpoint that was previously defined.</span></span> <span data-ttu-id="0f178-118">이 필터와 일치하는 메시지가 해당 대상으로 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f178-118">Messages matching this filter will be sent to this destination.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0f178-119">부모 요소</span><span class="sxs-lookup"><span data-stu-id="0f178-119">Parent Elements</span></span>  
  
|<span data-ttu-id="0f178-120">요소</span><span class="sxs-lookup"><span data-stu-id="0f178-120">Element</span></span>|<span data-ttu-id="0f178-121">Description</span><span class="sxs-lookup"><span data-stu-id="0f178-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0f178-122">\<routing></span><span class="sxs-lookup"><span data-stu-id="0f178-122">\<routing></span></span>](routing.md)|<span data-ttu-id="0f178-123">라우팅 테이블을 포함하는 구성 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="0f178-123">A configuration section that contains a routing table.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0f178-124">참고자료</span><span class="sxs-lookup"><span data-stu-id="0f178-124">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement?displayProperty=nameWithType>
