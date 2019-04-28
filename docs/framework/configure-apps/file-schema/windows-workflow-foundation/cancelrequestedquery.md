---
title: <cancelRequestedQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 8da9b1c4-338a-4f23-9830-6d257772d340
ms.openlocfilehash: 5f2e46d5e4cdd64c37219476790b9ff92c606b6b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61790236"
---
# <a name="cancelrequestedquery"></a><span data-ttu-id="debdc-101">\<cancelRequestedQuery></span><span class="sxs-lookup"><span data-stu-id="debdc-101">\<cancelRequestedQuery></span></span>
<span data-ttu-id="debdc-102">부모 활동에 의한 자식 활동 취소 요청을 추적하는 데 사용되는 쿼리를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="debdc-102">Represents a query that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="debdc-103">추적 참가자가 취소 요청 레코드 개체를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="debdc-103">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="debdc-104">추적 프로필 쿼리에 대 한 자세한 내용은 참조 하세요. [추적 프로필](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="debdc-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="debdc-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="debdc-105">\<system.serviceModel></span></span>  
<span data-ttu-id="debdc-106">\<tracking></span><span class="sxs-lookup"><span data-stu-id="debdc-106">\<tracking></span></span>  
<span data-ttu-id="debdc-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="debdc-107">\<trackingProfile></span></span>  
<span data-ttu-id="debdc-108">\<workflow></span><span class="sxs-lookup"><span data-stu-id="debdc-108">\<workflow></span></span>  
<span data-ttu-id="debdc-109">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="debdc-109">\<cancelRequestedQueries></span></span>  
<span data-ttu-id="debdc-110">\<cancelRequestedQuery></span><span class="sxs-lookup"><span data-stu-id="debdc-110">\<cancelRequestedQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="debdc-111">구문</span><span class="sxs-lookup"><span data-stu-id="debdc-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="debdc-112">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="debdc-112">Attributes and Elements</span></span>  
 <span data-ttu-id="debdc-113">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="debdc-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="debdc-114">특성</span><span class="sxs-lookup"><span data-stu-id="debdc-114">Attributes</span></span>  
  
|<span data-ttu-id="debdc-115">특성</span><span class="sxs-lookup"><span data-stu-id="debdc-115">Attribute</span></span>|<span data-ttu-id="debdc-116">설명</span><span class="sxs-lookup"><span data-stu-id="debdc-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="debdc-117">activityName</span><span class="sxs-lookup"><span data-stu-id="debdc-117">activityName</span></span>|<span data-ttu-id="debdc-118">취소를 요청하는 활동의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="debdc-118">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="debdc-119">childActivityName</span><span class="sxs-lookup"><span data-stu-id="debdc-119">childActivityName</span></span>|<span data-ttu-id="debdc-120">취소가 요청된 자식 활동의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="debdc-120">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="debdc-121">자식 요소</span><span class="sxs-lookup"><span data-stu-id="debdc-121">Child Elements</span></span>  
 <span data-ttu-id="debdc-122">없음</span><span class="sxs-lookup"><span data-stu-id="debdc-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="debdc-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="debdc-123">Parent Elements</span></span>  
  
|<span data-ttu-id="debdc-124">요소</span><span class="sxs-lookup"><span data-stu-id="debdc-124">Element</span></span>|<span data-ttu-id="debdc-125">설명</span><span class="sxs-lookup"><span data-stu-id="debdc-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="debdc-126">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="debdc-126">\<faultPropagationQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationquery.md)|<span data-ttu-id="debdc-127">부모 활동에 의한 자식 활동 취소 요청을 추적하는 데 사용되는 구성 요소의 목록을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="debdc-127">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="debdc-128">추적 참가자가 취소 요청 레코드 개체를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="debdc-128">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="debdc-129">참고자료</span><span class="sxs-lookup"><span data-stu-id="debdc-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CancelRequestedQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CancelRequestedQuery?displayProperty=nameWithType>
- [<span data-ttu-id="debdc-130">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="debdc-130">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="debdc-131">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="debdc-131">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
