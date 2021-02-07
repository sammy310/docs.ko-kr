---
description: 다음에 대해 자세히 알아보세요. <bookmarkResumptionQuery>
title: <bookmarkResumptionQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 226de75d-d25c-48d5-b069-4b7d80a6852b
ms.openlocfilehash: 4e6637b6edd54d9c1cf1a44986b362eb616bf14d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99725248"
---
# \<bookmarkResumptionQuery>

<span data-ttu-id="d6d03-102">워크플로 인스턴스 내의 책갈피 다시 시작을 추적하는 데 사용되는 쿼리를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d6d03-102">Represents a query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="d6d03-103">추적 참가자가 책갈피 다시 시작 레코드를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d03-103">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="d6d03-104">추적 프로필 쿼리에 대 한 자세한 내용은 [추적 프로필](../../../windows-workflow-foundation/tracking-profiles.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d6d03-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<bookmarkResumptionQueries>**](bookmarkresumptionqueries.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<bookmarkResumptionQuery>**  
  
## <a name="syntax"></a><span data-ttu-id="d6d03-105">구문</span><span class="sxs-lookup"><span data-stu-id="d6d03-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d6d03-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="d6d03-106">Attributes and Elements</span></span>  

 <span data-ttu-id="d6d03-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d03-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d6d03-108">특성</span><span class="sxs-lookup"><span data-stu-id="d6d03-108">Attributes</span></span>  
  
|<span data-ttu-id="d6d03-109">attribute</span><span class="sxs-lookup"><span data-stu-id="d6d03-109">Attribute</span></span>|<span data-ttu-id="d6d03-110">설명</span><span class="sxs-lookup"><span data-stu-id="d6d03-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d6d03-111">name</span><span class="sxs-lookup"><span data-stu-id="d6d03-111">name</span></span>|<span data-ttu-id="d6d03-112">구독할 책갈피 레코드의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="d6d03-112">A string that specifies the name of the bookmark record to subscribe to.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d6d03-113">자식 요소</span><span class="sxs-lookup"><span data-stu-id="d6d03-113">Child Elements</span></span>  

 <span data-ttu-id="d6d03-114">없음</span><span class="sxs-lookup"><span data-stu-id="d6d03-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d6d03-115">부모 요소</span><span class="sxs-lookup"><span data-stu-id="d6d03-115">Parent Elements</span></span>  
  
|<span data-ttu-id="d6d03-116">요소</span><span class="sxs-lookup"><span data-stu-id="d6d03-116">Element</span></span>|<span data-ttu-id="d6d03-117">설명</span><span class="sxs-lookup"><span data-stu-id="d6d03-117">Description</span></span>|  
|-------------|-----------------|  
|[\<bookmarkResumptionQueries>](bookmarkresumptionqueries.md)|<span data-ttu-id="d6d03-118">워크플로 인스턴스 내의 책갈피 다시 시작을 추적하는 데 사용되는 쿼리의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d6d03-118">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d6d03-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d6d03-119">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="d6d03-120">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="d6d03-120">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="d6d03-121">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="d6d03-121">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
