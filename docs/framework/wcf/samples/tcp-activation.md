---
title: TCP 활성화
ms.date: 03/30/2017
ms.assetid: bf8c215c-0228-4f4f-85c2-e33794ec09a7
ms.openlocfilehash: e6f40b31656746d3db37545709c4e4813a7422cf
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90555187"
---
# <a name="tcp-activation"></a><span data-ttu-id="dd8bb-102">TCP 활성화</span><span class="sxs-lookup"><span data-stu-id="dd8bb-102">TCP Activation</span></span>

<span data-ttu-id="dd8bb-103">이 샘플에서는 net.tcp 프로토콜을 통해 통신하는 서비스를 활성화하기 위해 WAS(Windows Process Activation Service)를 사용하는 서비스를 호스트하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="dd8bb-103">This sample demonstrates hosting a service that uses Windows Process Activation Services (WAS) to activate a service that communicates over the net.tcp protocol.</span></span> <span data-ttu-id="dd8bb-104">이 샘플은 [시작](getting-started-sample.md)을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd8bb-104">This sample is based on the [Getting Started](getting-started-sample.md).</span></span>

> [!NOTE]
> <span data-ttu-id="dd8bb-105">이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd8bb-105">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dd8bb-106">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd8bb-106">The samples may already be installed on your computer.</span></span> <span data-ttu-id="dd8bb-107">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="dd8bb-107">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="dd8bb-108">이 디렉터리가 없는 경우 [.NET Framework 4에 대 한 Windows Communication Foundation (wcf) 및 Windows Workflow Foundation (WF) 샘플](https://www.microsoft.com/download/details.aspx?id=21459) 로 이동 하 여 모든 WINDOWS COMMUNICATION FOUNDATION (wcf) 및 샘플을 다운로드 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd8bb-108">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="dd8bb-109">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd8bb-109">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\WASHost\TCPActivation`

<span data-ttu-id="dd8bb-110">이 샘플은 WAS에 의해 활성화된 작업자 프로세스에서 호스트되는 서비스 라이브러리(.dll) 및 클라이언트 콘솔 프로그램(.exe)으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd8bb-110">The sample consists of a client console program (.exe) and a service library (.dll) hosted in a worker process activated by WAS.</span></span> <span data-ttu-id="dd8bb-111">콘솔 창에는 클라이언트 동작이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd8bb-111">Client activity is visible in the console window.</span></span>

<span data-ttu-id="dd8bb-112">이 서비스는 요청-회신 통신 패턴을 정의하는 계약을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="dd8bb-112">The service implements a contract that defines a request-reply communication pattern.</span></span> <span data-ttu-id="dd8bb-113">다음 샘플 코드와 같이 계약은 수학 작업(Add, Subtract, Multifly 및 Divide)을 노출시키는 `ICalculator` 인터페이스에 의해 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd8bb-113">The contract is defined by the `ICalculator` interface, which exposes math operations (Add, Subtract, Multiply, and Divide), as shown in the following sample code:</span></span>

```csharp
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]
public interface ICalculator
{
    [OperationContract]
    double Add(double n1, double n2);
    [OperationContract]
    double Subtract(double n1, double n2);
    [OperationContract]
    double Multiply(double n1, double n2);
    [OperationContract]
    double Divide(double n1, double n2);
}
```

<span data-ttu-id="dd8bb-114">서비스 구현에서는 해당 결과를 계산하여 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="dd8bb-114">The service implementation calculates and returns the appropriate result:</span></span>

```csharp
// Service class that implements the service contract.
public class CalculatorService : ICalculator
{
    public double Add(double n1, double n2)
    {
        return n1 + n2;
    }
    public double Subtract(double n1, double n2)
    {
        return n1 - n2;
    }
    public double Multiply(double n1, double n2)
    {
        return n1 * n2;
    }
    public double Divide(double n1, double n2)
    {
        return n1 / n2;
    }
}
```

<span data-ttu-id="dd8bb-115">TCP 포트 공유가 설정되고 보안이 해제된 net.tcp 바인딩 변형이 샘플에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd8bb-115">The sample uses a variant of the net.tcp binding with TCP port sharing enabled and security turned off.</span></span> <span data-ttu-id="dd8bb-116">보안된 TCP 바인딩을 사용하려면 서버의 보안 모드를 원하는 설정으로 변경하고 클라이언트에서 Svcutil.exe를 다시 실행하여 업데이트 클라이언트 구성 파일을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="dd8bb-116">If you want to use a secured TCP binding, change the server's security mode to the desired setting and re-run Svcutil.exe on the client to generate an update client configuration file.</span></span>

<span data-ttu-id="dd8bb-117">다음 샘플에서는 서비스에 대한 구성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="dd8bb-117">The following sample shows the configuration for the service:</span></span>

```xml
<system.serviceModel>

    <services>
      <service name="Microsoft.ServiceModel.Samples.CalculatorService"
               behaviorConfiguration="CalculatorServiceBehavior">
        <!-- This endpoint is exposed at the base address provided by host: net.tcp://localhost/servicemodelsamples/service.svc  -->
        <endpoint binding="netTcpBinding" bindingConfiguration="PortSharingBinding"
          contract="Microsoft.ServiceModel.Samples.ICalculator" />
        <!-- the mex endpoint is exposed at net.tcp://localhost/servicemodelsamples/service.svc/mex -->
        <endpoint address="mex"
                  binding="mexTcpBinding"
                  contract="IMetadataExchange" />
      </service>
    </services>
    <bindings>
      <netTcpBinding>
        <binding name="PortSharingBinding" portSharingEnabled="true">
          <security mode="None" />
        </binding>
      </netTcpBinding>
    </bindings>

    <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->
    <behaviors>
      <serviceBehaviors>
        <behavior name="CalculatorServiceBehavior">
          <serviceMetadata />
          <serviceDebug includeExceptionDetailInFaults="False" />
        </behavior>
      </serviceBehaviors>
    </behaviors>

  </system.serviceModel>
```

<span data-ttu-id="dd8bb-118">다음 샘플 코드와 같이 클라이언트의 엔드포인트가 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd8bb-118">The client's endpoint is configured as shown in the following sample code:</span></span>

```xml
<system.serviceModel>
    <bindings>
        <netTcpBinding>
          <binding name="NetTcpBinding_ICalculator">
            <security mode="None"/>
          </binding>
        </netTcpBinding>
    </bindings>
    <client>
        <endpoint address="net.tcp://localhost/servicemodelsamples/service.svc"
            binding="netTcpBinding" bindingConfiguration="NetTcpBinding_ICalculator"
            contract="Microsoft.ServiceModel.Samples.ICalculator" name="NetTcpBinding_ICalculator" />
    </client>
</system.serviceModel>
```

<span data-ttu-id="dd8bb-119">샘플을 실행하면 작업 요청 및 응답이 클라이언트 콘솔 창에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd8bb-119">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="dd8bb-120">클라이언트를 종료하려면 클라이언트 창에서 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="dd8bb-120">Press ENTER in the client window to shut down the client.</span></span>

```console
Add(100,15.99) = 115.99
Subtract(145,76.54) = 68.46
Multiply(9,81.25) = 731.25
Divide(22,7) = 3.14285714285714

Press <ENTER> to terminate client.
```

### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="dd8bb-121">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="dd8bb-121">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="dd8bb-122">IIS 7.0이 설치 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd8bb-122">Ensure that IIS 7.0 is installed.</span></span> <span data-ttu-id="dd8bb-123">WAS 활성화에는 IIS 7.0가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd8bb-123">IIS 7.0 is required for WAS activation.</span></span>

2. <span data-ttu-id="dd8bb-124">[Windows Communication Foundation 샘플에 대 한 일회성 설치 절차](one-time-setup-procedure-for-the-wcf-samples.md)를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd8bb-124">Be sure you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

    <span data-ttu-id="dd8bb-125">또한 WCF 비 HTTP 활성화 구성 요소를 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd8bb-125">In addition, you must install the WCF non-HTTP activation components:</span></span>

    1. <span data-ttu-id="dd8bb-126">**시작** 메뉴에서 **제어판**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="dd8bb-126">From the **Start** menu, choose **Control Panel**.</span></span>

    2. <span data-ttu-id="dd8bb-127">**프로그램 및 기능**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd8bb-127">Select **Programs and Features**.</span></span>

    3. <span data-ttu-id="dd8bb-128">**Windows 구성 요소 사용/사용 안 함을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd8bb-128">Click **Turn Windows Components on or Off**.</span></span>

    4. <span data-ttu-id="dd8bb-129">**Microsoft .NET Framework 3.0** 노드를 확장 하 고 **Windows Communication Foundation 비 HTTP 활성화** 기능을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd8bb-129">Expand the **Microsoft .NET Framework 3.0** node and check the **Windows Communication Foundation Non-HTTP Activation** feature.</span></span>

3. <span data-ttu-id="dd8bb-130">TCP 활성화를 지원하도록 WAS를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="dd8bb-130">Configure WAS to support TCP activation.</span></span>

    <span data-ttu-id="dd8bb-131">편의를 위해 다음 두 단계는 샘플 디렉터리에 있는 AddNetTcpSiteBinding.cmd라는 배치 파일에서 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd8bb-131">As a convenience, the following two steps are implemented in a batch file called AddNetTcpSiteBinding.cmd located in the sample directory.</span></span>

    1. <span data-ttu-id="dd8bb-132">net.tcp 활성화를 지원하려면 먼저 기본 웹 사이트를 net.tcp 포트에 바인딩해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd8bb-132">To support net.tcp activation, the default Web site must first be bound to a net.tcp port.</span></span> <span data-ttu-id="dd8bb-133">IIS(인터넷 정보 서비스) 7.0 관리 도구 집합과 함께 설치되는 Appcmd.exe를 사용하여 이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd8bb-133">This can be done using Appcmd.exe, which is installed with the Internet Information Services 7.0 (IIS) management toolset.</span></span> <span data-ttu-id="dd8bb-134">관리자 수준 명령 프롬프트에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="dd8bb-134">From an administrator-level command prompt, run the following command:</span></span>

        ```console
        %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site" -+bindings.[protocol='net.tcp',bindingInformation='808:*']
        ```

        > [!TIP]
        > <span data-ttu-id="dd8bb-135">이 명령은 줄 바꿈 없이 한 줄로 입력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd8bb-135">This command is a single line of text.</span></span> <span data-ttu-id="dd8bb-136">이 명령은 임의의 호스트 이름을 사용하여 TCP 포트 808에서 수신 대기하는 기본 웹 사이트에 net.tcp 사이트 바인딩을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="dd8bb-136">This command adds a net.tcp site binding to the default Web site listening on TCP port 808 with any hostname.</span></span>

    2. <span data-ttu-id="dd8bb-137">사이트 내의 모든 애플리케이션이 공통된 net.tcp 바인딩을 공유하지만 각 애플리케이션에서 개별적으로 net.tcp 지원을 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd8bb-137">Although all applications within a site share a common net.tcp binding, each application can enable net.tcp support individually.</span></span> <span data-ttu-id="dd8bb-138">/servicemodelsamples 애플리케이션에 대해 net.tcp를 사용하도록 설정하려면 관리자 수준 명령 프롬프트에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="dd8bb-138">To enable net.tcp for the /servicemodelsamples application, run the following command from an administrator-level command prompt:</span></span>

        ```console
        %windir%\system32\inetsrv\appcmd.exe set app
        "Default Web Site/servicemodelsamples" /enabledProtocols:http,net.tcp
        ```

        > [!NOTE]
        > <span data-ttu-id="dd8bb-139">이 명령은 줄 바꿈 없이 한 줄로 입력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd8bb-139">This command is a single line of text.</span></span> <span data-ttu-id="dd8bb-140">이 명령을 사용 하면 및를 모두 사용 하 여/servicemodelsamples 응용 프로그램에 액세스할 수 있습니다 `http://localhost/servicemodelsamples` `net.tcp://localhost/servicemodelsamples` .</span><span class="sxs-lookup"><span data-stu-id="dd8bb-140">This command enables the /servicemodelsamples application to be accessed using both `http://localhost/servicemodelsamples` and `net.tcp://localhost/servicemodelsamples`.</span></span>

4. <span data-ttu-id="dd8bb-141">C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](building-the-samples.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="dd8bb-141">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>

5. <span data-ttu-id="dd8bb-142">단일 컴퓨터 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](running-the-samples.md)의 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="dd8bb-142">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>

    <span data-ttu-id="dd8bb-143">이 샘플에 대해 추가한 net.tcp 사이트 바인딩을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="dd8bb-143">Remove the net.tcp site binding you added for this sample.</span></span>

    <span data-ttu-id="dd8bb-144">편의를 위해 다음 두 단계는 샘플 디렉터리에 있는 RemoveNetTcpSiteBinding.cmd라는 배치 파일에서 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd8bb-144">As a convenience, the following two steps are implemented in a batch file called RemoveNetTcpSiteBinding.cmd located in the sample directory.</span></span>

    1. <span data-ttu-id="dd8bb-145">관리자 수준 명령 프롬프트에서 다음 명령을 실행하여 사용하도록 설정된 프로토콜 목록에서 net.tcp를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="dd8bb-145">Remove net.tcp from the list of enabled protocols by running the following command from an administrator-level command prompt:</span></span>

        ```console
        %windir%\system32\inetsrv\appcmd.exe set app
        "Default Web Site/servicemodelsamples" /enabledProtocols:http
        ```

        > [!NOTE]
        > <span data-ttu-id="dd8bb-146">이 명령은 줄 바꿈 없이 한 줄로 입력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd8bb-146">This command must be entered as a single line of text.</span></span>

    2. <span data-ttu-id="dd8bb-147">관리자 수준 명령 프롬프트에서 다음 명령을 실행하여 net.tcp 사이트 바인딩을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="dd8bb-147">Remove the net.tcp site binding by running the following command from an administrator-level command prompt:</span></span>

        ```console
        %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site"
        --bindings.[protocol='net.tcp',bindingInformation='808:*']
        ```

        > [!NOTE]
        > <span data-ttu-id="dd8bb-148">이 명령은 줄 바꿈 없이 한 줄로 입력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd8bb-148">This command must be typed in as a single line of text.</span></span>

## <a name="see-also"></a><span data-ttu-id="dd8bb-149">참조</span><span class="sxs-lookup"><span data-stu-id="dd8bb-149">See also</span></span>

- <span data-ttu-id="dd8bb-150">[AppFabric 호스팅 및 지속성 샘플](/previous-versions/appfabric/ff383418(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="dd8bb-150">[AppFabric Hosting and Persistence Samples](/previous-versions/appfabric/ff383418(v=azure.10))</span></span>
