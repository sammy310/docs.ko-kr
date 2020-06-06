---
title: <customTrackingQuery>WCF의
ms.date: 03/30/2017
ms.assetid: 164446ae-8440-4b67-b217-6786cfae1e01
ms.openlocfilehash: 204bbb6cf5ebcb30bf92b697885ecbbbd94385e0
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855425"
---
# <a name="customtrackingquery-of-wcf"></a><span data-ttu-id="4ab30-102">\<customTrackingQuery>WCF의</span><span class="sxs-lookup"><span data-stu-id="4ab30-102">\<customTrackingQuery> of WCF</span></span>

<span data-ttu-id="4ab30-103">코드 활동에서 정의 하는 이벤트를 추적 하는 데 사용 되는 쿼리를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4ab30-103">Represents a query that is used to track events that you define in your code activities.</span></span> <span data-ttu-id="4ab30-104">추적 참가자가 사용자 지정 추적 레코드를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="4ab30-104">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>

<span data-ttu-id="4ab30-105">추적 프로필 쿼리에 대 한 자세한 내용은 [추적 프로필](../../../windows-workflow-foundation/tracking-profiles.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4ab30-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customTrackingQueries>**](customtrackingqueries-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<customTrackingQuery>**  
  
## <a name="syntax"></a><span data-ttu-id="4ab30-106">구문</span><span class="sxs-lookup"><span data-stu-id="4ab30-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4ab30-107">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="4ab30-107">Attributes and elements</span></span>  

<span data-ttu-id="4ab30-108">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4ab30-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4ab30-109">특성</span><span class="sxs-lookup"><span data-stu-id="4ab30-109">Attributes</span></span>  
  
|<span data-ttu-id="4ab30-110">attribute</span><span class="sxs-lookup"><span data-stu-id="4ab30-110">Attribute</span></span>|<span data-ttu-id="4ab30-111">Description</span><span class="sxs-lookup"><span data-stu-id="4ab30-111">Description</span></span>|  
|---------------|-----------------|  
|`activityName`|<span data-ttu-id="4ab30-112">추적 레코드를 생성하는 활동의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="4ab30-112">A string that specifies the name of the activity that generated the tracking record.</span></span>|  
|`name`|<span data-ttu-id="4ab30-113">내보내는 사용자 지정 추적 레코드의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="4ab30-113">A string that specifies the name of the custom tracking record that is emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4ab30-114">자식 요소</span><span class="sxs-lookup"><span data-stu-id="4ab30-114">Child elements</span></span>

<span data-ttu-id="4ab30-115">없음</span><span class="sxs-lookup"><span data-stu-id="4ab30-115">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="4ab30-116">부모 요소</span><span class="sxs-lookup"><span data-stu-id="4ab30-116">Parent elements</span></span>

|<span data-ttu-id="4ab30-117">요소</span><span class="sxs-lookup"><span data-stu-id="4ab30-117">Element</span></span>|<span data-ttu-id="4ab30-118">Description</span><span class="sxs-lookup"><span data-stu-id="4ab30-118">Description</span></span>|  
|-------------|-----------------|  
|[\<customTrackingQueries>](customtrackingqueries-of-wcf.md)|<span data-ttu-id="4ab30-119">코드 활동에서 정의하는 이벤트를 추적하는 데 사용되는 쿼리의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4ab30-119">Represents a collection of queries that are used to track events that you define in your code activities.</span></span>|
  
## <a name="see-also"></a><span data-ttu-id="4ab30-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4ab30-120">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="4ab30-121">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="4ab30-121">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="4ab30-122">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="4ab30-122">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
