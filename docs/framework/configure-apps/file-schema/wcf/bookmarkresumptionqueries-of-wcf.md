---
description: '다음에 대 한 자세한 정보: <bookmarkResumptionQueries> WCF'
title: <bookmarkResumptionQueries> WCF의
ms.date: 03/30/2017
ms.assetid: ed086712-1dc7-4932-a592-d1116a0155f3
ms.openlocfilehash: dfe631865549915760255b1df22ee970b806e368
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99639369"
---
# <a name="bookmarkresumptionqueries-of-wcf"></a><span data-ttu-id="0afe9-103">\<bookmarkResumptionQueries> WCF의</span><span class="sxs-lookup"><span data-stu-id="0afe9-103">\<bookmarkResumptionQueries> of WCF</span></span>
  
<span data-ttu-id="0afe9-104">워크플로 인스턴스 내의 책갈피 다시 시작을 추적하는 데 사용되는 쿼리의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0afe9-104">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="0afe9-105">추적 참가자가 책갈피 다시 시작 레코드를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="0afe9-105">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
<span data-ttu-id="0afe9-106">추적 프로필 쿼리에 대 한 자세한 내용은 [추적 프로필](../../../windows-workflow-foundation/tracking-profiles.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0afe9-106">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<bookmarkResumptionQueries>**  

## <a name="syntax"></a><span data-ttu-id="0afe9-107">구문</span><span class="sxs-lookup"><span data-stu-id="0afe9-107">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <bookmarkResumptionQueries>
          <bookmarkResumptionQuery name="String" />
        </bookmarkResumptionQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0afe9-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="0afe9-108">Attributes and elements</span></span>  
  
<span data-ttu-id="0afe9-109">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0afe9-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0afe9-110">특성</span><span class="sxs-lookup"><span data-stu-id="0afe9-110">Attributes</span></span>  
  
<span data-ttu-id="0afe9-111">없음</span><span class="sxs-lookup"><span data-stu-id="0afe9-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="0afe9-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="0afe9-112">Child elements</span></span>  
  
|<span data-ttu-id="0afe9-113">요소</span><span class="sxs-lookup"><span data-stu-id="0afe9-113">Element</span></span>|<span data-ttu-id="0afe9-114">설명</span><span class="sxs-lookup"><span data-stu-id="0afe9-114">Description</span></span>|  
|-------------|-----------------|  
|[\<bookmarkResumptionQuery>](bookmarkresumptionquery-of-wcf.md)|<span data-ttu-id="0afe9-115">워크플로 인스턴스 내의 책갈피 다시 시작을 추적하는 데 사용되는 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="0afe9-115">A query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="0afe9-116">추적 참가자가 책갈피 다시 시작 레코드를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="0afe9-116">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0afe9-117">부모 요소</span><span class="sxs-lookup"><span data-stu-id="0afe9-117">Parent elements</span></span>  
  
|<span data-ttu-id="0afe9-118">요소</span><span class="sxs-lookup"><span data-stu-id="0afe9-118">Element</span></span>|<span data-ttu-id="0afe9-119">설명</span><span class="sxs-lookup"><span data-stu-id="0afe9-119">Description</span></span>|  
|-------------|-----------------|  
|[\<workflow>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="0afe9-120">`activityDefinitionId` 속성에 의해 식별되는 특정 워크플로에 대한 모든 쿼리를 포함하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="0afe9-120">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0afe9-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0afe9-121">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="0afe9-122">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="0afe9-122">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="0afe9-123">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="0afe9-123">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
