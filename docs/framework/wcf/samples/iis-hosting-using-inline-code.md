---
title: 인라인 코드를 사용한 IIS 호스팅
ms.date: 03/30/2017
helpviewer_keywords:
- Web hosted service
- IIS Hosting Using Inline Code Sample [Windows Communication Foundation]
ms.assetid: 56fe3687-a34b-4661-8e30-b33770f413fa
ms.openlocfilehash: 47d056e35b92654c8e47647c7273c5d69b37bd97
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84594649"
---
# <a name="iis-hosting-using-inline-code"></a><span data-ttu-id="785e9-102">인라인 코드를 사용한 IIS 호스팅</span><span class="sxs-lookup"><span data-stu-id="785e9-102">IIS Hosting Using Inline Code</span></span>

<span data-ttu-id="785e9-103">이 샘플에서는 IIS(인터넷 정보 서비스)에서 호스팅하는 서비스를 구현하는 방법을 보여 줍니다. 여기서 서비스 코드는 .svc 파일에 인라인으로 포함되어 있으며 필요할 때 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="785e9-103">This sample demonstrates how to implement a service hosted by Internet Information Services (IIS), where the service code is contained in-line in a .svc file and is compiled on demand.</span></span> <span data-ttu-id="785e9-104">또한 서비스 코드를 애플리케이션의 \App_Code 디렉터리에 있는 소스 코드 파일에서 직접 구현하거나 \bin에 배포된 어셈블리로 컴파일할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="785e9-104">Service code can also be implemented directly in source code files located in the application's \App_Code directory, or compiled into assembly deployed in \bin.</span></span> <span data-ttu-id="785e9-105">이 샘플에서는 이러한 기술은 보여 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="785e9-105">This sample does not demonstrate these techniques.</span></span>

> [!NOTE]
> <span data-ttu-id="785e9-106">이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="785e9-106">The set-up procedure and build instructions for this sample are located at the end of this topic.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="785e9-107">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="785e9-107">The samples may already be installed on your computer.</span></span> <span data-ttu-id="785e9-108">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="785e9-108">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="785e9-109">이 디렉터리가 없는 경우 [.NET Framework 4에 대 한 Windows Communication Foundation (wcf) 및 Windows Workflow Foundation (WF) 샘플](https://www.microsoft.com/download/details.aspx?id=21459) 로 이동 하 여 모든 WINDOWS COMMUNICATION FOUNDATION (wcf) 및 샘플을 다운로드 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 합니다.</span><span class="sxs-lookup"><span data-stu-id="785e9-109">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="785e9-110">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="785e9-110">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\WebHost\InlineCode`

<span data-ttu-id="785e9-111">이 샘플에서는 요청-회신 통신 패턴을 정의하는 계약을 구현하는 일반적인 서비스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="785e9-111">The sample demonstrates a typical service that implements a contract that defines a request-reply communication pattern.</span></span> <span data-ttu-id="785e9-112">이 서비스는 IIS에서 호스팅되며 서비스 코드는 모두 Service.svc 파일에 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="785e9-112">The service is hosted in IIS and the service code is entirely contained in the Service.svc file.</span></span> <span data-ttu-id="785e9-113">서비스는 호스트에서 활성화되며 서비스로 전송된 첫 번째 메시지에 의해 필요할 때 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="785e9-113">The service is host-activated and compiled on-demand by the first message sent to the service.</span></span> <span data-ttu-id="785e9-114">미리 컴파일할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="785e9-114">There is no pre-compilation necessary.</span></span> <span data-ttu-id="785e9-115">서비스는 다음 코드에 정의된 대로 `ICalculator` 계약을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="785e9-115">The service implements an `ICalculator` contract as defined in the following code:</span></span>

```csharp
// Define a service contract.
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

<span data-ttu-id="785e9-116">이 서비스 구현에서는 해당 결과를 계산하여 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="785e9-116">The service implementation calculates and returns the appropriate result.</span></span>

`<%@ServiceHost language=c# Debug="true" Service="Microsoft.ServiceModel.Samples.CalculatorService" %>`

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

<span data-ttu-id="785e9-117">샘플을 실행하면 작업 요청 및 응답이 클라이언트 콘솔 창에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="785e9-117">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="785e9-118">클라이언트를 종료하려면 클라이언트 창에서 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="785e9-118">Press ENTER in the client window to shut down the client.</span></span>

```console
Add(100,15.99) = 115.99
Subtract(145,76.54) = 68.46
Multiply(9,81.25) = 731.25
Divide(22,7) = 3.14285714285714

Press <ENTER> to terminate client.
```

### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="785e9-119">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="785e9-119">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="785e9-120">[Windows Communication Foundation 샘플에 대 한 일회성 설치 절차](one-time-setup-procedure-for-the-wcf-samples.md)를 수행 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="785e9-120">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="785e9-121">C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](building-the-samples.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="785e9-121">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>

3. <span data-ttu-id="785e9-122">솔루션이 빌드된 후에는 setup.exe를 실행 하 여 IIS 7.0에서 ServiceModelSamples 응용 프로그램을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="785e9-122">After the solution has been built, run setup.bat to set up the ServiceModelSamples Application in IIS 7.0.</span></span> <span data-ttu-id="785e9-123">이제 ServiceModelSamples 디렉터리가 IIS 7.0 응용 프로그램으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="785e9-123">The ServiceModelSamples directory should now appear as an IIS 7.0 Application.</span></span>

4. <span data-ttu-id="785e9-124">단일 컴퓨터 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](running-the-samples.md)의 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="785e9-124">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span> <span data-ttu-id="785e9-125">이 서비스를 호출할 수 있는 클라이언트 응용 프로그램을 만드는 방법에 대 한 예제는 [방법: 클라이언트 만들기](../how-to-create-a-wcf-client.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="785e9-125">For an example on how to create a client application that can call this service, see [How to: Create a Client](../how-to-create-a-wcf-client.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="785e9-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="785e9-126">See also</span></span>

- <span data-ttu-id="785e9-127">[AppFabric 호스팅 및 지속성 샘플](https://docs.microsoft.com/previous-versions/appfabric/ff383418(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="785e9-127">[AppFabric Hosting and Persistence Samples](https://docs.microsoft.com/previous-versions/appfabric/ff383418(v=azure.10))</span></span>
