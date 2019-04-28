---
title: <filterTable>
ms.date: 03/30/2017
ms.assetid: e9f05441-3ad1-49b9-a267-71724aa094b4
ms.openlocfilehash: 4e5c7d56e35afe3001f4c70064adbfef7702c720
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61673214"
---
# <a name="filtertable"></a><span data-ttu-id="a3882-101">\<filterTable></span><span class="sxs-lookup"><span data-stu-id="a3882-101">\<filterTable></span></span>
<span data-ttu-id="a3882-102">필터가 true로 평가 될 경우에 대해 메시지 및 메시지를 라우팅할 클라이언트 끝점을 평가 하는 필터의 목록을 포함 하는 라우팅 테이블을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a3882-102">Represents a routing table that contains a list of filters to evaluate messages against and the client endpoint to route messages to if the filter evaluates to true.</span></span>  
  
 <span data-ttu-id="a3882-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="a3882-103">\<system.serviceModel></span></span>  
<span data-ttu-id="a3882-104">\<라우팅 ></span><span class="sxs-lookup"><span data-stu-id="a3882-104">\<routing></span></span>  
<span data-ttu-id="a3882-105">\<routingTables></span><span class="sxs-lookup"><span data-stu-id="a3882-105">\<routingTables></span></span>  
<span data-ttu-id="a3882-106">\<table></span><span class="sxs-lookup"><span data-stu-id="a3882-106">\<table></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3882-107">구문</span><span class="sxs-lookup"><span data-stu-id="a3882-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a3882-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="a3882-108">Attributes and Elements</span></span>  
 <span data-ttu-id="a3882-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a3882-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a3882-110">특성</span><span class="sxs-lookup"><span data-stu-id="a3882-110">Attributes</span></span>  
  
|<span data-ttu-id="a3882-111">요소</span><span class="sxs-lookup"><span data-stu-id="a3882-111">Element</span></span>|<span data-ttu-id="a3882-112">설명</span><span class="sxs-lookup"><span data-stu-id="a3882-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a3882-113">name</span><span class="sxs-lookup"><span data-stu-id="a3882-113">name</span></span>|<span data-ttu-id="a3882-114">이 구성 요소의 고유 이름을 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="a3882-114">A string that contains the unique name of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a3882-115">자식 요소</span><span class="sxs-lookup"><span data-stu-id="a3882-115">Child Elements</span></span>  
  
|<span data-ttu-id="a3882-116">요소</span><span class="sxs-lookup"><span data-stu-id="a3882-116">Element</span></span>|<span data-ttu-id="a3882-117">설명</span><span class="sxs-lookup"><span data-stu-id="a3882-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a3882-118">\<필터></span><span class="sxs-lookup"><span data-stu-id="a3882-118">\<filters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md)|<span data-ttu-id="a3882-119">필터가 일치할 때 메시지를 보내기 위한 라우팅 필터와 대상 엔드포인트 간의 매핑입니다.</span><span class="sxs-lookup"><span data-stu-id="a3882-119">Mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a3882-120">부모 요소</span><span class="sxs-lookup"><span data-stu-id="a3882-120">Parent Elements</span></span>  
  
|<span data-ttu-id="a3882-121">요소</span><span class="sxs-lookup"><span data-stu-id="a3882-121">Element</span></span>|<span data-ttu-id="a3882-122">설명</span><span class="sxs-lookup"><span data-stu-id="a3882-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a3882-123">\<routing></span><span class="sxs-lookup"><span data-stu-id="a3882-123">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="a3882-124">라우팅 테이블을 포함하는 구성 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="a3882-124">A configuration section that contains routing tables.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a3882-125">참고자료</span><span class="sxs-lookup"><span data-stu-id="a3882-125">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
