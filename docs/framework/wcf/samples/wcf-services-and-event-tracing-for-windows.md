---
title: Windows용 WCF 서비스 및 이벤트 추척
ms.date: 03/30/2017
ms.assetid: eda4355d-0bd0-4dc9-80a2-d2c832152272
ms.openlocfilehash: b8a1f30f20aa2c541a574a070b3644569d633ca2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183208"
---
# <a name="wcf-services-and-event-tracing-for-windows"></a><span data-ttu-id="af883-102">Windows용 WCF 서비스 및 이벤트 추척</span><span class="sxs-lookup"><span data-stu-id="af883-102">WCF Services and Event Tracing for Windows</span></span>
<span data-ttu-id="af883-103">이 샘플에서는 WCF(Windows 통신 재단)의 분석 추적을 사용하여 ETW(Windows용 이벤트 추적)에서 이벤트를 내보하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="af883-103">This sample demonstrates how to use the analytic tracing in Windows Communication Foundation (WCF) to emit events in Event Tracing for Windows (ETW).</span></span> <span data-ttu-id="af883-104">분석 추적은 프로덕션 환경에서 WCF 서비스 문제를 해결할 수 있는 WCF 스택의 핵심 지점에서 내보낸 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="af883-104">The analytic traces are events emitted at key points in the WCF stack that allow troubleshooting of WCF services in production environment.</span></span>

 <span data-ttu-id="af883-105">WCF 서비스의 분석 추적은 성능에 미치는 영향을 최소화하면서 프로덕션 환경에서 켜질 수 있는 추적입니다.</span><span class="sxs-lookup"><span data-stu-id="af883-105">Analytic trace in WCF services is tracing that can be turned on in a production environment with minimal impact on performance.</span></span> <span data-ttu-id="af883-106">이러한 추적은 ETW 세션에 이벤트로 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="af883-106">These traces are emitted as events to an ETW session.</span></span>

 <span data-ttu-id="af883-107">이 샘플에는 이벤트 뷰어를 사용하여 볼 수 있는 이벤트로 이벤트가 서비스에서 이벤트로 내보내지는 기본 WCF 서비스가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af883-107">This sample includes a basic WCF service in which events are emitted from the service to the event log, which can be viewed using Event Viewer.</span></span> <span data-ttu-id="af883-108">WCF 서비스의 이벤트를 수신하는 전용 ETW 세션을 시작할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af883-108">It is also possible to start a dedicated ETW session that listens for events from the WCF service.</span></span> <span data-ttu-id="af883-109">이 샘플에는 이벤트 뷰어를 사용하여 읽을 수 있는 이진 파일에 이벤트를 저장하는 전용 ETW 세션을 만드는 스크립트가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af883-109">The sample includes a script to create a dedicated ETW session that stores events in a binary file that can be read using Event Viewer.</span></span>

#### <a name="to-use-this-sample"></a><span data-ttu-id="af883-110">이 샘플을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="af883-110">To use this sample</span></span>

1. <span data-ttu-id="af883-111">Visual Studio 2012를 사용하여 EtwAnalyticTraceSample.sln 솔루션 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="af883-111">Using Visual Studio 2012, open the EtwAnalyticTraceSample.sln solution file.</span></span>

2. <span data-ttu-id="af883-112">Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="af883-112">To build the solution, press CTRL+SHIFT+B.</span></span>

3. <span data-ttu-id="af883-113">Ctrl+F5를 눌러 솔루션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="af883-113">To run the solution, press CTRL+F5.</span></span>

     <span data-ttu-id="af883-114">웹 브라우저에서 **계산기.svc를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="af883-114">In the Web browser, click **Calculator.svc**.</span></span> <span data-ttu-id="af883-115">서비스의 WSDL 문서에 대한 URI가 브라우저에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="af883-115">The URI of the WSDL document for the service should appear in the browser.</span></span> <span data-ttu-id="af883-116">이 URI를 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="af883-116">Copy that URI.</span></span>

     <span data-ttu-id="af883-117">기본적으로 서비스는 포트 1378에서 `http://localhost:1378/Calculator.svc`요청을 수신 대기하기 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="af883-117">By default, the service starts listening for requests on port 1378 `http://localhost:1378/Calculator.svc`.</span></span>

4. <span data-ttu-id="af883-118">WCF 테스트 클라이언트(WcfTestClient.exe)를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="af883-118">Run the WCF test client (WcfTestClient.exe).</span></span>

     <span data-ttu-id="af883-119">WCF 테스트 클라이언트(WcfTestClient.exe)는 `\<Visual Studio 2012 Install Dir>\Common7\IDE\WcfTestClient.exe`에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af883-119">The WCF test client (WcfTestClient.exe) is located at `\<Visual Studio 2012 Install Dir>\Common7\IDE\WcfTestClient.exe`.</span></span>  <span data-ttu-id="af883-120">기본 Visual Studio 2012 `C:\Program Files\Microsoft Visual Studio 10.0`설치 dir은 .</span><span class="sxs-lookup"><span data-stu-id="af883-120">The default Visual Studio 2012 install dir is `C:\Program Files\Microsoft Visual Studio 10.0`.</span></span>

5. <span data-ttu-id="af883-121">WCF 테스트 클라이언트 내에서 **파일**을 선택한 다음 **서비스 추가를**선택하여 서비스를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="af883-121">Within the WCF test client, add the service by selecting **File**, and then **Add Service**.</span></span>

     <span data-ttu-id="af883-122">입력 상자에 엔드포인트 주소를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="af883-122">Add the endpoint address in the input box.</span></span> <span data-ttu-id="af883-123">기본값은 `http://localhost:1378/Calculator.svc`입니다.</span><span class="sxs-lookup"><span data-stu-id="af883-123">The default is `http://localhost:1378/Calculator.svc`.</span></span>

6. <span data-ttu-id="af883-124">이벤트 뷰어 애플리케이션을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="af883-124">Open the Event Viewer application.</span></span>

     <span data-ttu-id="af883-125">서비스를 호출하기 전에 이벤트 뷰어를 시작하고 이벤트 로그가 WCF 서비스에서 내보낸 이벤트를 추적하는 지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="af883-125">Before invoking the service, start Event Viewer and ensure that the event log is listening for tracking events emitted from the WCF service.</span></span>

7. <span data-ttu-id="af883-126">**시작** 메뉴에서 **관리 도구를**선택한 다음 이벤트 **뷰어**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="af883-126">From the **Start** menu, select **Administrative Tools**, and then **Event Viewer**.</span></span>  <span data-ttu-id="af883-127">**분석** 및 **디버그** 로그를 활성화합니다.</span><span class="sxs-lookup"><span data-stu-id="af883-127">Enable the **Analytic** and **Debug** logs.</span></span>

8. <span data-ttu-id="af883-128">이벤트 뷰어의 트리 보기에서 **이벤트 뷰어,** **응용 프로그램 및 서비스 로그,** **Microsoft,** **Windows**및 응용 프로그램 서버 응용 **프로그램으로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="af883-128">In the tree view in Event Viewer, navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application Server-Applications**.</span></span> <span data-ttu-id="af883-129">**응용 프로그램 서버-응용 프로그램을**마우스 오른쪽 단추로 클릭하고 **보기를**선택한 다음 분석 및 디버그 로그 표시 를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="af883-129">Right-click **Application Server-Applications**, select **View**, and then **Show Analytic and Debug Logs**.</span></span>

     <span data-ttu-id="af883-130">**분석 및 디버그 로그 표시** 옵션이 선택되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="af883-130">Ensure that the **Show Analytic and Debug Logs** option is checked.</span></span>

9. <span data-ttu-id="af883-131">분석 로그를 **활성화합니다.**</span><span class="sxs-lookup"><span data-stu-id="af883-131">Enable the **Analytic** log.</span></span>

     <span data-ttu-id="af883-132">이벤트 뷰어의 트리 보기에서 **이벤트 뷰어,** **응용 프로그램 및 서비스 로그,** **Microsoft,** **Windows**및 응용 프로그램 서버 응용 **프로그램으로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="af883-132">In the tree view in Event Viewer, navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application Server-Applications**.</span></span> <span data-ttu-id="af883-133">**분석** 클릭하고 **로그 사용 을**선택합니다.</span><span class="sxs-lookup"><span data-stu-id="af883-133">Right-click **Analytic** and select **Enable Log**.</span></span>

#### <a name="to-test-the-service"></a><span data-ttu-id="af883-134">서비스를 테스트하려면</span><span class="sxs-lookup"><span data-stu-id="af883-134">To test the service</span></span>

1. <span data-ttu-id="af883-135">WCF 테스트 클라이언트로 다시 전환하고 두 번 클릭하고 `Divide` 분모를 0으로 지정하는 기본값을 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="af883-135">Switch back to WCF test client and double-click `Divide` and keep the default values, which specify a denominator of 0.</span></span>

     <span data-ttu-id="af883-136">분모가 0이면 서비스에서는 오류를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="af883-136">If the denominator is 0, then the service throws a fault.</span></span>

2. <span data-ttu-id="af883-137">서비스에서 내보낸 이벤트를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="af883-137">Observe the events emitted from the service.</span></span>

     <span data-ttu-id="af883-138">이벤트 뷰어로 다시 전환 하고 **이벤트 뷰어로**이동 , **응용 프로그램 및 서비스 로그**, **마이크로 소프트**, **윈도우**, 다음 응용 프로그램 서버 **응용 프로그램**.</span><span class="sxs-lookup"><span data-stu-id="af883-138">Switch back to Event Viewer and navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application Server-Applications**.</span></span> <span data-ttu-id="af883-139">**분석** 단추를 클릭하고 **새로 고침을**선택합니다.</span><span class="sxs-lookup"><span data-stu-id="af883-139">Right-click **Analytic** and select **Refresh**.</span></span>

     <span data-ttu-id="af883-140">WCF 분석 추적 이벤트가 이벤트 뷰어에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="af883-140">The WCF analytic trace events are displayed in the event viewer.</span></span> <span data-ttu-id="af883-141">서비스에서 오류가 throw되었으므로 이벤트 뷰어에 오류 추적 이벤트가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="af883-141">Notice that because a fault was thrown by the service an error trace event is displayed in the event viewer.</span></span>

3. <span data-ttu-id="af883-142">1-2단계를 반복하되 이번에는 유효한 입력을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="af883-142">Repeat steps 1 and 2, but with valid inputs.</span></span> <span data-ttu-id="af883-143">`N2` 매개 변수 값으로는 0 이외의 모든 숫자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af883-143">The value of the `N2` parameter can be any number other than 0.</span></span>

     <span data-ttu-id="af883-144">분석 채널을 새로 고쳐 WCF 이벤트에 오류 이벤트가 포함되어 있지 않은지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="af883-144">Refresh the analytic channel to view the WCF events do not include any error events.</span></span>

 <span data-ttu-id="af883-145">이 샘플에서는 WCF 서비스에서 내보낸 분석 추적 이벤트를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="af883-145">The sample demonstrates the analytic trace events emitted from a WCF service.</span></span>

#### <a name="to-cleanup-optional"></a><span data-ttu-id="af883-146">정리하려면(옵션)</span><span class="sxs-lookup"><span data-stu-id="af883-146">To cleanup (Optional)</span></span>

1. <span data-ttu-id="af883-147">이벤트 뷰어를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="af883-147">Open Event Viewer.</span></span>

2. <span data-ttu-id="af883-148">이벤트 **뷰어,** **응용 프로그램 및 서비스 로그,** **Microsoft**, **Windows**및 **응용 프로그램-서버-응용 프로그램으로**이동합니다.</span><span class="sxs-lookup"><span data-stu-id="af883-148">Navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application-Server-Applications**.</span></span> <span data-ttu-id="af883-149">분석 클릭을 마우스 **오른쪽 단추로** 클릭하고 **로그 사용 안 함**선택.</span><span class="sxs-lookup"><span data-stu-id="af883-149">Right-click **Analytic** and select **Disable Log**.</span></span>

3. <span data-ttu-id="af883-150">이벤트 **뷰어,** **응용 프로그램 및 서비스 로그,** **Microsoft**, **Windows**및 **응용 프로그램-서버-응용 프로그램으로**이동합니다.</span><span class="sxs-lookup"><span data-stu-id="af883-150">Navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application-Server-Applications**.</span></span> <span data-ttu-id="af883-151">분석 클릭을 마우스 **오른쪽 단추로** 클릭하고 **로그 지우기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="af883-151">Right-click **Analytic** and select **Clear Log**.</span></span>

4. <span data-ttu-id="af883-152">이벤트를 지우려면 **지우기** 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="af883-152">Choose the **Clear** option to clear the events.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="af883-153">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af883-153">The samples may already be installed on your computer.</span></span> <span data-ttu-id="af883-154">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="af883-154">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="af883-155">이 디렉터리가 없는 경우 [.NET Framework 4에 대한 WCF(Windows 통신 재단) 및 WF(Windows 워크플로우 재단) 샘플로](https://www.microsoft.com/download/details.aspx?id=21459) 이동하여 모든 WCF(Windows 통신 재단) 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="af883-155">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="af883-156">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af883-156">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\ETWTracing`  
  
## <a name="see-also"></a><span data-ttu-id="af883-157">참고 항목</span><span class="sxs-lookup"><span data-stu-id="af883-157">See also</span></span>

- <span data-ttu-id="af883-158">[AppFabric 모니터링 샘플](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="af883-158">[AppFabric Monitoring Samples](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))</span></span>
