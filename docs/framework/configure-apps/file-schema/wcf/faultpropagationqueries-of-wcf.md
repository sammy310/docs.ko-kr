---
description: '다음에 대 한 자세한 정보: <faultPropagationQueries> WCF'
title: <faultPropagationQueries> WCF의
ms.date: 03/30/2017
ms.assetid: d85f66a7-e7b0-4dbb-83cc-89fa06fc9161
ms.openlocfilehash: e3ed504b3aada87246fabe54c0b32ef5ad60b34b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99684440"
---
# <a name="faultpropagationqueries-of-wcf"></a><span data-ttu-id="51dd4-103">\<faultPropagationQueries> WCF의</span><span class="sxs-lookup"><span data-stu-id="51dd4-103">\<faultPropagationQueries> of WCF</span></span>

<span data-ttu-id="51dd4-104">활동 내에서 발생하는 오류의 처리를 추적하는 데 사용되는 쿼리 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="51dd4-104">Represents a collection of queries that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="51dd4-105">이 이벤트는 FaultHandler가 오류를 처리할 때마다 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="51dd4-105">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="51dd4-106">활동 내에서 발생하는 오류 처리를 추적하려면 이러한 쿼리를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="51dd4-106">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="51dd4-107">추적 참가자가 오류 전파 레코드를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="51dd4-107">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>  
  
<span data-ttu-id="51dd4-108">추적 프로필 쿼리에 대 한 자세한 내용은 [추적 프로필](../../../windows-workflow-foundation/tracking-profiles.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="51dd4-108">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<faultPropagationQueries>**  
  
## <a name="syntax"></a><span data-ttu-id="51dd4-109">구문</span><span class="sxs-lookup"><span data-stu-id="51dd4-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="51dd4-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="51dd4-110">Attributes and elements</span></span>

<span data-ttu-id="51dd4-111">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="51dd4-111">The following sections describe attributes, child elements, and parent elements.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="51dd4-112">특성</span><span class="sxs-lookup"><span data-stu-id="51dd4-112">Attributes</span></span>

<span data-ttu-id="51dd4-113">없음</span><span class="sxs-lookup"><span data-stu-id="51dd4-113">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="51dd4-114">자식 요소</span><span class="sxs-lookup"><span data-stu-id="51dd4-114">Child elements</span></span>

|<span data-ttu-id="51dd4-115">요소</span><span class="sxs-lookup"><span data-stu-id="51dd4-115">Element</span></span>|<span data-ttu-id="51dd4-116">설명</span><span class="sxs-lookup"><span data-stu-id="51dd4-116">Description</span></span>|  
|-------------|-----------------|  
|[\<faultPropagationQuery>](faultpropagationquery-of-wcf.md)|<span data-ttu-id="51dd4-117">활동 내에서 발생하는 오류의 처리를 추적하는 데 사용되는 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="51dd4-117">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="51dd4-118">이 이벤트는 FaultHandler가 오류를 처리할 때마다 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="51dd4-118">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="51dd4-119">부모 요소</span><span class="sxs-lookup"><span data-stu-id="51dd4-119">Parent elements</span></span>  
  
|<span data-ttu-id="51dd4-120">요소</span><span class="sxs-lookup"><span data-stu-id="51dd4-120">Element</span></span>|<span data-ttu-id="51dd4-121">설명</span><span class="sxs-lookup"><span data-stu-id="51dd4-121">Description</span></span>|  
|-------------|-----------------|  
|[\<workflow>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="51dd4-122">`activityDefinitionId` 속성에 의해 식별되는 특정 워크플로에 대한 모든 쿼리를 포함하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="51dd4-122">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="51dd4-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="51dd4-123">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="51dd4-124">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="51dd4-124">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="51dd4-125">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="51dd4-125">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
