---
title: NamedPipe 활성화
ms.date: 03/30/2017
ms.assetid: f3c0437d-006c-442e-bfb0-6b29216e4e29
ms.openlocfilehash: 3e6084e8334eddc16b115cc1199819c6ab637666
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62051847"
---
# <a name="namedpipe-activation"></a><span data-ttu-id="e5b6f-102">NamedPipe 활성화</span><span class="sxs-lookup"><span data-stu-id="e5b6f-102">NamedPipe Activation</span></span>

<span data-ttu-id="e5b6f-103">이 샘플에서는 WAS(Windows Process Activation Service)를 사용하는 서비스를 호스트하여 이름 파이프를 통해 통신하는 서비스를 활성화하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e5b6f-103">This sample demonstrates hosting a service that uses Windows Process Activation Service (WAS) to activate a service that communicates over names pipes.</span></span> <span data-ttu-id="e5b6f-104">이 샘플은 기반 합니다 [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) 하며 [!INCLUDE[wv](../../../../includes/wv-md.md)] 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5b6f-104">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) and requires [!INCLUDE[wv](../../../../includes/wv-md.md)] to run.</span></span>

> [!NOTE]
> <span data-ttu-id="e5b6f-105">이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5b6f-105">The set-up procedure and build instructions for this sample are located at the end of this topic.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e5b6f-106">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5b6f-106">The samples may already be installed on your computer.</span></span> <span data-ttu-id="e5b6f-107">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="e5b6f-107">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="e5b6f-108">이 디렉터리가 없으면로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4 용 Windows WF (Workflow Foundation) 샘플](https://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플.</span><span class="sxs-lookup"><span data-stu-id="e5b6f-108">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="e5b6f-109">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5b6f-109">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\WASHost\NamedPipeActivation`

## <a name="sample-details"></a><span data-ttu-id="e5b6f-110">샘플 세부 정보</span><span class="sxs-lookup"><span data-stu-id="e5b6f-110">Sample Details</span></span>

<span data-ttu-id="e5b6f-111">이 샘플은 WAS(Windows Process Activation Services)에 의해 활성화된 작업자 프로세스에서 호스트되는 서비스 라이브러리(.dll) 및 클라이언트 콘솔 프로그램(.exe)으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5b6f-111">The sample consists of a client console program (.exe) and a service library (.dll) hosted in a worker process activated by the Windows Process Activation Services (WAS).</span></span> <span data-ttu-id="e5b6f-112">콘솔 창에는 클라이언트 동작이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5b6f-112">Client activity is visible in the console window.</span></span>

<span data-ttu-id="e5b6f-113">이 서비스는 요청-회신 통신 패턴을 정의하는 계약을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="e5b6f-113">The service implements a contract that defines a request-reply communication pattern.</span></span> <span data-ttu-id="e5b6f-114">계약은 다음 샘플 코드처럼 수학 연산(더하기, 빼기, 곱하기 및 나누기)을 노출시키는 `ICalculator` 인터페이스에서 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5b6f-114">The contract is defined by the `ICalculator` interface, which exposes math operations (Add, Subtract, Multiply, and Divide), as shown in the following sample code.</span></span>

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

<span data-ttu-id="e5b6f-115">클라이언트에서는 지정된 수학 연산을 동기적으로 요청하고 서비스 구현에서는 계산을 통해 올바른 결과를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="e5b6f-115">The client makes synchronous requests to a given math operation and the service implementation calculates and returns the appropriate result.</span></span>

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

<span data-ttu-id="e5b6f-116">샘플에서는 보안 없이 수정된 `netNamedPipeBinding` 바인딩을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e5b6f-116">The sample uses a modified `netNamedPipeBinding` binding with no security.</span></span> <span data-ttu-id="e5b6f-117">클라이언트 및 서비스 구성 파일에 바인딩이 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5b6f-117">The binding is specified in the configuration files for the client and service.</span></span> <span data-ttu-id="e5b6f-118">서비스의 바인딩 형식은 다음 샘플 구성과 같이 엔드포인트 요소의 `binding` 특성에 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5b6f-118">The binding type for the service is specified in the endpoint element’s `binding` attribute as shown in the following sample configuration.</span></span>

<span data-ttu-id="e5b6f-119">보안이 설정된 명명된 파이프 바인딩을 사용하려면 서버의 보안 모드를 원하는 보안 설정으로 변경하고 클라이언트에서 svcutil.exe를 다시 실행하여 업데이트된 클라이언트 구성 파일을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e5b6f-119">If you want use a secured named pipe binding, change the server's security mode to the desired security setting and run svcutil.exe again on the client to obtain an updated client configuration file.</span></span>

```xml
<system.serviceModel>
        <services>
            <service name="Microsoft.ServiceModel.Samples.CalculatorService"
               behaviorConfiguration="CalculatorServiceBehavior">

        <!-- This endpoint is exposed at the base address provided by host: net.pipe://localhost/servicemodelsamples/service.svc  -->
        <endpoint address=""
                  binding="netNamedPipeBinding"
                  bindingConfiguration="Binding1"
                  contract="Microsoft.ServiceModel.Samples.ICalculator" />
        <!-- the mex endpoint is exposed at net.pipe://localhost/servicemodelsamples/service.svc/mex -->
        <endpoint address="mex"
                  binding="mexNamedPipeBinding"
                  contract="IMetadataExchange" />
      </service>
        </services>
        <bindings>
            <netNamedPipeBinding>
                <binding name="Binding1" >
                    <security mode = "None">
                    </security>
                </binding >
            </netNamedPipeBinding>
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

<span data-ttu-id="e5b6f-120">클라이언트의 엔드포인트 정보는 다음 샘플 코드와 같이 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5b6f-120">The client’s endpoint information is configured as shown in the following sample code.</span></span>

```xml
<system.serviceModel>

    <client>
      <endpoint name=""
                          address="net.pipe://localhost/servicemodelsamples/service.svc"
                          binding="netNamedPipeBinding"
                          bindingConfiguration="Binding1"
                          contract="Microsoft.ServiceModel.Samples.ICalculator" />
    </client>

    <bindings>

      <!--  Following is the expanded configuration section for a NetNamedPipeBinding.
            Each property is configured with the default value. -->

      <netNamedPipeBinding>
        <binding name="Binding1"
                         maxBufferSize="65536"
                         maxConnections="10">
          <security mode = "None">
          </security>
        </binding >

      </netNamedPipeBinding>
    </bindings>

  </system.serviceModel>
```

<span data-ttu-id="e5b6f-121">샘플을 실행하면 작업 요청 및 응답이 클라이언트 콘솔 창에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5b6f-121">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="e5b6f-122">클라이언트를 종료하려면 클라이언트 창에서 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="e5b6f-122">Press ENTER in the client window to shut down the client.</span></span>

```console
Add(100,15.99) = 115.99
Subtract(145,76.54) = 68.46
Multiply(9,81.25) = 731.25
Divide(22,7) = 3.14285714285714

Press <ENTER> to terminate client.
```

### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="e5b6f-123">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="e5b6f-123">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="e5b6f-124">[!INCLUDE[iisver](../../../../includes/iisver-md.md)]이 설치되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="e5b6f-124">Ensure that [!INCLUDE[iisver](../../../../includes/iisver-md.md)] is installed.</span></span> [!INCLUDE[iisver](../../../../includes/iisver-md.md)]<span data-ttu-id="e5b6f-125">은 WAS 활성화에 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="e5b6f-125">is required for WAS activation.</span></span>

2. <span data-ttu-id="e5b6f-126">수행 했는지 확인 합니다 [Windows Communication Foundation 샘플에 대 한 일회성 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e5b6f-126">Ensure you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

    <span data-ttu-id="e5b6f-127">또한 WCF NON-HTTP activation 구성 요소를 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5b6f-127">In addition, you must install the WCF non-HTTP activation components:</span></span>

    1. <span data-ttu-id="e5b6f-128">**시작** 메뉴에서 **제어판**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e5b6f-128">From the **Start** menu, choose **Control Panel**.</span></span>

    2. <span data-ttu-id="e5b6f-129">선택 **프로그램 및 기능**합니다.</span><span class="sxs-lookup"><span data-stu-id="e5b6f-129">Select **Programs and Features**.</span></span>

    3. <span data-ttu-id="e5b6f-130">클릭 **Windows 구성 요소를 켜거나 끄려면**합니다.</span><span class="sxs-lookup"><span data-stu-id="e5b6f-130">Click **Turn Windows Components on or Off**.</span></span>

    4. <span data-ttu-id="e5b6f-131">확장을 **Microsoft.NET Framework 3.0** 노드와 확인 합니다 **Windows Communication Foundation 비 HTTP 활성화** 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="e5b6f-131">Expand the **Microsoft .NET Framework 3.0** node and check the **Windows Communication Foundation Non-HTTP Activation** feature.</span></span>

3. <span data-ttu-id="e5b6f-132">명명된 파이프 활성화를 지원하도록 WAS(Windows Process Activation Service)를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="e5b6f-132">Configure the Windows Process Activation Service (WAS) to support named pipe activation.</span></span>

    <span data-ttu-id="e5b6f-133">편의를 위해 다음 두 단계는 샘플 디렉터리에 있는 AddNetPipeSiteBinding.cmd라는 배치 파일에서 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="e5b6f-133">As a convenience, the following two steps are implemented in a batch file called AddNetPipeSiteBinding.cmd located in the sample directory.</span></span>

    1. <span data-ttu-id="e5b6f-134">net. pipe 활성화를 지원하려면 먼저 기본 웹 사이트를 net. pipe 프로토콜에 바인딩해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5b6f-134">To support net.pipe activation, the default Web site must first be bound to the net.pipe protocol.</span></span> <span data-ttu-id="e5b6f-135">이 작업은 IIS 7.0 관리 도구 집합과 함께 설치되는 appcmd.exe를 사용하여 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5b6f-135">This can be done using appcmd.exe, which is installed with the IIS 7.0 management toolset.</span></span> <span data-ttu-id="e5b6f-136">권한이 높은 명령 프롬프트에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e5b6f-136">From an elevated (administrator) command prompt, run the following command.</span></span>

        ```
        %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site"
        -+bindings.[protocol='net.pipe',bindingInformation='*']
        ```

        > [!NOTE]
        > <span data-ttu-id="e5b6f-137">이 명령은 줄 바꿈 없이 한 줄로 입력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5b6f-137">This command is a single line of text.</span></span>

        <span data-ttu-id="e5b6f-138">이 명령은 기본 웹 사이트에 net.pipe 사이트 바인딩을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="e5b6f-138">This command adds a net.pipe site binding to the default Web site.</span></span>

    2. <span data-ttu-id="e5b6f-139">사이트 내의 모든 응용 프로그램에서 공통된 net.pipe 바인딩을 공유하지만 각 응용 프로그램에서 net.pipe 지원을 개별적으로 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5b6f-139">Although all applications within a site share a common net.pipe binding, each application can enable net.pipe support individually.</span></span> <span data-ttu-id="e5b6f-140">/servicemodelsamples 응용 프로그램에서 net.pipe를 사용하도록 설정하려면 권한이 높은 명령 프롬프트에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e5b6f-140">To enable net.pipe for the /servicemodelsamples application, run the following command from an elevated command prompt.</span></span>

        ```
        %windir%\system32\inetsrv\appcmd.exe set app "Default Web Site/servicemodelsamples" /enabledProtocols:http,net.pipe
        ```

        > [!NOTE]
        > <span data-ttu-id="e5b6f-141">이 명령은 줄 바꿈 없이 한 줄로 입력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5b6f-141">This command is a single line of text.</span></span>

        <span data-ttu-id="e5b6f-142">이 명령을 사용 하 여 /servicemodelsamples 응용 프로그램에 모두 사용 하 여 액세스할 수 `http://localhost/servicemodelsamples` 고 `net.tcp://localhost/servicemodelsamples`입니다.</span><span class="sxs-lookup"><span data-stu-id="e5b6f-142">This command enables the /servicemodelsamples application to be accessed using both `http://localhost/servicemodelsamples` and `net.tcp://localhost/servicemodelsamples`.</span></span>

4. <span data-ttu-id="e5b6f-143">C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="e5b6f-143">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>

5. <span data-ttu-id="e5b6f-144">이 샘플에 대해 추가한 net. pipe 사이트 바인딩을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="e5b6f-144">Remove the net.pipe site binding you added for this sample.</span></span>

    <span data-ttu-id="e5b6f-145">편의를 위해 다음 두 단계는 샘플 디렉터리에 있는 RemoveNetPipeSiteBinding.cmd라는 배치 파일에서 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="e5b6f-145">As a convenience, the following two steps are implemented in a batch file called RemoveNetPipeSiteBinding.cmd located in the sample directory:</span></span>

    1. <span data-ttu-id="e5b6f-146">권한이 높은 명령 프롬프트에서 다음 명령을 실행하여 사용된 프로토콜 목록에서 net.tcp를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="e5b6f-146">Remove net.tcp from the list of enabled protocols by running the following command from an elevated command prompt.</span></span>

        ```
        %windir%\system32\inetsrv\appcmd.exe set app "Default Web Site/servicemodelsamples" /enabledProtocols:http
        ```

        > [!NOTE]
        > <span data-ttu-id="e5b6f-147">이 명령은 줄 바꿈 없이 한 줄로 입력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5b6f-147">This command must be entered as a single line of text.</span></span>

    2. <span data-ttu-id="e5b6f-148">권한이 높은 명령 프롬프트에서 다음 명령을 실행하여 net.tcp 사이트 바인딩을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="e5b6f-148">Remove the net.tcp site binding by running the following command from an elevated command prompt.</span></span>

        ```
        %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site" --bindings.[protocol='net.pipe',bindingInformation='*']
        ```

        > [!NOTE]
        > <span data-ttu-id="e5b6f-149">이 명령은 줄 바꿈 없이 한 줄로 입력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5b6f-149">This command must be typed in as a single line of text.</span></span>

## <a name="see-also"></a><span data-ttu-id="e5b6f-150">참고자료</span><span class="sxs-lookup"><span data-stu-id="e5b6f-150">See also</span></span>

- <span data-ttu-id="e5b6f-151">[AppFabric 호스팅 및 지 속성 샘플](https://docs.microsoft.com/previous-versions/appfabric/ff383418(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="e5b6f-151">[AppFabric Hosting and Persistence Samples](https://docs.microsoft.com/previous-versions/appfabric/ff383418(v=azure.10))</span></span>
