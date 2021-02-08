---
description: '자세히 알아보기: 사용자 지정 추적'
title: 사용자 지정 추적
ms.date: 03/30/2017
ms.assetid: 2d191c9f-62f4-4c63-92dd-cda917fcf254
ms.openlocfilehash: a06faaaa50a06d613f7183ca018438a8f2b4460b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99792559"
---
# <a name="custom-tracking"></a><span data-ttu-id="1d2bf-103">사용자 지정 추적</span><span class="sxs-lookup"><span data-stu-id="1d2bf-103">Custom Tracking</span></span>

<span data-ttu-id="1d2bf-104">이 샘플에서는 사용자 지정 추적 참가자를 만들고 추적 데이터의 내용을 콘솔에 쓰는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1d2bf-104">This sample demonstrates how to create a custom tracking participant and write the contents of the tracking data to console.</span></span> <span data-ttu-id="1d2bf-105">또한 사용자 정의 데이터로 채워진 <xref:System.Activities.Tracking.CustomTrackingRecord> 개체를 내보내는 방법도 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1d2bf-105">In addition, the sample demonstrates how to emit <xref:System.Activities.Tracking.CustomTrackingRecord> objects populated with user defined data.</span></span> <span data-ttu-id="1d2bf-106">콘솔 기반 추적 참가자는 코드로 만든 추적 프로필 개체를 사용하여 워크플로에서 내보낸 <xref:System.Activities.Tracking.TrackingRecord> 개체를 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="1d2bf-106">The console-based tracking participant filters the <xref:System.Activities.Tracking.TrackingRecord> objects emitted by the workflow using a tracking profile object created in code.</span></span>

## <a name="sample-details"></a><span data-ttu-id="1d2bf-107">샘플 세부 정보</span><span class="sxs-lookup"><span data-stu-id="1d2bf-107">Sample Details</span></span>

 <span data-ttu-id="1d2bf-108">WF (Windows Workflow Foundation)는 워크플로 인스턴스 실행을 추적 하기 위한 추적 인프라를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d2bf-108">Windows Workflow Foundation (WF) provides a tracking infrastructure to track execution of a workflow instance.</span></span> <span data-ttu-id="1d2bf-109">추적 런타임은 워크플로 인스턴스를 구현하여 워크플로 수명 주기와 관련된 이벤트, 워크플로 활동의 이벤트 및 사용자 지정 추적 이벤트를 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="1d2bf-109">The tracking runtime implements a workflow instance to emit events related to the workflow lifecycle, events from workflow activities and custom tracking events.</span></span> <span data-ttu-id="1d2bf-110">다음 표에서는 추적 인프라의 기본 구성 요소에 대해 자세히 설명합니다</span><span class="sxs-lookup"><span data-stu-id="1d2bf-110">The following table details the primary components of the tracking infrastructure.</span></span>

|<span data-ttu-id="1d2bf-111">구성 요소</span><span class="sxs-lookup"><span data-stu-id="1d2bf-111">Component</span></span>|<span data-ttu-id="1d2bf-112">설명</span><span class="sxs-lookup"><span data-stu-id="1d2bf-112">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="1d2bf-113">추적 런타임</span><span class="sxs-lookup"><span data-stu-id="1d2bf-113">Tracking runtime</span></span>|<span data-ttu-id="1d2bf-114">추적 레코드를 내보낼 인프라를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1d2bf-114">Provides the infrastructure to emit tracking records.</span></span>|
|<span data-ttu-id="1d2bf-115">추적 참가자</span><span class="sxs-lookup"><span data-stu-id="1d2bf-115">Tracking participants</span></span>|<span data-ttu-id="1d2bf-116">추적 레코드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1d2bf-116">Consumes the tracking records.</span></span> <span data-ttu-id="1d2bf-117">.NET Framework 4는 추적 레코드를 ETW (ETW(Windows용 이벤트 추적)) 이벤트로 기록 하는 추적 참가자와 함께 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d2bf-117">.NET Framework 4 ships with a tracking participant that writes tracking records as Event Tracing for Windows (ETW) events.</span></span>|
|<span data-ttu-id="1d2bf-118">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="1d2bf-118">Tracking profile</span></span>|<span data-ttu-id="1d2bf-119">추적 참가자가 워크플로 인스턴스에서 내보낸 추적 레코드의 하위 집합을 구독할 수 있도록 하는 필터링 메커니즘입니다.</span><span class="sxs-lookup"><span data-stu-id="1d2bf-119">A filtering mechanism that allows a tracking participant to subscribe for a subset of the tracking records emitted from a workflow instance.</span></span>|

 <span data-ttu-id="1d2bf-120">다음 표에서는 워크플로 런타임에서 내보내는 추적 레코드에 대해 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1d2bf-120">The following table details the tracking records that the workflow runtime emits.</span></span>

|<span data-ttu-id="1d2bf-121">추적 레코드</span><span class="sxs-lookup"><span data-stu-id="1d2bf-121">Tracking Record</span></span>|<span data-ttu-id="1d2bf-122">설명</span><span class="sxs-lookup"><span data-stu-id="1d2bf-122">Description</span></span>|
|---------------------|-----------------|
|<span data-ttu-id="1d2bf-123">워크플로 인스턴스 추적 레코드</span><span class="sxs-lookup"><span data-stu-id="1d2bf-123">Workflow instance tracking records.</span></span>|<span data-ttu-id="1d2bf-124">워크플로 인스턴스의 수명 주기에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1d2bf-124">Describes the life cycle of the workflow instance.</span></span> <span data-ttu-id="1d2bf-125">예를 들어 워크플로가 시작되거나 완료되면 인스턴스 레코드를 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="1d2bf-125">For example, an instance record is emitted when the workflow starts or completes.</span></span>|
|<span data-ttu-id="1d2bf-126">활동 상태 추적 레코드</span><span class="sxs-lookup"><span data-stu-id="1d2bf-126">Activity state Tracking Records.</span></span>|<span data-ttu-id="1d2bf-127">활동 실행에 대해 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1d2bf-127">Details activity execution.</span></span> <span data-ttu-id="1d2bf-128">이러한 레코드는 활동이 예약된 시점, 활동이 완료된 시점, 오류가 throw된 시점 등과 같은 워크플로 활동 상태를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1d2bf-128">These records indicate the state of a workflow activity such as when an activity is scheduled or when the activity completes or when a fault is thrown.</span></span>|
|<span data-ttu-id="1d2bf-129">책갈피 다시 시작 레코드</span><span class="sxs-lookup"><span data-stu-id="1d2bf-129">Bookmark resumption record.</span></span>|<span data-ttu-id="1d2bf-130">워크플로 인스턴스 내의 책갈피를 다시 시작할 때마다 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="1d2bf-130">Emitted whenever a bookmark within a workflow instance is resumed.</span></span>|
|<span data-ttu-id="1d2bf-131">사용자 지정 추적 레코드</span><span class="sxs-lookup"><span data-stu-id="1d2bf-131">Custom Tracking Records.</span></span>|<span data-ttu-id="1d2bf-132">워크플로 작성자가 사용자 지정 추적 레코드를 만들어 사용자 지정 활동 중에 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d2bf-132">A workflow author can create Custom Tracking Records and emit them within the custom activity.</span></span>|

 <span data-ttu-id="1d2bf-133">추적 참가자는 추적 프로필을 사용하여 내보낸 <xref:System.Activities.Tracking.TrackingRecord> 개체의 하위 집합을 구독합니다.</span><span class="sxs-lookup"><span data-stu-id="1d2bf-133">The tracking participant subscribes for a subset of the emitted <xref:System.Activities.Tracking.TrackingRecord> objects using tracking profiles.</span></span> <span data-ttu-id="1d2bf-134">추적 프로필에는 특정 추적 레코드 형식을 구독할 수 있도록 허용하는 추적 쿼리가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d2bf-134">A tracking profile contains tracking queries that allow subscribing for a particular tracking record type.</span></span> <span data-ttu-id="1d2bf-135">추적 프로필은 코드나 구성에 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d2bf-135">Tracking profiles can be specified in code or in configuration.</span></span>

### <a name="custom-tracking-participant"></a><span data-ttu-id="1d2bf-136">사용자 지정 추적 참가자</span><span class="sxs-lookup"><span data-stu-id="1d2bf-136">Custom Tracking Participant</span></span>

 <span data-ttu-id="1d2bf-137">추적 참가자 API를 사용하면 워크플로 런타임에서 내보낸 <xref:System.Activities.Tracking.TrackingRecord> 개체를 처리하기 위한 사용자 지정 논리를 포함할 수 있는 사용자 제공 추적 참가자를 사용하여 추적 런타임을 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d2bf-137">The tracking participant API allows extension of the tracking runtime with a user provided tracking participant that can include custom logic to handle <xref:System.Activities.Tracking.TrackingRecord> objects emitted by the workflow runtime.</span></span>

 <span data-ttu-id="1d2bf-138">추적 참가자를 기록하려면 사용자가 <xref:System.Activities.Tracking.TrackingParticipant>를 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d2bf-138">To write a tracking participant the user must implement <xref:System.Activities.Tracking.TrackingParticipant>.</span></span> <span data-ttu-id="1d2bf-139">특히 사용자 지정 참가자는 <xref:System.Activities.Tracking.TrackingParticipant.Track%2A> 메서드를 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d2bf-139">Specifically, the <xref:System.Activities.Tracking.TrackingParticipant.Track%2A> method has to be implemented by the custom participant.</span></span> <span data-ttu-id="1d2bf-140">이 메서드는 워크플로 런타임에서 <xref:System.Activities.Tracking.TrackingRecord>를 내보낼 때 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d2bf-140">This method is called when a <xref:System.Activities.Tracking.TrackingRecord> is emitted by the workflow runtime.</span></span>

```csharp
public abstract class TrackingParticipant
{
    protected TrackingParticipant();

    public virtual TrackingProfile TrackingProfile { get; set; }
    public abstract void Track(TrackingRecord record, TimeSpan timeout);
}
```

 <span data-ttu-id="1d2bf-141">ConsoleTrackingParticipant.cs 파일에서 전체 추적 참가자가 구현 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d2bf-141">The complete tracking participant is implemented in the ConsoleTrackingParticipant.cs file.</span></span> <span data-ttu-id="1d2bf-142">다음 코드 예제는 <xref:System.Activities.Tracking.TrackingParticipant.Track%2A> 사용자 지정 추적 참가자에 대 한 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="1d2bf-142">The following code example is the <xref:System.Activities.Tracking.TrackingParticipant.Track%2A> method for the custom tracking participant.</span></span>

```csharp
protected override void Track(TrackingRecord record, TimeSpan timeout)
{
    ...
    WorkflowInstanceRecord workflowInstanceRecord = record as WorkflowInstanceRecord;
    if (workflowInstanceRecord != null)
    {
        Console.WriteLine(String.Format(CultureInfo.InvariantCulture,
            " Workflow InstanceID: {0} Workflow instance state: {1}",
            record.InstanceId, workflowInstanceRecord.State));
    }

    ActivityStateRecord activityStateRecord = record as ActivityStateRecord;
    if (activityStateRecord != null)
    {
        IDictionary<String, object> variables = activityStateRecord.Variables;
        StringBuilder vars = new StringBuilder();

        if (variables.Count > 0)
        {
            vars.AppendLine("\n\tVariables:");
            foreach (KeyValuePair<string, object> variable in variables)
            {
                vars.AppendLine(String.Format(
                    "\t\tName: {0} Value: {1}", variable.Key, variable.Value));
            }
        }
        Console.WriteLine(String.Format(CultureInfo.InvariantCulture,
            " :Activity DisplayName: {0} :ActivityInstanceState: {1} {2}",
                activityStateRecord.Activity.Name, activityStateRecord.State,
            ((variables.Count > 0) ? vars.ToString() : String.Empty)));
    }

    CustomTrackingRecord customTrackingRecord = record as CustomTrackingRecord;

    if ((customTrackingRecord != null) && (customTrackingRecord.Data.Count > 0))
    {
        ...
    }
    Console.WriteLine();

}
```

 <span data-ttu-id="1d2bf-143">다음 코드 예제에서는 워크플로 호출자에 콘솔 참가자를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1d2bf-143">The following code example adds the console participant to the workflow invoker.</span></span>

```csharp
ConsoleTrackingParticipant customTrackingParticipant = new ConsoleTrackingParticipant()
{
    ...
    // The tracking profile is set here, refer to Program.CS
...
}

WorkflowInvoker invoker = new WorkflowInvoker(BuildSampleWorkflow());
invoker.Extensions.Add(customTrackingParticipant);
```

### <a name="emitting-custom-tracking-records"></a><span data-ttu-id="1d2bf-144">사용자 지정 추적 레코드 내보내기</span><span class="sxs-lookup"><span data-stu-id="1d2bf-144">Emitting Custom Tracking Records</span></span>

 <span data-ttu-id="1d2bf-145">이 샘플에서는 사용자 지정 워크플로 활동에서 <xref:System.Activities.Tracking.CustomTrackingRecord> 개체를 내보내는 기능도 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1d2bf-145">This sample also demonstrates the ability to emit <xref:System.Activities.Tracking.CustomTrackingRecord> objects from a custom workflow activity:</span></span>

- <span data-ttu-id="1d2bf-146"><xref:System.Activities.Tracking.CustomTrackingRecord> 개체가 만들어지고, 레코드와 함께 내보낼 사용자 정의 데이터로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="1d2bf-146">The <xref:System.Activities.Tracking.CustomTrackingRecord> objects are created and populated with user-defined data that is desired to be emitted with the record.</span></span>

- <span data-ttu-id="1d2bf-147">는 <xref:System.Activities.Tracking.CustomTrackingRecord> 의 track 메서드를 호출 하 여 내보내집니다 <xref:System.Activities.ActivityContext> .</span><span class="sxs-lookup"><span data-stu-id="1d2bf-147">The <xref:System.Activities.Tracking.CustomTrackingRecord> is emitted by calling the track method of the <xref:System.Activities.ActivityContext>.</span></span>

 <span data-ttu-id="1d2bf-148">다음 예제에서는 사용자 지정 활동에서 <xref:System.Activities.Tracking.CustomTrackingRecord> 개체를 내보내는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1d2bf-148">The following example demonstrates how to emit <xref:System.Activities.Tracking.CustomTrackingRecord> objects within a custom activity.</span></span>

```csharp
// Create the Custom Tracking Record
CustomTrackingRecord customRecord = new CustomTrackingRecord("OrderIn")
{
    Data =
    {
        {"OrderId", 200},
        {"OrderDate", "20 Aug 2001"}
    }
};

// Emit custom tracking record
context.Track(customRecord);
```

#### <a name="to-use-this-sample"></a><span data-ttu-id="1d2bf-149">이 샘플을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="1d2bf-149">To use this sample</span></span>

1. <span data-ttu-id="1d2bf-150">Visual Studio 2010을 사용 하 여 CustomTrackingSample .sln 솔루션 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="1d2bf-150">Using Visual Studio 2010, open the CustomTrackingSample.sln solution file.</span></span>

2. <span data-ttu-id="1d2bf-151">Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="1d2bf-151">To build the solution, press CTRL+SHIFT+B.</span></span>

3. <span data-ttu-id="1d2bf-152">Ctrl+F5를 눌러 솔루션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="1d2bf-152">To run the solution, press CTRL+F5.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1d2bf-153">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d2bf-153">The samples may already be installed on your computer.</span></span> <span data-ttu-id="1d2bf-154">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="1d2bf-154">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="1d2bf-155">이 디렉터리가 없는 경우 [.NET Framework 4에 대 한 Windows Communication Foundation (wcf) 및 Windows Workflow Foundation (WF) 샘플](https://www.microsoft.com/download/details.aspx?id=21459) 로 이동 하 여 모든 WINDOWS COMMUNICATION FOUNDATION (wcf) 및 샘플을 다운로드 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d2bf-155">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="1d2bf-156">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d2bf-156">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Tracking\CustomTracking`  
  
## <a name="see-also"></a><span data-ttu-id="1d2bf-157">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1d2bf-157">See also</span></span>

- <span data-ttu-id="1d2bf-158">[AppFabric 모니터링 샘플](/previous-versions/appfabric/ff383407(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="1d2bf-158">[AppFabric Monitoring Samples](/previous-versions/appfabric/ff383407(v=azure.10))</span></span>
