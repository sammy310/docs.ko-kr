---
description: '다음에 대 한 자세한 정보: <bookmarkResumptionQuery> WCF'
title: <bookmarkResumptionQuery> WCF의
ms.date: 03/30/2017
ms.assetid: 755a34f0-87c9-4a1e-ae4d-0fb8a6fbdc0e
ms.openlocfilehash: 9dadab3e304a2507a404bf43c377df46d5b33dda
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99639330"
---
# <a name="bookmarkresumptionquery-of-wcf"></a><span data-ttu-id="96064-103">\<bookmarkResumptionQuery> WCF의</span><span class="sxs-lookup"><span data-stu-id="96064-103">\<bookmarkResumptionQuery> of WCF</span></span>

<span data-ttu-id="96064-104">워크플로 인스턴스 내의 책갈피 다시 시작을 추적하는 데 사용되는 쿼리를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="96064-104">Represents a query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="96064-105">추적 참가자가 책갈피 다시 시작 레코드를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="96064-105">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
<span data-ttu-id="96064-106">추적 프로필 쿼리에 대 한 자세한 내용은 [추적 프로필](../../../windows-workflow-foundation/tracking-profiles.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="96064-106">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<bookmarkResumptionQueries>**](bookmarkresumptionqueries-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<bookmarkResumptionQuery>**  
  
## <a name="syntax"></a><span data-ttu-id="96064-107">구문</span><span class="sxs-lookup"><span data-stu-id="96064-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="96064-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="96064-108">Attributes and elements</span></span>

<span data-ttu-id="96064-109">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="96064-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="96064-110">특성</span><span class="sxs-lookup"><span data-stu-id="96064-110">Attributes</span></span>  
  
|<span data-ttu-id="96064-111">attribute</span><span class="sxs-lookup"><span data-stu-id="96064-111">Attribute</span></span>|<span data-ttu-id="96064-112">설명</span><span class="sxs-lookup"><span data-stu-id="96064-112">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="96064-113">구독할 책갈피 레코드의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="96064-113">A string that specifies the name of the bookmark record to subscribe to.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="96064-114">자식 요소</span><span class="sxs-lookup"><span data-stu-id="96064-114">Child elements</span></span>

<span data-ttu-id="96064-115">없음</span><span class="sxs-lookup"><span data-stu-id="96064-115">None.</span></span>
  
### <a name="parent-elements"></a><span data-ttu-id="96064-116">부모 요소</span><span class="sxs-lookup"><span data-stu-id="96064-116">Parent elements</span></span>  
  
|<span data-ttu-id="96064-117">요소</span><span class="sxs-lookup"><span data-stu-id="96064-117">Element</span></span>|<span data-ttu-id="96064-118">설명</span><span class="sxs-lookup"><span data-stu-id="96064-118">Description</span></span>|  
|-------------|-----------------|  
|[\<bookmarkResumptionQueries>](bookmarkresumptionqueries-of-wcf.md)|<span data-ttu-id="96064-119">워크플로 인스턴스 내의 책갈피 다시 시작을 추적하는 데 사용되는 쿼리의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="96064-119">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="96064-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="96064-120">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="96064-121">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="96064-121">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="96064-122">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="96064-122">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
