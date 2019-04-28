---
title: <entries>
ms.date: 03/30/2017
ms.assetid: 202e430c-c1b9-4343-abe2-ac78c181a3b7
ms.openlocfilehash: 5561cf61cef2258ec61bd32770538add1c69f5c1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704208"
---
# <a name="entries"></a><span data-ttu-id="fb2d4-101">\<entries></span><span class="sxs-lookup"><span data-stu-id="fb2d4-101">\<entries></span></span>
<span data-ttu-id="fb2d4-102">필터가 일치할 때 메시지를 보내기 위한 라우팅 필터와 대상 엔드포인트 간의 매핑을 포함하는 라우팅 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="fb2d4-102">A routing entry that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>  
  
 <span data-ttu-id="fb2d4-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="fb2d4-103">\<system.serviceModel></span></span>  
<span data-ttu-id="fb2d4-104">\<라우팅 ></span><span class="sxs-lookup"><span data-stu-id="fb2d4-104">\<routing></span></span>  
<span data-ttu-id="fb2d4-105">\<routingTables></span><span class="sxs-lookup"><span data-stu-id="fb2d4-105">\<routingTables></span></span>  
<span data-ttu-id="fb2d4-106">\<table></span><span class="sxs-lookup"><span data-stu-id="fb2d4-106">\<table></span></span>  
<span data-ttu-id="fb2d4-107">\<entries></span><span class="sxs-lookup"><span data-stu-id="fb2d4-107">\<entries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb2d4-108">구문</span><span class="sxs-lookup"><span data-stu-id="fb2d4-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fb2d4-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="fb2d4-109">Attributes and Elements</span></span>  
 <span data-ttu-id="fb2d4-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fb2d4-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fb2d4-111">특성</span><span class="sxs-lookup"><span data-stu-id="fb2d4-111">Attributes</span></span>  
 <span data-ttu-id="fb2d4-112">없음</span><span class="sxs-lookup"><span data-stu-id="fb2d4-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="fb2d4-113">자식 요소</span><span class="sxs-lookup"><span data-stu-id="fb2d4-113">Child Elements</span></span>  
  
|<span data-ttu-id="fb2d4-114">요소</span><span class="sxs-lookup"><span data-stu-id="fb2d4-114">Element</span></span>|<span data-ttu-id="fb2d4-115">설명</span><span class="sxs-lookup"><span data-stu-id="fb2d4-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fb2d4-116">\<필터></span><span class="sxs-lookup"><span data-stu-id="fb2d4-116">\<filters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md)|<span data-ttu-id="fb2d4-117">이전에 정의된 클라이언트 엔드포인트에 필터를 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="fb2d4-117">Maps a filter to a client endpoint that was previously defined.</span></span> <span data-ttu-id="fb2d4-118">이 필터와 일치하는 메시지가 해당 대상으로 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb2d4-118">Messages matching this filter will be sent to this destination.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="fb2d4-119">부모 요소</span><span class="sxs-lookup"><span data-stu-id="fb2d4-119">Parent Elements</span></span>  
  
|<span data-ttu-id="fb2d4-120">요소</span><span class="sxs-lookup"><span data-stu-id="fb2d4-120">Element</span></span>|<span data-ttu-id="fb2d4-121">설명</span><span class="sxs-lookup"><span data-stu-id="fb2d4-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fb2d4-122">\<routing></span><span class="sxs-lookup"><span data-stu-id="fb2d4-122">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="fb2d4-123">라우팅 테이블을 포함하는 구성 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="fb2d4-123">A configuration section that contains a routing table.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fb2d4-124">참고자료</span><span class="sxs-lookup"><span data-stu-id="fb2d4-124">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement?displayProperty=nameWithType>
