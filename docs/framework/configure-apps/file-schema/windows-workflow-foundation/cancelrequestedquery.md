---
title: <cancelRequestedQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 8da9b1c4-338a-4f23-9830-6d257772d340
ms.openlocfilehash: 3e6840ce647625c36356cccd4651f17de32777e2
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "79152289"
---
# \<cancelRequestedQuery>
<span data-ttu-id="ade92-101">부모 활동에 의한 자식 활동 취소 요청을 추적하는 데 사용되는 쿼리를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ade92-101">Represents a query that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="ade92-102">추적 참가자가 취소 요청 레코드 개체를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ade92-102">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="ade92-103">추적 프로필 쿼리에 대 한 자세한 내용은 [추적 프로필](../../../windows-workflow-foundation/tracking-profiles.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ade92-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cancelRequestedQueries>**](cancelrequestedqueries.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cancelRequestedQuery>**  
  
## <a name="syntax"></a><span data-ttu-id="ade92-104">구문</span><span class="sxs-lookup"><span data-stu-id="ade92-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ade92-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="ade92-105">Attributes and Elements</span></span>  
 <span data-ttu-id="ade92-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ade92-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ade92-107">특성</span><span class="sxs-lookup"><span data-stu-id="ade92-107">Attributes</span></span>  
  
|<span data-ttu-id="ade92-108">attribute</span><span class="sxs-lookup"><span data-stu-id="ade92-108">Attribute</span></span>|<span data-ttu-id="ade92-109">Description</span><span class="sxs-lookup"><span data-stu-id="ade92-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ade92-110">activityName</span><span class="sxs-lookup"><span data-stu-id="ade92-110">activityName</span></span>|<span data-ttu-id="ade92-111">취소를 요청하는 활동의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="ade92-111">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="ade92-112">childActivityName</span><span class="sxs-lookup"><span data-stu-id="ade92-112">childActivityName</span></span>|<span data-ttu-id="ade92-113">취소가 요청된 자식 활동의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="ade92-113">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ade92-114">자식 요소</span><span class="sxs-lookup"><span data-stu-id="ade92-114">Child Elements</span></span>  
 <span data-ttu-id="ade92-115">없음</span><span class="sxs-lookup"><span data-stu-id="ade92-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ade92-116">부모 요소</span><span class="sxs-lookup"><span data-stu-id="ade92-116">Parent Elements</span></span>  
  
|<span data-ttu-id="ade92-117">요소</span><span class="sxs-lookup"><span data-stu-id="ade92-117">Element</span></span>|<span data-ttu-id="ade92-118">Description</span><span class="sxs-lookup"><span data-stu-id="ade92-118">Description</span></span>|  
|-------------|-----------------|  
|[\<faultPropagationQuery>](faultpropagationquery.md)|<span data-ttu-id="ade92-119">부모 활동에 의한 자식 활동 취소 요청을 추적하는 데 사용되는 구성 요소의 목록을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ade92-119">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="ade92-120">추적 참가자가 취소 요청 레코드 개체를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ade92-120">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ade92-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ade92-121">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CancelRequestedQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CancelRequestedQuery?displayProperty=nameWithType>
- [<span data-ttu-id="ade92-122">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="ade92-122">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="ade92-123">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="ade92-123">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
