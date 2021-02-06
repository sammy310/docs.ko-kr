---
description: 다음에 대해 자세히 알아보세요. <cancelRequestedQuery>
title: <cancelRequestedQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 8da9b1c4-338a-4f23-9830-6d257772d340
ms.openlocfilehash: efd908fb52d2bc32bf05fce9099c7105abdc9b1a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99652642"
---
# \<cancelRequestedQuery>

<span data-ttu-id="a6e42-102">부모 활동에 의한 자식 활동 취소 요청을 추적하는 데 사용되는 쿼리를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a6e42-102">Represents a query that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="a6e42-103">추적 참가자가 취소 요청 레코드 개체를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="a6e42-103">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="a6e42-104">추적 프로필 쿼리에 대 한 자세한 내용은 [추적 프로필](../../../windows-workflow-foundation/tracking-profiles.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a6e42-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cancelRequestedQueries>**](cancelrequestedqueries.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cancelRequestedQuery>**  
  
## <a name="syntax"></a><span data-ttu-id="a6e42-105">구문</span><span class="sxs-lookup"><span data-stu-id="a6e42-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a6e42-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="a6e42-106">Attributes and Elements</span></span>  

 <span data-ttu-id="a6e42-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a6e42-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a6e42-108">특성</span><span class="sxs-lookup"><span data-stu-id="a6e42-108">Attributes</span></span>  
  
|<span data-ttu-id="a6e42-109">attribute</span><span class="sxs-lookup"><span data-stu-id="a6e42-109">Attribute</span></span>|<span data-ttu-id="a6e42-110">설명</span><span class="sxs-lookup"><span data-stu-id="a6e42-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a6e42-111">activityName</span><span class="sxs-lookup"><span data-stu-id="a6e42-111">activityName</span></span>|<span data-ttu-id="a6e42-112">취소를 요청하는 활동의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="a6e42-112">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="a6e42-113">childActivityName</span><span class="sxs-lookup"><span data-stu-id="a6e42-113">childActivityName</span></span>|<span data-ttu-id="a6e42-114">취소가 요청된 자식 활동의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="a6e42-114">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a6e42-115">자식 요소</span><span class="sxs-lookup"><span data-stu-id="a6e42-115">Child Elements</span></span>  

 <span data-ttu-id="a6e42-116">없음</span><span class="sxs-lookup"><span data-stu-id="a6e42-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a6e42-117">부모 요소</span><span class="sxs-lookup"><span data-stu-id="a6e42-117">Parent Elements</span></span>  
  
|<span data-ttu-id="a6e42-118">요소</span><span class="sxs-lookup"><span data-stu-id="a6e42-118">Element</span></span>|<span data-ttu-id="a6e42-119">설명</span><span class="sxs-lookup"><span data-stu-id="a6e42-119">Description</span></span>|  
|-------------|-----------------|  
|[\<faultPropagationQuery>](faultpropagationquery.md)|<span data-ttu-id="a6e42-120">부모 활동에 의한 자식 활동 취소 요청을 추적하는 데 사용되는 구성 요소의 목록을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a6e42-120">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="a6e42-121">추적 참가자가 취소 요청 레코드 개체를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="a6e42-121">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a6e42-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a6e42-122">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CancelRequestedQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CancelRequestedQuery?displayProperty=nameWithType>
- [<span data-ttu-id="a6e42-123">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="a6e42-123">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="a6e42-124">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="a6e42-124">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
