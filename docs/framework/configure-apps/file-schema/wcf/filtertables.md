---
title: <filterTables>
ms.date: 03/30/2017
ms.assetid: 41f1ac35-f559-473a-b2c3-8cc83a6a3831
ms.openlocfilehash: c49c7cf3a196595556c2bf1b4ed4365bfe1e4cbf
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704247"
---
# <a name="filtertables"></a><span data-ttu-id="fcf41-101">\<filterTables></span><span class="sxs-lookup"><span data-stu-id="fcf41-101">\<filterTables></span></span>
<span data-ttu-id="fcf41-102">필터가 일치할 때 메시지를 보내기 위한 라우팅 필터와 대상 엔드포인트 간의 매핑을 포함하는 라우팅 테이블을 정의하기 위한 구성 섹션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fcf41-102">Represents a configuration section for defining routing tables that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>  
  
 <span data-ttu-id="fcf41-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="fcf41-103">\<system.serviceModel></span></span>  
<span data-ttu-id="fcf41-104">\<라우팅 ></span><span class="sxs-lookup"><span data-stu-id="fcf41-104">\<routing></span></span>  
<span data-ttu-id="fcf41-105">\<routingTables></span><span class="sxs-lookup"><span data-stu-id="fcf41-105">\<routingTables></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fcf41-106">구문</span><span class="sxs-lookup"><span data-stu-id="fcf41-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fcf41-107">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="fcf41-107">Attributes and Elements</span></span>  
 <span data-ttu-id="fcf41-108">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fcf41-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fcf41-109">특성</span><span class="sxs-lookup"><span data-stu-id="fcf41-109">Attributes</span></span>  
 <span data-ttu-id="fcf41-110">없음</span><span class="sxs-lookup"><span data-stu-id="fcf41-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="fcf41-111">자식 요소</span><span class="sxs-lookup"><span data-stu-id="fcf41-111">Child Elements</span></span>  
  
|<span data-ttu-id="fcf41-112">요소</span><span class="sxs-lookup"><span data-stu-id="fcf41-112">Element</span></span>|<span data-ttu-id="fcf41-113">설명</span><span class="sxs-lookup"><span data-stu-id="fcf41-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fcf41-114">\<필터></span><span class="sxs-lookup"><span data-stu-id="fcf41-114">\<filters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md)|<span data-ttu-id="fcf41-115">필터가 일치할 때 메시지를 보내기 위한 라우팅 필터와 대상 엔드포인트 간의 매핑을 포함하는 라우팅 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="fcf41-115">A routing table that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="fcf41-116">부모 요소</span><span class="sxs-lookup"><span data-stu-id="fcf41-116">Parent Elements</span></span>  
  
|<span data-ttu-id="fcf41-117">요소</span><span class="sxs-lookup"><span data-stu-id="fcf41-117">Element</span></span>|<span data-ttu-id="fcf41-118">설명</span><span class="sxs-lookup"><span data-stu-id="fcf41-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fcf41-119">\<routing></span><span class="sxs-lookup"><span data-stu-id="fcf41-119">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="fcf41-120">라우팅 필터와 라우팅 테이블을 포함하는 구성 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="fcf41-120">A configuration section that contains routing filters and routing tables.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fcf41-121">참고자료</span><span class="sxs-lookup"><span data-stu-id="fcf41-121">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterTableCollection?displayProperty=nameWithType>
