---
title: 서비스 설명을
ms.date: 03/30/2017
ms.assetid: 7034b5d6-d608-45f3-b57d-ec135f83ff24
ms.openlocfilehash: c0fa389e9c894bcfec49ce7538b512c96f176c23
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96262582"
---
# <a name="service-description"></a><span data-ttu-id="dea07-102">서비스 설명을</span><span class="sxs-lookup"><span data-stu-id="dea07-102">Service Description</span></span>

<span data-ttu-id="dea07-103">Service Description 샘플에서는 런타임에 서비스에서 서비스 설명 정보를 검색하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="dea07-103">The Service Description sample demonstrates how a service can retrieve its service description information at runtime.</span></span> <span data-ttu-id="dea07-104">이 샘플은 서비스에 대 한 설명 정보를 반환 하도록 정의 된 추가 서비스 작업을 사용 하 여 [시작](getting-started-sample.md)을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="dea07-104">The sample is based on the [Getting Started](getting-started-sample.md), with an additional service operation defined to return descriptive information about the service.</span></span> <span data-ttu-id="dea07-105">반환되는 정보는 서비스의 기본 주소 및 엔드포인트를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="dea07-105">The information that is returned lists the base addresses and endpoints for the service.</span></span> <span data-ttu-id="dea07-106">서비스는 <xref:System.ServiceModel.OperationContext>, <xref:System.ServiceModel.ServiceHost> 및 <xref:System.ServiceModel.Description.ServiceDescription> 클래스를 사용하여 이 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="dea07-106">The service provides this information using the <xref:System.ServiceModel.OperationContext>, <xref:System.ServiceModel.ServiceHost>, and <xref:System.ServiceModel.Description.ServiceDescription> classes.</span></span>  
  
 <span data-ttu-id="dea07-107">이 샘플에서 클라이언트는 콘솔 애플리케이션(.exe)이고 서비스는 IIS(인터넷 정보 서비스)를 통해 호스트됩니다.</span><span class="sxs-lookup"><span data-stu-id="dea07-107">In this sample, the client is a console application (.exe) and the service is hosted by Internet Information Services (IIS).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="dea07-108">이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dea07-108">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="dea07-109">이 샘플에는 `IServiceDescriptionCalculator`라는 계산기 계약의 수정된 버전이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dea07-109">This sample has a modified version of the calculator contract called `IServiceDescriptionCalculator`.</span></span> <span data-ttu-id="dea07-110">이 계약에서는 서비스의 기본 주소 및 서비스 엔드포인트를 설명하는 다중 선 문자열을 클라이언트에 반환하는 `GetServiceDescriptionInfo`라는 추가 서비스 작업을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="dea07-110">The contract defines an additional service operation named `GetServiceDescriptionInfo` that returns a multi-line string to the client that describes the base address or addresses and service endpoint or endpoints for the service.</span></span>  
  
```csharp
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface IServiceDescriptionCalculator  
{  
    [OperationContract]  
    int Add(int n1, int n2);  
    [OperationContract]  
    int Subtract(int n1, int n2);  
    [OperationContract]  
    int Multiply(int n1, int n2);  
    [OperationContract]  
    int Divide(int n1, int n2);  
    [OperationContract]  
    string GetServiceDescriptionInfo();  
}  
```  
  
 <span data-ttu-id="dea07-111">`GetServiceDescriptionInfo`의 구현 코드에서는 <xref:System.ServiceModel.Description.ServiceDescription>을 사용하여 서비스 엔드포인트를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="dea07-111">The implementation code for `GetServiceDescriptionInfo` uses the <xref:System.ServiceModel.Description.ServiceDescription> to list the service endpoints.</span></span> <span data-ttu-id="dea07-112">서비스 엔드포인트는 상대 주소를 가질 수 있으므로 먼저 서비스의 기본 주소를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="dea07-112">Because service endpoints can have relative addresses, it first lists the base addresses for the service.</span></span> <span data-ttu-id="dea07-113">이 정보를 모두 가져오기 위해 코드는 <xref:System.ServiceModel.OperationContext.Current%2A>를 사용하여 작업 컨텍스트를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="dea07-113">To get all of this information, the code obtains its operation context using <xref:System.ServiceModel.OperationContext.Current%2A>.</span></span> <span data-ttu-id="dea07-114"><xref:System.ServiceModel.ServiceHost> 및 해당 <xref:System.ServiceModel.Description.ServiceDescription> 개체는 작업 컨텍스트로부터 검색됩니다.</span><span class="sxs-lookup"><span data-stu-id="dea07-114">The <xref:System.ServiceModel.ServiceHost> and its <xref:System.ServiceModel.Description.ServiceDescription> object are retrieved from the operation context.</span></span> <span data-ttu-id="dea07-115">서비스의 기본 엔드포인트를 나열하기 위해 코드는 서비스 호스트의 <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A> 컬렉션에서 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="dea07-115">To list the base endpoints for the service, the code iterates through the service host's <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A> collection.</span></span> <span data-ttu-id="dea07-116">서비스의 서비스 엔드포인트를 나열하기 위해 코드는 서비스 설명의 엔드포인트 컬렉션에서 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="dea07-116">To list the service endpoints for the service, the code iterates through the service description's endpoints collection.</span></span>  
  
```csharp
public string GetServiceDescriptionInfo()  
{  
    string info = "";  
    OperationContext operationContext = OperationContext.Current;  
    ServiceHost host = (ServiceHost)operationContext.Host;  
    ServiceDescription desc = host.Description;  
    // Enumerate the base addresses in the service host.  
    info += "Base addresses:\n";  
    foreach (Uri uri in host.BaseAddresses)  
    {  
        info += "    " + uri + "\n";  
    }  
    // Enumerate the service endpoints in the service description.  
    info += "Service endpoints:\n";  
    foreach (ServiceEndpoint endpoint in desc.Endpoints)  
    {  
        info += "    Address:  " + endpoint.Address + "\n";  
        info += "    Binding:  " + endpoint.Binding.Name + "\n";  
        info += "    Contract: " + endpoint.Contract.Name + "\n";  
    }  
     return info;  
}  
```  
  
 <span data-ttu-id="dea07-117">샘플을 실행하면 계산기 작업 및 `GetServiceDescriptionInfo` 작업에서 반환되는 서비스 정보가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="dea07-117">When you run the sample, you see the calculator operations and then the service information returned by the `GetServiceDescriptionInfo` operation.</span></span> <span data-ttu-id="dea07-118">클라이언트를 종료하려면 클라이언트 창에서 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="dea07-118">Press ENTER in the client window to shut down the client.</span></span>  
  
```console  
Add(15,3) = 18  
Subtract(145,76) = 69  
Multiply(9,81) = 729  
Divide(22,7) = 3  
GetServiceDescriptionInfo  
Base addresses:  
    http://<machine-name>/ServiceModelSamples/service.svc  
    https://<machine-name>/ServiceModelSamples/service.svc  
Service endpoints:  
    Address:  http://<machine-name>/ServiceModelSamples/service.svc  
    Binding:  WSHttpBinding  
    Contract: IServiceDescriptionCalculator  
    Address:  http://<machine-name>/ServiceModelSamples/service.svc/mex  
    Binding:  MetadataExchangeHttpBinding  
    Contract: IMetadataExchange  
  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="dea07-119">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="dea07-119">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="dea07-120">[Windows Communication Foundation 샘플에 대 한 일회성 설치 절차](one-time-setup-procedure-for-the-wcf-samples.md)를 수행 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="dea07-120">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="dea07-121">C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](building-the-samples.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="dea07-121">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="dea07-122">단일 컴퓨터 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](running-the-samples.md)의 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="dea07-122">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="dea07-123">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dea07-123">The samples may already be installed on your machine.</span></span> <span data-ttu-id="dea07-124">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="dea07-124">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="dea07-125">이 디렉터리가 없는 경우 [.NET Framework 4에 대 한 Windows Communication Foundation (wcf) 및 Windows Workflow Foundation (WF) 샘플](https://www.microsoft.com/download/details.aspx?id=21459) 로 이동 하 여 모든 WINDOWS COMMUNICATION FOUNDATION (wcf) 및 샘플을 다운로드 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 합니다.</span><span class="sxs-lookup"><span data-stu-id="dea07-125">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="dea07-126">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dea07-126">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\ServiceDescription`  
