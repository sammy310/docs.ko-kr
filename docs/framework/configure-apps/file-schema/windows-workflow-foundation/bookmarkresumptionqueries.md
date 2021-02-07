---
description: 다음에 대해 자세히 알아보세요. <bookmarkResumptionQueries>
title: <bookmarkResumptionQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 8ed61a7f-4254-439c-bdd8-b474971533f7
ms.openlocfilehash: e8ff21e2183fe31411674e9d4de6bf3d99d14836
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99698156"
---
# \<bookmarkResumptionQueries>

<span data-ttu-id="3d327-102">워크플로 인스턴스 내의 책갈피 다시 시작을 추적하는 데 사용되는 쿼리의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3d327-102">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="3d327-103">추적 참가자가 책갈피 다시 시작 레코드를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="3d327-103">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="3d327-104">추적 프로필 쿼리에 대 한 자세한 내용은 [추적 프로필](../../../windows-workflow-foundation/tracking-profiles.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3d327-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<bookmarkResumptionQueries>**  

## <a name="syntax"></a><span data-ttu-id="3d327-105">구문</span><span class="sxs-lookup"><span data-stu-id="3d327-105">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <bookmarkResumptionQueries>
        <bookmarkResumptionQuery name="String" />
      </bookmarkResumptionQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3d327-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="3d327-106">Attributes and Elements</span></span>  

 <span data-ttu-id="3d327-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3d327-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3d327-108">특성</span><span class="sxs-lookup"><span data-stu-id="3d327-108">Attributes</span></span>  

 <span data-ttu-id="3d327-109">없음</span><span class="sxs-lookup"><span data-stu-id="3d327-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="3d327-110">자식 요소</span><span class="sxs-lookup"><span data-stu-id="3d327-110">Child Elements</span></span>  
  
|<span data-ttu-id="3d327-111">요소</span><span class="sxs-lookup"><span data-stu-id="3d327-111">Element</span></span>|<span data-ttu-id="3d327-112">설명</span><span class="sxs-lookup"><span data-stu-id="3d327-112">Description</span></span>|  
|-------------|-----------------|  
|[\<bookmarkResumptionQuery>](bookmarkresumptionquery.md)|<span data-ttu-id="3d327-113">워크플로 인스턴스 내의 책갈피 다시 시작을 추적하는 데 사용되는 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="3d327-113">A query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="3d327-114">추적 참가자가 책갈피 다시 시작 레코드를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="3d327-114">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3d327-115">부모 요소</span><span class="sxs-lookup"><span data-stu-id="3d327-115">Parent Elements</span></span>  
  
|<span data-ttu-id="3d327-116">요소</span><span class="sxs-lookup"><span data-stu-id="3d327-116">Element</span></span>|<span data-ttu-id="3d327-117">설명</span><span class="sxs-lookup"><span data-stu-id="3d327-117">Description</span></span>|  
|-------------|-----------------|  
|[\<workflow>](workflow.md)|<span data-ttu-id="3d327-118">**ActivityDefinitionId** 속성으로 식별 되는 특정 워크플로에 대 한 모든 쿼리를 포함 하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="3d327-118">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3d327-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3d327-119">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="3d327-120">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="3d327-120">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="3d327-121">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="3d327-121">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
