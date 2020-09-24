---
title: <cancelRequestedQueries> WCF의
ms.date: 03/30/2017
ms.assetid: a7cc7125-9ea3-4d3f-99c0-878cdeb1258a
ms.openlocfilehash: 205399330c1aa69b332c2149ee32d9b6098ccdbe
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91151170"
---
# <a name="cancelrequestedqueries-of-wcf"></a><span data-ttu-id="1c2b1-102">\<cancelRequestedQueries> WCF의</span><span class="sxs-lookup"><span data-stu-id="1c2b1-102">\<cancelRequestedQueries> of WCF</span></span>

<span data-ttu-id="1c2b1-103">부모 활동에 의한 자식 활동 취소 요청을 추적하는 데 사용되는 쿼리의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1c2b1-103">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="1c2b1-104">추적 참가자가 취소 요청 레코드 개체를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="1c2b1-104">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
<span data-ttu-id="1c2b1-105">추적 프로필 쿼리에 대 한 자세한 내용은 [추적 프로필](../../../windows-workflow-foundation/tracking-profiles.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1c2b1-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cancelRequestedQueries>**  
  
## <a name="syntax"></a><span data-ttu-id="1c2b1-106">구문</span><span class="sxs-lookup"><span data-stu-id="1c2b1-106">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <cancelRequestQueries>
          <cancelRequestQuery activityName="String"
                              childActivityName="String" />
        </cancelRequestQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1c2b1-107">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="1c2b1-107">Attributes and elements</span></span>  

<span data-ttu-id="1c2b1-108">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1c2b1-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1c2b1-109">특성</span><span class="sxs-lookup"><span data-stu-id="1c2b1-109">Attributes</span></span>

<span data-ttu-id="1c2b1-110">없음</span><span class="sxs-lookup"><span data-stu-id="1c2b1-110">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="1c2b1-111">자식 요소</span><span class="sxs-lookup"><span data-stu-id="1c2b1-111">Child elements</span></span>
  
|<span data-ttu-id="1c2b1-112">요소</span><span class="sxs-lookup"><span data-stu-id="1c2b1-112">Element</span></span>|<span data-ttu-id="1c2b1-113">설명</span><span class="sxs-lookup"><span data-stu-id="1c2b1-113">Description</span></span>|  
|-------------|-----------------|  
|[\<cancelRequestedQuery>](cancelrequestedquery-of-wcf.md)|<span data-ttu-id="1c2b1-114">부모 활동에 의한 자식 활동 취소 요청을 추적하는 데 사용되는 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="1c2b1-114">A query that is used to track requests to cancel a child activity by the parent activity</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1c2b1-115">부모 요소</span><span class="sxs-lookup"><span data-stu-id="1c2b1-115">Parent elements</span></span>  
  
|<span data-ttu-id="1c2b1-116">요소</span><span class="sxs-lookup"><span data-stu-id="1c2b1-116">Element</span></span>|<span data-ttu-id="1c2b1-117">설명</span><span class="sxs-lookup"><span data-stu-id="1c2b1-117">Description</span></span>|  
|-------------|-----------------|  
|[\<workflow>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="1c2b1-118"><xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId> 속성에 의해 식별되는 특정 워크플로에 대한 모든 쿼리를 포함하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="1c2b1-118">A configuration element that contains all queries for a specific workflow identified by the <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId> property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1c2b1-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1c2b1-119">See also</span></span>

- <xref:System.Activities.Tracking.CancelRequestedQuery>
- [<span data-ttu-id="1c2b1-120">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="1c2b1-120">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="1c2b1-121">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="1c2b1-121">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
