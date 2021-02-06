---
description: '다음에 대 한 자세한 정보: <cancelRequestedQuery> WCF'
title: <cancelRequestedQuery> WCF의
ms.date: 03/30/2017
ms.assetid: b690d870-02eb-4c56-8bc3-e5ca99d7097b
ms.openlocfilehash: e477e33650eb901cf2e9275570d8538196c52b6b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99639174"
---
# <a name="cancelrequestedquery-of-wcf"></a><span data-ttu-id="903b6-103">\<cancelRequestedQuery> WCF의</span><span class="sxs-lookup"><span data-stu-id="903b6-103">\<cancelRequestedQuery> of WCF</span></span>

<span data-ttu-id="903b6-104">부모 활동에 의한 자식 활동 취소 요청을 추적하는 데 사용되는 쿼리를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="903b6-104">Represents a query that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="903b6-105">추적 참가자가 취소 요청 레코드 개체를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="903b6-105">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
<span data-ttu-id="903b6-106">추적 프로필 쿼리에 대 한 자세한 내용은 [추적 프로필](../../../windows-workflow-foundation/tracking-profiles.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="903b6-106">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cancelRequestedQueries>**](cancelrequestedqueries-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cancelRequestedQuery>**  

## <a name="syntax"></a><span data-ttu-id="903b6-107">구문</span><span class="sxs-lookup"><span data-stu-id="903b6-107">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <cancelRequestedQueries>
          <cancelRequestedQuery activityName="String"
                                childActivityName="String" />
        </cancelRequestedQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="903b6-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="903b6-108">Attributes and elements</span></span>

<span data-ttu-id="903b6-109">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="903b6-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="903b6-110">특성</span><span class="sxs-lookup"><span data-stu-id="903b6-110">Attributes</span></span>  
  
|<span data-ttu-id="903b6-111">attribute</span><span class="sxs-lookup"><span data-stu-id="903b6-111">Attribute</span></span>|<span data-ttu-id="903b6-112">설명</span><span class="sxs-lookup"><span data-stu-id="903b6-112">Description</span></span>|  
|---------------|-----------------|  
|`activityName`|<span data-ttu-id="903b6-113">취소를 요청하는 활동의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="903b6-113">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|`childActivityName`|<span data-ttu-id="903b6-114">취소가 요청된 자식 활동의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="903b6-114">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="903b6-115">자식 요소</span><span class="sxs-lookup"><span data-stu-id="903b6-115">Child elements</span></span>

<span data-ttu-id="903b6-116">없음</span><span class="sxs-lookup"><span data-stu-id="903b6-116">None.</span></span>
  
### <a name="parent-elements"></a><span data-ttu-id="903b6-117">부모 요소</span><span class="sxs-lookup"><span data-stu-id="903b6-117">Parent elements</span></span>
  
|<span data-ttu-id="903b6-118">요소</span><span class="sxs-lookup"><span data-stu-id="903b6-118">Element</span></span>|<span data-ttu-id="903b6-119">설명</span><span class="sxs-lookup"><span data-stu-id="903b6-119">Description</span></span>|  
|-------------|-----------------|  
|[\<cancelRequestedQueries>](cancelrequestedqueries-of-wcf.md)|<span data-ttu-id="903b6-120">부모 활동에 의한 자식 활동 취소 요청을 추적하는 데 사용되는 쿼리의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="903b6-120">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="903b6-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="903b6-121">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CancelRequestedQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CancelRequestedQuery?displayProperty=nameWithType>
- [<span data-ttu-id="903b6-122">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="903b6-122">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="903b6-123">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="903b6-123">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
