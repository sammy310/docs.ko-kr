---
title: <bookmarkResumptionQuery>WCF의
ms.date: 03/30/2017
ms.assetid: 755a34f0-87c9-4a1e-ae4d-0fb8a6fbdc0e
ms.openlocfilehash: 8cb254599a9742305ec958fd77174f4c4b8a57c2
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "71834000"
---
# <a name="bookmarkresumptionquery-of-wcf"></a><span data-ttu-id="752b5-102">\<bookmarkResumptionQuery>WCF의</span><span class="sxs-lookup"><span data-stu-id="752b5-102">\<bookmarkResumptionQuery> of WCF</span></span>

<span data-ttu-id="752b5-103">워크플로 인스턴스 내의 책갈피 다시 시작을 추적하는 데 사용되는 쿼리를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="752b5-103">Represents a query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="752b5-104">추적 참가자가 책갈피 다시 시작 레코드를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="752b5-104">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
<span data-ttu-id="752b5-105">추적 프로필 쿼리에 대 한 자세한 내용은 [추적 프로필](../../../windows-workflow-foundation/tracking-profiles.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="752b5-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<bookmarkResumptionQueries>**](bookmarkresumptionqueries-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<bookmarkResumptionQuery>**  
  
## <a name="syntax"></a><span data-ttu-id="752b5-106">구문</span><span class="sxs-lookup"><span data-stu-id="752b5-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="752b5-107">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="752b5-107">Attributes and elements</span></span>

<span data-ttu-id="752b5-108">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="752b5-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="752b5-109">특성</span><span class="sxs-lookup"><span data-stu-id="752b5-109">Attributes</span></span>  
  
|<span data-ttu-id="752b5-110">attribute</span><span class="sxs-lookup"><span data-stu-id="752b5-110">Attribute</span></span>|<span data-ttu-id="752b5-111">Description</span><span class="sxs-lookup"><span data-stu-id="752b5-111">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="752b5-112">구독할 책갈피 레코드의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="752b5-112">A string that specifies the name of the bookmark record to subscribe to.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="752b5-113">자식 요소</span><span class="sxs-lookup"><span data-stu-id="752b5-113">Child elements</span></span>

<span data-ttu-id="752b5-114">없음</span><span class="sxs-lookup"><span data-stu-id="752b5-114">None.</span></span>
  
### <a name="parent-elements"></a><span data-ttu-id="752b5-115">부모 요소</span><span class="sxs-lookup"><span data-stu-id="752b5-115">Parent elements</span></span>  
  
|<span data-ttu-id="752b5-116">요소</span><span class="sxs-lookup"><span data-stu-id="752b5-116">Element</span></span>|<span data-ttu-id="752b5-117">Description</span><span class="sxs-lookup"><span data-stu-id="752b5-117">Description</span></span>|  
|-------------|-----------------|  
|[\<bookmarkResumptionQueries>](bookmarkresumptionqueries-of-wcf.md)|<span data-ttu-id="752b5-118">워크플로 인스턴스 내의 책갈피 다시 시작을 추적하는 데 사용되는 쿼리의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="752b5-118">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="752b5-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="752b5-119">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="752b5-120">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="752b5-120">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="752b5-121">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="752b5-121">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
