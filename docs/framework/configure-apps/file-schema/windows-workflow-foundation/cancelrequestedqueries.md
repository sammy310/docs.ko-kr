---
title: <cancelRequestedQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: eab5af7e-76fa-434d-9d36-873e995cee05
ms.openlocfilehash: 4db30f3fed12b585b73339120fa5bc6602150e7d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91189541"
---
# \<cancelRequestedQueries>

<span data-ttu-id="ef794-101">부모 활동에 의한 자식 활동 취소 요청을 추적하는 데 사용되는 쿼리의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ef794-101">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="ef794-102">추적 참가자가 취소 요청 레코드 개체를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ef794-102">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="ef794-103">추적 프로필 쿼리에 대 한 자세한 내용은 [추적 프로필](../../../windows-workflow-foundation/tracking-profiles.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ef794-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cancelRequestedQueries>**  
  
## <a name="syntax"></a><span data-ttu-id="ef794-104">구문</span><span class="sxs-lookup"><span data-stu-id="ef794-104">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <cancelRequestQueries>
        <cancelRequestQuery activityName="String"
                            childActivityName="String"/>
      </cancelRequestQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ef794-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="ef794-105">Attributes and Elements</span></span>  

 <span data-ttu-id="ef794-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ef794-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ef794-107">특성</span><span class="sxs-lookup"><span data-stu-id="ef794-107">Attributes</span></span>  

 <span data-ttu-id="ef794-108">없음</span><span class="sxs-lookup"><span data-stu-id="ef794-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ef794-109">자식 요소</span><span class="sxs-lookup"><span data-stu-id="ef794-109">Child Elements</span></span>  
  
|<span data-ttu-id="ef794-110">요소</span><span class="sxs-lookup"><span data-stu-id="ef794-110">Element</span></span>|<span data-ttu-id="ef794-111">설명</span><span class="sxs-lookup"><span data-stu-id="ef794-111">Description</span></span>|  
|-------------|-----------------|  
|[\<cancelRequestedQuery>](cancelrequestedquery.md)|<span data-ttu-id="ef794-112">부모 활동에 의한 자식 활동 취소 요청을 추적하는 데 사용되는 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="ef794-112">A query that is used to track requests to cancel a child activity by the parent activity</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ef794-113">부모 요소</span><span class="sxs-lookup"><span data-stu-id="ef794-113">Parent Elements</span></span>  
  
|<span data-ttu-id="ef794-114">요소</span><span class="sxs-lookup"><span data-stu-id="ef794-114">Element</span></span>|<span data-ttu-id="ef794-115">설명</span><span class="sxs-lookup"><span data-stu-id="ef794-115">Description</span></span>|  
|-------------|-----------------|  
|[\<workflow>](workflow.md)|<span data-ttu-id="ef794-116">**ActivityDefinitionId** 속성으로 식별 되는 특정 워크플로에 대 한 모든 쿼리를 포함 하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="ef794-116">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ef794-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ef794-117">See also</span></span>

- [<span data-ttu-id="ef794-118">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="ef794-118">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="ef794-119">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="ef794-119">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
