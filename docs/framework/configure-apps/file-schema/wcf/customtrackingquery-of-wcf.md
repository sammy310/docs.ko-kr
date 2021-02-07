---
description: '다음에 대 한 자세한 정보: <customTrackingQuery> WCF'
title: <customTrackingQuery> WCF의
ms.date: 03/30/2017
ms.assetid: 164446ae-8440-4b67-b217-6786cfae1e01
ms.openlocfilehash: 3eac26ee94a95b480d743e3c6ec554a84b8747a3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99754461"
---
# <a name="customtrackingquery-of-wcf"></a><span data-ttu-id="69efa-103">\<customTrackingQuery> WCF의</span><span class="sxs-lookup"><span data-stu-id="69efa-103">\<customTrackingQuery> of WCF</span></span>

<span data-ttu-id="69efa-104">코드 활동에서 정의 하는 이벤트를 추적 하는 데 사용 되는 쿼리를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="69efa-104">Represents a query that is used to track events that you define in your code activities.</span></span> <span data-ttu-id="69efa-105">추적 참가자가 사용자 지정 추적 레코드를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="69efa-105">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>

<span data-ttu-id="69efa-106">추적 프로필 쿼리에 대 한 자세한 내용은 [추적 프로필](../../../windows-workflow-foundation/tracking-profiles.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="69efa-106">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customTrackingQueries>**](customtrackingqueries-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<customTrackingQuery>**  
  
## <a name="syntax"></a><span data-ttu-id="69efa-107">구문</span><span class="sxs-lookup"><span data-stu-id="69efa-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="69efa-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="69efa-108">Attributes and elements</span></span>  

<span data-ttu-id="69efa-109">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="69efa-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="69efa-110">특성</span><span class="sxs-lookup"><span data-stu-id="69efa-110">Attributes</span></span>  
  
|<span data-ttu-id="69efa-111">attribute</span><span class="sxs-lookup"><span data-stu-id="69efa-111">Attribute</span></span>|<span data-ttu-id="69efa-112">설명</span><span class="sxs-lookup"><span data-stu-id="69efa-112">Description</span></span>|  
|---------------|-----------------|  
|`activityName`|<span data-ttu-id="69efa-113">추적 레코드를 생성하는 활동의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="69efa-113">A string that specifies the name of the activity that generated the tracking record.</span></span>|  
|`name`|<span data-ttu-id="69efa-114">내보내는 사용자 지정 추적 레코드의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="69efa-114">A string that specifies the name of the custom tracking record that is emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="69efa-115">자식 요소</span><span class="sxs-lookup"><span data-stu-id="69efa-115">Child elements</span></span>

<span data-ttu-id="69efa-116">없음</span><span class="sxs-lookup"><span data-stu-id="69efa-116">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="69efa-117">부모 요소</span><span class="sxs-lookup"><span data-stu-id="69efa-117">Parent elements</span></span>

|<span data-ttu-id="69efa-118">요소</span><span class="sxs-lookup"><span data-stu-id="69efa-118">Element</span></span>|<span data-ttu-id="69efa-119">설명</span><span class="sxs-lookup"><span data-stu-id="69efa-119">Description</span></span>|  
|-------------|-----------------|  
|[\<customTrackingQueries>](customtrackingqueries-of-wcf.md)|<span data-ttu-id="69efa-120">코드 활동에서 정의하는 이벤트를 추적하는 데 사용되는 쿼리의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="69efa-120">Represents a collection of queries that are used to track events that you define in your code activities.</span></span>|
  
## <a name="see-also"></a><span data-ttu-id="69efa-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="69efa-121">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="69efa-122">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="69efa-122">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="69efa-123">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="69efa-123">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
