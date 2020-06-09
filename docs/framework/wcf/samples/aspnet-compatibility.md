---
title: ASP.NET 호환성
ms.date: 03/30/2017
ms.assetid: c8b51f1e-c096-4c42-ad99-0519887bbbc5
ms.openlocfilehash: 23930e0756d3fbefc28a8f650b5a056106145a50
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84594714"
---
# <a name="aspnet-compatibility"></a><span data-ttu-id="a40b7-102">ASP.NET 호환성</span><span class="sxs-lookup"><span data-stu-id="a40b7-102">ASP.NET Compatibility</span></span>

<span data-ttu-id="a40b7-103">이 샘플에서는 WCF (Windows Communication Foundation)에서 ASP.NET 호환성 모드를 사용 하도록 설정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a40b7-103">This sample demonstrates how to enable ASP.NET Compatibility mode in Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="a40b7-104">ASP.NET 호환 모드에서 실행 되는 서비스는 ASP.NET 응용 프로그램 파이프라인에 완전히 참여 하며 파일/URL 권한 부여, 세션 상태 및 클래스와 같은 ASP.NET 기능을 활용할 수 있습니다 <xref:System.Web.HttpContext> .</span><span class="sxs-lookup"><span data-stu-id="a40b7-104">Services running in ASP.NET Compatibility mode participate fully in the ASP.NET application pipeline and can make use of ASP.NET features such as file/URL authorization, session state, and the <xref:System.Web.HttpContext> class.</span></span> <span data-ttu-id="a40b7-105"><xref:System.Web.HttpContext>클래스를 사용 하면 쿠키, 세션 및 기타 ASP.NET 기능에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a40b7-105">The <xref:System.Web.HttpContext> class allows access to cookies, sessions, and other ASP.NET features.</span></span> <span data-ttu-id="a40b7-106">이 모드에서는 바인딩에 HTTP 전송이 사용되고 서비스 자체가 IIS에서 호스트되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a40b7-106">This mode requires that the bindings use the HTTP transport and the service itself must be hosted in IIS.</span></span>

<span data-ttu-id="a40b7-107">이 샘플에서 클라이언트는 콘솔 애플리케이션(실행 파일)이고 서비스는 IIS(인터넷 정보 서비스)에서 호스트됩니다.</span><span class="sxs-lookup"><span data-stu-id="a40b7-107">In this sample, the client is a console application (an executable) and the service is hosted in Internet Information Services (IIS).</span></span>

> [!NOTE]
> <span data-ttu-id="a40b7-108">이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a40b7-108">The set-up procedure and build instructions for this sample are located at the end of this topic.</span></span>

<span data-ttu-id="a40b7-109">이 샘플을 실행 하려면 .NET Framework 4 응용 프로그램 풀이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="a40b7-109">This sample requires a .NET Framework 4 application pool in order to run.</span></span> <span data-ttu-id="a40b7-110">새 애플리케이션 풀을 만들거나 기본 애플리케이션 풀을 수정하려면 다음 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="a40b7-110">To create a new application pool, or to modify the default application pool, follow these steps.</span></span>

1. <span data-ttu-id="a40b7-111">**제어판**을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a40b7-111">Open **Control Panel**.</span></span>  <span data-ttu-id="a40b7-112">**시스템 및 보안** 머리글 아래의 **관리 도구** 애플릿을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a40b7-112">Open the **Administrative Tools** applet under the **System and Security** heading.</span></span> <span data-ttu-id="a40b7-113">**인터넷 정보 서비스 (IIS) 관리자** 애플릿을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a40b7-113">Open the **Internet Information Services (IIS) Manager** applet.</span></span>

2. <span data-ttu-id="a40b7-114">**연결** 창에서 treeview를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="a40b7-114">Expand the treeview in the **Connections** pane.</span></span> <span data-ttu-id="a40b7-115">**응용 프로그램 풀** 노드를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a40b7-115">Select the **Application Pools** node.</span></span>

3. <span data-ttu-id="a40b7-116">.NET Framework 4를 사용 하도록 기본 응용 프로그램 풀을 설정 하려면 (이 경우 기존 사이트와 비 호환성 문제가 발생할 수 있음) **DefaultAppPool** 목록 항목을 마우스 오른쪽 단추로 클릭 하 고 **기본 설정**...을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a40b7-116">To set the default application pool to use .NET Framework 4 (which may cause incompatibility problems with existing sites), right-click the **DefaultAppPool** list item and select **Basic Settings…**.</span></span> <span data-ttu-id="a40b7-117">**.Net Framework 버전** 풀을 **.net framework v v4.0.30128** 이상으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a40b7-117">Set the **.Net Framework Version** pull-down to **.Net Framework v4.0.30128** (or later).</span></span>

4. <span data-ttu-id="a40b7-118">.NET Framework 4를 사용 하 여 다른 응용 프로그램의 호환성을 유지 하는 새 응용 프로그램 풀을 만들려면 **응용 프로그램** 풀 노드를 마우스 오른쪽 단추로 클릭 하 고 **응용 프로그램 풀 추가**...를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a40b7-118">To create a new application pool that uses .NET Framework 4 (to preserve compatibility for other applications), right-click the **Application Pools** node and select **Add Application Pool…**.</span></span> <span data-ttu-id="a40b7-119">새 응용 프로그램 풀의 이름을로 설정 하 고 **.Net Framework 버전** 풀을 **.net framework v v4.0.30128** 이상으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a40b7-119">Name the new application pool, and set the **.Net Framework Version** pull-down to **.Net Framework v4.0.30128** (or later).</span></span> <span data-ttu-id="a40b7-120">아래 설치 단계를 실행 한 후 **ServiceModelSamples** 응용 프로그램을 마우스 오른쪽 단추로 클릭 하 고 **응용 프로그램 관리**, **고급 설정**...을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a40b7-120">After running the setup steps below, right-click the **ServiceModelSamples** application and select **Manage Application**, **Advanced Settings…**.</span></span> <span data-ttu-id="a40b7-121">**응용 프로그램 풀** 을 새 응용 프로그램 풀로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a40b7-121">Set the **Application Pool** to the new application pool.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a40b7-122">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a40b7-122">The samples may already be installed on your computer.</span></span> <span data-ttu-id="a40b7-123">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="a40b7-123">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="a40b7-124">이 디렉터리가 없는 경우 [.NET Framework 4에 대 한 Windows Communication Foundation (wcf) 및 Windows Workflow Foundation (WF) 샘플](https://www.microsoft.com/download/details.aspx?id=21459) 로 이동 하 여 모든 WINDOWS COMMUNICATION FOUNDATION (wcf) 및 샘플을 다운로드 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 합니다.</span><span class="sxs-lookup"><span data-stu-id="a40b7-124">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="a40b7-125">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a40b7-125">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\WebHost\ASPNetCompatibility`

<span data-ttu-id="a40b7-126">이 샘플은 계산기 서비스를 구현 하는 [시작](getting-started-sample.md)을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="a40b7-126">This sample is based on the [Getting Started](getting-started-sample.md), which implements a calculator service.</span></span> <span data-ttu-id="a40b7-127">실행 결과를 유지하면서 일련의 작업을 수행할 수 있도록 `ICalculator` 계약은 `ICalculatorSession` 계약으로 수정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a40b7-127">The `ICalculator` contract has been modified as the `ICalculatorSession` contract to allow a set of operations to be performed, while keeping a running result.</span></span>

```csharp
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]
public interface ICalculatorSession
{
    [OperationContract]
    void Clear();
    [OperationContract]
    void AddTo(double n);
    [OperationContract]
    void SubtractFrom(double n);
    [OperationContract]
    void MultiplyBy(double n);
    [OperationContract]
    void DivideBy(double n);
    [OperationContract]
    double Result();
}
```

<span data-ttu-id="a40b7-128">계산을 수행하기 위해 여러 서비스 작업이 호출될 때 서비스는 이 기능을 사용하여 각 클라이언트에 대한 상태를 유지 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="a40b7-128">The service maintains state, using the feature, for each client as multiple service operations are called to perform a calculation.</span></span> <span data-ttu-id="a40b7-129">클라이언트는 `Result`를 호출하여 현재 결과를 검색하고 `Clear`를 호출하여 결과를 0으로 지울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a40b7-129">The client can retrieve the current result by calling `Result` and can clear the result to zero by calling `Clear`.</span></span>

<span data-ttu-id="a40b7-130">서비스는 ASP.NET 세션을 사용 하 여 각 클라이언트 세션에 대 한 결과를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="a40b7-130">The service uses the ASP.NET session to store the result for each client session.</span></span> <span data-ttu-id="a40b7-131">따라서 서비스는 여러 서비스 호출에서 각 클라이언트에 대한 실행 결과를 유지 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a40b7-131">This allows the service to maintain the running result for each client across multiple calls to the service.</span></span>

> [!NOTE]
> <span data-ttu-id="a40b7-132">ASP.NET 세션 상태와 WCF 세션은 매우 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="a40b7-132">ASP.NET session state and WCF sessions are very different things.</span></span> <span data-ttu-id="a40b7-133">WCF 세션에 대 한 자세한 내용은 [세션](session.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a40b7-133">See [Session](session.md) for details on WCF sessions.</span></span>

<span data-ttu-id="a40b7-134">이 서비스는 ASP.NET 세션 상태에 대해 보다 종속성이 있으며 ASP.NET 호환 모드가 제대로 작동 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a40b7-134">The service has an intimate dependency on ASP.NET session state and requires ASP.NET compatibility mode to function correctly.</span></span> <span data-ttu-id="a40b7-135">이러한 요구 사항은 `AspNetCompatibilityRequirements` 특성을 적용하여 선언적으로 표현됩니다.</span><span class="sxs-lookup"><span data-stu-id="a40b7-135">These requirements are expressed declaratively by applying the `AspNetCompatibilityRequirements` attribute.</span></span>

```csharp
[AspNetCompatibilityRequirements(RequirementsMode =
                       AspNetCompatibilityRequirementsMode.Required)]
public class CalculatorService : ICalculatorSession
{
    double Result
    {  // store result in AspNet Session
       get {
          if (HttpContext.Current.Session["Result"] != null)
             return (double)HttpContext.Current.Session["Result"];
          return 0.0D;
       }
       set
       {
          HttpContext.Current.Session["Result"] = value;
       }
    }
    public void Clear()
    {
        Result = 0.0D;
    }
    public void AddTo(double n)
    {
        Result += n;
    }
    public void SubtractFrom(double n)
    {
        Result -= n;
    }
    public void MultiplyBy(double n)
    {
        Result *= n;
    }
    public void DivideBy(double n)
    {
        Result /= n;
    }
    public double Result()
    {
        return Result;
    }
}
```

<span data-ttu-id="a40b7-136">샘플을 실행하면 작업 요청 및 응답이 클라이언트 콘솔 창에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a40b7-136">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="a40b7-137">클라이언트를 종료하려면 클라이언트 창에서 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="a40b7-137">Press ENTER in the client window to shut down the client.</span></span>

```console
0, + 100, - 50, * 17.65, / 2 = 441.25
Press <ENTER> to terminate client.
```

### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="a40b7-138">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="a40b7-138">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="a40b7-139">[Windows Communication Foundation 샘플에 대 한 일회성 설치 절차](one-time-setup-procedure-for-the-wcf-samples.md)를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a40b7-139">Be sure you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="a40b7-140">C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](building-the-samples.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="a40b7-140">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>

3. <span data-ttu-id="a40b7-141">솔루션이 빌드된 후에는 Setup.exe를 실행 하 여 IIS 7.0에서 ServiceModelSamples 응용 프로그램을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a40b7-141">After the solution has been built, run Setup.bat to set up the ServiceModelSamples Application in IIS 7.0.</span></span> <span data-ttu-id="a40b7-142">이제 ServiceModelSamples 디렉터리가 IIS 7.0 응용 프로그램으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a40b7-142">The ServiceModelSamples directory should now appear as an IIS 7.0 Application.</span></span>

4. <span data-ttu-id="a40b7-143">단일 컴퓨터 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](running-the-samples.md)의 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="a40b7-143">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a40b7-144">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a40b7-144">See also</span></span>

- <span data-ttu-id="a40b7-145">[AppFabric 호스팅 및 지속성 샘플](https://docs.microsoft.com/previous-versions/appfabric/ff383418(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="a40b7-145">[AppFabric Hosting and Persistence Samples](https://docs.microsoft.com/previous-versions/appfabric/ff383418(v=azure.10))</span></span>
