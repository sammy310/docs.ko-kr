---
title: <bookmarkResumptionQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 8ed61a7f-4254-439c-bdd8-b474971533f7
ms.openlocfilehash: 047d13bc8477214fa1e3c9ffdbed6785b29da637
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91189581"
---
# \<bookmarkResumptionQueries>

<span data-ttu-id="9a0cd-101">워크플로 인스턴스 내의 책갈피 다시 시작을 추적하는 데 사용되는 쿼리의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9a0cd-101">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="9a0cd-102">추적 참가자가 책갈피 다시 시작 레코드를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="9a0cd-102">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="9a0cd-103">추적 프로필 쿼리에 대 한 자세한 내용은 [추적 프로필](../../../windows-workflow-foundation/tracking-profiles.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9a0cd-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<bookmarkResumptionQueries>**  

## <a name="syntax"></a><span data-ttu-id="9a0cd-104">구문</span><span class="sxs-lookup"><span data-stu-id="9a0cd-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9a0cd-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="9a0cd-105">Attributes and Elements</span></span>  

 <span data-ttu-id="9a0cd-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9a0cd-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9a0cd-107">특성</span><span class="sxs-lookup"><span data-stu-id="9a0cd-107">Attributes</span></span>  

 <span data-ttu-id="9a0cd-108">없음</span><span class="sxs-lookup"><span data-stu-id="9a0cd-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="9a0cd-109">자식 요소</span><span class="sxs-lookup"><span data-stu-id="9a0cd-109">Child Elements</span></span>  
  
|<span data-ttu-id="9a0cd-110">요소</span><span class="sxs-lookup"><span data-stu-id="9a0cd-110">Element</span></span>|<span data-ttu-id="9a0cd-111">설명</span><span class="sxs-lookup"><span data-stu-id="9a0cd-111">Description</span></span>|  
|-------------|-----------------|  
|[\<bookmarkResumptionQuery>](bookmarkresumptionquery.md)|<span data-ttu-id="9a0cd-112">워크플로 인스턴스 내의 책갈피 다시 시작을 추적하는 데 사용되는 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="9a0cd-112">A query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="9a0cd-113">추적 참가자가 책갈피 다시 시작 레코드를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="9a0cd-113">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9a0cd-114">부모 요소</span><span class="sxs-lookup"><span data-stu-id="9a0cd-114">Parent Elements</span></span>  
  
|<span data-ttu-id="9a0cd-115">요소</span><span class="sxs-lookup"><span data-stu-id="9a0cd-115">Element</span></span>|<span data-ttu-id="9a0cd-116">설명</span><span class="sxs-lookup"><span data-stu-id="9a0cd-116">Description</span></span>|  
|-------------|-----------------|  
|[\<workflow>](workflow.md)|<span data-ttu-id="9a0cd-117">**ActivityDefinitionId** 속성으로 식별 되는 특정 워크플로에 대 한 모든 쿼리를 포함 하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="9a0cd-117">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9a0cd-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9a0cd-118">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="9a0cd-119">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="9a0cd-119">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="9a0cd-120">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="9a0cd-120">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
