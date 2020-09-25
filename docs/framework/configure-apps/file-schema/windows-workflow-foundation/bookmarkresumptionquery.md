---
title: <bookmarkResumptionQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 226de75d-d25c-48d5-b069-4b7d80a6852b
ms.openlocfilehash: efd1e4e54223ff9f5d60b4087fbe5b6bebf1af2f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91189592"
---
# \<bookmarkResumptionQuery>

<span data-ttu-id="e1cc4-101">워크플로 인스턴스 내의 책갈피 다시 시작을 추적하는 데 사용되는 쿼리를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e1cc4-101">Represents a query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="e1cc4-102">추적 참가자가 책갈피 다시 시작 레코드를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="e1cc4-102">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="e1cc4-103">추적 프로필 쿼리에 대 한 자세한 내용은 [추적 프로필](../../../windows-workflow-foundation/tracking-profiles.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e1cc4-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<bookmarkResumptionQueries>**](bookmarkresumptionqueries.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<bookmarkResumptionQuery>**  
  
## <a name="syntax"></a><span data-ttu-id="e1cc4-104">구문</span><span class="sxs-lookup"><span data-stu-id="e1cc4-104">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <bookmarkResumptionQueries>
        <bookmarkResumptionQuery name="String" />
      </bookmarkResumptionQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e1cc4-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="e1cc4-105">Attributes and Elements</span></span>  

 <span data-ttu-id="e1cc4-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e1cc4-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e1cc4-107">특성</span><span class="sxs-lookup"><span data-stu-id="e1cc4-107">Attributes</span></span>  
  
|<span data-ttu-id="e1cc4-108">attribute</span><span class="sxs-lookup"><span data-stu-id="e1cc4-108">Attribute</span></span>|<span data-ttu-id="e1cc4-109">Description</span><span class="sxs-lookup"><span data-stu-id="e1cc4-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e1cc4-110">name</span><span class="sxs-lookup"><span data-stu-id="e1cc4-110">name</span></span>|<span data-ttu-id="e1cc4-111">구독할 책갈피 레코드의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="e1cc4-111">A string that specifies the name of the bookmark record to subscribe to.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e1cc4-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="e1cc4-112">Child Elements</span></span>  

 <span data-ttu-id="e1cc4-113">없음</span><span class="sxs-lookup"><span data-stu-id="e1cc4-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e1cc4-114">부모 요소</span><span class="sxs-lookup"><span data-stu-id="e1cc4-114">Parent Elements</span></span>  
  
|<span data-ttu-id="e1cc4-115">요소</span><span class="sxs-lookup"><span data-stu-id="e1cc4-115">Element</span></span>|<span data-ttu-id="e1cc4-116">설명</span><span class="sxs-lookup"><span data-stu-id="e1cc4-116">Description</span></span>|  
|-------------|-----------------|  
|[\<bookmarkResumptionQueries>](bookmarkresumptionqueries.md)|<span data-ttu-id="e1cc4-117">워크플로 인스턴스 내의 책갈피 다시 시작을 추적하는 데 사용되는 쿼리의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e1cc4-117">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e1cc4-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e1cc4-118">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="e1cc4-119">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="e1cc4-119">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="e1cc4-120">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="e1cc4-120">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
