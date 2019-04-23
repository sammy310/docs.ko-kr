---
title: WCF 분석 추적
ms.date: 03/30/2017
ms.assetid: 6029c7c7-3515-4d36-9d43-13e8f4971790
ms.openlocfilehash: 9ed89bdbe2469a96f2a959c9fda8442e80b6f7ec
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59332315"
---
# <a name="wcf-analytic-tracing"></a><span data-ttu-id="1cd33-102">WCF 분석 추적</span><span class="sxs-lookup"><span data-stu-id="1cd33-102">WCF Analytic Tracing</span></span>
<span data-ttu-id="1cd33-103">이 샘플에는 Windows Communication Foundation (WCF) ETW에 기록 하는 분석 추적 스트림에 고유한 추적 이벤트를 추가 하는 방법을 보여 줍니다. [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="1cd33-103">This sample demonstrates how to add your own tracing events into the stream of analytic traces that Windows Communication Foundation (WCF) writes to ETW in [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)].</span></span> <span data-ttu-id="1cd33-104">분석 추적은 성능을 크게 저하시키지 않으면서 서비스를 쉽게 확인할 수 있도록 하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1cd33-104">Analytic traces are meant to make it easy to get visibility into your services without paying a high performance penalty.</span></span> <span data-ttu-id="1cd33-105">이 샘플에 사용 하는 방법을 보여 줍니다는 <xref:System.Diagnostics.Eventing?displayProperty=nameWithType> WCF 서비스와 통합 하는 쓰기 이벤트에는 Api입니다.</span><span class="sxs-lookup"><span data-stu-id="1cd33-105">This sample shows how to use the <xref:System.Diagnostics.Eventing?displayProperty=nameWithType> APIs to write events that integrate with WCF services.</span></span>  
  
 <span data-ttu-id="1cd33-106">에 대 한 자세한 내용은 합니다 <xref:System.Diagnostics.Eventing?displayProperty=nameWithType> Api 참조 <xref:System.Diagnostics.Eventing?displayProperty=nameWithType>합니다.</span><span class="sxs-lookup"><span data-stu-id="1cd33-106">For more information about the <xref:System.Diagnostics.Eventing?displayProperty=nameWithType> APIs, see <xref:System.Diagnostics.Eventing?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="1cd33-107">Windows에서 이벤트 추적에 대 한 자세한 내용은 참조 하세요 [디버깅 및 ETW를 사용한 성능 조정 개선](https://go.microsoft.com/fwlink/?LinkId=166488)합니다.</span><span class="sxs-lookup"><span data-stu-id="1cd33-107">To learn more about event tracing in Windows, see [Improve Debugging and Performance Tuning with ETW](https://go.microsoft.com/fwlink/?LinkId=166488).</span></span>  
  
## <a name="disposing-eventprovider"></a><span data-ttu-id="1cd33-108">EventProvider 삭제</span><span class="sxs-lookup"><span data-stu-id="1cd33-108">Disposing EventProvider</span></span>  
 <span data-ttu-id="1cd33-109">이 샘플에서는 <xref:System.Diagnostics.Eventing.EventProvider?displayProperty=nameWithType>을 구현하는 <xref:System.IDisposable?displayProperty=nameWithType> 클래스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1cd33-109">This sample uses the <xref:System.Diagnostics.Eventing.EventProvider?displayProperty=nameWithType> class, which implements <xref:System.IDisposable?displayProperty=nameWithType>.</span></span> <span data-ttu-id="1cd33-110">WCF 서비스에 대 한 추적을 구현할 때 사용할 수 있는 가능성이 <xref:System.Diagnostics.Eventing.EventProvider>의 서비스의 수명에 대 한 리소스입니다.</span><span class="sxs-lookup"><span data-stu-id="1cd33-110">When implementing tracing for a WCF service, it is likely that you may use the <xref:System.Diagnostics.Eventing.EventProvider>’s resources for the lifetime of the service.</span></span> <span data-ttu-id="1cd33-111">이러한 이유로, 또한 읽기 쉽게 하려는 목적으로 이 샘플에서는 래핑된 <xref:System.Diagnostics.Eventing.EventProvider>를 삭제하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1cd33-111">For this reason, and for readability, this sample never disposes of the wrapped <xref:System.Diagnostics.Eventing.EventProvider>.</span></span> <span data-ttu-id="1cd33-112">어떤 이유로 서비스에 다른 추적 요구 사항이 있으며 이 리소스를 삭제해야 하는 경우 관리되지 않는 리소스를 삭제하기 위한 최선의 방법에 따라 이 샘플을 수정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cd33-112">If for some reason your service has different requirements for tracing and you must dispose of this resource, then you should modify this sample in accordance with the best practices for disposing of unmanaged resources.</span></span> <span data-ttu-id="1cd33-113">관리 되지 않는 리소스를 삭제 하는 방법에 대 한 자세한 내용은 참조 하세요. [Dispose 메서드 구현](https://go.microsoft.com/fwlink/?LinkId=166436)합니다.</span><span class="sxs-lookup"><span data-stu-id="1cd33-113">For more information about disposing unmanaged resources, see [Implementing a Dispose Method](https://go.microsoft.com/fwlink/?LinkId=166436).</span></span>  
  
## <a name="self-hosting-vs-web-hosting"></a><span data-ttu-id="1cd33-114">자체 호스팅 및 웹 호스팅</span><span class="sxs-lookup"><span data-stu-id="1cd33-114">Self-Hosting vs. Web Hosting</span></span>  
 <span data-ttu-id="1cd33-115">웹 호스팅 서비스에 대 한 WCF의 분석 추적은 추적을 내보내는 서비스를 식별 하는 데 사용 되는 "HostReference" 라는 필드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cd33-115">For Web-hosted services, WCF’s analytic traces provide a field, called "HostReference", which is used to identify the service that is emitting the traces.</span></span> <span data-ttu-id="1cd33-116">확장 가능한 사용자 추적이 이 모델에 관여할 수 있으며 이 샘플에서는 이 작업을 수행하기 위한 최선의 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1cd33-116">The extensible user traces can participate in this model and this sample demonstrates best practices for doing so.</span></span> <span data-ttu-id="1cd33-117">웹 호스트의 형식을 참조할 때 파이프를 '&#124;' 문자는 실제로 결과 표시 문자열에는 다음 중 하나일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1cd33-117">The format of a Web host reference when the pipe ‘&#124;’ character actually appears in the resulting string can be any one of the following:</span></span>  
  
-   <span data-ttu-id="1cd33-118">응용 프로그램이 루트에 없는 경우</span><span class="sxs-lookup"><span data-stu-id="1cd33-118">If the application is not at the root.</span></span>  
  
     <span data-ttu-id="1cd33-119">\<SiteName>\<ApplicationVirtualPath>&#124;\<ServiceVirtualPath>&#124;\<ServiceName></span><span class="sxs-lookup"><span data-stu-id="1cd33-119">\<SiteName>\<ApplicationVirtualPath>&#124;\<ServiceVirtualPath>&#124;\<ServiceName></span></span>  
  
-   <span data-ttu-id="1cd33-120">응용 프로그램이 루트에 있는 경우</span><span class="sxs-lookup"><span data-stu-id="1cd33-120">If the application is at the root.</span></span>  
  
     <span data-ttu-id="1cd33-121">\<SiteName>&#124;\<ServiceVirtualPath>&#124;\<ServiceName></span><span class="sxs-lookup"><span data-stu-id="1cd33-121">\<SiteName>&#124;\<ServiceVirtualPath>&#124;\<ServiceName></span></span>  
  
 <span data-ttu-id="1cd33-122">자체 호스팅된 서비스에 대 한 WCF의 분석 추적은 "HostReference" 필드를 채우지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1cd33-122">For self-hosted services, WCF’s analytic traces do not populate the "HostReference" field.</span></span> <span data-ttu-id="1cd33-123">이 샘플의 `WCFUserEventProvider` 클래스는 자체 호스팅 서비스에서 사용될 때 일관성 있게 동작합니다.</span><span class="sxs-lookup"><span data-stu-id="1cd33-123">The `WCFUserEventProvider` class in this sample behaves consistently when used by a self-hosted service.</span></span>  
  
## <a name="custom-event-details"></a><span data-ttu-id="1cd33-124">사용자 지정 이벤트 상세 정보</span><span class="sxs-lookup"><span data-stu-id="1cd33-124">Custom Event Details</span></span>  
 <span data-ttu-id="1cd33-125">WCF의 ETW 이벤트 공급자 매니페스트는 서비스 코드 내에서 WCF 서비스 작성자 내보내도록 설계 된 세 가지 이벤트를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cd33-125">WCF’s ETW Event Provider manifest defines three events that are designed to be emitted by WCF service authors from within service code.</span></span> <span data-ttu-id="1cd33-126">다음 표에서는 세 개의 이벤트를 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1cd33-126">The following table shows a breakdown of the three events.</span></span>  
  
|<span data-ttu-id="1cd33-127">이벤트</span><span class="sxs-lookup"><span data-stu-id="1cd33-127">Event</span></span>|<span data-ttu-id="1cd33-128">설명</span><span class="sxs-lookup"><span data-stu-id="1cd33-128">Description</span></span>|<span data-ttu-id="1cd33-129">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="1cd33-129">Event ID</span></span>|  
|-----------|-----------------|--------------|  
|<span data-ttu-id="1cd33-130">UserDefinedInformationEventOccurred</span><span class="sxs-lookup"><span data-stu-id="1cd33-130">UserDefinedInformationEventOccurred</span></span>|<span data-ttu-id="1cd33-131">문제는 아니지만 중요한 사항이 서비스에 발생하면 이 이벤트를 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="1cd33-131">Emit this event when something of note happens in your service that is not a problem.</span></span> <span data-ttu-id="1cd33-132">예를 들어 데이터베이스를 성공적으로 호출한 후 이벤트를 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1cd33-132">For example, you might emit an event after successfully making a call to a database.</span></span>|<span data-ttu-id="1cd33-133">301</span><span class="sxs-lookup"><span data-stu-id="1cd33-133">301</span></span>|  
|<span data-ttu-id="1cd33-134">UserDefinedWarningOccurred</span><span class="sxs-lookup"><span data-stu-id="1cd33-134">UserDefinedWarningOccurred</span></span>|<span data-ttu-id="1cd33-135">이후에 오류를 초래할 수 있는 문제가 발생하면 이 이벤트를 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="1cd33-135">Emit this event when a problem occurs that may result in a failure in the future.</span></span> <span data-ttu-id="1cd33-136">예를 들어 데이터베이스에 대한 호출에 실패했지만 중복 데이터 저장소를 대신 사용하여 복구할 수 있는 경우 경고 이벤트를 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1cd33-136">For example, you may emit a warning event when a call to a database fails but you were able to recover by falling back to a redundant data store.</span></span>|<span data-ttu-id="1cd33-137">302</span><span class="sxs-lookup"><span data-stu-id="1cd33-137">302</span></span>|  
|<span data-ttu-id="1cd33-138">UserDefinedErrorOccurred</span><span class="sxs-lookup"><span data-stu-id="1cd33-138">UserDefinedErrorOccurred</span></span>|<span data-ttu-id="1cd33-139">서비스가 예상한 대로 동작하지 않으면 이 이벤트를 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="1cd33-139">Emit this event when your service fails to behave as expected.</span></span> <span data-ttu-id="1cd33-140">예를 들어 데이터베이스에 대한 호출에 실패하고 다른 위치에서 데이터를 검색할 수 없는 경우 이벤트를 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1cd33-140">For example, you might emit an event if a call to a database fails and you could not retrieve the data from elsewhere.</span></span>|<span data-ttu-id="1cd33-141">303</span><span class="sxs-lookup"><span data-stu-id="1cd33-141">303</span></span>|  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="1cd33-142">이 샘플을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="1cd33-142">To use this sample</span></span>  
  
1. <span data-ttu-id="1cd33-143">WCFAnalyticTracingExtensibility.sln 솔루션 파일을 열고 Visual Studio 2012를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cd33-143">Using Visual Studio 2012, open the WCFAnalyticTracingExtensibility.sln solution file.</span></span>  
  
2. <span data-ttu-id="1cd33-144">Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="1cd33-144">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3. <span data-ttu-id="1cd33-145">Ctrl+F5를 눌러 솔루션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="1cd33-145">To run the solution, press CTRL+F5.</span></span>  
  
     <span data-ttu-id="1cd33-146">웹 브라우저에서 클릭 **Calculator.svc**합니다.</span><span class="sxs-lookup"><span data-stu-id="1cd33-146">In the Web browser, click **Calculator.svc**.</span></span> <span data-ttu-id="1cd33-147">서비스의 WSDL 문서에 대한 URI가 브라우저에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="1cd33-147">The URI of the WSDL document for the service should appear in the browser.</span></span> <span data-ttu-id="1cd33-148">이 URI를 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="1cd33-148">Copy that URI.</span></span>  
  
4. <span data-ttu-id="1cd33-149">WCF 테스트 클라이언트 (WcfTestClient.exe)를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cd33-149">Run the WCF test client (WcfTestClient.exe).</span></span>  
  
     <span data-ttu-id="1cd33-150">WCF 테스트 클라이언트 (WcfTestClient.exe)에 위치한 `\<Visual Studio 2012 Install Dir>\Common7\IDE\WcfTestClient.exe`합니다.</span><span class="sxs-lookup"><span data-stu-id="1cd33-150">The WCF test client (WcfTestClient.exe) is located at `\<Visual Studio 2012 Install Dir>\Common7\IDE\WcfTestClient.exe`.</span></span> <span data-ttu-id="1cd33-151">기본 Visual Studio 2012 설치 디렉터리는 `C:\Program Files\Microsoft Visual Studio 10.0`합니다.</span><span class="sxs-lookup"><span data-stu-id="1cd33-151">The default Visual Studio 2012 install dir is `C:\Program Files\Microsoft Visual Studio 10.0`.</span></span>  
  
5. <span data-ttu-id="1cd33-152">WCF 테스트 클라이언트 내에서 선택 하 여 서비스를 추가할 **파일**를 차례로 **서비스 추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="1cd33-152">Within the WCF test client, add the service by selecting **File**, and then **Add Service**.</span></span>  
  
     <span data-ttu-id="1cd33-153">입력 상자에 엔드포인트 주소를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1cd33-153">Add the endpoint address in the input box.</span></span>  
  
6. <span data-ttu-id="1cd33-154">클릭 **확인** 는 대화 상자를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="1cd33-154">Click **OK** to close the dialog.</span></span>  
  
     <span data-ttu-id="1cd33-155">ICalculator 서비스가 아래 왼쪽된 창에서 추가 된 **내 서비스 프로젝트**합니다.</span><span class="sxs-lookup"><span data-stu-id="1cd33-155">The ICalculator service is added in the left pane under **My Service Projects**.</span></span>  
  
7. <span data-ttu-id="1cd33-156">이벤트 뷰어 애플리케이션을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="1cd33-156">Open the Event Viewer application.</span></span>  
  
     <span data-ttu-id="1cd33-157">서비스를 호출 하기 전에 이벤트 뷰어를 시작 하 고 WCF 서비스에서 내보낸 추적 이벤트에 대 한 이벤트 로그에서이 수신 대기 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cd33-157">Before invoking the service, start Event Viewer and ensure that the event log is listening for tracking events emitted from the WCF service.</span></span>  
  
8. <span data-ttu-id="1cd33-158">**시작** 메뉴에서 **관리 도구**를 차례로 **이벤트 뷰어**합니다.</span><span class="sxs-lookup"><span data-stu-id="1cd33-158">From the **Start** menu, select **Administrative Tools**, and then **Event Viewer**.</span></span> <span data-ttu-id="1cd33-159">사용 하도록 설정 합니다 **분석** 하 고 **디버그** 로그 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cd33-159">Enable the **Analytic** and **Debug** logs.</span></span>  
  
9. <span data-ttu-id="1cd33-160">이동할 이벤트 뷰어의 트리 뷰에서 **이벤트 뷰어**, **Applications and Services Logs**를 **Microsoft**를 **Windows**, 한 다음 **응용 프로그램 서버-응용 프로그램**합니다.</span><span class="sxs-lookup"><span data-stu-id="1cd33-160">In the tree view in Event Viewer, navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application Server-Applications**.</span></span> <span data-ttu-id="1cd33-161">마우스 오른쪽 단추로 클릭 **응용 프로그램 서버-응용 프로그램**를 선택 **뷰**를 차례로 **분석 및 디버그 로그 표시**합니다.</span><span class="sxs-lookup"><span data-stu-id="1cd33-161">Right-click **Application Server-Applications**, select **View**, and then **Show Analytic and Debug Logs**.</span></span>  
  
     <span data-ttu-id="1cd33-162">있는지 확인 합니다 **분석 및 디버그 로그 표시** 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cd33-162">Ensure that the **Show Analytic and Debug Logs** option is checked.</span></span> <span data-ttu-id="1cd33-163">사용 하도록 설정 합니다 **분석** 로그 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cd33-163">Enable the **Analytic** log.</span></span>  
  
     <span data-ttu-id="1cd33-164">이동할 이벤트 뷰어의 트리 뷰에서 **이벤트 뷰어**, **Applications and Services Logs**를 **Microsoft**를 **Windows**합니다  **응용 프로그램 서버-응용 프로그램**, 차례로 **분석**합니다.</span><span class="sxs-lookup"><span data-stu-id="1cd33-164">In the tree view in Event Viewer, navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, **Application Server-Applications**, and then **Analytic**.</span></span> <span data-ttu-id="1cd33-165">마우스 오른쪽 단추로 클릭 **분석** 선택한 **로그 사용**합니다.</span><span class="sxs-lookup"><span data-stu-id="1cd33-165">Right-click **Analytic** and select **Enable Log**.</span></span>  
  
10. <span data-ttu-id="1cd33-166">WCF 테스트 클라이언트를 사용하여 서비스를 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="1cd33-166">Test the service using the WCF Test Client.</span></span>  
  
    1.  <span data-ttu-id="1cd33-167">WCF 테스트 클라이언트에서 두 번 클릭 **add ()** ICalculator 서비스 노드에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cd33-167">In the WCF Test Client, double-click **Add()** under the ICalculator service node.</span></span>  
  
         <span data-ttu-id="1cd33-168">합니다 **add ()** 메서드가 두 개의 매개 변수를 사용 하 여 오른쪽 창에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="1cd33-168">The **Add()** method appears in the right pane with two parameters.</span></span>  
  
    2.  <span data-ttu-id="1cd33-169">첫 번째 매개 변수에 2를 입력하고 두 번째 매개 변수에 3을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="1cd33-169">Type in 2 for the first parameter and 3 for the second parameter.</span></span>  
  
    3.  <span data-ttu-id="1cd33-170">클릭 **Invoke** 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cd33-170">Click **Invoke** to invoke the method.</span></span>  
  
11. <span data-ttu-id="1cd33-171">로 이동 합니다 **이벤트 뷰어** 열려 있는 창입니다.</span><span class="sxs-lookup"><span data-stu-id="1cd33-171">Go to the **Event Viewer** window that you have already opened.</span></span> <span data-ttu-id="1cd33-172">이동할 **이벤트 뷰어**, **Applications and Services Logs**합니다 **Microsoft**를 **Windows**, **응용 프로그램 서버-응용 프로그램**합니다.</span><span class="sxs-lookup"><span data-stu-id="1cd33-172">Navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, **Application Server-Applications**.</span></span>  
  
12. <span data-ttu-id="1cd33-173">마우스 오른쪽 단추로 클릭 합니다 **분석** 노드와 선택 **새로 고침**합니다.</span><span class="sxs-lookup"><span data-stu-id="1cd33-173">Right-click the **Analytic** node and select **Refresh**.</span></span>  
  
     <span data-ttu-id="1cd33-174">오른쪽 창에 이벤트가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="1cd33-174">The events appear in the right pane.</span></span>  
  
13. <span data-ttu-id="1cd33-175">ID가 303인 이벤트를 찾아서 두 번 클릭하여 열고 해당 내용을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="1cd33-175">Locate the event with the ID of 303 and double-click it to open it up and inspect its contents.</span></span>  
  
     <span data-ttu-id="1cd33-176">이 이벤트를 내 보냈으므로 `Add()` ICalculator 서비스의 메서드에 같음 페이로드 및 "2 + 3 = 5".</span><span class="sxs-lookup"><span data-stu-id="1cd33-176">This event was emitted by the `Add()` method of the ICalculator service and has a payload equal to "2+3=5".</span></span>  
  
#### <a name="to-clean-up-optional"></a><span data-ttu-id="1cd33-177">정리하려면(옵션)</span><span class="sxs-lookup"><span data-stu-id="1cd33-177">To clean up (Optional)</span></span>  
  
1. <span data-ttu-id="1cd33-178">오픈 **이벤트 뷰어**합니다.</span><span class="sxs-lookup"><span data-stu-id="1cd33-178">Open **Event Viewer**.</span></span>  
  
2. <span data-ttu-id="1cd33-179">이동할 **이벤트 뷰어**를 **Applications and Services Logs**를 **Microsoft**를 **Windows**를 차례로  **응용 프로그램 서버-응용 프로그램**합니다.</span><span class="sxs-lookup"><span data-stu-id="1cd33-179">Navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application-Server-Applications**.</span></span> <span data-ttu-id="1cd33-180">마우스 오른쪽 단추로 클릭 **분석** 선택한 **로그 사용 안 함**합니다.</span><span class="sxs-lookup"><span data-stu-id="1cd33-180">Right-click **Analytic** and select **Disable Log**.</span></span>  
  
3. <span data-ttu-id="1cd33-181">이동할 **이벤트 뷰어**, **Applications and Services Logs**합니다 **Microsoft**를 **Windows**,  **응용 프로그램 서버-응용 프로그램**, 차례로 **분석**합니다.</span><span class="sxs-lookup"><span data-stu-id="1cd33-181">Navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, **Application-Server-Applications**, and then **Analytic**.</span></span> <span data-ttu-id="1cd33-182">마우스 오른쪽 단추로 클릭 **분석** 선택한 **로그 지우기**합니다.</span><span class="sxs-lookup"><span data-stu-id="1cd33-182">Right-click **Analytic** and select **Clear Log**.</span></span>  
  
4. <span data-ttu-id="1cd33-183">클릭 **의 선택을 취소** 이벤트의 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cd33-183">Click **Clear** to clear the events.</span></span>  
  
## <a name="known-issue"></a><span data-ttu-id="1cd33-184">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="1cd33-184">Known Issue</span></span>  
 <span data-ttu-id="1cd33-185">알려진 문제가 합니다 **이벤트 뷰어** ETW 이벤트가 디코딩되지 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1cd33-185">There is a known issue in the **Event Viewer** where it may fail to decode ETW events.</span></span> <span data-ttu-id="1cd33-186">라는 오류 메시지가 표시 될 수 있습니다. "이벤트 ID에 대 한 설명을 \<id > 원본 Microsoft-Windows-응용 프로그램 서버-응용 프로그램을 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1cd33-186">You may see an error message that says: "The description for Event ID \<id> from source Microsoft-Windows-Application Server-Applications cannot be found.</span></span> <span data-ttu-id="1cd33-187">이 이벤트를 발생시킨 구성 요소가 로컬 컴퓨터에 설치되어 있지 않거나 설치가 손상되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1cd33-187">Either the component that raises this event is not installed on your local computer or the installation is corrupted.</span></span> <span data-ttu-id="1cd33-188">설치 또는 로컬 컴퓨터의 구성 요소를 복구 합니다. "</span><span class="sxs-lookup"><span data-stu-id="1cd33-188">You can install or repair the component on the local computer."</span></span> <span data-ttu-id="1cd33-189">이 오류가 발생 하는 경우 선택할 **새로 고침** 에서 합니다 **작업** 메뉴.</span><span class="sxs-lookup"><span data-stu-id="1cd33-189">If you encounter this error, select **Refresh** from the **Actions** menu.</span></span> <span data-ttu-id="1cd33-190">그러면 이벤트가 올바르게 디코딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="1cd33-190">The event should then decode properly.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="1cd33-191">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1cd33-191">The samples may already be installed on your computer.</span></span> <span data-ttu-id="1cd33-192">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="1cd33-192">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="1cd33-193">이 디렉터리가 없으면로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4 용 Windows WF (Workflow Foundation) 샘플](https://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플.</span><span class="sxs-lookup"><span data-stu-id="1cd33-193">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="1cd33-194">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1cd33-194">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\ETWTrace`  
  
## <a name="see-also"></a><span data-ttu-id="1cd33-195">참고자료</span><span class="sxs-lookup"><span data-stu-id="1cd33-195">See also</span></span>

- [<span data-ttu-id="1cd33-196">AppFabric 모니터링 샘플</span><span class="sxs-lookup"><span data-stu-id="1cd33-196">AppFabric Monitoring Samples</span></span>](https://go.microsoft.com/fwlink/?LinkId=193959)
