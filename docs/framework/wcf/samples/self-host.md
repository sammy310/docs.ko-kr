---
title: 자체 호스팅
ms.date: 03/30/2017
helpviewer_keywords:
- Self hosted service
- Self Host Sample [Windows Communication Foundation]
ms.assetid: 05e68661-1ddf-4abf-a899-9bb1b8272a5b
ms.openlocfilehash: 5a94eff021074a24df5b8891fe7b418b1fcf3c35
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/09/2020
ms.locfileid: "77094919"
---
# <a name="self-host"></a><span data-ttu-id="10620-102">자체 호스팅</span><span class="sxs-lookup"><span data-stu-id="10620-102">Self-Host</span></span>
<span data-ttu-id="10620-103">이 샘플에서는 콘솔 애플리케이션에서 자체 호스팅 서비스를 구현하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="10620-103">This sample demonstrates how to implement a self-hosted service in a console application.</span></span> <span data-ttu-id="10620-104">이 샘플은 [시작](../../../../docs/framework/wcf/samples/getting-started-sample.md)을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="10620-104">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span></span> <span data-ttu-id="10620-105">서비스 구성 파일이 Web.config에서 App.config로 이름이 바뀌고 호스트에서 사용하는 기본 주소를 구성하도록 수정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="10620-105">The service configuration file has been renamed from Web.config to App.config and modified to configure a base address, which the host uses.</span></span> <span data-ttu-id="10620-106">서비스 소스 코드가 구성된 기본 주소를 제공하는 서비스 호스트를 만들고 여는 정적 `Main` 기능을 구현하도록 수정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="10620-106">The service source code has been modified to implement a static `Main` function that creates and opens a service host that provides the configured base address.</span></span> <span data-ttu-id="10620-107">서비스 구현이 각 작업에 대해 콘솔에 출력을 쓰도록 수정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="10620-107">The service implementation has been modified to write output to the console for each operation.</span></span> <span data-ttu-id="10620-108">클라이언트는 서비스의 올바른 엔드포인트 주소를 구성하기 위한 부분을 제외하고는 수정되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="10620-108">The client has been unmodified, except for configuring the correct endpoint address of the service.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="10620-109">이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10620-109">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="10620-110">샘플에서는 다음 샘플 코드에 표시된 것과 같이 지정된 <xref:System.ServiceModel.ServiceHost> 형식에 `CalculatorService`를 만드는 정적 main 함수를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="10620-110">The sample implements a static main function to create a <xref:System.ServiceModel.ServiceHost> for the given `CalculatorService` type, as shown in the following sample code.</span></span>  
  
```csharp
// Host the service within this EXE console application.  
public static void Main()  
{  
    // Create a ServiceHost for the CalculatorService type.  
    using (ServiceHost serviceHost =   
           new ServiceHost(typeof(CalculatorService)))  
    {  
        // Open the ServiceHost to create listeners   
        // and start listening for messages.  
        serviceHost.Open();  
  
        // The service can now be accessed.  
        Console.WriteLine("The service is ready.");  
        Console.WriteLine("Press <ENTER> to terminate service.");  
        Console.WriteLine();  
        Console.ReadLine();  
    }  
}  
```  
  
 <span data-ttu-id="10620-111">인터넷 정보 서비스(IIS) 또는 WAS(Windows Process Activation Service)에 서비스가 호스팅된 경우 서비스의 기본 주소는 호스팅 환경에 의해 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="10620-111">When a service is hosted in Internet Information Services (IIS) or Windows Process Activation Service (WAS), the base address of the service is provided by the hosting environment.</span></span> <span data-ttu-id="10620-112">자체 호스팅의 경우에는 직접 기본 주소를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="10620-112">In the self-hosted case, you must specify the base address yourself.</span></span> <span data-ttu-id="10620-113">이 작업은 다음 샘플 구성에서 보여 주는 것 처럼 `add` 요소, [\<baseAddresses](../../../../docs/framework/configure-apps/file-schema/wcf/baseaddresses.md) [\<](../../../../docs/framework/configure-apps/file-schema/wcf/host.md)>의 자식 ( [> 서비스](../../../../docs/framework/configure-apps/file-schema/wcf/service.md)\<의 자식)을 사용 하 여 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="10620-113">This is done using the `add` element, child of [\<baseAddresses>](../../../../docs/framework/configure-apps/file-schema/wcf/baseaddresses.md), child of [\<host>](../../../../docs/framework/configure-apps/file-schema/wcf/host.md), child of [\<service>](../../../../docs/framework/configure-apps/file-schema/wcf/service.md) as demonstrated in the following sample configuration.</span></span>  
  
```xml  
<service   
    name="Microsoft.ServiceModel.Samples.CalculatorService"  
    behaviorConfiguration="CalculatorServiceBehavior">  
  <host>  
    <baseAddresses>  
      <add baseAddress="http://localhost:8000/ServiceModelSamples/service"/>  
    </baseAddresses>  
  </host>  
  ...  
</service>  
```  
  
 <span data-ttu-id="10620-114">샘플을 실행하면 작업 요청 및 응답이 서비스와 클라이언트 콘솔 창 모두에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="10620-114">When you run the sample, the operation requests and responses are displayed in both the service and client console windows.</span></span> <span data-ttu-id="10620-115">서비스와 클라이언트를 종료하려면 각 콘솔 창에서 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="10620-115">Press ENTER in each console window to shut down the service and client.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="10620-116">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="10620-116">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="10620-117">[Windows Communication Foundation 샘플에 대 한 일회성 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)를 수행 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="10620-117">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="10620-118">C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="10620-118">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="10620-119">단일 컴퓨터 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)의 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="10620-119">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="10620-120">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10620-120">The samples may already be installed on your computer.</span></span> <span data-ttu-id="10620-121">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="10620-121">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="10620-122">이 디렉터리가 없으면 [.NET Framework 4에 대 한 Windows Communication Foundation (wcf) 및 Windows Workflow Foundation (WF) 샘플](https://www.microsoft.com/download/details.aspx?id=21459) 로 이동 하 여 모든 WINDOWS COMMUNICATION FOUNDATION (wcf) 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="10620-122">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="10620-123">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10620-123">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\SelfHost`  
  
## <a name="see-also"></a><span data-ttu-id="10620-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="10620-124">See also</span></span>

- <span data-ttu-id="10620-125">[AppFabric 호스팅 및 지 속성 샘플](https://docs.microsoft.com/previous-versions/appfabric/ff383418(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="10620-125">[AppFabric Hosting and Persistence Samples](https://docs.microsoft.com/previous-versions/appfabric/ff383418(v=azure.10))</span></span>
