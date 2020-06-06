---
title: <customTrackingQueries>WCF의
ms.date: 03/30/2017
ms.assetid: 14cfe47e-9935-4120-84f1-8f38de8ca4c1
ms.openlocfilehash: 2c4bd74ae346c536e8bc0ae454e638b7c76a40fc
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855438"
---
# <a name="customtrackingqueries-of-wcf"></a><span data-ttu-id="34235-102">\<customTrackingQueries>WCF의</span><span class="sxs-lookup"><span data-stu-id="34235-102">\<customTrackingQueries> of WCF</span></span>

<span data-ttu-id="34235-103">코드 활동에서 정의하는 이벤트를 추적하는 데 사용되는 쿼리의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="34235-103">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="34235-104">추적 참가자가 사용자 지정 추적 레코드를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="34235-104">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
<span data-ttu-id="34235-105">추적 프로필 쿼리에 대 한 자세한 내용은 [추적 프로필](../../../windows-workflow-foundation/tracking-profiles.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="34235-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<customTrackingQueries>**  

## <a name="syntax"></a><span data-ttu-id="34235-106">구문</span><span class="sxs-lookup"><span data-stu-id="34235-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="34235-107">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="34235-107">Attributes and elements</span></span>

<span data-ttu-id="34235-108">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="34235-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="34235-109">특성</span><span class="sxs-lookup"><span data-stu-id="34235-109">Attributes</span></span>

<span data-ttu-id="34235-110">없음</span><span class="sxs-lookup"><span data-stu-id="34235-110">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="34235-111">자식 요소</span><span class="sxs-lookup"><span data-stu-id="34235-111">Child elements</span></span>
  
|<span data-ttu-id="34235-112">요소</span><span class="sxs-lookup"><span data-stu-id="34235-112">Element</span></span>|<span data-ttu-id="34235-113">Description</span><span class="sxs-lookup"><span data-stu-id="34235-113">Description</span></span>|  
|-------------|-----------------|  
|[\<customTrackingQuery>](customtrackingquery-of-wcf.md)|<span data-ttu-id="34235-114">코드 활동에서 정의하는 이벤트를 추적하기 위해 사용되는 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="34235-114">A query that is used to track events that you define in your code activities.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="34235-115">부모 요소</span><span class="sxs-lookup"><span data-stu-id="34235-115">Parent elements</span></span>  
  
|<span data-ttu-id="34235-116">요소</span><span class="sxs-lookup"><span data-stu-id="34235-116">Element</span></span>|<span data-ttu-id="34235-117">Description</span><span class="sxs-lookup"><span data-stu-id="34235-117">Description</span></span>|  
|-------------|-----------------|  
|[\<workflow>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="34235-118">`activityDefinitionId` 속성에 의해 식별되는 특정 워크플로에 대한 모든 쿼리를 포함하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="34235-118">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="34235-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="34235-119">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="34235-120">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="34235-120">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="34235-121">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="34235-121">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
