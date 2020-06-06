---
title: <faultPropagationQueries>WCF의
ms.date: 03/30/2017
ms.assetid: d85f66a7-e7b0-4dbb-83cc-89fa06fc9161
ms.openlocfilehash: 709c2c6907b4d0d28118f9de12edb047aa16d741
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855269"
---
# <a name="faultpropagationqueries-of-wcf"></a><span data-ttu-id="cc948-102">\<faultPropagationQueries>WCF의</span><span class="sxs-lookup"><span data-stu-id="cc948-102">\<faultPropagationQueries> of WCF</span></span>

<span data-ttu-id="cc948-103">활동 내에서 발생하는 오류의 처리를 추적하는 데 사용되는 쿼리 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="cc948-103">Represents a collection of queries that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="cc948-104">이 이벤트는 FaultHandler가 오류를 처리할 때마다 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="cc948-104">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="cc948-105">활동 내에서 발생하는 오류 처리를 추적하려면 이러한 쿼리를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc948-105">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="cc948-106">추적 참가자가 오류 전파 레코드를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="cc948-106">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>  
  
<span data-ttu-id="cc948-107">추적 프로필 쿼리에 대 한 자세한 내용은 [추적 프로필](../../../windows-workflow-foundation/tracking-profiles.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cc948-107">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<faultPropagationQueries>**  
  
## <a name="syntax"></a><span data-ttu-id="cc948-108">구문</span><span class="sxs-lookup"><span data-stu-id="cc948-108">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <faultPropagationQueries>
          <faultPropagationQuery faultSourceActivityName="String"
                                 faultHandlerActivityName="String"/>
        </faultPropagationQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cc948-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="cc948-109">Attributes and elements</span></span>

<span data-ttu-id="cc948-110">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="cc948-110">The following sections describe attributes, child elements, and parent elements.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="cc948-111">특성</span><span class="sxs-lookup"><span data-stu-id="cc948-111">Attributes</span></span>

<span data-ttu-id="cc948-112">없음</span><span class="sxs-lookup"><span data-stu-id="cc948-112">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="cc948-113">자식 요소</span><span class="sxs-lookup"><span data-stu-id="cc948-113">Child elements</span></span>

|<span data-ttu-id="cc948-114">요소</span><span class="sxs-lookup"><span data-stu-id="cc948-114">Element</span></span>|<span data-ttu-id="cc948-115">Description</span><span class="sxs-lookup"><span data-stu-id="cc948-115">Description</span></span>|  
|-------------|-----------------|  
|[\<faultPropagationQuery>](faultpropagationquery-of-wcf.md)|<span data-ttu-id="cc948-116">활동 내에서 발생하는 오류의 처리를 추적하는 데 사용되는 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="cc948-116">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="cc948-117">이 이벤트는 FaultHandler가 오류를 처리할 때마다 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="cc948-117">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="cc948-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="cc948-118">Parent elements</span></span>  
  
|<span data-ttu-id="cc948-119">요소</span><span class="sxs-lookup"><span data-stu-id="cc948-119">Element</span></span>|<span data-ttu-id="cc948-120">Description</span><span class="sxs-lookup"><span data-stu-id="cc948-120">Description</span></span>|  
|-------------|-----------------|  
|[\<workflow>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="cc948-121">`activityDefinitionId` 속성에 의해 식별되는 특정 워크플로에 대한 모든 쿼리를 포함하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="cc948-121">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cc948-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cc948-122">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="cc948-123">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="cc948-123">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="cc948-124">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="cc948-124">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
