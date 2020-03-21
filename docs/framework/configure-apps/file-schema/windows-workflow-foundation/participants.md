---
title: <participants>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 560dd0bb-f9fb-423c-8857-2101a3654b06
ms.openlocfilehash: e6e996bd1cc32258167e30287e9338a4773ce921
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152030"
---
# <a name="participants"></a><span data-ttu-id="86b54-101">\<참가자는></span><span class="sxs-lookup"><span data-stu-id="86b54-101">\<participants></span></span>
<span data-ttu-id="86b54-102">런타임에서 내보내지는 추적 레코드를 수신하는 추적 참가자의 목록을 직접 구성하고 구성된 방식대로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="86b54-102">Configure a list of tracking participants that listen to the tracking records being emitted from the runtime directly and process them in whatever way they are configured.</span></span> <span data-ttu-id="86b54-103">여기에는 특정 출력(예: 파일, 콘솔, ETW)에 쓰기, 레코드 처리/집계 또는 필요한 기타 조합이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="86b54-103">This includes writing to a specific output (e.g., file, Console, ETW), processing/aggregating the records, or any other combination that might be required.</span></span>  
  
 <span data-ttu-id="86b54-104">워크플로 추적 및 추적 참가자에 대한 자세한 내용은 [워크플로 추적 및 추적](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) [참가자를](../../../windows-workflow-foundation/tracking-participants.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="86b54-104">For more information in workflow tracking and tracking participants, see [Workflow Tracking and Tracing](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Tracking Participants](../../../windows-workflow-foundation/tracking-participants.md).</span></span>  
  
<span data-ttu-id="86b54-105">[**\<구성>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="86b54-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="86b54-106">&nbsp;&nbsp;[**\<시스템. 서비스 모델>**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="86b54-106">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="86b54-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<추적>**](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="86b54-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="86b54-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<참가자들은>**</span><span class="sxs-lookup"><span data-stu-id="86b54-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<participants>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86b54-109">구문</span><span class="sxs-lookup"><span data-stu-id="86b54-109">Syntax</span></span>  
  
```xml
<tracking>
  <participants>
    <add name="String"
         profileName="String"
         type="String" />
  </participants>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="86b54-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="86b54-110">Attributes and Elements</span></span>  
 <span data-ttu-id="86b54-111">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="86b54-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="86b54-112">특성</span><span class="sxs-lookup"><span data-stu-id="86b54-112">Attributes</span></span>  
 <span data-ttu-id="86b54-113">없음</span><span class="sxs-lookup"><span data-stu-id="86b54-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="86b54-114">자식 요소</span><span class="sxs-lookup"><span data-stu-id="86b54-114">Child Elements</span></span>  
  
|<span data-ttu-id="86b54-115">요소</span><span class="sxs-lookup"><span data-stu-id="86b54-115">Element</span></span>|<span data-ttu-id="86b54-116">Description</span><span class="sxs-lookup"><span data-stu-id="86b54-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="86b54-117">\<>추가</span><span class="sxs-lookup"><span data-stu-id="86b54-117">\<add></span></span>](add-of-participants.md)|<span data-ttu-id="86b54-118">추적 참가자에 대한 설정을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="86b54-118">Contains settings for a tracking participant.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="86b54-119">부모 요소</span><span class="sxs-lookup"><span data-stu-id="86b54-119">Parent Elements</span></span>  
  
|<span data-ttu-id="86b54-120">요소</span><span class="sxs-lookup"><span data-stu-id="86b54-120">Element</span></span>|<span data-ttu-id="86b54-121">Description</span><span class="sxs-lookup"><span data-stu-id="86b54-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="86b54-122">\<추적></span><span class="sxs-lookup"><span data-stu-id="86b54-122">\<tracking></span></span>](tracking.md)|<span data-ttu-id="86b54-123">워크플로 서비스에 대한 추적 설정을 정의하기 위한 구성 섹션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="86b54-123">Represents a configuration section for defining tracking settings for a workflow service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="86b54-124">설명</span><span class="sxs-lookup"><span data-stu-id="86b54-124">Remarks</span></span>  
 <span data-ttu-id="86b54-125">추적 참가자는 워크플로에서 내보내지는 추적 데이터를 가져오고 이 데이터를 다른 미디어에 저장하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="86b54-125">Tracking participants are used to get the tracking data emitted from the workflow and store it into different mediums.</span></span> <span data-ttu-id="86b54-126">마찬가지로 추적 레코드에 대한 모든 사후 처리를 추적 참가자 내에서 수행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86b54-126">Likewise, any post processing on the tracking Records can also be done within the tracking participant.</span></span>  
  
 <span data-ttu-id="86b54-127">여러 추적 참가자가 추적 이벤트를 동시에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86b54-127">Multiple tracking participants can consume the tracking events simultaneously.</span></span> <span data-ttu-id="86b54-128">각 추적 참가자는 서로 다른 추적 프로필과 연결될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86b54-128">Each tracking participant can be associated with a different tracking profile.</span></span>  
  
 <span data-ttu-id="86b54-129">ETW 세션에 추적 레코드를 작성하는 표준 추적 참가자가 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="86b54-129">A standard tracking participant is provided which writes the tracking records to an ETW session.</span></span> <span data-ttu-id="86b54-130">추적 참가자는 워크플로 서비스에서 구성 파일에 추적별 동작을 추가하여 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86b54-130">The participant is configured on a workflow service by adding a tracking-specific behavior in a configuration file.</span></span> <span data-ttu-id="86b54-131">ETW 추적 참가자를 사용하여 이벤트 뷰어에서 추적 레코드를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86b54-131">Enabling an ETW tracking participant allows tracking records to be viewed in the event viewer.</span></span> <span data-ttu-id="86b54-132">표준 참가자가 요구 사항에 맞지 않는 경우 사용자 지정 추적 참가자를 작성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86b54-132">If that does not meet your requirements, you can also write a custom tracking participant.</span></span>  
  
## <a name="example"></a><span data-ttu-id="86b54-133">예제</span><span class="sxs-lookup"><span data-stu-id="86b54-133">Example</span></span>  
 <span data-ttu-id="86b54-134">다음 구성 예제에서는 Web.config 파일에서 구성되는 표준 ETW 추적 참가자를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="86b54-134">The following configuration example shows the standard ETW tracking participant being configured in the Web.config file.</span></span>  
  
 <span data-ttu-id="86b54-135">ETW 추적 참가자가 추적 레코드를 ETW에 기록하는 데 사용하는 공급자 ID는 \*\* \<진단>\*\* 섹션에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86b54-135">The Provider Id that the ETW Tracking Participant uses for writing the Tracking Records to ETW is defined in the **\<diagnostics>** section.</span></span> <span data-ttu-id="86b54-136">추적 참가자에는 구독하는 추적 레코드를 지정하기 위해 연결된 프로필이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86b54-136">The tracking participant has a profile associated with it to specify the tracking records it has subscribed to.</span></span> <span data-ttu-id="86b54-137">이>\*\* \<추가\*\* 요소의 **profileName** 특성에 의해 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="86b54-137">This is defined by the **profileName** attribute of the **\<add>** element.</span></span> <span data-ttu-id="86b54-138">이러한 정의가 정의되면 추적 참가자가 \*\* \<etwTracking>\*\* 서비스 동작에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="86b54-138">Once these are defined, the Tracking Participant is added to the **\<etwTracking>** service behavior.</span></span> <span data-ttu-id="86b54-139">이렇게 하면 선택된 추적 참가자가 워크플로 인스턴스의 확장에 추가되어 추적 레코드를 받기 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="86b54-139">This will add the selected Tracking Participants to the Workflow instance’s extensions, so that they begin to receive the Tracking Records.</span></span>  
  
```xml
<configuration>
  <system.web>
    <compilation targetFrameworkMoniker=".NETFramework,Version=v4.0"/>
  </system.web>
  <system.serviceModel>
    <diagnostics etwProviderId="52A3165D-4AD9-405C-B1E8-7D9A257EAC9F" />
    <tracking>
      <participants>
        <add name="EtwTrackingParticipant"
             type="System.Activities.Tracking.EtwTrackingParticipant, System.Activities, Version=4.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35"
             profileName="HealthMonitoring_Tracking_Profile"/>
      </participants>
    </tracking>
    <behaviors>
      <serviceBehaviors>
        <behavior>
          <etwTracking profileName="Sample Tracking Profile"/>  
        </behavior>
      </serviceBehaviors>
    </behaviors>
  </system.serviceModel>
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="86b54-140">참고 항목</span><span class="sxs-lookup"><span data-stu-id="86b54-140">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.TrackingSection>
- <xref:System.ServiceModel.Activities.Description.EtwTrackingBehavior>
- <xref:System.ServiceModel.Activities.Configuration.EtwTrackingBehaviorElement>
- [<span data-ttu-id="86b54-141">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="86b54-141">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="86b54-142">참가자 추적</span><span class="sxs-lookup"><span data-stu-id="86b54-142">Tracking Participants</span></span>](../../../windows-workflow-foundation/tracking-participants.md)
