---
description: '다음에 대 한 자세한 정보: <customTrackingQueries> WCF'
title: <customTrackingQueries> WCF의
ms.date: 03/30/2017
ms.assetid: 14cfe47e-9935-4120-84f1-8f38de8ca4c1
ms.openlocfilehash: ac1cdcc074201b97344b3727f6957e1b62c88dab
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99754474"
---
# <a name="customtrackingqueries-of-wcf"></a><span data-ttu-id="6556e-103">\<customTrackingQueries> WCF의</span><span class="sxs-lookup"><span data-stu-id="6556e-103">\<customTrackingQueries> of WCF</span></span>

<span data-ttu-id="6556e-104">코드 활동에서 정의하는 이벤트를 추적하는 데 사용되는 쿼리의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6556e-104">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="6556e-105">추적 참가자가 사용자 지정 추적 레코드를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="6556e-105">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
<span data-ttu-id="6556e-106">추적 프로필 쿼리에 대 한 자세한 내용은 [추적 프로필](../../../windows-workflow-foundation/tracking-profiles.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6556e-106">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<customTrackingQueries>**  

## <a name="syntax"></a><span data-ttu-id="6556e-107">구문</span><span class="sxs-lookup"><span data-stu-id="6556e-107">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <customTrackingQueries>
          <customTrackingQuery activityName="String"
                               name="String"/>
        </customTrackingQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6556e-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="6556e-108">Attributes and elements</span></span>

<span data-ttu-id="6556e-109">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6556e-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6556e-110">특성</span><span class="sxs-lookup"><span data-stu-id="6556e-110">Attributes</span></span>

<span data-ttu-id="6556e-111">없음</span><span class="sxs-lookup"><span data-stu-id="6556e-111">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="6556e-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="6556e-112">Child elements</span></span>
  
|<span data-ttu-id="6556e-113">요소</span><span class="sxs-lookup"><span data-stu-id="6556e-113">Element</span></span>|<span data-ttu-id="6556e-114">설명</span><span class="sxs-lookup"><span data-stu-id="6556e-114">Description</span></span>|  
|-------------|-----------------|  
|[\<customTrackingQuery>](customtrackingquery-of-wcf.md)|<span data-ttu-id="6556e-115">코드 활동에서 정의하는 이벤트를 추적하기 위해 사용되는 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="6556e-115">A query that is used to track events that you define in your code activities.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6556e-116">부모 요소</span><span class="sxs-lookup"><span data-stu-id="6556e-116">Parent elements</span></span>  
  
|<span data-ttu-id="6556e-117">요소</span><span class="sxs-lookup"><span data-stu-id="6556e-117">Element</span></span>|<span data-ttu-id="6556e-118">설명</span><span class="sxs-lookup"><span data-stu-id="6556e-118">Description</span></span>|  
|-------------|-----------------|  
|[\<workflow>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="6556e-119">`activityDefinitionId` 속성에 의해 식별되는 특정 워크플로에 대한 모든 쿼리를 포함하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="6556e-119">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6556e-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6556e-120">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="6556e-121">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="6556e-121">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="6556e-122">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="6556e-122">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
