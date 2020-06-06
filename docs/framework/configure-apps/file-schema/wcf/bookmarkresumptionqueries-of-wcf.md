---
title: <bookmarkResumptionQueries>WCF의
ms.date: 03/30/2017
ms.assetid: ed086712-1dc7-4932-a592-d1116a0155f3
ms.openlocfilehash: 94ff9f44f295b45c03e1bd8f52a85d6b7b0c6e3b
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "70850131"
---
# <a name="bookmarkresumptionqueries-of-wcf"></a><span data-ttu-id="738e8-102">\<bookmarkResumptionQueries>WCF의</span><span class="sxs-lookup"><span data-stu-id="738e8-102">\<bookmarkResumptionQueries> of WCF</span></span>
  
<span data-ttu-id="738e8-103">워크플로 인스턴스 내의 책갈피 다시 시작을 추적하는 데 사용되는 쿼리의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="738e8-103">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="738e8-104">추적 참가자가 책갈피 다시 시작 레코드를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="738e8-104">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
<span data-ttu-id="738e8-105">추적 프로필 쿼리에 대 한 자세한 내용은 [추적 프로필](../../../windows-workflow-foundation/tracking-profiles.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="738e8-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<bookmarkResumptionQueries>**  

## <a name="syntax"></a><span data-ttu-id="738e8-106">구문</span><span class="sxs-lookup"><span data-stu-id="738e8-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="738e8-107">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="738e8-107">Attributes and elements</span></span>  
  
<span data-ttu-id="738e8-108">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="738e8-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="738e8-109">특성</span><span class="sxs-lookup"><span data-stu-id="738e8-109">Attributes</span></span>  
  
<span data-ttu-id="738e8-110">없음</span><span class="sxs-lookup"><span data-stu-id="738e8-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="738e8-111">자식 요소</span><span class="sxs-lookup"><span data-stu-id="738e8-111">Child elements</span></span>  
  
|<span data-ttu-id="738e8-112">요소</span><span class="sxs-lookup"><span data-stu-id="738e8-112">Element</span></span>|<span data-ttu-id="738e8-113">Description</span><span class="sxs-lookup"><span data-stu-id="738e8-113">Description</span></span>|  
|-------------|-----------------|  
|[\<bookmarkResumptionQuery>](bookmarkresumptionquery-of-wcf.md)|<span data-ttu-id="738e8-114">워크플로 인스턴스 내의 책갈피 다시 시작을 추적하는 데 사용되는 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="738e8-114">A query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="738e8-115">추적 참가자가 책갈피 다시 시작 레코드를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="738e8-115">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="738e8-116">부모 요소</span><span class="sxs-lookup"><span data-stu-id="738e8-116">Parent elements</span></span>  
  
|<span data-ttu-id="738e8-117">요소</span><span class="sxs-lookup"><span data-stu-id="738e8-117">Element</span></span>|<span data-ttu-id="738e8-118">Description</span><span class="sxs-lookup"><span data-stu-id="738e8-118">Description</span></span>|  
|-------------|-----------------|  
|[\<workflow>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="738e8-119">`activityDefinitionId` 속성에 의해 식별되는 특정 워크플로에 대한 모든 쿼리를 포함하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="738e8-119">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="738e8-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="738e8-120">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="738e8-121">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="738e8-121">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="738e8-122">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="738e8-122">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
