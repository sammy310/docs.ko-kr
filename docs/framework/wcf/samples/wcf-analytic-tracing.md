---
title: WCF 분석 추적
ms.date: 03/30/2017
ms.assetid: 6029c7c7-3515-4d36-9d43-13e8f4971790
ms.openlocfilehash: 13c66fbe1b59158cb9d2ba3829bb12f1180ad576
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90552981"
---
# <a name="wcf-analytic-tracing"></a><span data-ttu-id="a542d-102">WCF 분석 추적</span><span class="sxs-lookup"><span data-stu-id="a542d-102">WCF Analytic Tracing</span></span>
<span data-ttu-id="a542d-103">이 샘플에서는에서 ETW에 쓰기를 Windows Communication Foundation 하는 분석 추적 스트림에 사용자 고유의 추적 이벤트를 추가 하는 방법을 보여 줍니다 [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a542d-103">This sample demonstrates how to add your own tracing events into the stream of analytic traces that Windows Communication Foundation (WCF) writes to ETW in [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)].</span></span> <span data-ttu-id="a542d-104">분석 추적은 성능을 크게 저하시키지 않으면서 서비스를 쉽게 확인할 수 있도록 하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a542d-104">Analytic traces are meant to make it easy to get visibility into your services without paying a high performance penalty.</span></span> <span data-ttu-id="a542d-105">이 샘플에서는 api를 사용 하 여 <xref:System.Diagnostics.Eventing?displayProperty=nameWithType> WCF 서비스와 통합 되는 이벤트를 작성 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a542d-105">This sample shows how to use the <xref:System.Diagnostics.Eventing?displayProperty=nameWithType> APIs to write events that integrate with WCF services.</span></span>  
  
 <span data-ttu-id="a542d-106">Api에 대 한 자세한 내용은 <xref:System.Diagnostics.Eventing?displayProperty=nameWithType> 을 참조 하십시오 <xref:System.Diagnostics.Eventing?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="a542d-106">For more information about the <xref:System.Diagnostics.Eventing?displayProperty=nameWithType> APIs, see <xref:System.Diagnostics.Eventing?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="a542d-107">Windows에서 이벤트 추적에 대 한 자세한 내용은 [ETW를 사용한 디버깅 및 성능 조정 개선](/archive/msdn-magazine/2007/april/event-tracing-improve-debugging-and-performance-tuning-with-etw)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a542d-107">To learn more about event tracing in Windows, see [Improve Debugging and Performance Tuning with ETW](/archive/msdn-magazine/2007/april/event-tracing-improve-debugging-and-performance-tuning-with-etw).</span></span>  
  
## <a name="disposing-eventprovider"></a><span data-ttu-id="a542d-108">EventProvider 삭제</span><span class="sxs-lookup"><span data-stu-id="a542d-108">Disposing EventProvider</span></span>  
 <span data-ttu-id="a542d-109">이 샘플에서는 <xref:System.Diagnostics.Eventing.EventProvider?displayProperty=nameWithType>을 구현하는 <xref:System.IDisposable?displayProperty=nameWithType> 클래스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a542d-109">This sample uses the <xref:System.Diagnostics.Eventing.EventProvider?displayProperty=nameWithType> class, which implements <xref:System.IDisposable?displayProperty=nameWithType>.</span></span> <span data-ttu-id="a542d-110">WCF 서비스에 대 한 추적을 구현 하는 경우 <xref:System.Diagnostics.Eventing.EventProvider> 서비스 수명 동안의 리소스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a542d-110">When implementing tracing for a WCF service, it is likely that you may use the <xref:System.Diagnostics.Eventing.EventProvider>’s resources for the lifetime of the service.</span></span> <span data-ttu-id="a542d-111">이러한 이유로, 또한 읽기 쉽게 하려는 목적으로 이 샘플에서는 래핑된 <xref:System.Diagnostics.Eventing.EventProvider>를 삭제하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a542d-111">For this reason, and for readability, this sample never disposes of the wrapped <xref:System.Diagnostics.Eventing.EventProvider>.</span></span> <span data-ttu-id="a542d-112">어떤 이유로 서비스에 다른 추적 요구 사항이 있으며 이 리소스를 삭제해야 하는 경우 관리되지 않는 리소스를 삭제하기 위한 최선의 방법에 따라 이 샘플을 수정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a542d-112">If for some reason your service has different requirements for tracing and you must dispose of this resource, then you should modify this sample in accordance with the best practices for disposing of unmanaged resources.</span></span> <span data-ttu-id="a542d-113">관리 되지 않는 리소스를 삭제 하는 방법에 대 한 자세한 내용은 [Dispose 메서드 구현](../../../standard/garbage-collection/implementing-dispose.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a542d-113">For more information about disposing unmanaged resources, see [Implementing a Dispose Method](../../../standard/garbage-collection/implementing-dispose.md).</span></span>  
  
## <a name="self-hosting-vs-web-hosting"></a><span data-ttu-id="a542d-114">자체 호스팅과 웹 호스팅 비교</span><span class="sxs-lookup"><span data-stu-id="a542d-114">Self-Hosting vs. Web Hosting</span></span>  
 <span data-ttu-id="a542d-115">웹 호스팅 서비스의 경우 WCF의 분석 추적은 추적을 내보내는 서비스를 식별 하는 데 사용 되는 "HostReference" 라는 필드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a542d-115">For Web-hosted services, WCF’s analytic traces provide a field, called "HostReference", which is used to identify the service that is emitting the traces.</span></span> <span data-ttu-id="a542d-116">확장 가능한 사용자 추적이 이 모델에 관여할 수 있으며 이 샘플에서는 이 작업을 수행하기 위한 최선의 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a542d-116">The extensible user traces can participate in this model and this sample demonstrates best practices for doing so.</span></span> <span data-ttu-id="a542d-117">파이프 ' &#124; ' 문자가 실제로 결과 문자열에 표시 되는 경우 웹 호스트 참조의 형식은 다음 중 하나일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a542d-117">The format of a Web host reference when the pipe ‘&#124;’ character actually appears in the resulting string can be any one of the following:</span></span>  
  
- <span data-ttu-id="a542d-118">애플리케이션이 루트에 없는 경우</span><span class="sxs-lookup"><span data-stu-id="a542d-118">If the application is not at the root.</span></span>  
  
     <span data-ttu-id="a542d-119">\<SiteName>\<ApplicationVirtualPath>&#124;\<ServiceVirtualPath>&#124;\<ServiceName></span><span class="sxs-lookup"><span data-stu-id="a542d-119">\<SiteName>\<ApplicationVirtualPath>&#124;\<ServiceVirtualPath>&#124;\<ServiceName></span></span>  
  
- <span data-ttu-id="a542d-120">애플리케이션이 루트에 있는 경우</span><span class="sxs-lookup"><span data-stu-id="a542d-120">If the application is at the root.</span></span>  
  
     <span data-ttu-id="a542d-121">\<SiteName>&#124;\<ServiceVirtualPath>&#124;\<ServiceName></span><span class="sxs-lookup"><span data-stu-id="a542d-121">\<SiteName>&#124;\<ServiceVirtualPath>&#124;\<ServiceName></span></span>  
  
 <span data-ttu-id="a542d-122">자체 호스팅 서비스의 경우 WCF의 분석 추적은 "HostReference" 필드를 채우지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a542d-122">For self-hosted services, WCF’s analytic traces do not populate the "HostReference" field.</span></span> <span data-ttu-id="a542d-123">이 샘플의 `WCFUserEventProvider` 클래스는 자체 호스팅 서비스에서 사용될 때 일관성 있게 동작합니다.</span><span class="sxs-lookup"><span data-stu-id="a542d-123">The `WCFUserEventProvider` class in this sample behaves consistently when used by a self-hosted service.</span></span>  
  
## <a name="custom-event-details"></a><span data-ttu-id="a542d-124">사용자 지정 이벤트 상세 정보</span><span class="sxs-lookup"><span data-stu-id="a542d-124">Custom Event Details</span></span>  
 <span data-ttu-id="a542d-125">WCF의 ETW 이벤트 공급자 매니페스트는 WCF 서비스 작성자가 서비스 코드 내에서 내보내도록 디자인 된 세 개의 이벤트를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="a542d-125">WCF’s ETW Event Provider manifest defines three events that are designed to be emitted by WCF service authors from within service code.</span></span> <span data-ttu-id="a542d-126">다음 표에서는 세 개의 이벤트를 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a542d-126">The following table shows a breakdown of the three events.</span></span>  
  
|<span data-ttu-id="a542d-127">이벤트</span><span class="sxs-lookup"><span data-stu-id="a542d-127">Event</span></span>|<span data-ttu-id="a542d-128">Description</span><span class="sxs-lookup"><span data-stu-id="a542d-128">Description</span></span>|<span data-ttu-id="a542d-129">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="a542d-129">Event ID</span></span>|  
|-----------|-----------------|--------------|  
|<span data-ttu-id="a542d-130">UserDefinedInformationEventOccurred</span><span class="sxs-lookup"><span data-stu-id="a542d-130">UserDefinedInformationEventOccurred</span></span>|<span data-ttu-id="a542d-131">문제는 아니지만 중요한 사항이 서비스에 발생하면 이 이벤트를 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="a542d-131">Emit this event when something of note happens in your service that is not a problem.</span></span> <span data-ttu-id="a542d-132">예를 들어 데이터베이스를 성공적으로 호출한 후 이벤트를 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a542d-132">For example, you might emit an event after successfully making a call to a database.</span></span>|<span data-ttu-id="a542d-133">301</span><span class="sxs-lookup"><span data-stu-id="a542d-133">301</span></span>|  
|<span data-ttu-id="a542d-134">UserDefinedWarningOccurred</span><span class="sxs-lookup"><span data-stu-id="a542d-134">UserDefinedWarningOccurred</span></span>|<span data-ttu-id="a542d-135">이후에 오류를 초래할 수 있는 문제가 발생하면 이 이벤트를 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="a542d-135">Emit this event when a problem occurs that may result in a failure in the future.</span></span> <span data-ttu-id="a542d-136">예를 들어 데이터베이스에 대한 호출에 실패했지만 중복 데이터 저장소를 대신 사용하여 복구할 수 있는 경우 경고 이벤트를 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a542d-136">For example, you may emit a warning event when a call to a database fails but you were able to recover by falling back to a redundant data store.</span></span>|<span data-ttu-id="a542d-137">302</span><span class="sxs-lookup"><span data-stu-id="a542d-137">302</span></span>|  
|<span data-ttu-id="a542d-138">UserDefinedErrorOccurred</span><span class="sxs-lookup"><span data-stu-id="a542d-138">UserDefinedErrorOccurred</span></span>|<span data-ttu-id="a542d-139">서비스가 예상한 대로 동작하지 않으면 이 이벤트를 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="a542d-139">Emit this event when your service fails to behave as expected.</span></span> <span data-ttu-id="a542d-140">예를 들어 데이터베이스에 대한 호출에 실패하고 다른 위치에서 데이터를 검색할 수 없는 경우 이벤트를 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a542d-140">For example, you might emit an event if a call to a database fails and you could not retrieve the data from elsewhere.</span></span>|<span data-ttu-id="a542d-141">303</span><span class="sxs-lookup"><span data-stu-id="a542d-141">303</span></span>|  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="a542d-142">이 샘플을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="a542d-142">To use this sample</span></span>  
  
1. <span data-ttu-id="a542d-143">Visual Studio 2012을 사용 하 여 WCFAnalyticTracingExtensibility 솔루션 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a542d-143">Using Visual Studio 2012, open the WCFAnalyticTracingExtensibility.sln solution file.</span></span>  
  
2. <span data-ttu-id="a542d-144">Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="a542d-144">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3. <span data-ttu-id="a542d-145">Ctrl+F5를 눌러 솔루션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a542d-145">To run the solution, press CTRL+F5.</span></span>  
  
     <span data-ttu-id="a542d-146">웹 브라우저에서 **계산기 .svc**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a542d-146">In the Web browser, click **Calculator.svc**.</span></span> <span data-ttu-id="a542d-147">서비스의 WSDL 문서에 대한 URI가 브라우저에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="a542d-147">The URI of the WSDL document for the service should appear in the browser.</span></span> <span data-ttu-id="a542d-148">이 URI를 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="a542d-148">Copy that URI.</span></span>  
  
4. <span data-ttu-id="a542d-149">WCF 테스트 클라이언트 (WcfTestClient.exe)를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a542d-149">Run the WCF test client (WcfTestClient.exe).</span></span>  
  
     <span data-ttu-id="a542d-150">WCF 테스트 클라이언트 (WcfTestClient.exe)는에 `\<Visual Studio 2012 Install Dir>\Common7\IDE\WcfTestClient.exe` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a542d-150">The WCF test client (WcfTestClient.exe) is located at `\<Visual Studio 2012 Install Dir>\Common7\IDE\WcfTestClient.exe`.</span></span> <span data-ttu-id="a542d-151">기본 Visual Studio 2012 설치 디렉터리는 `C:\Program Files\Microsoft Visual Studio 10.0` 입니다.</span><span class="sxs-lookup"><span data-stu-id="a542d-151">The default Visual Studio 2012 install dir is `C:\Program Files\Microsoft Visual Studio 10.0`.</span></span>  
  
5. <span data-ttu-id="a542d-152">WCF 테스트 클라이언트 내에서 **파일**을 선택 하 고 **서비스 추가**를 선택 하 여 서비스를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="a542d-152">Within the WCF test client, add the service by selecting **File**, and then **Add Service**.</span></span>  
  
     <span data-ttu-id="a542d-153">입력 상자에 엔드포인트 주소를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a542d-153">Add the endpoint address in the input box.</span></span>  
  
6. <span data-ttu-id="a542d-154">**확인**을 클릭하여 대화 상자를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="a542d-154">Click **OK** to close the dialog.</span></span>  
  
     <span data-ttu-id="a542d-155">ICalculator 서비스가 **내 서비스 프로젝트**아래의 왼쪽 창에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a542d-155">The ICalculator service is added in the left pane under **My Service Projects**.</span></span>  
  
7. <span data-ttu-id="a542d-156">이벤트 뷰어 애플리케이션을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a542d-156">Open the Event Viewer application.</span></span>  
  
     <span data-ttu-id="a542d-157">서비스를 호출 하기 전에 이벤트 뷰어를 시작 하 고 이벤트 로그가 WCF 서비스에서 내보낸 추적 이벤트를 수신 대기 하 고 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a542d-157">Before invoking the service, start Event Viewer and ensure that the event log is listening for tracking events emitted from the WCF service.</span></span>  
  
8. <span data-ttu-id="a542d-158">**시작** 메뉴에서 **관리 도구**를 선택한 다음 **이벤트 뷰어**합니다.</span><span class="sxs-lookup"><span data-stu-id="a542d-158">From the **Start** menu, select **Administrative Tools**, and then **Event Viewer**.</span></span> <span data-ttu-id="a542d-159">**분석** 및 **디버그** 로그를 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a542d-159">Enable the **Analytic** and **Debug** logs.</span></span>  
  
9. <span data-ttu-id="a542d-160">이벤트 뷰어의 트리 뷰에서 **이벤트 뷰어**, **응용 프로그램 및 서비스 로그**, **Microsoft**, **Windows**, **응용 프로그램 서버-응용**프로그램으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="a542d-160">In the tree view in Event Viewer, navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application Server-Applications**.</span></span> <span data-ttu-id="a542d-161">**응용 프로그램 서버-응용 프로그램**을 마우스 오른쪽 단추로 클릭 하 고 **보기**를 선택한 다음 **분석 및 디버그 로그 표시**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a542d-161">Right-click **Application Server-Applications**, select **View**, and then **Show Analytic and Debug Logs**.</span></span>  
  
     <span data-ttu-id="a542d-162">**분석 및 디버그 로그 표시** 옵션이 선택 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a542d-162">Ensure that the **Show Analytic and Debug Logs** option is checked.</span></span> <span data-ttu-id="a542d-163">**분석** 로그를 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a542d-163">Enable the **Analytic** log.</span></span>  
  
     <span data-ttu-id="a542d-164">이벤트 뷰어의 트리 뷰에서 **이벤트 뷰어**, **응용 프로그램 및 서비스 로그**, **Microsoft**, **Windows**, **응용 프로그램 서버-응용**프로그램, **분석**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="a542d-164">In the tree view in Event Viewer, navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, **Application Server-Applications**, and then **Analytic**.</span></span> <span data-ttu-id="a542d-165">**분석** 을 마우스 오른쪽 단추로 클릭 하 고 **로그 사용**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a542d-165">Right-click **Analytic** and select **Enable Log**.</span></span>  
  
10. <span data-ttu-id="a542d-166">WCF 테스트 클라이언트를 사용하여 서비스를 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="a542d-166">Test the service using the WCF Test Client.</span></span>  
  
    1. <span data-ttu-id="a542d-167">WCF 테스트 클라이언트에서 ICalculator service 노드의 **Add ()** 를 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a542d-167">In the WCF Test Client, double-click **Add()** under the ICalculator service node.</span></span>  
  
         <span data-ttu-id="a542d-168">**Add ()** 메서드는 두 개의 매개 변수를 사용 하 여 오른쪽 창에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a542d-168">The **Add()** method appears in the right pane with two parameters.</span></span>  
  
    2. <span data-ttu-id="a542d-169">첫 번째 매개 변수에 2를 입력하고 두 번째 매개 변수에 3을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="a542d-169">Type in 2 for the first parameter and 3 for the second parameter.</span></span>  
  
    3. <span data-ttu-id="a542d-170">**호출** 을 클릭 하 여 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="a542d-170">Click **Invoke** to invoke the method.</span></span>  
  
11. <span data-ttu-id="a542d-171">이미 열려 있는 **이벤트 뷰어** 창으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="a542d-171">Go to the **Event Viewer** window that you have already opened.</span></span> <span data-ttu-id="a542d-172">**이벤트 뷰어**, **응용 프로그램 및 서비스 로그**, **Microsoft**, **Windows**, **응용 프로그램 서버-응용**프로그램으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="a542d-172">Navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, **Application Server-Applications**.</span></span>  
  
12. <span data-ttu-id="a542d-173">**분석** 노드를 마우스 오른쪽 단추로 클릭 하 고 **새로 고침**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a542d-173">Right-click the **Analytic** node and select **Refresh**.</span></span>  
  
     <span data-ttu-id="a542d-174">오른쪽 창에 이벤트가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="a542d-174">The events appear in the right pane.</span></span>  
  
13. <span data-ttu-id="a542d-175">ID가 303인 이벤트를 찾아서 두 번 클릭하여 열고 해당 내용을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="a542d-175">Locate the event with the ID of 303 and double-click it to open it up and inspect its contents.</span></span>  
  
     <span data-ttu-id="a542d-176">이 이벤트는 `Add()` ICalculator 서비스의 메서드에서 내보내고 "2 + 3 = 5"와 같은 페이로드를 가집니다.</span><span class="sxs-lookup"><span data-stu-id="a542d-176">This event was emitted by the `Add()` method of the ICalculator service and has a payload equal to "2+3=5".</span></span>  
  
#### <a name="to-clean-up-optional"></a><span data-ttu-id="a542d-177">정리하려면(옵션)</span><span class="sxs-lookup"><span data-stu-id="a542d-177">To clean up (Optional)</span></span>  
  
1. <span data-ttu-id="a542d-178">**이벤트 뷰어**를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a542d-178">Open **Event Viewer**.</span></span>  
  
2. <span data-ttu-id="a542d-179">**이벤트 뷰어**, **응용 프로그램 및 서비스 로그**, **Microsoft**, **Windows**, **응용 프로그램-서버-** 응용 프로그램으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="a542d-179">Navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application-Server-Applications**.</span></span> <span data-ttu-id="a542d-180">**분석** 을 마우스 오른쪽 단추로 클릭 하 고 **로그 사용 안 함**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a542d-180">Right-click **Analytic** and select **Disable Log**.</span></span>  
  
3. <span data-ttu-id="a542d-181">**이벤트 뷰어**, **응용 프로그램 및 서비스 로그**, **Microsoft**, **Windows**, 응용 프로그램- **서버-응용 프로그램**, **분석**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="a542d-181">Navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, **Application-Server-Applications**, and then **Analytic**.</span></span> <span data-ttu-id="a542d-182">**분석** 을 마우스 오른쪽 단추로 클릭 하 고 **로그 지우기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a542d-182">Right-click **Analytic** and select **Clear Log**.</span></span>  
  
4. <span data-ttu-id="a542d-183">**지우기** 를 클릭 하 여 이벤트를 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="a542d-183">Click **Clear** to clear the events.</span></span>  
  
## <a name="known-issue"></a><span data-ttu-id="a542d-184">알려진 이슈</span><span class="sxs-lookup"><span data-stu-id="a542d-184">Known Issue</span></span>  
 <span data-ttu-id="a542d-185">**이벤트 뷰어** 에는 ETW 이벤트를 디코딩하는 데 실패할 수 있는 알려진 문제가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a542d-185">There is a known issue in the **Event Viewer** where it may fail to decode ETW events.</span></span> <span data-ttu-id="a542d-186">" \<id> 소스 Microsoft-Windows-응용 프로그램 서버의 이벤트 ID에 대 한 설명-응용 프로그램을 찾을 수 없습니다." 라는 오류 메시지가 표시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a542d-186">You may see an error message that says: "The description for Event ID \<id> from source Microsoft-Windows-Application Server-Applications cannot be found.</span></span> <span data-ttu-id="a542d-187">이 이벤트가 발생되는 구성 요소가 로컬 컴퓨터에 설치되지 않았거나 설치가 손상되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a542d-187">Either the component that raises this event is not installed on your local computer or the installation is corrupted.</span></span> <span data-ttu-id="a542d-188">로컬 컴퓨터에 구성 요소를 설치 하거나 복구할 수 있습니다. "</span><span class="sxs-lookup"><span data-stu-id="a542d-188">You can install or repair the component on the local computer."</span></span> <span data-ttu-id="a542d-189">이 오류가 발생 하는 경우 **작업** 메뉴에서 **새로 고침** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a542d-189">If you encounter this error, select **Refresh** from the **Actions** menu.</span></span> <span data-ttu-id="a542d-190">그러면 이벤트가 올바르게 디코딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="a542d-190">The event should then decode properly.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="a542d-191">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a542d-191">The samples may already be installed on your computer.</span></span> <span data-ttu-id="a542d-192">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="a542d-192">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="a542d-193">이 디렉터리가 없는 경우 [.NET Framework 4에 대 한 Windows Communication Foundation (wcf) 및 Windows Workflow Foundation (WF) 샘플](https://www.microsoft.com/download/details.aspx?id=21459) 로 이동 하 여 모든 WINDOWS COMMUNICATION FOUNDATION (wcf) 및 샘플을 다운로드 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 합니다.</span><span class="sxs-lookup"><span data-stu-id="a542d-193">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="a542d-194">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a542d-194">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\ETWTrace`  
  
## <a name="see-also"></a><span data-ttu-id="a542d-195">참조</span><span class="sxs-lookup"><span data-stu-id="a542d-195">See also</span></span>

- <span data-ttu-id="a542d-196">[AppFabric 모니터링 샘플](/previous-versions/appfabric/ff383407(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="a542d-196">[AppFabric Monitoring Samples](/previous-versions/appfabric/ff383407(v=azure.10))</span></span>
