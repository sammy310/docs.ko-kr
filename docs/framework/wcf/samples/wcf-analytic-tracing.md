---
title: WCF 분석 추적
ms.date: 03/30/2017
ms.assetid: 6029c7c7-3515-4d36-9d43-13e8f4971790
ms.openlocfilehash: ef636a672d9384e8e3d658f0488cfaadb8d293e4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183224"
---
# <a name="wcf-analytic-tracing"></a><span data-ttu-id="f5dee-102">WCF 분석 추적</span><span class="sxs-lookup"><span data-stu-id="f5dee-102">WCF Analytic Tracing</span></span>
<span data-ttu-id="f5dee-103">이 샘플에서는 WCF(Windows 통신 재단)가 에서 ETW에 기록하는 분석 추적 스트림에 [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)]고유한 추적 이벤트를 추가하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f5dee-103">This sample demonstrates how to add your own tracing events into the stream of analytic traces that Windows Communication Foundation (WCF) writes to ETW in [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)].</span></span> <span data-ttu-id="f5dee-104">분석 추적은 성능을 크게 저하시키지 않으면서 서비스를 쉽게 확인할 수 있도록 하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f5dee-104">Analytic traces are meant to make it easy to get visibility into your services without paying a high performance penalty.</span></span> <span data-ttu-id="f5dee-105">이 샘플에서는 API를 <xref:System.Diagnostics.Eventing?displayProperty=nameWithType> 사용하여 WCF 서비스와 통합되는 이벤트를 작성하는 방법을 보여 주며, 이 샘플에서는 API를 사용하는 방법을 보여 주며, 이 샘플에서는 API를 사용하는 방법을 보여 주며, 이 샘플에서는 API를 사용하는 방법을 보여 주며, 이 샘플에서는 API를 사용하여 WCF</span><span class="sxs-lookup"><span data-stu-id="f5dee-105">This sample shows how to use the <xref:System.Diagnostics.Eventing?displayProperty=nameWithType> APIs to write events that integrate with WCF services.</span></span>  
  
 <span data-ttu-id="f5dee-106">API에 <xref:System.Diagnostics.Eventing?displayProperty=nameWithType> 대한 자세한 내용은 <xref:System.Diagnostics.Eventing?displayProperty=nameWithType>를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="f5dee-106">For more information about the <xref:System.Diagnostics.Eventing?displayProperty=nameWithType> APIs, see <xref:System.Diagnostics.Eventing?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="f5dee-107">Windows에서 이벤트 추적에 대한 자세한 내용은 [ETW를 사용하여 디버깅 및 성능 조정 개선을](https://docs.microsoft.com/archive/msdn-magazine/2007/april/event-tracing-improve-debugging-and-performance-tuning-with-etw)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="f5dee-107">To learn more about event tracing in Windows, see [Improve Debugging and Performance Tuning with ETW](https://docs.microsoft.com/archive/msdn-magazine/2007/april/event-tracing-improve-debugging-and-performance-tuning-with-etw).</span></span>  
  
## <a name="disposing-eventprovider"></a><span data-ttu-id="f5dee-108">EventProvider 삭제</span><span class="sxs-lookup"><span data-stu-id="f5dee-108">Disposing EventProvider</span></span>  
 <span data-ttu-id="f5dee-109">이 샘플에서는 <xref:System.Diagnostics.Eventing.EventProvider?displayProperty=nameWithType>을 구현하는 <xref:System.IDisposable?displayProperty=nameWithType> 클래스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f5dee-109">This sample uses the <xref:System.Diagnostics.Eventing.EventProvider?displayProperty=nameWithType> class, which implements <xref:System.IDisposable?displayProperty=nameWithType>.</span></span> <span data-ttu-id="f5dee-110">WCF 서비스에 대한 추적을 구현할 때 서비스 수명 동안 <xref:System.Diagnostics.Eventing.EventProvider>'리소스'를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5dee-110">When implementing tracing for a WCF service, it is likely that you may use the <xref:System.Diagnostics.Eventing.EventProvider>’s resources for the lifetime of the service.</span></span> <span data-ttu-id="f5dee-111">이러한 이유로, 또한 읽기 쉽게 하려는 목적으로 이 샘플에서는 래핑된 <xref:System.Diagnostics.Eventing.EventProvider>를 삭제하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f5dee-111">For this reason, and for readability, this sample never disposes of the wrapped <xref:System.Diagnostics.Eventing.EventProvider>.</span></span> <span data-ttu-id="f5dee-112">어떤 이유로 서비스에 다른 추적 요구 사항이 있으며 이 리소스를 삭제해야 하는 경우 관리되지 않는 리소스를 삭제하기 위한 최선의 방법에 따라 이 샘플을 수정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f5dee-112">If for some reason your service has different requirements for tracing and you must dispose of this resource, then you should modify this sample in accordance with the best practices for disposing of unmanaged resources.</span></span> <span data-ttu-id="f5dee-113">관리되지 않는 리소스를 삭제하는 방법에 대한 자세한 내용은 [Dispose 메서드 구현을](https://docs.microsoft.com/dotnet/standard/garbage-collection/implementing-dispose)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="f5dee-113">For more information about disposing unmanaged resources, see [Implementing a Dispose Method](https://docs.microsoft.com/dotnet/standard/garbage-collection/implementing-dispose).</span></span>  
  
## <a name="self-hosting-vs-web-hosting"></a><span data-ttu-id="f5dee-114">자체 호스팅과 웹 호스팅 비교</span><span class="sxs-lookup"><span data-stu-id="f5dee-114">Self-Hosting vs. Web Hosting</span></span>  
 <span data-ttu-id="f5dee-115">웹 호스팅 서비스의 경우 WCF의 분석 추적은 추적을 내보내는 서비스를 식별하는 데 사용되는 "HostReference"라는 필드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f5dee-115">For Web-hosted services, WCF’s analytic traces provide a field, called "HostReference", which is used to identify the service that is emitting the traces.</span></span> <span data-ttu-id="f5dee-116">확장 가능한 사용자 추적이 이 모델에 관여할 수 있으며 이 샘플에서는 이 작업을 수행하기 위한 최선의 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f5dee-116">The extensible user traces can participate in this model and this sample demonstrates best practices for doing so.</span></span> <span data-ttu-id="f5dee-117">파이프 '&#124;' 문자가 실제로 결과 문자열에 나타날 때 웹 호스트 참조의 형식은 다음 중 하나일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5dee-117">The format of a Web host reference when the pipe ‘&#124;’ character actually appears in the resulting string can be any one of the following:</span></span>  
  
- <span data-ttu-id="f5dee-118">애플리케이션이 루트에 없는 경우</span><span class="sxs-lookup"><span data-stu-id="f5dee-118">If the application is not at the root.</span></span>  
  
     <span data-ttu-id="f5dee-119">\<사이트 이름 \<>응용 \<프로그램VirtualPath \<>&#124;서비스VirtualPath>&#124;서비스 이름></span><span class="sxs-lookup"><span data-stu-id="f5dee-119">\<SiteName>\<ApplicationVirtualPath>&#124;\<ServiceVirtualPath>&#124;\<ServiceName></span></span>  
  
- <span data-ttu-id="f5dee-120">애플리케이션이 루트에 있는 경우</span><span class="sxs-lookup"><span data-stu-id="f5dee-120">If the application is at the root.</span></span>  
  
     <span data-ttu-id="f5dee-121">\<사이트 이름 \<>&#124;서비스VirtualPath>&#124;\<서비스 이름></span><span class="sxs-lookup"><span data-stu-id="f5dee-121">\<SiteName>&#124;\<ServiceVirtualPath>&#124;\<ServiceName></span></span>  
  
 <span data-ttu-id="f5dee-122">자체 호스팅 서비스의 경우 WCF의 분석 추적은 "HostReference" 필드를 채우지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f5dee-122">For self-hosted services, WCF’s analytic traces do not populate the "HostReference" field.</span></span> <span data-ttu-id="f5dee-123">이 샘플의 `WCFUserEventProvider` 클래스는 자체 호스팅 서비스에서 사용될 때 일관성 있게 동작합니다.</span><span class="sxs-lookup"><span data-stu-id="f5dee-123">The `WCFUserEventProvider` class in this sample behaves consistently when used by a self-hosted service.</span></span>  
  
## <a name="custom-event-details"></a><span data-ttu-id="f5dee-124">사용자 지정 이벤트 상세 정보</span><span class="sxs-lookup"><span data-stu-id="f5dee-124">Custom Event Details</span></span>  
 <span data-ttu-id="f5dee-125">WCF의 ETW 이벤트 공급자 매니페스트는 서비스 코드 내에서 WCF 서비스 작성자에서 내보내도록 설계된 세 가지 이벤트를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="f5dee-125">WCF’s ETW Event Provider manifest defines three events that are designed to be emitted by WCF service authors from within service code.</span></span> <span data-ttu-id="f5dee-126">다음 표에서는 세 개의 이벤트를 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f5dee-126">The following table shows a breakdown of the three events.</span></span>  
  
|<span data-ttu-id="f5dee-127">행사</span><span class="sxs-lookup"><span data-stu-id="f5dee-127">Event</span></span>|<span data-ttu-id="f5dee-128">Description</span><span class="sxs-lookup"><span data-stu-id="f5dee-128">Description</span></span>|<span data-ttu-id="f5dee-129">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="f5dee-129">Event ID</span></span>|  
|-----------|-----------------|--------------|  
|<span data-ttu-id="f5dee-130">UserDefinedInformationEventOccurred</span><span class="sxs-lookup"><span data-stu-id="f5dee-130">UserDefinedInformationEventOccurred</span></span>|<span data-ttu-id="f5dee-131">문제는 아니지만 중요한 사항이 서비스에 발생하면 이 이벤트를 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="f5dee-131">Emit this event when something of note happens in your service that is not a problem.</span></span> <span data-ttu-id="f5dee-132">예를 들어 데이터베이스를 성공적으로 호출한 후 이벤트를 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5dee-132">For example, you might emit an event after successfully making a call to a database.</span></span>|<span data-ttu-id="f5dee-133">301</span><span class="sxs-lookup"><span data-stu-id="f5dee-133">301</span></span>|  
|<span data-ttu-id="f5dee-134">UserDefinedWarningOccurred</span><span class="sxs-lookup"><span data-stu-id="f5dee-134">UserDefinedWarningOccurred</span></span>|<span data-ttu-id="f5dee-135">이후에 오류를 초래할 수 있는 문제가 발생하면 이 이벤트를 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="f5dee-135">Emit this event when a problem occurs that may result in a failure in the future.</span></span> <span data-ttu-id="f5dee-136">예를 들어 데이터베이스에 대한 호출에 실패했지만 중복 데이터 저장소를 대신 사용하여 복구할 수 있는 경우 경고 이벤트를 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5dee-136">For example, you may emit a warning event when a call to a database fails but you were able to recover by falling back to a redundant data store.</span></span>|<span data-ttu-id="f5dee-137">302</span><span class="sxs-lookup"><span data-stu-id="f5dee-137">302</span></span>|  
|<span data-ttu-id="f5dee-138">UserDefinedErrorOccurred</span><span class="sxs-lookup"><span data-stu-id="f5dee-138">UserDefinedErrorOccurred</span></span>|<span data-ttu-id="f5dee-139">서비스가 예상한 대로 동작하지 않으면 이 이벤트를 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="f5dee-139">Emit this event when your service fails to behave as expected.</span></span> <span data-ttu-id="f5dee-140">예를 들어 데이터베이스에 대한 호출에 실패하고 다른 위치에서 데이터를 검색할 수 없는 경우 이벤트를 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5dee-140">For example, you might emit an event if a call to a database fails and you could not retrieve the data from elsewhere.</span></span>|<span data-ttu-id="f5dee-141">303</span><span class="sxs-lookup"><span data-stu-id="f5dee-141">303</span></span>|  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="f5dee-142">이 샘플을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="f5dee-142">To use this sample</span></span>  
  
1. <span data-ttu-id="f5dee-143">Visual Studio 2012를 사용하여 WCFAnalyticTracingExtensibility.sln 솔루션 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="f5dee-143">Using Visual Studio 2012, open the WCFAnalyticTracingExtensibility.sln solution file.</span></span>  
  
2. <span data-ttu-id="f5dee-144">Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="f5dee-144">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3. <span data-ttu-id="f5dee-145">Ctrl+F5를 눌러 솔루션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f5dee-145">To run the solution, press CTRL+F5.</span></span>  
  
     <span data-ttu-id="f5dee-146">웹 브라우저에서 **계산기.svc를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="f5dee-146">In the Web browser, click **Calculator.svc**.</span></span> <span data-ttu-id="f5dee-147">서비스의 WSDL 문서에 대한 URI가 브라우저에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="f5dee-147">The URI of the WSDL document for the service should appear in the browser.</span></span> <span data-ttu-id="f5dee-148">이 URI를 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="f5dee-148">Copy that URI.</span></span>  
  
4. <span data-ttu-id="f5dee-149">WCF 테스트 클라이언트(WcfTestClient.exe)를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f5dee-149">Run the WCF test client (WcfTestClient.exe).</span></span>  
  
     <span data-ttu-id="f5dee-150">WCF 테스트 클라이언트(WcfTestClient.exe)는 `\<Visual Studio 2012 Install Dir>\Common7\IDE\WcfTestClient.exe`에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5dee-150">The WCF test client (WcfTestClient.exe) is located at `\<Visual Studio 2012 Install Dir>\Common7\IDE\WcfTestClient.exe`.</span></span> <span data-ttu-id="f5dee-151">기본 Visual Studio 2012 `C:\Program Files\Microsoft Visual Studio 10.0`설치 dir은 .</span><span class="sxs-lookup"><span data-stu-id="f5dee-151">The default Visual Studio 2012 install dir is `C:\Program Files\Microsoft Visual Studio 10.0`.</span></span>  
  
5. <span data-ttu-id="f5dee-152">WCF 테스트 클라이언트 내에서 **파일**을 선택한 다음 **서비스 추가를**선택하여 서비스를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f5dee-152">Within the WCF test client, add the service by selecting **File**, and then **Add Service**.</span></span>  
  
     <span data-ttu-id="f5dee-153">입력 상자에 엔드포인트 주소를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f5dee-153">Add the endpoint address in the input box.</span></span>  
  
6. <span data-ttu-id="f5dee-154">**확인**을 클릭하여 대화 상자를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="f5dee-154">Click **OK** to close the dialog.</span></span>  
  
     <span data-ttu-id="f5dee-155">ICalculator 서비스는 **내 서비스 프로젝트**의 왼쪽 창에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5dee-155">The ICalculator service is added in the left pane under **My Service Projects**.</span></span>  
  
7. <span data-ttu-id="f5dee-156">이벤트 뷰어 애플리케이션을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="f5dee-156">Open the Event Viewer application.</span></span>  
  
     <span data-ttu-id="f5dee-157">서비스를 호출하기 전에 이벤트 뷰어를 시작하고 이벤트 로그가 WCF 서비스에서 내보낸 이벤트를 추적하는 지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="f5dee-157">Before invoking the service, start Event Viewer and ensure that the event log is listening for tracking events emitted from the WCF service.</span></span>  
  
8. <span data-ttu-id="f5dee-158">**시작** 메뉴에서 **관리 도구를**선택한 다음 이벤트 **뷰어**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f5dee-158">From the **Start** menu, select **Administrative Tools**, and then **Event Viewer**.</span></span> <span data-ttu-id="f5dee-159">**분석** 및 **디버그** 로그를 활성화합니다.</span><span class="sxs-lookup"><span data-stu-id="f5dee-159">Enable the **Analytic** and **Debug** logs.</span></span>  
  
9. <span data-ttu-id="f5dee-160">이벤트 뷰어의 트리 보기에서 **이벤트 뷰어,** **응용 프로그램 및 서비스 로그,** **Microsoft,** **Windows**및 응용 프로그램 서버 응용 **프로그램으로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="f5dee-160">In the tree view in Event Viewer, navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application Server-Applications**.</span></span> <span data-ttu-id="f5dee-161">**응용 프로그램 서버-응용 프로그램을**마우스 오른쪽 단추로 클릭하고 **보기를**선택한 다음 분석 및 디버그 로그 표시 를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="f5dee-161">Right-click **Application Server-Applications**, select **View**, and then **Show Analytic and Debug Logs**.</span></span>  
  
     <span data-ttu-id="f5dee-162">**분석 및 디버그 로그 표시** 옵션이 선택되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="f5dee-162">Ensure that the **Show Analytic and Debug Logs** option is checked.</span></span> <span data-ttu-id="f5dee-163">분석 로그를 **활성화합니다.**</span><span class="sxs-lookup"><span data-stu-id="f5dee-163">Enable the **Analytic** log.</span></span>  
  
     <span data-ttu-id="f5dee-164">이벤트 뷰어의 트리 보기에서 **이벤트 뷰어,** **응용 프로그램 및 서비스 로그,** **Microsoft,** **Windows,** **응용 프로그램 서버 응용 프로그램**및 **분석으로**이동합니다.</span><span class="sxs-lookup"><span data-stu-id="f5dee-164">In the tree view in Event Viewer, navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, **Application Server-Applications**, and then **Analytic**.</span></span> <span data-ttu-id="f5dee-165">**분석** 클릭하고 **로그 사용 을**선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f5dee-165">Right-click **Analytic** and select **Enable Log**.</span></span>  
  
10. <span data-ttu-id="f5dee-166">WCF 테스트 클라이언트를 사용하여 서비스를 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="f5dee-166">Test the service using the WCF Test Client.</span></span>  
  
    1. <span data-ttu-id="f5dee-167">WCF 테스트 클라이언트에서 ICalculator 서비스 노드 에서 **Add()를** 두 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f5dee-167">In the WCF Test Client, double-click **Add()** under the ICalculator service node.</span></span>  
  
         <span data-ttu-id="f5dee-168">**Add()** 메서드는 두 개의 매개 변수가 있는 오른쪽 창에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="f5dee-168">The **Add()** method appears in the right pane with two parameters.</span></span>  
  
    2. <span data-ttu-id="f5dee-169">첫 번째 매개 변수에 2를 입력하고 두 번째 매개 변수에 3을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="f5dee-169">Type in 2 for the first parameter and 3 for the second parameter.</span></span>  
  
    3. <span data-ttu-id="f5dee-170">**호출을** 클릭하여 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="f5dee-170">Click **Invoke** to invoke the method.</span></span>  
  
11. <span data-ttu-id="f5dee-171">이미 열린 **이벤트 뷰어** 창으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="f5dee-171">Go to the **Event Viewer** window that you have already opened.</span></span> <span data-ttu-id="f5dee-172">이벤트 **뷰어,** **응용 프로그램 및 서비스 로그,** 마이크로 **소프트,** **윈도우,** **응용 프로그램 서버 응용 프로그램으로**이동 .</span><span class="sxs-lookup"><span data-stu-id="f5dee-172">Navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, **Application Server-Applications**.</span></span>  
  
12. <span data-ttu-id="f5dee-173">**분석** 노드를 마우스 오른쪽 단추로 클릭하고 **새로 고침을**선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f5dee-173">Right-click the **Analytic** node and select **Refresh**.</span></span>  
  
     <span data-ttu-id="f5dee-174">오른쪽 창에 이벤트가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="f5dee-174">The events appear in the right pane.</span></span>  
  
13. <span data-ttu-id="f5dee-175">ID가 303인 이벤트를 찾아서 두 번 클릭하여 열고 해당 내용을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="f5dee-175">Locate the event with the ID of 303 and double-click it to open it up and inspect its contents.</span></span>  
  
     <span data-ttu-id="f5dee-176">이 이벤트는 ICalculator 서비스의 `Add()` 메서드에 의해 내보내지며 페이로드가 "2+3=5"와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f5dee-176">This event was emitted by the `Add()` method of the ICalculator service and has a payload equal to "2+3=5".</span></span>  
  
#### <a name="to-clean-up-optional"></a><span data-ttu-id="f5dee-177">정리하려면(옵션)</span><span class="sxs-lookup"><span data-stu-id="f5dee-177">To clean up (Optional)</span></span>  
  
1. <span data-ttu-id="f5dee-178">**이벤트 뷰어**를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="f5dee-178">Open **Event Viewer**.</span></span>  
  
2. <span data-ttu-id="f5dee-179">이벤트 **뷰어,** **응용 프로그램 및 서비스 로그,** **Microsoft**, **Windows**및 **응용 프로그램-서버-응용 프로그램으로**이동합니다.</span><span class="sxs-lookup"><span data-stu-id="f5dee-179">Navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application-Server-Applications**.</span></span> <span data-ttu-id="f5dee-180">분석 클릭을 마우스 **오른쪽 단추로** 클릭하고 **로그 사용 안 함**선택.</span><span class="sxs-lookup"><span data-stu-id="f5dee-180">Right-click **Analytic** and select **Disable Log**.</span></span>  
  
3. <span data-ttu-id="f5dee-181">이벤트 **뷰어,** **응용 프로그램 및 서비스 로그,** **Microsoft,** **Windows,** **응용 프로그램-서버-응용 프로그램**및 **분석으로**이동합니다.</span><span class="sxs-lookup"><span data-stu-id="f5dee-181">Navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, **Application-Server-Applications**, and then **Analytic**.</span></span> <span data-ttu-id="f5dee-182">분석 클릭을 마우스 **오른쪽 단추로** 클릭하고 **로그 지우기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f5dee-182">Right-click **Analytic** and select **Clear Log**.</span></span>  
  
4. <span data-ttu-id="f5dee-183">**지우기를** 클릭하여 이벤트를 지웁히 다.</span><span class="sxs-lookup"><span data-stu-id="f5dee-183">Click **Clear** to clear the events.</span></span>  
  
## <a name="known-issue"></a><span data-ttu-id="f5dee-184">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="f5dee-184">Known Issue</span></span>  
 <span data-ttu-id="f5dee-185">**이벤트 뷰어에서** ETW 이벤트를 디코딩하지 못할 수 있는 알려진 문제가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5dee-185">There is a known issue in the **Event Viewer** where it may fail to decode ETW events.</span></span> <span data-ttu-id="f5dee-186">"소스 Microsoft-Windows-응용 프로그램 서버 응용 \<프로그램에서 이벤트 ID> 대한 설명을 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f5dee-186">You may see an error message that says: "The description for Event ID \<id> from source Microsoft-Windows-Application Server-Applications cannot be found.</span></span> <span data-ttu-id="f5dee-187">이 이벤트가 발생되는 구성 요소가 로컬 컴퓨터에 설치되지 않았거나 설치가 손상되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f5dee-187">Either the component that raises this event is not installed on your local computer or the installation is corrupted.</span></span> <span data-ttu-id="f5dee-188">로컬 컴퓨터에서 구성 요소를 설치하거나 복구할 수 있습니다."</span><span class="sxs-lookup"><span data-stu-id="f5dee-188">You can install or repair the component on the local computer."</span></span> <span data-ttu-id="f5dee-189">이 오류가 발생하면 **작업** 메뉴에서 **새로 고침을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f5dee-189">If you encounter this error, select **Refresh** from the **Actions** menu.</span></span> <span data-ttu-id="f5dee-190">그러면 이벤트가 올바르게 디코딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5dee-190">The event should then decode properly.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="f5dee-191">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5dee-191">The samples may already be installed on your computer.</span></span> <span data-ttu-id="f5dee-192">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="f5dee-192">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="f5dee-193">이 디렉터리가 없는 경우 [.NET Framework 4에 대한 WCF(Windows 통신 재단) 및 WF(Windows 워크플로우 재단) 샘플로](https://www.microsoft.com/download/details.aspx?id=21459) 이동하여 모든 WCF(Windows 통신 재단) 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="f5dee-193">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="f5dee-194">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5dee-194">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\ETWTrace`  
  
## <a name="see-also"></a><span data-ttu-id="f5dee-195">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f5dee-195">See also</span></span>

- <span data-ttu-id="f5dee-196">[AppFabric 모니터링 샘플](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="f5dee-196">[AppFabric Monitoring Samples](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))</span></span>
