---
description: '자세히 알아보기: Windows에서 이벤트 추적으로 이벤트 추적'
title: Windows에서 이벤트 추적으로 이벤트 추적
ms.date: 03/30/2017
ms.assetid: f812659b-0943-45ff-9430-4defa733182b
ms.openlocfilehash: 92ad4aaee100bb3ba7f4174bbbde1dc7eaed58de
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99653747"
---
# <a name="tracking-events-into-event-tracing-in-windows"></a><span data-ttu-id="bfb0c-103">Windows에서 이벤트 추적으로 이벤트 추적</span><span class="sxs-lookup"><span data-stu-id="bfb0c-103">Tracking Events into Event Tracing in Windows</span></span>

<span data-ttu-id="bfb0c-104">이 샘플에서는 워크플로 서비스에서 WF (Windows Workflow Foundation) 추적을 사용 하도록 설정 하 고 ETW (ETW(Windows용 이벤트 추적))에서 추적 이벤트를 내보내는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bfb0c-104">This sample demonstrates how to enable Windows Workflow Foundation (WF) tracking on a workflow service and emit the tracking events in Event Tracing for Windows (ETW).</span></span> <span data-ttu-id="bfb0c-105">이 샘플에서는 ETW 추적 참가자(<xref:System.Activities.Tracking.EtwTrackingParticipant>)를 사용하여 워크플로 추적 레코드를 ETW로 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="bfb0c-105">To emit workflow tracking records into ETW, the sample uses the ETW tracking participant (<xref:System.Activities.Tracking.EtwTrackingParticipant>).</span></span>

<span data-ttu-id="bfb0c-106">샘플에서 워크플로는 요청을 받고, 입력 데이터의 상호 데이터를 입력 변수에 할당한 다음, 클라이언트에 상호 데이터를 다시 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="bfb0c-106">The workflow in the sample receives a request, assigns the reciprocal of the input data to the input variable and returns the reciprocal back to the client.</span></span> <span data-ttu-id="bfb0c-107">입력 데이터가 0인 경우 처리되지 않는 0으로 나누기 예외가 발생하여 워크플로가 중단됩니다.</span><span class="sxs-lookup"><span data-stu-id="bfb0c-107">When the input data is 0, a divide by zero exception occurs that is unhandled that causes the workflow to abort.</span></span> <span data-ttu-id="bfb0c-108">추적 기능을 사용하도록 설정되어 있으면 오류 추적 레코드가 ETW로 내보내지므로 나중에 오류 문제를 해결하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bfb0c-108">With tracking enabled, the error track record is emitted to ETW, which can help troubleshoot the error later.</span></span> <span data-ttu-id="bfb0c-109">ETW 추적 참가자는 추적 레코드를 구독하도록 추적 프로필을 사용하여 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="bfb0c-109">The ETW tracking participant is configured with a tracking profile to subscribe to tracking records.</span></span> <span data-ttu-id="bfb0c-110">추적 프로필은 Web.config 파일에 정의되고 ETW 추적 참가자에 구성 매개 변수로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="bfb0c-110">The tracking profile is defined in the Web.config file and provided as a configuration parameter to the ETW tracking participant.</span></span> <span data-ttu-id="bfb0c-111">ETW 추적 참가자는 워크플로 서비스의 Web.config 파일에 구성되며 서비스에 서비스 동작으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="bfb0c-111">The ETW tracking participant is configured in the Web.config file of the workflow service and is applied to the service as a service behavior.</span></span> <span data-ttu-id="bfb0c-112">이 샘플에서는 이벤트 뷰어를 사용하여 이벤트 로그의 추적 이벤트를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="bfb0c-112">In this sample, you view the tracking events in the event log using Event Viewer.</span></span>

## <a name="workflow-tracking-details"></a><span data-ttu-id="bfb0c-113">워크플로 추적 세부 정보</span><span class="sxs-lookup"><span data-stu-id="bfb0c-113">Workflow Tracking Details</span></span>

<span data-ttu-id="bfb0c-114">Windows Workflow Foundation는 추적 인프라를 제공 하 여 워크플로 인스턴스 실행을 추적 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfb0c-114">Windows Workflow Foundation provides a tracking infrastructure to track the execution of a workflow instance.</span></span> <span data-ttu-id="bfb0c-115">추적 런타임은 워크플로 인스턴스를 만들어 워크플로 수명 주기와 관련된 이벤트, 워크플로 활동의 이벤트 및 사용자 지정 이벤트를 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="bfb0c-115">The tracking runtime creates a workflow instance to emit events related to the workflow lifecycle, events from workflow activities and custom events.</span></span> <span data-ttu-id="bfb0c-116">다음 표에서는 추적 인프라의 기본 구성 요소에 대해 자세히 설명합니다</span><span class="sxs-lookup"><span data-stu-id="bfb0c-116">The following table details the primary components of the tracking infrastructure.</span></span>

|<span data-ttu-id="bfb0c-117">구성 요소</span><span class="sxs-lookup"><span data-stu-id="bfb0c-117">Component</span></span>|<span data-ttu-id="bfb0c-118">설명</span><span class="sxs-lookup"><span data-stu-id="bfb0c-118">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="bfb0c-119">추적 런타임</span><span class="sxs-lookup"><span data-stu-id="bfb0c-119">Tracking runtime</span></span>|<span data-ttu-id="bfb0c-120">추적 레코드를 내보낼 인프라를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="bfb0c-120">Provides the infrastructure to emit tracking records.</span></span>|
|<span data-ttu-id="bfb0c-121">추적 참가자</span><span class="sxs-lookup"><span data-stu-id="bfb0c-121">Tracking participants</span></span>|<span data-ttu-id="bfb0c-122">추적 레코드에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="bfb0c-122">Accesses the tracking records.</span></span> [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)]<span data-ttu-id="bfb0c-123">에는 추적 레코드를 ETW(Windows용 이벤트 추적) 이벤트로 기록하는 추적 참가자가 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="bfb0c-123">ships with a tracking participant that writes tracking records as Event Tracing for Windows (ETW) events.</span></span>|
|<span data-ttu-id="bfb0c-124">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="bfb0c-124">Tracking profile</span></span>|<span data-ttu-id="bfb0c-125">추적 참가자가 워크플로 인스턴스에서 내보낸 추적 레코드의 하위 집합을 구독할 수 있도록 하는 필터링 메커니즘입니다.</span><span class="sxs-lookup"><span data-stu-id="bfb0c-125">A filtering mechanism that allows a tracking participant to subscribe for a subset of the tracking records emitted from a workflow instance.</span></span>|

<span data-ttu-id="bfb0c-126">다음 표에서는 워크플로 런타임에서 내보내는 추적 레코드에 대해 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bfb0c-126">The following table details the tracking records that the workflow runtime emits.</span></span>

|<span data-ttu-id="bfb0c-127">추적 레코드</span><span class="sxs-lookup"><span data-stu-id="bfb0c-127">Tracking record</span></span>|<span data-ttu-id="bfb0c-128">설명</span><span class="sxs-lookup"><span data-stu-id="bfb0c-128">Description</span></span>|
|---------------------|-----------------|
|<span data-ttu-id="bfb0c-129">워크플로 인스턴스 추적 레코드</span><span class="sxs-lookup"><span data-stu-id="bfb0c-129">Workflow instance tracking records.</span></span>|<span data-ttu-id="bfb0c-130">워크플로 인스턴스의 수명 주기에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bfb0c-130">Describes the lifecycle of the workflow instance.</span></span> <span data-ttu-id="bfb0c-131">예를 들어 워크플로가 시작되거나 완료되면 인스턴스 레코드를 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="bfb0c-131">For example, an instance record is emitted when the workflow starts or completes.</span></span>|
|<span data-ttu-id="bfb0c-132">활동 상태 추적 레코드</span><span class="sxs-lookup"><span data-stu-id="bfb0c-132">Activity state tracking records.</span></span>|<span data-ttu-id="bfb0c-133">활동 실행에 대해 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bfb0c-133">Details activity execution.</span></span> <span data-ttu-id="bfb0c-134">이러한 레코드는 활동이 예약된 시점, 활동이 완료된 시점, 오류가 throw된 시점 등과 같은 워크플로 활동 상태를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="bfb0c-134">These records indicate the state of a workflow activity such as when an activity is scheduled or when the activity completes or when a fault is thrown.</span></span>|
|<span data-ttu-id="bfb0c-135">책갈피 다시 시작 레코드</span><span class="sxs-lookup"><span data-stu-id="bfb0c-135">Bookmark resumption record.</span></span>|<span data-ttu-id="bfb0c-136">워크플로 인스턴스 내의 책갈피를 다시 시작할 때마다 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="bfb0c-136">Emitted whenever a bookmark within a workflow instance is resumed.</span></span>|
|<span data-ttu-id="bfb0c-137">사용자 지정 추적 레코드</span><span class="sxs-lookup"><span data-stu-id="bfb0c-137">Custom tracking records.</span></span>|<span data-ttu-id="bfb0c-138">워크플로 작성자가 사용자 지정 추적 레코드를 만들어 사용자 지정 활동 중에 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfb0c-138">A workflow author can create custom tracking records and emit them within the custom activity.</span></span>|
|<xref:System.Activities.Tracking.ActivityScheduledRecord>|<span data-ttu-id="bfb0c-139">이 레코드는 활동이 다른 활동을 예약할 때 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="bfb0c-139">This record is emitted when an activity schedules another activity.</span></span>|
|<xref:System.Activities.Tracking.FaultPropagationRecord>|<span data-ttu-id="bfb0c-140">이 레코드는 활동에서 오류가 전파될 때 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="bfb0c-140">This record is emitted when a fault is propagated from an activity.</span></span>|
|<xref:System.Activities.Tracking.CancelRequestedRecord>|<span data-ttu-id="bfb0c-141">이 레코드는 활동이 다른 활동에 의해 취소될 때 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="bfb0c-141">This record is emitted when an activity is canceled by another activity.</span></span>|

<span data-ttu-id="bfb0c-142">추적 참가자는 추적 프로필을 사용하여 내보낸 추적 레코드의 하위 집합을 구독합니다.</span><span class="sxs-lookup"><span data-stu-id="bfb0c-142">The tracking participant subscribes for a subset of the emitted tracking records using tracking profiles.</span></span> <span data-ttu-id="bfb0c-143">추적 프로필에는 특정 추적 레코드 형식을 구독할 수 있도록 허용하는 추적 쿼리가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="bfb0c-143">A tracking profile contains tracking queries that allow subscribing for a particular tracking record type.</span></span> <span data-ttu-id="bfb0c-144">추적 프로필은 코드나 구성에 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfb0c-144">Tracking profiles can be specified in code or in configuration.</span></span>

#### <a name="to-use-this-sample"></a><span data-ttu-id="bfb0c-145">이 샘플을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="bfb0c-145">To use this sample</span></span>

1. <span data-ttu-id="bfb0c-146">Visual Studio 2010을 사용 하 여 EtwTrackingParticipantSample 솔루션 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="bfb0c-146">Using Visual Studio 2010, open the EtwTrackingParticipantSample.sln solution file.</span></span>

2. <span data-ttu-id="bfb0c-147">Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="bfb0c-147">To build the solution, press CTRL+SHIFT+B.</span></span>

3. <span data-ttu-id="bfb0c-148">F5 키를 눌러 솔루션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="bfb0c-148">To run the solution, press F5.</span></span>

    <span data-ttu-id="bfb0c-149">기본적으로이 서비스는 포트 53797 ()에서 수신 대기 `http://localhost:53797/SampleWorkflowService.xamlx` 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfb0c-149">By default, the service is listening on port 53797 (`http://localhost:53797/SampleWorkflowService.xamlx`).</span></span>

4. <span data-ttu-id="bfb0c-150">파일 탐색기를 사용 하 여 WCF 테스트 클라이언트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="bfb0c-150">Using File Explorer, open the WCF test client.</span></span>

    <span data-ttu-id="bfb0c-151">WCF 테스트 클라이언트 (WcfTestClient.exe)는 \Common7\IDE\ 폴더에 있습니다 \<Visual Studio 2010 installation folder> .</span><span class="sxs-lookup"><span data-stu-id="bfb0c-151">The WCF test client (WcfTestClient.exe) is located in the \<Visual Studio 2010 installation folder>\Common7\IDE\ folder.</span></span>

    <span data-ttu-id="bfb0c-152">기본 Visual Studio 2010 설치 폴더는 C:\Program Files\Microsoft Visual Studio 10.0입니다.</span><span class="sxs-lookup"><span data-stu-id="bfb0c-152">The default Visual Studio 2010 installation folder is C:\Program Files\Microsoft Visual Studio 10.0.</span></span>

5. <span data-ttu-id="bfb0c-153">WCF 테스트 클라이언트의 **파일** 메뉴에서 **서비스 추가** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfb0c-153">In WCF test client, select **Add Service** from the **File** menu.</span></span>

    <span data-ttu-id="bfb0c-154">입력 상자에 엔드포인트 주소를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="bfb0c-154">Add the endpoint address in the input box.</span></span> <span data-ttu-id="bfb0c-155">기본값은 `http://localhost:53797/SampleWorkflowService.xamlx`입니다.</span><span class="sxs-lookup"><span data-stu-id="bfb0c-155">The default is `http://localhost:53797/SampleWorkflowService.xamlx`.</span></span>

6. <span data-ttu-id="bfb0c-156">이벤트 뷰어 애플리케이션을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="bfb0c-156">Open the Event Viewer application.</span></span>

    <span data-ttu-id="bfb0c-157">서비스를 호출 하기 전에 **시작** 메뉴에서 이벤트 뷰어을 시작 하 고 **실행** 을 선택 하 고 입력을 입력 `eventvwr.exe` 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfb0c-157">Before invoking the service, start Event Viewer from the **Start** menu, select **Run** and type in `eventvwr.exe`.</span></span> <span data-ttu-id="bfb0c-158">이벤트 로그가 워크플로 서비스에서 내보낸 추적 이벤트를 수신 대기하고 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="bfb0c-158">Ensure that the event log is listening for tracking events emitted from the workflow service.</span></span>

7. <span data-ttu-id="bfb0c-159">이벤트 뷰어의 트리 뷰에서 **이벤트 뷰어**, **응용 프로그램 및 서비스 로그** 및 **Microsoft** 로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfb0c-159">In the tree view of the Event Viewer, navigate to **Event Viewer**, **Applications and Services Logs**, and **Microsoft**.</span></span> <span data-ttu-id="bfb0c-160">**Microsoft** 를 마우스 오른쪽 단추로 클릭 하 고 **보기** 를 선택한 다음 **분석 및 디버그 로그 표시** 를 선택 하 여 분석 및 디버그 로그를 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfb0c-160">Right-click **Microsoft** and select **View** and then **Show Analytic and Debug Logs** to enable the analytic and debug logs</span></span>

    <span data-ttu-id="bfb0c-161">**분석 및 디버그 로그 표시** 옵션이 선택 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfb0c-161">Ensure that the **Show Analytic and Debug Logs** option is checked.</span></span>

8. <span data-ttu-id="bfb0c-162">이벤트 뷰어의 트리 뷰에서 **이벤트 뷰어**, **응용 프로그램 및 서비스 로그**, **Microsoft**, **Windows**, **응용 프로그램 서버-응용** 프로그램으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfb0c-162">In the tree view in Event Viewer, navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, **Application Server-Applications**.</span></span> <span data-ttu-id="bfb0c-163">**분석** 을 마우스 오른쪽 단추로 클릭 하 고 **로그 사용** 을 선택 하 여 **분석** 로그를 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfb0c-163">Right-click **Analytic** and select **Enable Log** to enable the **Analytic** log.</span></span>

9. <span data-ttu-id="bfb0c-164">`GetData`를 두 번 클릭하여 WCF 테스트 클라이언트로 서비스를 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="bfb0c-164">Test the service using the WCF test client by double-clicking `GetData`.</span></span>

    <span data-ttu-id="bfb0c-165">그러면 `GetData` 메서드가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="bfb0c-165">This opens the `GetData` method.</span></span> <span data-ttu-id="bfb0c-166">요청은 하나의 매개 변수를 받아들이고 값이 기본값인 0인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="bfb0c-166">The request accepts one parameter and ensures that the value is 0, which is the default.</span></span>

     <span data-ttu-id="bfb0c-167">**호출** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfb0c-167">Click **Invoke**.</span></span>

10. <span data-ttu-id="bfb0c-168">워크플로에서 내보낸 이벤트를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="bfb0c-168">Observe the events emitted from the workflow.</span></span>

    <span data-ttu-id="bfb0c-169">이벤트 뷰어으로 다시 전환 하 여 **이벤트 뷰어**, **응용 프로그램 및 서비스 로그**, **Microsoft**, **Windows**, **응용 프로그램 서버-응용** 프로그램으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfb0c-169">Switch back to Event Viewer and navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, **Application Server-Applications**.</span></span> <span data-ttu-id="bfb0c-170">**분석** 을 마우스 오른쪽 단추로 클릭 하 고 **새로 고침** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfb0c-170">Right-click **Analytic** and select **Refresh**.</span></span>

    <span data-ttu-id="bfb0c-171">이벤트 뷰어에 워크플로 이벤트가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="bfb0c-171">The workflow events are displayed in the event viewer.</span></span> <span data-ttu-id="bfb0c-172">워크플로 실행 이벤트가 표시되며, 이 중 하나는 워크플로의 오류에 해당하는 처리되지 않은 예외입니다.</span><span class="sxs-lookup"><span data-stu-id="bfb0c-172">Notice that workflow execution events are displayed and that one of them is an unhandled exception that corresponds to the error in workflow.</span></span> <span data-ttu-id="bfb0c-173">또한 워크플로 활동에서 경고 이벤트를 내보내며 이는 활동이 오류를 throw할 것임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="bfb0c-173">Also, a warning event is emitted from the workflow activity, which indicates that the activity is throwing a fault.</span></span>

11. <span data-ttu-id="bfb0c-174">오류가 throw되지 않도록 0 이외의 입력 데이터를 사용하여 9단계와 10단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="bfb0c-174">Repeat steps 9 and 10 with an input of data other than 0, so that no error is thrown.</span></span>

<span data-ttu-id="bfb0c-175">추적 프로필을 사용하면 워크플로 인스턴스 상태가 변경될 때 런타임에서 내보내는 이벤트를 구독할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfb0c-175">Tracking profiles allow you to subscribe to events that are emitted by the runtime when the state of a workflow instance changes.</span></span> <span data-ttu-id="bfb0c-176">모니터링 요구 사항에 따라 워크플로에서 상위 수준의 상태 변경 내용 중 작은 부분만 구독하는 매우 개괄적인 프로필을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfb0c-176">Depending on your monitoring requirements, you can create a profile that is very coarse, which subscribes to a small set of high-level state changes on a workflow.</span></span> <span data-ttu-id="bfb0c-177">그러나 나중에 실행을 다시 생성할 수 있을 정도로 출력이 풍부한 매우 정확한 프로필을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfb0c-177">On the other hand, you can create a very precise profile whose output is rich enough to reconstruct the execution later.</span></span> <span data-ttu-id="bfb0c-178">이 샘플에서는 작은 이벤트 집합을 내보내는 `HealthMonitoring Tracking Profile`을 사용하여 워크플로 런타임에서 ETW로 내보내는 이벤트를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bfb0c-178">The sample demonstrates the events emitted from the workflow runtime to ETW using the `HealthMonitoring Tracking Profile`, which emits a small set of events.</span></span> <span data-ttu-id="bfb0c-179">추가 워크플로 추적 이벤트를 내보내는 다른 프로필도 `Troubleshooting Tracking Profile`이라는 Web.config에 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="bfb0c-179">A different profile that emits more workflow tracking events is also provided in the Web.config that is named `Troubleshooting Tracking Profile`.</span></span> <span data-ttu-id="bfb0c-180">[!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)]가 설치되어 있으면 Machine.config 파일에 이름이 비어 있는 기본 프로필이 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="bfb0c-180">When the [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)] is installed, a default profile with an empty name is configured in the Machine.config file.</span></span> <span data-ttu-id="bfb0c-181">프로필 이름을 지정하지 않았거나 빈 프로필 이름을 지정한 경우에는 ETW 추적 동작 구성에서 이 프로필을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="bfb0c-181">This profile is used by the ETW tracking behavior configuration when no profile name or an empty profile name is specified.</span></span>

<span data-ttu-id="bfb0c-182">상태 모니터링 추적 프로필은 워크플로 인스턴스 레코드와 활동 오류 전파 레코드를 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="bfb0c-182">The health monitoring tracking profile emits workflow instance records and activity fault propagation records.</span></span> <span data-ttu-id="bfb0c-183">이 프로필은 Web.config 구성 파일에 다음 추적 프로필을 추가하여 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="bfb0c-183">This profile is created by adding the following tracking profile to a Web.config configuration file.</span></span>

```xml
<tracking>
  <profiles>
    <trackingProfile name="HealthMonitoring Tracking Profile">
      <workflow activityDefinitionId="*">
        <workflowInstanceQueries>
          <workflowInstanceQuery>
            <states>
              <state name="Started"/>
              <state name="Completed"/>
              <state name="Aborted"/>
              <state name="UnhandledException"/>
            </states>
          </workflowInstanceQuery>
        </workflowInstanceQueries>
        <faultPropagationQueries>
          <faultPropagationQuery faultSourceActivityName ="*" faultHandlerActivityName="*"/>
        </faultPropagationQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```

 <span data-ttu-id="bfb0c-184">`EtwTrackingParticipant` 구성을 다음 내용으로 변경하여 프로필을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfb0c-184">The profile can be changed by changing the `EtwTrackingParticipant` configuration to the following.</span></span>

```xml
<behaviors>
  <serviceBehaviors>
    <behavior>
      <etwTracking profileName="HealthMonitoring Tracking Profile"/>
    </behavior>
  </serviceBehaviors>
</behaviors>
```

#### <a name="to-clean-up-optional"></a><span data-ttu-id="bfb0c-185">정리하려면(옵션)</span><span class="sxs-lookup"><span data-stu-id="bfb0c-185">To clean up (Optional)</span></span>

1. <span data-ttu-id="bfb0c-186">이벤트 뷰어를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="bfb0c-186">Open Event Viewer.</span></span>

2. <span data-ttu-id="bfb0c-187">**이벤트 뷰어**, **응용 프로그램 및 서비스 로그**, **Microsoft**, **Windows**, **응용 프로그램 서버-응용** 프로그램으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfb0c-187">Navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, **Application Server-Applications**.</span></span> <span data-ttu-id="bfb0c-188">**분석** 을 마우스 오른쪽 단추로 클릭 하 고 **로그 사용 안 함** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfb0c-188">Right-click **Analytic** and select **Disable Log**.</span></span>

3. <span data-ttu-id="bfb0c-189">**이벤트 뷰어**, **응용 프로그램 및 서비스 로그**, **Microsoft**, **Windows**, **응용 프로그램 서버-응용** 프로그램으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfb0c-189">Navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, **Application Server-Applications**.</span></span> <span data-ttu-id="bfb0c-190">**분석** 을 마우스 오른쪽 단추로 클릭 하 고 **로그 지우기** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfb0c-190">Right-click **Analytic** and select **Clear Log**.</span></span>

4. <span data-ttu-id="bfb0c-191">**지우기** 옵션을 선택 하 여 이벤트를 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="bfb0c-191">Choose the **Clear** option to clear the events.</span></span>

## <a name="known-issue"></a><span data-ttu-id="bfb0c-192">알려진 이슈</span><span class="sxs-lookup"><span data-stu-id="bfb0c-192">Known Issue</span></span>

> [!NOTE]
> <span data-ttu-id="bfb0c-193">ETW 이벤트가 디코딩되지 않을 수 있으며, 이는 이벤트 뷰어와 관련하여 알려진 문제입니다.</span><span class="sxs-lookup"><span data-stu-id="bfb0c-193">There is a known issue in the Event Viewer where it may fail to decode ETW events.</span></span> <span data-ttu-id="bfb0c-194">다음과 같은 오류 메시지가 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfb0c-194">You may see an error message that looks like the following.</span></span>
>
> <span data-ttu-id="bfb0c-195">\<id>원본 Microsoft-Windows 응용 프로그램 Server-Applications의 이벤트 ID에 대 한 설명을 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bfb0c-195">The description for Event ID \<id> from source Microsoft-Windows-Application Server-Applications cannot be found.</span></span> <span data-ttu-id="bfb0c-196">이 이벤트가 발생되는 구성 요소가 로컬 컴퓨터에 설치되지 않았거나 설치가 손상되었습니다.</span><span class="sxs-lookup"><span data-stu-id="bfb0c-196">Either the component that raises this event is not installed on your local computer or the installation is corrupted.</span></span> <span data-ttu-id="bfb0c-197">로컬 컴퓨터에 구성 요소를 설치하거나 복구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfb0c-197">You can install or repair the component on the local computer.</span></span>
>
> <span data-ttu-id="bfb0c-198">이 오류가 발생하면 동작 창에서 새로 고침을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="bfb0c-198">If you encounter this error, click refresh in the actions pane.</span></span> <span data-ttu-id="bfb0c-199">그러면 이벤트가 올바르게 디코딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="bfb0c-199">The event should now decode properly.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bfb0c-200">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfb0c-200">The samples may already be installed on your computer.</span></span> <span data-ttu-id="bfb0c-201">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="bfb0c-201">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="bfb0c-202">이 디렉터리가 없는 경우 [.NET Framework 4에 대 한 Windows Communication Foundation (wcf) 및 Windows Workflow Foundation (WF) 샘플](https://www.microsoft.com/download/details.aspx?id=21459) 로 이동 하 여 모든 WINDOWS COMMUNICATION FOUNDATION (wcf) 및 샘플을 다운로드 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfb0c-202">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="bfb0c-203">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfb0c-203">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Tracking\EtwTracking`

## <a name="see-also"></a><span data-ttu-id="bfb0c-204">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bfb0c-204">See also</span></span>

- <span data-ttu-id="bfb0c-205">[AppFabric 모니터링 샘플](/previous-versions/appfabric/ff383407(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="bfb0c-205">[AppFabric Monitoring Samples](/previous-versions/appfabric/ff383407(v=azure.10))</span></span>
