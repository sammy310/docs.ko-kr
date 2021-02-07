---
description: '자세한 정보: WCF 서비스 및 ETW(Windows용 이벤트 추적)'
title: Windows용 WCF 서비스 및 이벤트 추척
ms.date: 03/30/2017
ms.assetid: eda4355d-0bd0-4dc9-80a2-d2c832152272
ms.openlocfilehash: ba2d323322a2d3481f1414ac58fbf0b44508bb03
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99755683"
---
# <a name="wcf-services-and-event-tracing-for-windows"></a><span data-ttu-id="b1630-103">Windows용 WCF 서비스 및 이벤트 추척</span><span class="sxs-lookup"><span data-stu-id="b1630-103">WCF Services and Event Tracing for Windows</span></span>

<span data-ttu-id="b1630-104">이 샘플에서는 Windows Communication Foundation (WCF)에서 분석 추적을 사용 하 여 ETW (ETW(Windows용 이벤트 추적))에서 이벤트를 내보내는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b1630-104">This sample demonstrates how to use the analytic tracing in Windows Communication Foundation (WCF) to emit events in Event Tracing for Windows (ETW).</span></span> <span data-ttu-id="b1630-105">분석 추적은 프로덕션 환경에서 WCF 서비스의 문제를 해결할 수 있는 WCF 스택의 주요 지점에서 발생 하는 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="b1630-105">The analytic traces are events emitted at key points in the WCF stack that allow troubleshooting of WCF services in production environment.</span></span>

 <span data-ttu-id="b1630-106">WCF 서비스의 분석 추적은 성능에 미치는 영향을 최소화 하면서 프로덕션 환경에서 설정 될 수 있는 추적입니다.</span><span class="sxs-lookup"><span data-stu-id="b1630-106">Analytic trace in WCF services is tracing that can be turned on in a production environment with minimal impact on performance.</span></span> <span data-ttu-id="b1630-107">이러한 추적은 ETW 세션에 이벤트로 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="b1630-107">These traces are emitted as events to an ETW session.</span></span>

 <span data-ttu-id="b1630-108">이 샘플에는 서비스에서 이벤트 로그로 이벤트를 내보내는 기본 WCF 서비스가 포함 되어 있습니다 .이 서비스는 이벤트 뷰어을 사용 하 여 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1630-108">This sample includes a basic WCF service in which events are emitted from the service to the event log, which can be viewed using Event Viewer.</span></span> <span data-ttu-id="b1630-109">또한 WCF 서비스에서 이벤트를 수신 대기 하는 전용 ETW 세션을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1630-109">It is also possible to start a dedicated ETW session that listens for events from the WCF service.</span></span> <span data-ttu-id="b1630-110">이 샘플에는 이벤트 뷰어를 사용하여 읽을 수 있는 이진 파일에 이벤트를 저장하는 전용 ETW 세션을 만드는 스크립트가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1630-110">The sample includes a script to create a dedicated ETW session that stores events in a binary file that can be read using Event Viewer.</span></span>

#### <a name="to-use-this-sample"></a><span data-ttu-id="b1630-111">이 샘플을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="b1630-111">To use this sample</span></span>

1. <span data-ttu-id="b1630-112">Visual Studio 2012을 사용 하 여 EtwAnalyticTraceSample 솔루션 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="b1630-112">Using Visual Studio 2012, open the EtwAnalyticTraceSample.sln solution file.</span></span>

2. <span data-ttu-id="b1630-113">Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="b1630-113">To build the solution, press CTRL+SHIFT+B.</span></span>

3. <span data-ttu-id="b1630-114">Ctrl+F5를 눌러 솔루션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="b1630-114">To run the solution, press CTRL+F5.</span></span>

     <span data-ttu-id="b1630-115">웹 브라우저에서 **계산기 .svc** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1630-115">In the Web browser, click **Calculator.svc**.</span></span> <span data-ttu-id="b1630-116">서비스의 WSDL 문서에 대한 URI가 브라우저에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="b1630-116">The URI of the WSDL document for the service should appear in the browser.</span></span> <span data-ttu-id="b1630-117">이 URI를 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="b1630-117">Copy that URI.</span></span>

     <span data-ttu-id="b1630-118">기본적으로 서비스는 포트 1378에서 요청 수신을 시작 `http://localhost:1378/Calculator.svc` 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1630-118">By default, the service starts listening for requests on port 1378 `http://localhost:1378/Calculator.svc`.</span></span>

4. <span data-ttu-id="b1630-119">WCF 테스트 클라이언트 (WcfTestClient.exe)를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1630-119">Run the WCF test client (WcfTestClient.exe).</span></span>

     <span data-ttu-id="b1630-120">WCF 테스트 클라이언트 (WcfTestClient.exe)는에 `\<Visual Studio 2012 Install Dir>\Common7\IDE\WcfTestClient.exe` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1630-120">The WCF test client (WcfTestClient.exe) is located at `\<Visual Studio 2012 Install Dir>\Common7\IDE\WcfTestClient.exe`.</span></span>  <span data-ttu-id="b1630-121">기본 Visual Studio 2012 설치 디렉터리는 `C:\Program Files\Microsoft Visual Studio 10.0` 입니다.</span><span class="sxs-lookup"><span data-stu-id="b1630-121">The default Visual Studio 2012 install dir is `C:\Program Files\Microsoft Visual Studio 10.0`.</span></span>

5. <span data-ttu-id="b1630-122">WCF 테스트 클라이언트 내에서 **파일** 을 선택 하 고 **서비스 추가** 를 선택 하 여 서비스를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1630-122">Within the WCF test client, add the service by selecting **File**, and then **Add Service**.</span></span>

     <span data-ttu-id="b1630-123">입력 상자에 엔드포인트 주소를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b1630-123">Add the endpoint address in the input box.</span></span> <span data-ttu-id="b1630-124">기본값은 `http://localhost:1378/Calculator.svc`입니다.</span><span class="sxs-lookup"><span data-stu-id="b1630-124">The default is `http://localhost:1378/Calculator.svc`.</span></span>

6. <span data-ttu-id="b1630-125">이벤트 뷰어 애플리케이션을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="b1630-125">Open the Event Viewer application.</span></span>

     <span data-ttu-id="b1630-126">서비스를 호출 하기 전에 이벤트 뷰어를 시작 하 고 이벤트 로그가 WCF 서비스에서 내보낸 추적 이벤트를 수신 대기 하 고 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1630-126">Before invoking the service, start Event Viewer and ensure that the event log is listening for tracking events emitted from the WCF service.</span></span>

7. <span data-ttu-id="b1630-127">**시작** 메뉴에서 **관리 도구** 를 선택한 다음 **이벤트 뷰어** 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1630-127">From the **Start** menu, select **Administrative Tools**, and then **Event Viewer**.</span></span>  <span data-ttu-id="b1630-128">**분석** 및 **디버그** 로그를 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1630-128">Enable the **Analytic** and **Debug** logs.</span></span>

8. <span data-ttu-id="b1630-129">이벤트 뷰어의 트리 뷰에서 **이벤트 뷰어**, **응용 프로그램 및 서비스 로그**, **Microsoft**, **Windows**, **응용 프로그램 서버-응용** 프로그램으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1630-129">In the tree view in Event Viewer, navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application Server-Applications**.</span></span> <span data-ttu-id="b1630-130">**응용 프로그램 서버-응용 프로그램** 을 마우스 오른쪽 단추로 클릭 하 고 **보기** 를 선택한 다음 **분석 및 디버그 로그 표시** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1630-130">Right-click **Application Server-Applications**, select **View**, and then **Show Analytic and Debug Logs**.</span></span>

     <span data-ttu-id="b1630-131">**분석 및 디버그 로그 표시** 옵션이 선택 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1630-131">Ensure that the **Show Analytic and Debug Logs** option is checked.</span></span>

9. <span data-ttu-id="b1630-132">**분석** 로그를 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1630-132">Enable the **Analytic** log.</span></span>

     <span data-ttu-id="b1630-133">이벤트 뷰어의 트리 뷰에서 **이벤트 뷰어**, **응용 프로그램 및 서비스 로그**, **Microsoft**, **Windows**, **응용 프로그램 서버-응용** 프로그램으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1630-133">In the tree view in Event Viewer, navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application Server-Applications**.</span></span> <span data-ttu-id="b1630-134">**분석** 을 마우스 오른쪽 단추로 클릭 하 고 **로그 사용** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1630-134">Right-click **Analytic** and select **Enable Log**.</span></span>

#### <a name="to-test-the-service"></a><span data-ttu-id="b1630-135">서비스를 테스트하려면</span><span class="sxs-lookup"><span data-stu-id="b1630-135">To test the service</span></span>

1. <span data-ttu-id="b1630-136">WCF 테스트 클라이언트로 다시 전환 하 고 분모를 0으로 지정 하는 기본값을 두 번 클릭 `Divide` 하 고 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1630-136">Switch back to WCF test client and double-click `Divide` and keep the default values, which specify a denominator of 0.</span></span>

     <span data-ttu-id="b1630-137">분모가 0이면 서비스에서는 오류를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="b1630-137">If the denominator is 0, then the service throws a fault.</span></span>

2. <span data-ttu-id="b1630-138">서비스에서 내보낸 이벤트를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b1630-138">Observe the events emitted from the service.</span></span>

     <span data-ttu-id="b1630-139">이벤트 뷰어으로 다시 전환 하 고 **이벤트 뷰어**, **응용 프로그램 및 서비스 로그**, **Microsoft**, **Windows**, **응용 프로그램 서버-응용** 프로그램으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1630-139">Switch back to Event Viewer and navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application Server-Applications**.</span></span> <span data-ttu-id="b1630-140">**분석** 을 마우스 오른쪽 단추로 클릭 하 고 **새로 고침** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1630-140">Right-click **Analytic** and select **Refresh**.</span></span>

     <span data-ttu-id="b1630-141">WCF 분석 추적 이벤트가 이벤트 뷰어에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1630-141">The WCF analytic trace events are displayed in the event viewer.</span></span> <span data-ttu-id="b1630-142">서비스에서 오류가 throw되었으므로 이벤트 뷰어에 오류 추적 이벤트가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1630-142">Notice that because a fault was thrown by the service an error trace event is displayed in the event viewer.</span></span>

3. <span data-ttu-id="b1630-143">1-2단계를 반복하되 이번에는 유효한 입력을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b1630-143">Repeat steps 1 and 2, but with valid inputs.</span></span> <span data-ttu-id="b1630-144">`N2` 매개 변수 값으로는 0 이외의 모든 숫자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1630-144">The value of the `N2` parameter can be any number other than 0.</span></span>

     <span data-ttu-id="b1630-145">분석 채널을 새로 고쳐 WCF 이벤트에 오류 이벤트가 포함되어 있지 않은지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b1630-145">Refresh the analytic channel to view the WCF events do not include any error events.</span></span>

 <span data-ttu-id="b1630-146">이 샘플에서는 WCF 서비스에서 내보낸 분석 추적 이벤트를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b1630-146">The sample demonstrates the analytic trace events emitted from a WCF service.</span></span>

#### <a name="to-cleanup-optional"></a><span data-ttu-id="b1630-147">정리하려면(옵션)</span><span class="sxs-lookup"><span data-stu-id="b1630-147">To cleanup (Optional)</span></span>

1. <span data-ttu-id="b1630-148">이벤트 뷰어를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="b1630-148">Open Event Viewer.</span></span>

2. <span data-ttu-id="b1630-149">**이벤트 뷰어**, **응용 프로그램 및 서비스 로그**, **Microsoft**, **Windows**, **응용 프로그램-서버-** 응용 프로그램으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1630-149">Navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application-Server-Applications**.</span></span> <span data-ttu-id="b1630-150">**분석** 을 마우스 오른쪽 단추로 클릭 하 고 **로그 사용 안 함** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1630-150">Right-click **Analytic** and select **Disable Log**.</span></span>

3. <span data-ttu-id="b1630-151">**이벤트 뷰어**, **응용 프로그램 및 서비스 로그**, **Microsoft**, **Windows**, **응용 프로그램-서버-** 응용 프로그램으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1630-151">Navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application-Server-Applications**.</span></span> <span data-ttu-id="b1630-152">**분석** 을 마우스 오른쪽 단추로 클릭 하 고 **로그 지우기** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1630-152">Right-click **Analytic** and select **Clear Log**.</span></span>

4. <span data-ttu-id="b1630-153">**지우기** 옵션을 선택 하 여 이벤트를 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="b1630-153">Choose the **Clear** option to clear the events.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b1630-154">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1630-154">The samples may already be installed on your computer.</span></span> <span data-ttu-id="b1630-155">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="b1630-155">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="b1630-156">이 디렉터리가 없는 경우 [.NET Framework 4에 대 한 Windows Communication Foundation (wcf) 및 Windows Workflow Foundation (WF) 샘플](https://www.microsoft.com/download/details.aspx?id=21459) 로 이동 하 여 모든 WINDOWS COMMUNICATION FOUNDATION (wcf) 및 샘플을 다운로드 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1630-156">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="b1630-157">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1630-157">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\ETWTracing`  
  
## <a name="see-also"></a><span data-ttu-id="b1630-158">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b1630-158">See also</span></span>

- <span data-ttu-id="b1630-159">[AppFabric 모니터링 샘플](/previous-versions/appfabric/ff383407(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="b1630-159">[AppFabric Monitoring Samples](/previous-versions/appfabric/ff383407(v=azure.10))</span></span>
