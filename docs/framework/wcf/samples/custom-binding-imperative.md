---
title: 사용자 지정 바인딩 명령
ms.date: 03/30/2017
ms.assetid: 6e13bf96-5de0-4476-b646-5f150774418d
ms.openlocfilehash: f7ba5c21b35d556be2c8d0817c37d98ad7d7dfcb
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84594740"
---
# <a name="custom-binding-imperative"></a><span data-ttu-id="a2e55-102">사용자 지정 바인딩 명령</span><span class="sxs-lookup"><span data-stu-id="a2e55-102">Custom Binding Imperative</span></span>
<span data-ttu-id="a2e55-103">이 샘플에서는 구성 파일 또는 WCF (Windows Communication Foundation) 생성 클라이언트를 사용 하지 않고 사용자 지정 바인딩을 정의 하 고 사용 하는 명령적 코드를 작성 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a2e55-103">The sample demonstrates how to write imperative code to define and use custom bindings without using a configuration file or a Windows Communication Foundation (WCF) generated client.</span></span> <span data-ttu-id="a2e55-104">이 샘플에서는 HTTP 전송에서 제공하는 기능과 신뢰할 수 있는 세션 채널을 조합하여 신뢰할 수 있는 HTTP 기반 바인딩을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a2e55-104">This sample combines the features provided by the HTTP transport and the reliable session channel to create a reliable HTTP-based binding.</span></span> <span data-ttu-id="a2e55-105">이 샘플은 계산기 서비스를 구현 하는 [시작](getting-started-sample.md) 을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2e55-105">This sample is based on the [Getting Started](getting-started-sample.md) that implements a calculator service.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a2e55-106">이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2e55-106">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="a2e55-107">클라이언트와 서버에서 모두 두 바인딩 요소(신뢰할 수 있는 세션 및 HTTP)를 포함하는 사용자 지정 바인딩을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a2e55-107">On both the client and the service, a custom binding is created that contains two binding elements (Reliable Session and HTTP):</span></span>  

```csharp
ReliableSessionBindingElement reliableSession = new ReliableSessionBindingElement();  
reliableSession.Ordered = true;  
  
HttpTransportBindingElement httpTransport = new HttpTransportBindingElement();  
httpTransport.AuthenticationScheme = System.Net.AuthenticationSchemes.Anonymous;  
httpTransport.HostNameComparisonMode = HostNameComparisonMode.StrongWildcard;  
  
CustomBinding binding = new CustomBinding(reliableSession, httpTransport);  
```
  
 <span data-ttu-id="a2e55-108">서비스에서는 ServiceHost에 엔드포인트를 추가하여 바인딩을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a2e55-108">On the service, the binding is used by adding an endpoint to the ServiceHost:</span></span>  

```csharp
serviceHost.AddServiceEndpoint(typeof(ICalculator), binding, "");  
```

 <span data-ttu-id="a2e55-109">클라이언트에서는 <xref:System.ServiceModel.ChannelFactory>에서 서비스에 대해 채널을 만들기 위해 바인딩을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a2e55-109">On the client, the binding is used by a <xref:System.ServiceModel.ChannelFactory> to create a channel to the service:</span></span>  

```csharp
EndpointAddress address = new EndpointAddress("http://localhost:8000/servicemodelsamples/service");  
ChannelFactory<ICalculator> channelFactory = new ChannelFactory<ICalculator>(binding, address);  
ICalculator channel = channelFactory.CreateChannel();  
```

 <span data-ttu-id="a2e55-110">그런 다음 이 채널은 서비스와의 상호 작용에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2e55-110">This channel is then used to interact with the service:</span></span>  

```csharp
// Call the Add service operation.  
double value1 = 100.00D;  
double value2 = 15.99D;  
double result = channel.Add(value1, value2);  
Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);  
```

 <span data-ttu-id="a2e55-111">샘플을 실행하면 작업 요청 및 응답이 클라이언트 콘솔 창에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2e55-111">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="a2e55-112">클라이언트를 종료하려면 클라이언트 창에서 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="a2e55-112">Press ENTER in the client window to shut down the client.</span></span>  
  
```console  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="a2e55-113">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="a2e55-113">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="a2e55-114">[Windows Communication Foundation 샘플에 대 한 일회성 설치 절차](one-time-setup-procedure-for-the-wcf-samples.md)를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2e55-114">Be sure you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="a2e55-115">C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](building-the-samples.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="a2e55-115">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="a2e55-116">단일 컴퓨터 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](running-the-samples.md)의 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="a2e55-116">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="a2e55-117">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2e55-117">The samples may already be installed on your machine.</span></span> <span data-ttu-id="a2e55-118">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="a2e55-118">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="a2e55-119">이 디렉터리가 없는 경우 [.NET Framework 4에 대 한 Windows Communication Foundation (wcf) 및 Windows Workflow Foundation (WF) 샘플](https://www.microsoft.com/download/details.aspx?id=21459) 로 이동 하 여 모든 WINDOWS COMMUNICATION FOUNDATION (wcf) 및 샘플을 다운로드 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2e55-119">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="a2e55-120">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2e55-120">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Binding\Custom\Imperative`  
  
## <a name="see-also"></a><span data-ttu-id="a2e55-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a2e55-121">See also</span></span>

- [<span data-ttu-id="a2e55-122">사용자 지정 바인딩 샘플</span><span class="sxs-lookup"><span data-stu-id="a2e55-122">Custom Binding Samples</span></span>](custom-binding.md)
