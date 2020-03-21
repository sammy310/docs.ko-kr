---
title: 성능 카운터 사용
ms.date: 03/30/2017
ms.assetid: 00a787af-1876-473c-a48d-f52b51e28a3f
ms.openlocfilehash: 7ffd9f5de5efb4be22968958246839e804daf23d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79143579"
---
# <a name="using-performance-counters"></a><span data-ttu-id="d7a03-102">성능 카운터 사용</span><span class="sxs-lookup"><span data-stu-id="d7a03-102">Using Performance Counters</span></span>
<span data-ttu-id="d7a03-103">이 샘플에서는 WCF(Windows 통신 Foundation) 성능 카운터에 액세스하는 방법과 사용자 정의 성능 카운터를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d7a03-103">This sample demonstrates how to access Windows Communication Foundation (WCF) performance counters and how to create user-defined performance counters.</span></span> <span data-ttu-id="d7a03-104">이 샘플은 [시작하기](../../../../docs/framework/wcf/samples/getting-started-sample.md)를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a03-104">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d7a03-105">이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7a03-105">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="d7a03-106">이 샘플에서 클라이언트는 `ICalculator` 서비스의 메서드 4개를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a03-106">In this sample, the client calls the four methods of the `ICalculator` service.</span></span> <span data-ttu-id="d7a03-107">클라이언트는 사용자가 중단할 때까지 이 작업을 계속 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a03-107">The client continues to do this until it is interrupted by the user.</span></span> <span data-ttu-id="d7a03-108">서비스는 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d7a03-108">The service remains unchanged.</span></span>  
  
 <span data-ttu-id="d7a03-109">성능 카운터는 다음 샘플 구성에 표시된 것과 같이 서비스에 대한 Web.config 파일의 진단 섹션에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7a03-109">Performance counters are enabled in the diagnostics section of the Web.config file for the service, as shown in the following sample configuration.</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <diagnostics performanceCounters="All" />
  </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="d7a03-110">이 작업은 [구성 편집기 도구(SvcConfigEditor.exe)를](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md)사용하여 수행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7a03-110">This task can also be done using the [Configuration Editor Tool (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md).</span></span>  
  
 <span data-ttu-id="d7a03-111">성능 카운터를 사용하도록 설정하면 서비스에 대해 전체 WCF 성능 카운터 제품군이 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7a03-111">When performance counters are enabled, the entire suite of WCF performance counters is enabled for the service.</span></span> <span data-ttu-id="d7a03-112">.NET Framework는 `ServiceModelService`, `ServiceModelEndpoint` 및 `ServiceModelOperation`의 세 가지 수준에서 성능 데이터를 자동으로 유지 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a03-112">The .NET Framework automatically maintains performance data at three levels: `ServiceModelService`, `ServiceModelEndpoint` and `ServiceModelOperation`.</span></span> <span data-ttu-id="d7a03-113">이러한 각 수준에는 "Calls", "Calls per Second" 및 "Security Calls Not Authorized"와 같은 성능 카운터가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7a03-113">Each of these levels has performance counters such as "Calls", "Calls per Second", and "Security Calls Not Authorized".</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="d7a03-114">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="d7a03-114">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="d7a03-115">Windows 통신 기초 [샘플에 대한 일회성 설치 절차를](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)수행했어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a03-115">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="d7a03-116">C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="d7a03-116">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="d7a03-117">단일 또는 컴퓨터 간 구성에서 샘플을 실행하려면 Windows [통신 기반 샘플 실행의 지침을 따르십시오.](../../../../docs/framework/wcf/samples/running-the-samples.md)</span><span class="sxs-lookup"><span data-stu-id="d7a03-117">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
### <a name="to-view-performance-data"></a><span data-ttu-id="d7a03-118">성능 데이터를 보려면</span><span class="sxs-lookup"><span data-stu-id="d7a03-118">To view performance data</span></span>  
  
1. <span data-ttu-id="d7a03-119">시작 **,** **실행,** `perfmon` **입력** 및 확인을 클릭하거나 제어판에서 관리 **도구를** 선택하고 **성능을**두 번 클릭하여 성능 모니터 도구를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a03-119">Start the Performance Monitor Tool by clicking **Start**, **Run…**, enter `perfmon` and click **OK,** or from Control Panel, select **Administrative Tools** and double-click **Performance**.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="d7a03-120">샘플 코드가 실행될 때까지는 카운터를 추가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d7a03-120">You cannot add counters until the sample code is running.</span></span>  
  
2. <span data-ttu-id="d7a03-121">나열된 성능 카운터를 선택한 다음 Delete 키를 누르면 성능 카운터를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7a03-121">Remove the performance counters that are listed by selecting them and pressing the Delete key.</span></span>  
  
3. <span data-ttu-id="d7a03-122">그래프 창을 마우스 오른쪽 단추로 클릭하고 카운터 추가를 선택하여 WCF **카운터를 추가합니다.**</span><span class="sxs-lookup"><span data-stu-id="d7a03-122">Add WCF counters by right-clicking the graph pane and selecting **Add Counters**.</span></span> <span data-ttu-id="d7a03-123">카운터 **추가** 대화 상자에서 **ServiceModelOperation 3.0.0.0, ServiceModelEndpoint 3.0.0.0 또는 ServiceModelService 3.0.0.0을** 성능 개체 드롭다운 목록 상자에서 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a03-123">In the **Add Counters** dialog box, select **ServiceModelOperation 3.0.0.0, ServiceModelEndpoint 3.0.0.0, or ServiceModelService 3.0.0.0** in the Performance object drop down list box.</span></span> <span data-ttu-id="d7a03-124">목록에서 보려는 카운터를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a03-124">Select the counters you want to view from the list.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="d7a03-125">컴퓨터에서 실행 중인 WCF 서비스가 없는 경우 서비스에 대한 WCF 성능 카운터가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d7a03-125">There are no WCF performance counters for a service if there are no WCF services running on the computer.</span></span>  
  
### <a name="to-use-the-configuration-editor-to-enable-counters"></a><span data-ttu-id="d7a03-126">Configuration Editor를 사용하여 카운터를 사용하려면</span><span class="sxs-lookup"><span data-stu-id="d7a03-126">To use the Configuration Editor to enable counters</span></span>  
  
1. <span data-ttu-id="d7a03-127">SvcConfigEditor.exe의 인스턴스를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="d7a03-127">Open an instance of the SvcConfigEditor.exe.</span></span>  
  
2. <span data-ttu-id="d7a03-128">파일 메뉴에서 **열기를** 클릭한 다음 **구성 파일을 클릭합니다...**</span><span class="sxs-lookup"><span data-stu-id="d7a03-128">On the File menu, click **Open** and then click **Config file…**.</span></span>  
  
3. <span data-ttu-id="d7a03-129">샘플 애플리케이션의 서비스 폴더로 이동한 다음 Web.config 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="d7a03-129">Navigate to the sample application's service folder and open the Web.config file.</span></span>  
  
4. <span data-ttu-id="d7a03-130">구성 트리에서 **진단을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="d7a03-130">Click **Diagnostics** on the Configuration tree.</span></span>  
  
5. <span data-ttu-id="d7a03-131">진단 창에서 **성능 카운터를** 전환하여 '모두'를 **표시합니다.**</span><span class="sxs-lookup"><span data-stu-id="d7a03-131">Toggle **Performance Counter** in the **Diagnostics** window to show 'All'.</span></span>  
  
6. <span data-ttu-id="d7a03-132">구성 파일을 저장하고 편집기를 끝냅니다.</span><span class="sxs-lookup"><span data-stu-id="d7a03-132">Save the configuration file and exit the editor.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="d7a03-133">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7a03-133">The samples may already be installed on your computer.</span></span> <span data-ttu-id="d7a03-134">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="d7a03-134">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="d7a03-135">이 디렉터리가 없는 경우 [.NET Framework 4에 대한 WCF(Windows 통신 재단) 및 WF(Windows 워크플로우 재단) 샘플로](https://www.microsoft.com/download/details.aspx?id=21459) 이동하여 모든 WCF(Windows 통신 재단) 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a03-135">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="d7a03-136">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7a03-136">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\PerfCounters`  
  
## <a name="see-also"></a><span data-ttu-id="d7a03-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d7a03-137">See also</span></span>

- <span data-ttu-id="d7a03-138">[AppFabric 모니터링 샘플](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="d7a03-138">[AppFabric Monitoring Samples](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))</span></span>
