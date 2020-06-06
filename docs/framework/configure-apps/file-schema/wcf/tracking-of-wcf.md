---
title: <tracking>WCF의
ms.date: 03/30/2017
ms.assetid: 70cfaf24-a91c-4e56-ac47-d2ed87a963b3
ms.openlocfilehash: e8f74d635299a965b754536234e6be28e4e7a104
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "70399425"
---
# <a name="tracking-of-wcf"></a><span data-ttu-id="b53c3-102">\<tracking>WCF의</span><span class="sxs-lookup"><span data-stu-id="b53c3-102">\<tracking> of WCF</span></span>
<span data-ttu-id="b53c3-103">워크플로 서비스에 대한 추적 설정을 정의하기 위한 구성 섹션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b53c3-103">Represents a configuration section for defining tracking settings for a workflow service.</span></span>  
  
 <span data-ttu-id="b53c3-104">워크플로 추적 및 해당 구성에 대 한 자세한 내용은 워크플로 [추적 및](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) 추적 및 [워크플로에 대 한 추적 구성](../../../windows-workflow-foundation/configuring-tracking-for-a-workflow.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b53c3-104">For more information in workflow tracking and its configuration, see [Workflow Tracking and Tracing](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Configuring Tracking for a Workflow](../../../windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<tracking>**  
  
## <a name="syntax"></a><span data-ttu-id="b53c3-105">구문</span><span class="sxs-lookup"><span data-stu-id="b53c3-105">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <tracking>
    <participants>
      <add name="String"
           profileName="String"
           type="String" />
    </participants>
    <profiles>
      <trackingProfile name="String">
        <workflow activityDefinitionId="String">
          <activityScheduledQueries>
            <activityScheduledQuery activityName="String"
                                    childActivityName="String"/>
          </activityScheduledQueries>
          <activityStateQueries>
            <activityStateQuery activityName="String" />
            <arguments>
              <argument name="String"/>
            </arguments>
            <states>
              <state name="String"/>
            </states>
            <variables>
              <variable name="String"/>
            </variables>
          </activityStateQueries>
          <bookmarkResumptionQueries>
            <bookmarkResumptionQuery name="String" />
          </bookmarkResumptionQueries>
          <cancelRequestQueries>
            <cancelRequestQuery activityName="String"
                                childActivityName="String"/>
          </cancelRequestQueries>
          <customTrackingQueries>
            <customTrackingQuery activityName="String"
                                 name="String"/>
          </customTrackingQueries>
          <faultPropagationQueries>
            <faultPropagationQuery activityName="String"
                                   faultHandlerActivityName="String"/>
          </faultPropagationQueries>
          <workflowInstanceQueries>
            <workflowInstanceQuery>
              <states>
                <state name="String"/>
              </states>
            </workflowInstanceQuery>
          </workflowInstanceQueries>
        </workflow>
      </trackingProfile>
    </profiles>
  </tracking>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b53c3-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="b53c3-106">Attributes and Elements</span></span>  
 <span data-ttu-id="b53c3-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b53c3-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b53c3-108">특성</span><span class="sxs-lookup"><span data-stu-id="b53c3-108">Attributes</span></span>  
 <span data-ttu-id="b53c3-109">없음</span><span class="sxs-lookup"><span data-stu-id="b53c3-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b53c3-110">자식 요소</span><span class="sxs-lookup"><span data-stu-id="b53c3-110">Child Elements</span></span>  
  
|<span data-ttu-id="b53c3-111">요소</span><span class="sxs-lookup"><span data-stu-id="b53c3-111">Element</span></span>|<span data-ttu-id="b53c3-112">Description</span><span class="sxs-lookup"><span data-stu-id="b53c3-112">Description</span></span>|  
|-------------|-----------------|  
|[\<participants>](../windows-workflow-foundation/participants.md)|<span data-ttu-id="b53c3-113">추적 레코드를 구독하는 참가자를 정의하는 구성 요소의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="b53c3-113">A collection of configuration elements defining participants that subscribe to tracking records.</span></span> <span data-ttu-id="b53c3-114">추적 참가자에는 추적 레코드에서 페이로드를 처리하기 위한 논리가 포함됩니다. 예를 들어 파일에 기록하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b53c3-114">The tracking participants contain the logic to process the payload from the tracking records (for example, they could choose to write to a file).</span></span>|  
|[\<trackingProfile>](../windows-workflow-foundation/trackingprofile.md)|<span data-ttu-id="b53c3-115">워크플로 인스턴스에서 내보내지는 추적 레코드를 필터링하기 위한 추적 프로필입니다.</span><span class="sxs-lookup"><span data-stu-id="b53c3-115">A tracking profile to filter tracking records emitted from a workflow instance.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b53c3-116">부모 요소</span><span class="sxs-lookup"><span data-stu-id="b53c3-116">Parent Elements</span></span>  
  
|<span data-ttu-id="b53c3-117">요소</span><span class="sxs-lookup"><span data-stu-id="b53c3-117">Element</span></span>|<span data-ttu-id="b53c3-118">Description</span><span class="sxs-lookup"><span data-stu-id="b53c3-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b53c3-119">system.ServiceModel</span><span class="sxs-lookup"><span data-stu-id="b53c3-119">system.ServiceModel</span></span>|<span data-ttu-id="b53c3-120">모든 워크플로 구성 요소의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="b53c3-120">The root element of all workflow configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b53c3-121">설명</span><span class="sxs-lookup"><span data-stu-id="b53c3-121">Remarks</span></span>  
 <span data-ttu-id="b53c3-122">추적은 워크플로 실행을 검사하는 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b53c3-122">Tracking provides you with the ability to examine the execution of a workflow.</span></span> <span data-ttu-id="b53c3-123">워크플로 추적 인프라는 실행 중 주요 이벤트를 반영하는 레코드를 내보내기 위한 워크플로를 계측합니다.</span><span class="sxs-lookup"><span data-stu-id="b53c3-123">The workflow tracking infrastructure instruments a workflow to emit records reflecting key events during the execution.</span></span> <span data-ttu-id="b53c3-124">예를 들어 워크플로 인스턴스가 시작되거나 완료되면 추적 레코드가 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="b53c3-124">For example, when a workflow instance starts or completes tracking records are emitted.</span></span> <span data-ttu-id="b53c3-125">추적에서는 워크플로 변수와 연결된 비즈니스 관련 데이터를 추출할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b53c3-125">Tracking can also extract business relevant data associated with the workflow variables.</span></span> <span data-ttu-id="b53c3-126">예를 들어 워크플로가 주문 처리 시스템을 나타내는 경우 주문 ID가 추적 레코드와 함께 추출될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b53c3-126">For example, if the workflow represents an order processing system the order id can be extracted along with the tracking record.</span></span> <span data-ttu-id="b53c3-127">일반적으로 WF 추적을 사용하면 워크플로 실행에 대한 진단 또는 비즈니스 분석에 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b53c3-127">In general, enabling WF tracking facilitates diagnostics or business analytics over a workflow execution.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b53c3-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b53c3-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.TrackingSection?displayProperty=nameWithType>
- [<span data-ttu-id="b53c3-129">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="b53c3-129">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
