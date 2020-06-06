---
title: <participants>WCF의
ms.date: 03/30/2017
ms.assetid: d99dbddc-0057-4e18-8e42-f91411d39970
ms.openlocfilehash: 35ed7a49967143838a6f74c51e77c553817bd09a
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855087"
---
# <a name="participants-of-wcf"></a><span data-ttu-id="75cd9-102">\<participants>WCF의</span><span class="sxs-lookup"><span data-stu-id="75cd9-102">\<participants> of WCF</span></span>
<span data-ttu-id="75cd9-103">런타임에서 내보내지는 추적 레코드를 수신하는 추적 참가자의 목록을 직접 구성하고 구성된 방식대로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="75cd9-103">Configure a list of tracking participants that listen to the tracking records being emitted from the runtime directly and process them in whatever way they are configured.</span></span> <span data-ttu-id="75cd9-104">여기에는 특정 출력(예: 파일, 콘솔, ETW)에 쓰기, 레코드 처리/집계 또는 필요한 기타 조합이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="75cd9-104">This includes writing to a specific output (e.g., file, Console, ETW), processing/aggregating the records, or any other combination that might be required.</span></span>  
  
<span data-ttu-id="75cd9-105">워크플로 추적 및 추적 참가자에 대 한 자세한 내용은 [워크플로 추적 및](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) 추적 및 추적 [참가자](../../../windows-workflow-foundation/tracking-participants.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="75cd9-105">For more information in workflow tracking and tracking participants, see [Workflow Tracking and Tracing](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Tracking Participants](../../../windows-workflow-foundation/tracking-participants.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<participants>**  
  
## <a name="syntax"></a><span data-ttu-id="75cd9-106">구문</span><span class="sxs-lookup"><span data-stu-id="75cd9-106">Syntax</span></span>  
  
```xml  
<tracking>
  <participants>
    <add name="String"
         profileName="String"
         type="String" />
  </participants>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="75cd9-107">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="75cd9-107">Attributes and Elements</span></span>  
 <span data-ttu-id="75cd9-108">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="75cd9-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="75cd9-109">특성</span><span class="sxs-lookup"><span data-stu-id="75cd9-109">Attributes</span></span>  
 <span data-ttu-id="75cd9-110">없음</span><span class="sxs-lookup"><span data-stu-id="75cd9-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="75cd9-111">자식 요소</span><span class="sxs-lookup"><span data-stu-id="75cd9-111">Child Elements</span></span>  
  
|<span data-ttu-id="75cd9-112">요소</span><span class="sxs-lookup"><span data-stu-id="75cd9-112">Element</span></span>|<span data-ttu-id="75cd9-113">Description</span><span class="sxs-lookup"><span data-stu-id="75cd9-113">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](../windows-workflow-foundation/add-of-participants.md)|<span data-ttu-id="75cd9-114">추적 참가자에 대한 설정을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="75cd9-114">Contains settings for a tracking participant.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="75cd9-115">부모 요소</span><span class="sxs-lookup"><span data-stu-id="75cd9-115">Parent Elements</span></span>  
  
|<span data-ttu-id="75cd9-116">요소</span><span class="sxs-lookup"><span data-stu-id="75cd9-116">Element</span></span>|<span data-ttu-id="75cd9-117">Description</span><span class="sxs-lookup"><span data-stu-id="75cd9-117">Description</span></span>|  
|-------------|-----------------|  
|[\<tracking>](../windows-workflow-foundation/tracking.md)|<span data-ttu-id="75cd9-118">워크플로 서비스에 대한 추적 설정을 정의하기 위한 구성 섹션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="75cd9-118">Represents a configuration section for defining tracking settings for a workflow service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="75cd9-119">설명</span><span class="sxs-lookup"><span data-stu-id="75cd9-119">Remarks</span></span>  
 <span data-ttu-id="75cd9-120">추적 참가자는 워크플로에서 내보내지는 추적 데이터를 가져오고 이 데이터를 다른 미디어에 저장하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="75cd9-120">Tracking participants are used to get the tracking data emitted from the workflow and store it into different mediums.</span></span> <span data-ttu-id="75cd9-121">마찬가지로 추적 레코드에 대한 모든 사후 처리를 추적 참가자 내에서 수행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75cd9-121">Likewise, any post processing on the tracking Records can also be done within the tracking participant.</span></span>  
  
 <span data-ttu-id="75cd9-122">여러 추적 참가자가 추적 이벤트를 동시에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75cd9-122">Multiple tracking participants can consume the tracking events simultaneously.</span></span> <span data-ttu-id="75cd9-123">각 추적 참가자는 서로 다른 추적 프로필과 연결될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75cd9-123">Each tracking participant can be associated with a different tracking profile.</span></span>  
  
 <span data-ttu-id="75cd9-124">ETW 세션에 추적 레코드를 작성하는 표준 추적 참가자가 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="75cd9-124">A standard tracking participant is provided which writes the tracking records to an ETW session.</span></span> <span data-ttu-id="75cd9-125">추적 참가자는 워크플로 서비스에서 구성 파일에 추적별 동작을 추가하여 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75cd9-125">The participant is configured on a workflow service by adding a tracking-specific behavior in a configuration file.</span></span> <span data-ttu-id="75cd9-126">ETW 추적 참가자를 사용하여 이벤트 뷰어에서 추적 레코드를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75cd9-126">Enabling an ETW tracking participant allows tracking records to be viewed in the event viewer.</span></span> <span data-ttu-id="75cd9-127">표준 참가자가 요구 사항에 맞지 않는 경우 사용자 지정 추적 참가자를 작성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75cd9-127">If that does not meet your requirements, you can also write a custom tracking participant.</span></span>  
  
## <a name="example"></a><span data-ttu-id="75cd9-128">예제</span><span class="sxs-lookup"><span data-stu-id="75cd9-128">Example</span></span>  
 <span data-ttu-id="75cd9-129">다음 구성 예제에서는 Web.config 파일에서 구성되는 표준 ETW 추적 참가자를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="75cd9-129">The following configuration example shows the standard ETW tracking participant being configured in the Web.config file.</span></span>  
  
 <span data-ttu-id="75cd9-130">ETW 추적 참가자에서 ETW에 추적 레코드를 작성하기 위해 사용하는 공급자 ID는 `<diagnostics>` 섹션에서 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="75cd9-130">The Provider Id that the ETW Tracking Participant uses for writing the Tracking Records to ETW is defined in the `<diagnostics>` section.</span></span> <span data-ttu-id="75cd9-131">추적 참가자에는 구독하는 추적 레코드를 지정하기 위해 연결된 프로필이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75cd9-131">The tracking participant has a profile associated with it to specify the tracking records it has subscribed to.</span></span> <span data-ttu-id="75cd9-132">이 프로필은 `profileName` 요소의 `<add>` 특성에서 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="75cd9-132">This is defined by the `profileName` attribute of the `<add>` element.</span></span> <span data-ttu-id="75cd9-133">프로필이 정의되면 추적 참가자가 `<etwTracking>` 서비스 동작에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="75cd9-133">Once these are defined, the Tracking Participant is added to the `<etwTracking>` service behavior.</span></span> <span data-ttu-id="75cd9-134">이렇게 하면 선택된 추적 참가자가 워크플로 인스턴스의 확장에 추가되어 추적 레코드를 받기 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="75cd9-134">This will add the selected Tracking Participants to the Workflow instance’s extensions, so that they begin to receive the Tracking Records.</span></span>  
  
```xml  
<configuration>
  <system.web>
    <compilation targetFrameworkMoniker=".NETFramework,Version=v4.0" />
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
  
## <a name="see-also"></a><span data-ttu-id="75cd9-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="75cd9-135">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.TrackingSection>
- <xref:System.ServiceModel.Activities.Description.EtwTrackingBehavior>
- [<span data-ttu-id="75cd9-136">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="75cd9-136">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="75cd9-137">추적 참가자</span><span class="sxs-lookup"><span data-stu-id="75cd9-137">Tracking Participants</span></span>](../../../windows-workflow-foundation/tracking-participants.md)
