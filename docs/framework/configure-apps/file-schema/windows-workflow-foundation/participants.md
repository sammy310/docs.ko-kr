---
title: <participants>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 560dd0bb-f9fb-423c-8857-2101a3654b06
ms.openlocfilehash: f04a5ee3940986cabc08895452c12ebcfd631694
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69947576"
---
# <a name="participants"></a><span data-ttu-id="c995a-101">\<participants></span><span class="sxs-lookup"><span data-stu-id="c995a-101">\<participants></span></span>
<span data-ttu-id="c995a-102">런타임에서 내보내지는 추적 레코드를 수신하는 추적 참가자의 목록을 직접 구성하고 구성된 방식대로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="c995a-102">Configure a list of tracking participants that listen to the tracking records being emitted from the runtime directly and process them in whatever way they are configured.</span></span> <span data-ttu-id="c995a-103">여기에는 특정 출력(예: 파일, 콘솔, ETW)에 쓰기, 레코드 처리/집계 또는 필요한 기타 조합이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="c995a-103">This includes writing to a specific output (e.g., file, Console, ETW), processing/aggregating the records, or any other combination that might be required.</span></span>  
  
 <span data-ttu-id="c995a-104">워크플로 추적 및 추적 참가자에 대 한 자세한 내용은 [워크플로 추적 및](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) 추적 및 추적 [참가자](../../../windows-workflow-foundation/tracking-participants.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c995a-104">For more information in workflow tracking and tracking participants, see [Workflow Tracking and Tracing](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Tracking Participants](../../../windows-workflow-foundation/tracking-participants.md).</span></span>  
  
<span data-ttu-id="c995a-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="c995a-105">\<system.serviceModel></span></span>  
<span data-ttu-id="c995a-106">\<tracking></span><span class="sxs-lookup"><span data-stu-id="c995a-106">\<tracking></span></span>  
<span data-ttu-id="c995a-107">\<participants></span><span class="sxs-lookup"><span data-stu-id="c995a-107">\<participants></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c995a-108">구문</span><span class="sxs-lookup"><span data-stu-id="c995a-108">Syntax</span></span>  
  
```xml
<tracking>
  <participants>
    <add name="String" 
         profileName="String" 
         type="String" />
  </participants>
</tracking>   
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c995a-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="c995a-109">Attributes and Elements</span></span>  
 <span data-ttu-id="c995a-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c995a-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c995a-111">특성</span><span class="sxs-lookup"><span data-stu-id="c995a-111">Attributes</span></span>  
 <span data-ttu-id="c995a-112">없음</span><span class="sxs-lookup"><span data-stu-id="c995a-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c995a-113">자식 요소</span><span class="sxs-lookup"><span data-stu-id="c995a-113">Child Elements</span></span>  
  
|<span data-ttu-id="c995a-114">요소</span><span class="sxs-lookup"><span data-stu-id="c995a-114">Element</span></span>|<span data-ttu-id="c995a-115">설명</span><span class="sxs-lookup"><span data-stu-id="c995a-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c995a-116">\<add></span><span class="sxs-lookup"><span data-stu-id="c995a-116">\<add></span></span>](add-of-participants.md)|<span data-ttu-id="c995a-117">추적 참가자에 대한 설정을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="c995a-117">Contains settings for a tracking participant.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c995a-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="c995a-118">Parent Elements</span></span>  
  
|<span data-ttu-id="c995a-119">요소</span><span class="sxs-lookup"><span data-stu-id="c995a-119">Element</span></span>|<span data-ttu-id="c995a-120">Description</span><span class="sxs-lookup"><span data-stu-id="c995a-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c995a-121">\<tracking></span><span class="sxs-lookup"><span data-stu-id="c995a-121">\<tracking></span></span>](tracking.md)|<span data-ttu-id="c995a-122">워크플로 서비스에 대한 추적 설정을 정의하기 위한 구성 섹션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c995a-122">Represents a configuration section for defining tracking settings for a workflow service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c995a-123">설명</span><span class="sxs-lookup"><span data-stu-id="c995a-123">Remarks</span></span>  
 <span data-ttu-id="c995a-124">추적 참가자는 워크플로에서 내보내지는 추적 데이터를 가져오고 이 데이터를 다른 미디어에 저장하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c995a-124">Tracking participants are used to get the tracking data emitted from the workflow and store it into different mediums.</span></span> <span data-ttu-id="c995a-125">마찬가지로 추적 레코드에 대한 모든 사후 처리를 추적 참가자 내에서 수행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c995a-125">Likewise, any post processing on the tracking Records can also be done within the tracking participant.</span></span>  
  
 <span data-ttu-id="c995a-126">여러 추적 참가자가 추적 이벤트를 동시에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c995a-126">Multiple tracking participants can consume the tracking events simultaneously.</span></span> <span data-ttu-id="c995a-127">각 추적 참가자는 서로 다른 추적 프로필과 연결될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c995a-127">Each tracking participant can be associated with a different tracking profile.</span></span>  
  
 <span data-ttu-id="c995a-128">ETW 세션에 추적 레코드를 작성하는 표준 추적 참가자가 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="c995a-128">A standard tracking participant is provided which writes the tracking records to an ETW session.</span></span> <span data-ttu-id="c995a-129">추적 참가자는 워크플로 서비스에서 구성 파일에 추적별 동작을 추가하여 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c995a-129">The participant is configured on a workflow service by adding a tracking-specific behavior in a configuration file.</span></span> <span data-ttu-id="c995a-130">ETW 추적 참가자를 사용하여 이벤트 뷰어에서 추적 레코드를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c995a-130">Enabling an ETW tracking participant allows tracking records to be viewed in the event viewer.</span></span> <span data-ttu-id="c995a-131">표준 참가자가 요구 사항에 맞지 않는 경우 사용자 지정 추적 참가자를 작성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c995a-131">If that does not meet your requirements, you can also write a custom tracking participant.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c995a-132">예제</span><span class="sxs-lookup"><span data-stu-id="c995a-132">Example</span></span>  
 <span data-ttu-id="c995a-133">다음 구성 예제에서는 Web.config 파일에서 구성되는 표준 ETW 추적 참가자를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c995a-133">The following configuration example shows the standard ETW tracking participant being configured in the Web.config file.</span></span>  
  
 <span data-ttu-id="c995a-134">Etw 추적 참가자가 etw에 추적 레코드를 기록 하는 데 사용 하는 공급자 Id는  **\<진단 >** 섹션에서 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c995a-134">The Provider Id that the ETW Tracking Participant uses for writing the Tracking Records to ETW is defined in the **\<diagnostics>** section.</span></span> <span data-ttu-id="c995a-135">추적 참가자에는 구독하는 추적 레코드를 지정하기 위해 연결된 프로필이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c995a-135">The tracking participant has a profile associated with it to specify the tracking records it has subscribed to.</span></span> <span data-ttu-id="c995a-136">이는  **\<add >** 요소의 **profileName** 특성에 의해 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c995a-136">This is defined by the **profileName** attribute of the **\<add>** element.</span></span> <span data-ttu-id="c995a-137">이러한 설정이 정의 되 면 추적 참가자가  **\<etwtracking >** 서비스 동작에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c995a-137">Once these are defined, the Tracking Participant is added to the **\<etwTracking>** service behavior.</span></span> <span data-ttu-id="c995a-138">이렇게 하면 선택된 추적 참가자가 워크플로 인스턴스의 확장에 추가되어 추적 레코드를 받기 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="c995a-138">This will add the selected Tracking Participants to the Workflow instance’s extensions, so that they begin to receive the Tracking Records.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="c995a-139">참고자료</span><span class="sxs-lookup"><span data-stu-id="c995a-139">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.TrackingSection>
- <xref:System.ServiceModel.Activities.Description.EtwTrackingBehavior>
- <xref:System.ServiceModel.Activities.Configuration.EtwTrackingBehaviorElement>
- [<span data-ttu-id="c995a-140">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="c995a-140">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="c995a-141">추적 참가자</span><span class="sxs-lookup"><span data-stu-id="c995a-141">Tracking Participants</span></span>](../../../windows-workflow-foundation/tracking-participants.md)
