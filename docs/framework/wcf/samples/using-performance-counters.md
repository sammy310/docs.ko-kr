---
description: '자세한 정보: 성능 카운터 사용'
title: 성능 카운터 사용
ms.date: 03/30/2017
ms.assetid: 00a787af-1876-473c-a48d-f52b51e28a3f
ms.openlocfilehash: f2305310238df9c11ebc2612248f2d7d1b6ea6f6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99755735"
---
# <a name="using-performance-counters"></a><span data-ttu-id="c2412-103">성능 카운터 사용</span><span class="sxs-lookup"><span data-stu-id="c2412-103">Using Performance Counters</span></span>

<span data-ttu-id="c2412-104">이 샘플에서는 WCF (Windows Communication Foundation) 성능 카운터에 액세스 하는 방법과 사용자 정의 성능 카운터를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c2412-104">This sample demonstrates how to access Windows Communication Foundation (WCF) performance counters and how to create user-defined performance counters.</span></span> <span data-ttu-id="c2412-105">이 샘플은 [시작](getting-started-sample.md)을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2412-105">This sample is based on the [Getting Started](getting-started-sample.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c2412-106">이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2412-106">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="c2412-107">이 샘플에서 클라이언트는 `ICalculator` 서비스의 메서드 4개를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="c2412-107">In this sample, the client calls the four methods of the `ICalculator` service.</span></span> <span data-ttu-id="c2412-108">클라이언트는 사용자가 중단할 때까지 이 작업을 계속 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="c2412-108">The client continues to do this until it is interrupted by the user.</span></span> <span data-ttu-id="c2412-109">서비스는 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c2412-109">The service remains unchanged.</span></span>  
  
 <span data-ttu-id="c2412-110">성능 카운터는 다음 샘플 구성에 표시된 것과 같이 서비스에 대한 Web.config 파일의 진단 섹션에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2412-110">Performance counters are enabled in the diagnostics section of the Web.config file for the service, as shown in the following sample configuration.</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <diagnostics performanceCounters="All" />
  </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="c2412-111">[구성 편집기 도구 (SvcConfigEditor.exe)](../configuration-editor-tool-svcconfigeditor-exe.md)를 사용 하 여이 작업을 수행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2412-111">This task can also be done using the [Configuration Editor Tool (SvcConfigEditor.exe)](../configuration-editor-tool-svcconfigeditor-exe.md).</span></span>  
  
 <span data-ttu-id="c2412-112">성능 카운터를 사용 하도록 설정 하면 서비스에 대 한 전체 WCF 성능 카운터 집합이 활성화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2412-112">When performance counters are enabled, the entire suite of WCF performance counters is enabled for the service.</span></span> <span data-ttu-id="c2412-113">.NET Framework는 `ServiceModelService`, `ServiceModelEndpoint` 및 `ServiceModelOperation`의 세 가지 수준에서 성능 데이터를 자동으로 유지 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="c2412-113">The .NET Framework automatically maintains performance data at three levels: `ServiceModelService`, `ServiceModelEndpoint` and `ServiceModelOperation`.</span></span> <span data-ttu-id="c2412-114">이러한 각 수준에는 "Calls", "Calls per Second" 및 "Security Calls Not Authorized"와 같은 성능 카운터가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2412-114">Each of these levels has performance counters such as "Calls", "Calls per Second", and "Security Calls Not Authorized".</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="c2412-115">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="c2412-115">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="c2412-116">[Windows Communication Foundation 샘플에 대 한 일회성 설치 절차](one-time-setup-procedure-for-the-wcf-samples.md)를 수행 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2412-116">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="c2412-117">C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](building-the-samples.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="c2412-117">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="c2412-118">단일 컴퓨터 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](running-the-samples.md)의 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="c2412-118">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
  
### <a name="to-view-performance-data"></a><span data-ttu-id="c2412-119">성능 데이터를 보려면</span><span class="sxs-lookup"><span data-stu-id="c2412-119">To view performance data</span></span>  
  
1. <span data-ttu-id="c2412-120">**시작**, **실행** 을 차례로 클릭 하 `perfmon` 고 **확인을** 클릭 하거나 제어판에서 **관리 도구** 를 선택 하 고 **성능** 을 두 번 클릭 하 여 성능 모니터 도구를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2412-120">Start the Performance Monitor Tool by clicking **Start**, **Run…**, enter `perfmon` and click **OK,** or from Control Panel, select **Administrative Tools** and double-click **Performance**.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="c2412-121">샘플 코드가 실행될 때까지는 카운터를 추가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c2412-121">You cannot add counters until the sample code is running.</span></span>  
  
2. <span data-ttu-id="c2412-122">나열된 성능 카운터를 선택한 다음 Delete 키를 누르면 성능 카운터를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2412-122">Remove the performance counters that are listed by selecting them and pressing the Delete key.</span></span>  
  
3. <span data-ttu-id="c2412-123">그래프 창을 마우스 오른쪽 단추로 클릭 하 고 **카운터 추가** 를 선택 하 여 WCF 카운터를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2412-123">Add WCF counters by right-clicking the graph pane and selecting **Add Counters**.</span></span> <span data-ttu-id="c2412-124">**카운터 추가** 대화 상자의 성능 개체 드롭다운 목록 상자에서 **ServiceModelOperation 3.0.0.0, ServiceModelEndpoint 3.0.0.0 또는 ServiceModelService 3.0.0.0** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2412-124">In the **Add Counters** dialog box, select **ServiceModelOperation 3.0.0.0, ServiceModelEndpoint 3.0.0.0, or ServiceModelService 3.0.0.0** in the Performance object drop down list box.</span></span> <span data-ttu-id="c2412-125">목록에서 보려는 카운터를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c2412-125">Select the counters you want to view from the list.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="c2412-126">컴퓨터에서 실행 중인 WCF 서비스가 없는 경우에는 서비스에 대 한 WCF 성능 카운터가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c2412-126">There are no WCF performance counters for a service if there are no WCF services running on the computer.</span></span>  
  
### <a name="to-use-the-configuration-editor-to-enable-counters"></a><span data-ttu-id="c2412-127">Configuration Editor를 사용하여 카운터를 사용하려면</span><span class="sxs-lookup"><span data-stu-id="c2412-127">To use the Configuration Editor to enable counters</span></span>  
  
1. <span data-ttu-id="c2412-128">SvcConfigEditor.exe의 인스턴스를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="c2412-128">Open an instance of the SvcConfigEditor.exe.</span></span>  
  
2. <span data-ttu-id="c2412-129">파일 메뉴에서 **열기** 를 클릭 한 다음 **구성 파일 ...** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2412-129">On the File menu, click **Open** and then click **Config file…**.</span></span>  
  
3. <span data-ttu-id="c2412-130">샘플 애플리케이션의 서비스 폴더로 이동한 다음 Web.config 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="c2412-130">Navigate to the sample application's service folder and open the Web.config file.</span></span>  
  
4. <span data-ttu-id="c2412-131">구성 트리에서 **진단** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2412-131">Click **Diagnostics** on the Configuration tree.</span></span>  
  
5. <span data-ttu-id="c2412-132">**진단** 창에서 **성능 카운터** 를 설정/해제 하 여 ' 모두 '를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2412-132">Toggle **Performance Counter** in the **Diagnostics** window to show 'All'.</span></span>  
  
6. <span data-ttu-id="c2412-133">구성 파일을 저장하고 편집기를 끝냅니다.</span><span class="sxs-lookup"><span data-stu-id="c2412-133">Save the configuration file and exit the editor.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="c2412-134">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2412-134">The samples may already be installed on your computer.</span></span> <span data-ttu-id="c2412-135">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="c2412-135">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="c2412-136">이 디렉터리가 없는 경우 [.NET Framework 4에 대 한 Windows Communication Foundation (wcf) 및 Windows Workflow Foundation (WF) 샘플](https://www.microsoft.com/download/details.aspx?id=21459) 로 이동 하 여 모든 WINDOWS COMMUNICATION FOUNDATION (wcf) 및 샘플을 다운로드 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2412-136">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="c2412-137">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2412-137">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\PerfCounters`  
  
## <a name="see-also"></a><span data-ttu-id="c2412-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c2412-138">See also</span></span>

- <span data-ttu-id="c2412-139">[AppFabric 모니터링 샘플](/previous-versions/appfabric/ff383407(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="c2412-139">[AppFabric Monitoring Samples](/previous-versions/appfabric/ff383407(v=azure.10))</span></span>
