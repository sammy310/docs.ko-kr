---
title: <faultPropagationQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 00ff90ae-ebe0-4c85-a93f-61557288d0a3
ms.openlocfilehash: 24e9136729df1352ebb1e665d1ebaf0ce9dc28a5
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91175839"
---
# \<faultPropagationQueries>

<span data-ttu-id="5a92c-101">활동 내에서 발생하는 오류의 처리를 추적하는 데 사용되는 쿼리 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5a92c-101">Represents a collection of queries that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="5a92c-102">이 이벤트는 FaultHandler가 오류를 처리할 때마다 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="5a92c-102">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="5a92c-103">활동 내에서 발생하는 오류 처리를 추적하려면 이러한 쿼리를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a92c-103">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="5a92c-104">추적 참가자가 오류 전파 레코드를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="5a92c-104">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>  
  
 <span data-ttu-id="5a92c-105">추적 프로필 쿼리에 대 한 자세한 내용은 [추적 프로필](../../../windows-workflow-foundation/tracking-profiles.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5a92c-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<faultPropagationQueries>**
  
## <a name="syntax"></a><span data-ttu-id="5a92c-106">구문</span><span class="sxs-lookup"><span data-stu-id="5a92c-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5a92c-107">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="5a92c-107">Attributes and Elements</span></span>  

 <span data-ttu-id="5a92c-108">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5a92c-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5a92c-109">특성</span><span class="sxs-lookup"><span data-stu-id="5a92c-109">Attributes</span></span>  

 <span data-ttu-id="5a92c-110">없음</span><span class="sxs-lookup"><span data-stu-id="5a92c-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="5a92c-111">자식 요소</span><span class="sxs-lookup"><span data-stu-id="5a92c-111">Child Elements</span></span>  
  
|<span data-ttu-id="5a92c-112">요소</span><span class="sxs-lookup"><span data-stu-id="5a92c-112">Element</span></span>|<span data-ttu-id="5a92c-113">설명</span><span class="sxs-lookup"><span data-stu-id="5a92c-113">Description</span></span>|  
|-------------|-----------------|  
|[\<faultPropagationQuery>](faultpropagationquery.md)|<span data-ttu-id="5a92c-114">활동 내에서 발생하는 오류의 처리를 추적하는 데 사용되는 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="5a92c-114">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="5a92c-115">이 이벤트는 FaultHandler가 오류를 처리할 때마다 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="5a92c-115">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5a92c-116">부모 요소</span><span class="sxs-lookup"><span data-stu-id="5a92c-116">Parent Elements</span></span>  
  
|<span data-ttu-id="5a92c-117">요소</span><span class="sxs-lookup"><span data-stu-id="5a92c-117">Element</span></span>|<span data-ttu-id="5a92c-118">설명</span><span class="sxs-lookup"><span data-stu-id="5a92c-118">Description</span></span>|  
|-------------|-----------------|  
|[\<workflow>](workflow.md)|<span data-ttu-id="5a92c-119">**ActivityDefinitionId** 속성으로 식별 되는 특정 워크플로에 대 한 모든 쿼리를 포함 하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="5a92c-119">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5a92c-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5a92c-120">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="5a92c-121">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="5a92c-121">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="5a92c-122">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="5a92c-122">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
