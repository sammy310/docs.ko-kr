---
description: 다음에 대해 자세히 알아보세요. <faultPropagationQueries>
title: <faultPropagationQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 00ff90ae-ebe0-4c85-a93f-61557288d0a3
ms.openlocfilehash: 13bd19a3673846bfbd641cd2f8eeafc20b8186f8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99719072"
---
# \<faultPropagationQueries>

<span data-ttu-id="f677f-102">활동 내에서 발생하는 오류의 처리를 추적하는 데 사용되는 쿼리 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f677f-102">Represents a collection of queries that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="f677f-103">이 이벤트는 FaultHandler가 오류를 처리할 때마다 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="f677f-103">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="f677f-104">활동 내에서 발생하는 오류 처리를 추적하려면 이러한 쿼리를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f677f-104">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="f677f-105">추적 참가자가 오류 전파 레코드를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f677f-105">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>  
  
 <span data-ttu-id="f677f-106">추적 프로필 쿼리에 대 한 자세한 내용은 [추적 프로필](../../../windows-workflow-foundation/tracking-profiles.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f677f-106">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<faultPropagationQueries>**
  
## <a name="syntax"></a><span data-ttu-id="f677f-107">구문</span><span class="sxs-lookup"><span data-stu-id="f677f-107">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <faultPropagationQueries>
        <faultPropagationQuery activityName="String"
                               faultHandlerActivityName="String" />
      </faultPropagationQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f677f-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="f677f-108">Attributes and Elements</span></span>  

 <span data-ttu-id="f677f-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f677f-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f677f-110">특성</span><span class="sxs-lookup"><span data-stu-id="f677f-110">Attributes</span></span>  

 <span data-ttu-id="f677f-111">없음</span><span class="sxs-lookup"><span data-stu-id="f677f-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f677f-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="f677f-112">Child Elements</span></span>  
  
|<span data-ttu-id="f677f-113">요소</span><span class="sxs-lookup"><span data-stu-id="f677f-113">Element</span></span>|<span data-ttu-id="f677f-114">설명</span><span class="sxs-lookup"><span data-stu-id="f677f-114">Description</span></span>|  
|-------------|-----------------|  
|[\<faultPropagationQuery>](faultpropagationquery.md)|<span data-ttu-id="f677f-115">활동 내에서 발생하는 오류의 처리를 추적하는 데 사용되는 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="f677f-115">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="f677f-116">이 이벤트는 FaultHandler가 오류를 처리할 때마다 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="f677f-116">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f677f-117">부모 요소</span><span class="sxs-lookup"><span data-stu-id="f677f-117">Parent Elements</span></span>  
  
|<span data-ttu-id="f677f-118">요소</span><span class="sxs-lookup"><span data-stu-id="f677f-118">Element</span></span>|<span data-ttu-id="f677f-119">설명</span><span class="sxs-lookup"><span data-stu-id="f677f-119">Description</span></span>|  
|-------------|-----------------|  
|[\<workflow>](workflow.md)|<span data-ttu-id="f677f-120">**ActivityDefinitionId** 속성으로 식별 되는 특정 워크플로에 대 한 모든 쿼리를 포함 하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="f677f-120">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f677f-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f677f-121">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="f677f-122">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="f677f-122">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="f677f-123">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="f677f-123">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
