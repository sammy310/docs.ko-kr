---
title: .NET Remoting에서 WCF로 마이그레이션
ms.date: 03/30/2017
ms.assetid: 16902a42-ef80-40e9-8c4c-90e61ddfdfe5
ms.openlocfilehash: 8dcc019017195fd55231fbea3493d4c53d500cb3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183956"
---
# <a name="migrating-from-net-remoting-to-wcf"></a><span data-ttu-id="05ea2-102">.NET Remoting에서 WCF로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="05ea2-102">Migrating from .NET Remoting to WCF</span></span>
<span data-ttu-id="05ea2-103">이 문서에서는 WCF(Windows Communication Foundation)를 사용하기 위해 .NET Remoting을 사용하는 애플리케이션을 마이그레이션하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-103">This article describes how to migrate an application that uses .NET Remoting to use Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="05ea2-104">이러한 제품 간의 비슷한 개념을 비교한 다음 WCF의 몇 가지 일반적인 Remoting 시나리오를 수행하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-104">It compares similar concepts between these products and then describes how to accomplish several common Remoting scenarios in WCF.</span></span>  
  
 <span data-ttu-id="05ea2-105">.NET Remoting은 이전 버전과의 호환성을 위해서만 지원되는 레거시 제품입니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-105">.NET Remoting is a legacy product that is supported only for backward compatibility.</span></span> <span data-ttu-id="05ea2-106">클라이언트와 서버 간에 개별 신뢰 수준을 유지할 수 없으므로 복합 신뢰 환경에서는 안전하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-106">It is not secure across mixed-trust environments because it cannot maintain the separate trust levels between client and server.</span></span> <span data-ttu-id="05ea2-107">예를 들어 .NET Remoting 엔드포인트를 인터넷 또는 신뢰할 수 없는 클라이언트에 노출하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-107">For example, you should never expose a .NET Remoting endpoint to the Internet or to untrusted clients.</span></span> <span data-ttu-id="05ea2-108">기존 Remoting 애플리케이션을 더욱 안전한 최신 기술로 마이그레이션하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-108">We recommend existing Remoting applications be migrated to newer and more secure technologies.</span></span> <span data-ttu-id="05ea2-109">애플리케이션의 디자인에서 HTTP만 사용하고 RESTful인 경우 ASP.NET Web API를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-109">If the application’s design uses only HTTP and is RESTful, we recommend ASP.NET Web API.</span></span> <span data-ttu-id="05ea2-110">자세한 내용은 ASP.NET Web API를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="05ea2-110">For more information, see ASP.NET Web API.</span></span> <span data-ttu-id="05ea2-111">애플리케이션이 SOAP을 기반으로 하거나 TCP와 같이 Http가 아닌 프로토콜을 필요로 하는 경우 WCF를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-111">If the application is based on SOAP or requires non-Http protocols such as TCP, we recommend WCF.</span></span>  

## <a name="comparing-net-remoting-to-wcf"></a><span data-ttu-id="05ea2-112">.NET Remoting과 WCF 비교</span><span class="sxs-lookup"><span data-stu-id="05ea2-112">Comparing .NET Remoting to WCF</span></span>  
 <span data-ttu-id="05ea2-113">이 섹션에서는 .NET Remoting의 기본 빌딩 블록을 해당 WCF의 빌딩 블록과 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-113">This section compares the basic building blocks of .NET Remoting with their WCF equivalents.</span></span> <span data-ttu-id="05ea2-114">나중에 이러한 구성 요소를 사용하여 WCF에서 몇 가지 일반적인 클라이언트 서버 시나리오를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-114">We will use these building blocks later to create some common client-server scenarios in WCF.</span></span> <span data-ttu-id="05ea2-115">다음 차트는 .NET Remoting과 WCF 간의 주요 유사점과 차이점을 요약합니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-115">The following chart summarizes the main similarities and differences between .NET Remoting and WCF.</span></span>  
  
||<span data-ttu-id="05ea2-116">.NET Remoting</span><span class="sxs-lookup"><span data-stu-id="05ea2-116">.NET Remoting</span></span>|<span data-ttu-id="05ea2-117">WCF</span><span class="sxs-lookup"><span data-stu-id="05ea2-117">WCF</span></span>|  
|-|-------------------|---------|  
|<span data-ttu-id="05ea2-118">서버 유형</span><span class="sxs-lookup"><span data-stu-id="05ea2-118">Server type</span></span>|<span data-ttu-id="05ea2-119">Subclass MarshalByRefObject</span><span class="sxs-lookup"><span data-stu-id="05ea2-119">Subclass MarshalByRefObject</span></span>|<span data-ttu-id="05ea2-120">[ServiceContract] 특성으로 표시</span><span class="sxs-lookup"><span data-stu-id="05ea2-120">Mark with [ServiceContract] attribute</span></span>|  
|<span data-ttu-id="05ea2-121">서비스 작업</span><span class="sxs-lookup"><span data-stu-id="05ea2-121">Service operations</span></span>|<span data-ttu-id="05ea2-122">서버 유형의 공용 메서드</span><span class="sxs-lookup"><span data-stu-id="05ea2-122">Public methods on server type</span></span>|<span data-ttu-id="05ea2-123">[OperationContract] 특성으로 표시</span><span class="sxs-lookup"><span data-stu-id="05ea2-123">Mark with [OperationContract] attribute</span></span>|  
|<span data-ttu-id="05ea2-124">직렬화</span><span class="sxs-lookup"><span data-stu-id="05ea2-124">Serialization</span></span>|<span data-ttu-id="05ea2-125">ISerializable 또는 [Serializable]</span><span class="sxs-lookup"><span data-stu-id="05ea2-125">ISerializable or [Serializable]</span></span>|<span data-ttu-id="05ea2-126">DataContractSerializer 또는 XmlSerializer</span><span class="sxs-lookup"><span data-stu-id="05ea2-126">DataContractSerializer or XmlSerializer</span></span>|  
|<span data-ttu-id="05ea2-127">전달된 개체</span><span class="sxs-lookup"><span data-stu-id="05ea2-127">Objects passed</span></span>|<span data-ttu-id="05ea2-128">값 방식 또는 참조 방식</span><span class="sxs-lookup"><span data-stu-id="05ea2-128">By-value or by-reference</span></span>|<span data-ttu-id="05ea2-129">값 방식만 해당</span><span class="sxs-lookup"><span data-stu-id="05ea2-129">By-value only</span></span>|  
|<span data-ttu-id="05ea2-130">오류/예외</span><span class="sxs-lookup"><span data-stu-id="05ea2-130">Errors/exceptions</span></span>|<span data-ttu-id="05ea2-131">모든 직렬화 가능 예외</span><span class="sxs-lookup"><span data-stu-id="05ea2-131">Any serializable exception</span></span>|<span data-ttu-id="05ea2-132">오류\<계약 t세부 사항></span><span class="sxs-lookup"><span data-stu-id="05ea2-132">FaultContract\<TDetail></span></span>|  
|<span data-ttu-id="05ea2-133">클라이언트 프록시 개체</span><span class="sxs-lookup"><span data-stu-id="05ea2-133">Client proxy objects</span></span>|<span data-ttu-id="05ea2-134">강력한 형식의 투명 프록시는 MarshalByRefObjects에서 자동으로 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-134">Strongly typed transparent proxies are created automatically from MarshalByRefObjects</span></span>|<span data-ttu-id="05ea2-135">강력하게 입력된 프록시는 ChannelFactory\<TChannel> 사용하여 주문형으로 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-135">Strongly typed proxies are generated on-demand using ChannelFactory\<TChannel></span></span>|  
|<span data-ttu-id="05ea2-136">필요한 플랫폼</span><span class="sxs-lookup"><span data-stu-id="05ea2-136">Platform required</span></span>|<span data-ttu-id="05ea2-137">클라이언트와 서버 모두 Microsoft OS 및 .NET를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-137">Both client and server must use Microsoft OS and .NET</span></span>|<span data-ttu-id="05ea2-138">플랫폼 간</span><span class="sxs-lookup"><span data-stu-id="05ea2-138">Cross-platform</span></span>|  
|<span data-ttu-id="05ea2-139">메시지 형식</span><span class="sxs-lookup"><span data-stu-id="05ea2-139">Message format</span></span>|<span data-ttu-id="05ea2-140">프라이빗</span><span class="sxs-lookup"><span data-stu-id="05ea2-140">Private</span></span>|<span data-ttu-id="05ea2-141">산업 표준(SOAP, WS-\* 등)</span><span class="sxs-lookup"><span data-stu-id="05ea2-141">Industry standards (SOAP, WS-\*, etc.)</span></span>|  
  
### <a name="server-implementation-comparison"></a><span data-ttu-id="05ea2-142">서버 구현 비교</span><span class="sxs-lookup"><span data-stu-id="05ea2-142">Server Implementation Comparison</span></span>  
  
#### <a name="creating-a-server-in-net-remoting"></a><span data-ttu-id="05ea2-143">.NET Remoting에서 서버 만들기</span><span class="sxs-lookup"><span data-stu-id="05ea2-143">Creating a Server in .NET Remoting</span></span>  
 <span data-ttu-id="05ea2-144">.NET Remoting 서버 유형은 MarshalByRefObject에서 파생되어야 하며 클라이언트가 호출할 수 있는 다음과 같은 메서드를 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-144">.NET Remoting server types must derive from MarshalByRefObject and define methods the client can call, like the following:</span></span>  
  
```csharp
public class RemotingServer : MarshalByRefObject  
{  
    public Customer GetCustomer(int customerId) { … }  
}  
```  
  
 <span data-ttu-id="05ea2-145">이 서버 유형의 공용 메서드가 클라이언트에서 사용할 수 있는 공용 계약이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-145">The public methods of this server type become the public contract available to clients.</span></span>  <span data-ttu-id="05ea2-146">서버의 공용 인터페이스와 구현은 분리되지 않습니다. 하나의 형식이 둘 다를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-146">There is no separation between the server’s public interface and its implementation – one type handles both.</span></span>  
  
 <span data-ttu-id="05ea2-147">서버 유형을 정의한 후 다음 예제와 같이 클라이언트에서 사용 가능하게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-147">Once the server type has been defined, it can be made available to clients, like in the following example:</span></span>  
  
```csharp
TcpChannel channel = new TcpChannel(8080);  
ChannelServices.RegisterChannel(channel, ensureSecurity : true);  
RemotingConfiguration.RegisterWellKnownServiceType(  
    typeof(RemotingServer),
    "RemotingServer",
    WellKnownObjectMode.Singleton);  
Console.WriteLine("RemotingServer is running.  Press ENTER to terminate...");  
Console.ReadLine();  
```  
  
 <span data-ttu-id="05ea2-148">Remoting 유형을 서버로 사용 가능하게 하는 방법은 구성 파일 사용을 비롯하여 여러 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-148">There are many ways to make the Remoting type available as a server, including using configuration files.</span></span> <span data-ttu-id="05ea2-149">이것은 한 가지 예일 뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-149">This is just one example.</span></span>  
  
#### <a name="creating-a-server-in-wcf"></a><span data-ttu-id="05ea2-150">WCF에서 서버 만들기</span><span class="sxs-lookup"><span data-stu-id="05ea2-150">Creating a Server in WCF</span></span>  
 <span data-ttu-id="05ea2-151">WCF의 해당 단계에서는 두 가지 유형, 즉 공용 "서비스 계약"과 구체적인 구현을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-151">The equivalent step in WCF involves creating two types -- the public "service contract" and the concrete implementation.</span></span> <span data-ttu-id="05ea2-152">첫 번째는 [ServiceContract]로 표시된 인터페이스로 선언됩니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-152">The first is declared as an interface marked with [ServiceContract].</span></span> <span data-ttu-id="05ea2-153">클라이언트에 사용할 수 있는 메서드는 [OperationContract]로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-153">Methods available to clients are marked with [OperationContract]:</span></span>  
  
```csharp
[ServiceContract]  
public interface IWCFServer  
{  
    [OperationContract]  
    Customer GetCustomer(int customerId);  
}  
```  
  
 <span data-ttu-id="05ea2-154">서버 구현은 다음 예제와 같이 별도의 구체적인 클래스에서 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-154">The server’s implementation is defined in a separate concrete class, like in the following example:</span></span>  
  
```csharp
public class WCFServer : IWCFServer  
{  
    public Customer GetCustomer(int customerId) { … }  
}  
```  
  
 <span data-ttu-id="05ea2-155">이러한 형식이 정의되고 나면 다음 예제와 같이 클라이언트에서 WCF 서버를 사용 가능하게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-155">Once these types have been defined, the WCF server can be made available to clients, like in the following example:</span></span>  
  
```csharp
NetTcpBinding binding = new NetTcpBinding();  
Uri baseAddress = new Uri("net.tcp://localhost:8000/wcfserver");  
  
using (ServiceHost serviceHost = new ServiceHost(typeof(WCFServer), baseAddress))  
{  
    serviceHost.AddServiceEndpoint(typeof(IWCFServer), binding, baseAddress);  
    serviceHost.Open();  
  
    Console.WriteLine($"The WCF server is ready at {baseAddress}.");
    Console.WriteLine("Press <ENTER> to terminate service...");  
    Console.WriteLine();  
    Console.ReadLine();  
}  
```  
  
> [!NOTE]
> <span data-ttu-id="05ea2-156">최대한 비슷하게 유지하기 위해 두 예제에서 모두 TCP가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-156">TCP is used in both examples to keep them as similar as possible.</span></span> <span data-ttu-id="05ea2-157">HTTP를 사용하는 예제를 보려면 이 항목의 뒷부분에 있는 시나리오 연습을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="05ea2-157">Refer to the scenario walk-throughs later in this topic for examples using HTTP.</span></span>  
  
 <span data-ttu-id="05ea2-158">WCF 서비스를 구성하고 호스트하는 방법에는 여러 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-158">There are many ways to configure and to host WCF services.</span></span> <span data-ttu-id="05ea2-159">다음은 "자체 호스트"라는 한 가지 예제에 불과합니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-159">This is just one example, known as "self-hosted".</span></span> <span data-ttu-id="05ea2-160">자세한 내용은 아래 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="05ea2-160">For more information, see the following topics:</span></span>  
  
- [<span data-ttu-id="05ea2-161">방법: 서비스 계약 정의</span><span class="sxs-lookup"><span data-stu-id="05ea2-161">How to: Define a Service Contract</span></span>](how-to-define-a-wcf-service-contract.md)  
  
- [<span data-ttu-id="05ea2-162">구성 파일을 사용하여 서비스 구성</span><span class="sxs-lookup"><span data-stu-id="05ea2-162">Configuring Services Using Configuration Files</span></span>](configuring-services-using-configuration-files.md)  
  
- [<span data-ttu-id="05ea2-163">서비스 호스팅</span><span class="sxs-lookup"><span data-stu-id="05ea2-163">Hosting Services</span></span>](hosting-services.md)  
  
### <a name="client-implementation-comparison"></a><span data-ttu-id="05ea2-164">클라이언트 구현 비교</span><span class="sxs-lookup"><span data-stu-id="05ea2-164">Client Implementation Comparison</span></span>  
  
#### <a name="creating-a-client-in-net-remoting"></a><span data-ttu-id="05ea2-165">.NET Remoting에서 클라이언트 만들기</span><span class="sxs-lookup"><span data-stu-id="05ea2-165">Creating a Client in .NET Remoting</span></span>  
 <span data-ttu-id="05ea2-166">.NET Remoting 서버 개체가 사용 가능하게 되면 다음 예제와 같이 클라이언트에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-166">Once a .NET Remoting server object has been made available, it can be consumed by clients, like in the following example:</span></span>  
  
```csharp
TcpChannel channel = new TcpChannel();  
ChannelServices.RegisterChannel(channel, ensureSecurity : true);  
RemotingServer server = (RemotingServer)Activator.GetObject(  
                            typeof(RemotingServer),
                            "tcp://localhost:8080/RemotingServer");  
  
RemotingCustomer customer = server.GetCustomer(42);  
Console.WriteLine($"Customer {customer.FirstName} {customer.LastName} received.");
```  
  
 <span data-ttu-id="05ea2-167">Activator.GetObject()에서 반환된 RemotingServer 인스턴스는 "투명 프록시"라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-167">The RemotingServer instance returned from Activator.GetObject() is known as a "transparent proxy."</span></span> <span data-ttu-id="05ea2-168">클라이언트에 RemotingServer 형식의 공용 API를 구현하지만, 모든 메서드에서 다른 프로세스나 컴퓨터에서 실행 중인 서버 개체를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-168">It implements the public API for the RemotingServer type on the client, but all the methods call the server object running in a different process or machine.</span></span>  
  
#### <a name="creating-a-client-in-wcf"></a><span data-ttu-id="05ea2-169">WCF에서 클라이언트 만들기</span><span class="sxs-lookup"><span data-stu-id="05ea2-169">Creating a Client in WCF</span></span>  
 <span data-ttu-id="05ea2-170">WCF의 해당 단계에서는 채널 팩터리를 사용하여 명시적으로 프록시를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-170">The equivalent step in WCF involves using a channel factory to create the proxy explicitly.</span></span> <span data-ttu-id="05ea2-171">Remoting과 마찬가지로 프록시 개체는 다음 예제와 같이 서버에서 작업을 호출하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-171">Like Remoting, the proxy object can be used to invoke operations on the server, like in the following example:</span></span>  
  
```csharp
NetTcpBinding binding = new NetTcpBinding();  
String url = "net.tcp://localhost:8000/wcfserver";  
EndpointAddress address = new EndpointAddress(url);  
ChannelFactory<IWCFServer> channelFactory =
    new ChannelFactory<IWCFServer>(binding, address);  
IWCFServer server = channelFactory.CreateChannel();  
  
Customer customer = server.GetCustomer(42);  
Console.WriteLine($"  Customer {customer.FirstName} {customer.LastName} received.");
```  
  
 <span data-ttu-id="05ea2-172">이 예제는 Remoting 예제와 가장 비슷하므로 채널 수준의 프로그래밍을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-172">This example shows programming at the channel level because it is most similar to the Remoting example.</span></span> <span data-ttu-id="05ea2-173">클라이언트 프로그래밍을 단순화하기 위해 코드를 생성하는 Visual Studio의 **서비스 참조 추가** 접근 방식도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-173">Also available is the **Add Service Reference** approach in Visual Studio that generates code to simplify client programming.</span></span> <span data-ttu-id="05ea2-174">자세한 내용은 아래 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="05ea2-174">For more information, see the following topics:</span></span>  
  
- [<span data-ttu-id="05ea2-175">클라이언트 채널 수준 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="05ea2-175">Client Channel-Level Programming</span></span>](./extending/client-channel-level-programming.md)  
  
- [<span data-ttu-id="05ea2-176">방법: 서비스 참조 추가, 업데이트 또는 제거</span><span class="sxs-lookup"><span data-stu-id="05ea2-176">How to: Add, Update, or Remove a Service Reference</span></span>](/visualstudio/data-tools/how-to-add-update-or-remove-a-wcf-data-service-reference)  
  
### <a name="serialization-usage"></a><span data-ttu-id="05ea2-177">직렬화 사용</span><span class="sxs-lookup"><span data-stu-id="05ea2-177">Serialization Usage</span></span>  
 <span data-ttu-id="05ea2-178">.NET Remoting과 WCF 둘 다 직렬화를 사용하여 클라이언트와 서버 간에 개체를 전송하지만 다음과 같은 중요한 차이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-178">Both .NET Remoting and WCF use serialization to send objects between client and server, but they differ in these important ways:</span></span>  
  
1. <span data-ttu-id="05ea2-179">서로 다른 직렬 변환기 및 규칙을 사용하여 직렬화할 사항을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-179">They use different serializers and conventions to indicate what to serialize.</span></span>  
  
2. <span data-ttu-id="05ea2-180">.NET Remoting에서는 “참조 방식" 직렬화를 지원하여 한 계층에 있는 메서드나 속성 액세스에서 보안 경계 건너편 다른 계층에 있는 코드를 실행할 수 있게 합니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-180">.NET Remoting supports "by reference" serialization that allows method or property access on one tier to execute code on the other tier, which is across security boundaries.</span></span> <span data-ttu-id="05ea2-181">이 기능을 사용하면 보안 취약성이 노출되며, 따라서 신뢰할 수 없는 클라이언트에 Remoting 엔드포인트를 절대 노출해서는 안 되는 주요 이유 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-181">This capability exposes security vulnerabilities and is one of the main reasons why Remoting endpoints should never be exposed to untrusted clients.</span></span>  
  
3. <span data-ttu-id="05ea2-182">Remoting에서 사용하는 직렬화는 옵트아웃(직렬화하지 않을 사항을 명시적으로 제외)이고 WCF 직렬화는 옵트인(직렬화할 멤버를 명시적으로 표시)입니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-182">Serialization used by Remoting is opt-out (explicitly exclude what not to serialize) and WCF serialization is opt-in (explicitly mark which members to serialize).</span></span>  
  
#### <a name="serialization-in-net-remoting"></a><span data-ttu-id="05ea2-183">.NET Remoting의 직렬화</span><span class="sxs-lookup"><span data-stu-id="05ea2-183">Serialization in .NET Remoting</span></span>  
 <span data-ttu-id="05ea2-184">.NET Remoting에서는 클라이언트와 서버 간에 개체를 직렬화하고 역직렬화하는 다음 두 가지 방법을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-184">.NET Remoting supports two ways to serialize and deserialize objects between the client and server:</span></span>  
  
- <span data-ttu-id="05ea2-185">*값별* – 개체의 값은 계층 경계를 넘어 직렬화되고 해당 개체의 새 인스턴스는 다른 계층에서 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-185">*By value* – the values of the object are serialized across tier boundaries, and a new instance of that object is created on the other tier.</span></span> <span data-ttu-id="05ea2-186">새 인스턴스의 속성 또는 메소드를 호출하면 로컬에서만 실행되며 원래 개체나 계층에는 영향을 미치지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-186">Any calls to methods or properties of that new instance execute only locally and do not affect the original object or tier.</span></span>  
  
- <span data-ttu-id="05ea2-187">*참조로* – 특수 "개체 참조"는 계층 경계를 넘어 직렬화됩니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-187">*By reference* – a special "object reference" is serialized across tier boundaries.</span></span> <span data-ttu-id="05ea2-188">한 계층에서 해당 개체의 메서드나 속성과 상호 작용하는 경우 원래 계층의 원본 개체와 다시 통신합니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-188">When one tier interacts with methods or properties of that object, it communicates back to the original object on the original tier.</span></span> <span data-ttu-id="05ea2-189">참조 방식 개체는 양방향, 즉 서버에서 클라이언트 또는 클라이언트에서 서버로 전달될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-189">By-reference objects can flow in either direction – server to client, or client to server.</span></span>  
  
 <span data-ttu-id="05ea2-190">Remoting에서 값 방식 유형은 [Serializable] 특성으로 표시되거나 다음 예제와 같이 ISerializable을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-190">By-value types in Remoting are marked with the [Serializable] attribute or implement ISerializable, like in the following example:</span></span>  
  
```csharp
[Serializable]  
public class RemotingCustomer  
{  
    public string FirstName { get; set; }  
    public string LastName { get; set; }  
    public int CustomerId { get; set; }  
}  
```  
  
 <span data-ttu-id="05ea2-191">참조 방식 유형은 다음 예제와 같이 MarshalByRefObject 클래스에서 파생됩니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-191">By-reference types derive from the MarshalByRefObject class, like in the following example:</span></span>  
  
```csharp
public class RemotingCustomerReference : MarshalByRefObject  
{  
    public string FirstName { get; set; }  
    public string LastName { get; set; }  
    public int CustomerId { get; set; }  
}  
```  
  
 <span data-ttu-id="05ea2-192">Remoting의 참조 방식 개체의 의미를 이해하는 것이 매우 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-192">It is extremely important to understand the implications of Remoting’s by-reference objects.</span></span> <span data-ttu-id="05ea2-193">두 계층(클라이언트 또는 서버) 중 하나에서 다른 계층에 참조 방식 개체를 전송하는 경우, 개체를 소유하는 계층에서 모든 메서드 호출이 다시 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-193">If either tier (client or server) sends a by-reference object to the other tier, all method calls execute back on the tier owning the object.</span></span> <span data-ttu-id="05ea2-194">예를 들어 서버에서 반환한 참조 방식 개체에서 메서드를 호출하는 클라이언트가 서버에서 코드를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-194">For example, a client calling methods on a by-reference object returned by the server will execute code on the server.</span></span> <span data-ttu-id="05ea2-195">마찬가지로, 클라이언트에서 제공한 참조 방식 개체에서 메서드를 호출하는 서버는 다시 클라이언트에서 코드를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-195">Similarly, a server calling methods on a by-reference object provided by the client will execute code back on the client.</span></span> <span data-ttu-id="05ea2-196">따라서 .NET Remoting은 완전히 신뢰할 수 있는 환경에서만 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-196">For this reason, the use of .NET Remoting is recommended only within fully-trusted environments.</span></span> <span data-ttu-id="05ea2-197">신뢰할 수 없는 클라이언트에 공용 .NET Remoting 엔드포인트를 노출하면 Remoting 서버가 공격에 취약하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-197">Exposing a public .NET Remoting endpoint to untrusted clients will make a Remoting server vulnerable to attack.</span></span>  
  
#### <a name="serialization-in-wcf"></a><span data-ttu-id="05ea2-198">WCF의 직렬화</span><span class="sxs-lookup"><span data-stu-id="05ea2-198">Serialization in WCF</span></span>  
 <span data-ttu-id="05ea2-199">WCF에서는 값 방식 직렬화만 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-199">WCF supports only by-value serialization.</span></span> <span data-ttu-id="05ea2-200">클라이언트와 서버 간에 교환할 형식을 정의하는 가장 일반적인 방법은 다음 예제와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-200">The most common way to define a type to exchange between client and server is like in the following example:</span></span>  
  
```csharp
[DataContract]  
public class WCFCustomer  
{  
    [DataMember]  
    public string FirstName { get; set; }  
  
    [DataMember]  
    public string LastName { get; set; }  
  
    [DataMember]  
    public int CustomerId { get; set; }  
}  
```  
  
 <span data-ttu-id="05ea2-201">[DataContract] 특성에서는 클라이언트와 서버 간에 직렬화 및 역직렬화할 수 있는 형식으로 이 형식을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-201">The [DataContract] attribute identifies this type as one that can be serialized and deserialized between client and server.</span></span> <span data-ttu-id="05ea2-202">[DataMember] 특성을 통해서는 직렬화할 개별 속성 또는 필드를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-202">The [DataMember] attribute identifies the individual properties or fields to serialize.</span></span>  
  
 <span data-ttu-id="05ea2-203">WCF는 계층 전체에 개체를 전송할 때 값만 직렬화하고 다른 계층에 새로운 개체 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-203">When WCF sends an object across tiers, it serializes only the values and creates a new instance of the object on the other tier.</span></span> <span data-ttu-id="05ea2-204">개체 값과의 상호 작용은 로컬에서만 발생합니다. .NET Remoting 참조 방식 개체와는 달리 다른 계층과 통신하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-204">Any interactions with the values of the object occur only locally – they do not communicate with the other tier the way .NET Remoting by-reference objects do.</span></span> <span data-ttu-id="05ea2-205">자세한 내용은 [Serialization 및 Deserialization](./feature-details/serialization-and-deserialization.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-205">For more information, see [Serialization and Deserialization](./feature-details/serialization-and-deserialization.md).</span></span>  
  
### <a name="exception-handling-capabilities"></a><span data-ttu-id="05ea2-206">예외 처리 기능</span><span class="sxs-lookup"><span data-stu-id="05ea2-206">Exception Handling Capabilities</span></span>  
  
#### <a name="exceptions-in-net-remoting"></a><span data-ttu-id="05ea2-207">.NET Remoting의 예외</span><span class="sxs-lookup"><span data-stu-id="05ea2-207">Exceptions in .NET Remoting</span></span>  
 <span data-ttu-id="05ea2-208">Remoting 서버에서 발생한 예외는 직렬화되어 클라이언트에 전송되고, 다른 예외와 마찬가지로 클라이언트에서 로컬로 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-208">Exceptions thrown by a Remoting server are serialized, sent to the client, and thrown locally on the client like any other exception.</span></span> <span data-ttu-id="05ea2-209">사용자 지정 예외는 Exception 유형을 하위 클래스로 생성하고 [Serializable]로 표시하여 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-209">Custom exceptions can be created by sub-classing the Exception type and marking it with [Serializable].</span></span>   <span data-ttu-id="05ea2-210">대부분의 프레임워크 예외는 이미 이 방식으로 표시되므로, 대부분 서버에서 발생하여, 직렬화되고 클라이언트에서 다시 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-210">Most framework exceptions are already marked in this way, allowing most to be thrown by the server, serialized, and re-thrown on the client.</span></span> <span data-ttu-id="05ea2-211">이 디자인은 개발 중에는 편리하지만 서버 측 정보가 클라이언트에 실수로 공개될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-211">Though this design is convenient during development, server-side information can inadvertently be disclosed to the client.</span></span> <span data-ttu-id="05ea2-212">이것이 완전히 신뢰할 수 있는 환경에서만 Remoting을 사용해야 하는 많은 이유 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-212">This is one of many reasons Remoting should be used only in fully-trusted environments.</span></span>  
  
#### <a name="exceptions-and-faults-in-wcf"></a><span data-ttu-id="05ea2-213">WCF의 예외 및 결함</span><span class="sxs-lookup"><span data-stu-id="05ea2-213">Exceptions and Faults in WCF</span></span>  
 <span data-ttu-id="05ea2-214">임의의 예외 형식을 서버에서 반환하면 의도하지 않게 정보가 공개될 수 있으므로 WCF에서는 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-214">WCF does not allow arbitrary exception types to be returned from the server to the client because it could lead to inadvertent information disclosure.</span></span> <span data-ttu-id="05ea2-215">서비스 작업에서 예기치 않은 예외가 발생하면 클라이언트에서 범용 FaultException이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-215">If a service operation throws an unexpected exception, it causes a general purpose FaultException to be thrown on the client.</span></span> <span data-ttu-id="05ea2-216">이 예외는 문제점이 발생한 이유 또는 위치에 관한 정보를 포함하지 않습니다. 일부 애플리케이션에서는 이것만으로도 충분합니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-216">This exception does not carry any information why or where the problem occurred, and for some applications this is sufficient.</span></span> <span data-ttu-id="05ea2-217">클라이언트에 자세한 오류 정보를 전달해야 하는 애플리케이션에서는 오류 계약을 정의하여 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-217">Applications that need to communicate richer error information to the client do this by defining a fault contract.</span></span>  
  
 <span data-ttu-id="05ea2-218">이 작업을 수행하려면 먼저 오류 정보를 포함할 [DataContract] 형식을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-218">To do this, first create a [DataContract] type to carry the fault information.</span></span>  
  
```csharp
[DataContract]  
public class CustomerServiceFault  
{  
    [DataMember]  
    public string ErrorMessage { get; set; }  
  
    [DataMember]  
    public int CustomerId {get;set;}  
}  
```  
  
 <span data-ttu-id="05ea2-219">각 서비스 작업에 사용할 오류 계약을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-219">Specify the fault contract to use for each service operation.</span></span>  
  
```csharp
[ServiceContract]  
public interface IWCFServer  
{  
    [OperationContract]  
    [FaultContract(typeof(CustomerServiceFault))]  
    Customer GetCustomer(int customerId);  
}  
```  
  
 <span data-ttu-id="05ea2-220">서버에서 FaultException을 발생시켜 오류 상태를 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-220">The server reports error conditions by throwing a FaultException.</span></span>  
  
```csharp
throw new FaultException<CustomerServiceFault>(  
    new CustomerServiceFault() {
        CustomerId = customerId,
        ErrorMessage = "Illegal customer Id"
    });  
```  
  
 <span data-ttu-id="05ea2-221">클라이언트에서 서버에 요청할 때마다 결함을 일반 예외로 catch할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-221">And whenever the client makes a request to the server, it can catch faults as normal exceptions.</span></span>  
  
```csharp
try  
{  
    Customer customer = server.GetCustomer(-1);  
}  
catch (FaultException<CustomerServiceFault> fault)  
{  
    Console.WriteLine($"Fault received: {fault.Detail.ErrorMessage}");
}  
```  
  
 <span data-ttu-id="05ea2-222">오류 계약에 대한 자세한 내용은 <xref:System.ServiceModel.FaultException>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="05ea2-222">For more information about fault contracts, see <xref:System.ServiceModel.FaultException>.</span></span>  
  
### <a name="security-considerations"></a><span data-ttu-id="05ea2-223">보안 고려사항</span><span class="sxs-lookup"><span data-stu-id="05ea2-223">Security Considerations</span></span>  
  
#### <a name="security-in-net-remoting"></a><span data-ttu-id="05ea2-224">.NET Remoting의 보안</span><span class="sxs-lookup"><span data-stu-id="05ea2-224">Security in .NET Remoting</span></span>  
 <span data-ttu-id="05ea2-225">일부.NET Remoting 채널에서는 채널 계층의 인증 및 암호화(IPC 및 TCP)와 같은 보안 기능을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-225">Some .NET Remoting channels support security features such as authentication and encryption at the channel layer (IPC and TCP).</span></span> <span data-ttu-id="05ea2-226">HTTP 채널은 IIS(인터넷 정보 서비스)를 사용하여 인증과 암호화를 모두 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-226">The HTTP channel relies on Internet Information Services (IIS) for both authentication and encryption.</span></span> <span data-ttu-id="05ea2-227">이와 같은 지원이 있어도, 보안되지 않은 통신 프로토콜에 대해 .NET Remoting을 고려하고 완전히 신뢰할 수 있는 환경에서만 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-227">Despite this support, you should consider .NET Remoting an unsecure communication protocol and use it only within fully-trusted environments.</span></span> <span data-ttu-id="05ea2-228">공용 Remoting 엔드포인트를 인터넷이나 신뢰할 수 없는 클라이언트에 노출하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="05ea2-228">Never expose a public Remoting endpoint to the Internet or untrusted clients.</span></span>  
  
#### <a name="security-in-wcf"></a><span data-ttu-id="05ea2-229">WCF에서 보안</span><span class="sxs-lookup"><span data-stu-id="05ea2-229">Security in WCF</span></span>  
 <span data-ttu-id="05ea2-230">WCF는.NET Remoting에서 발견된 유형의 취약성을 해결하기 위해 보안을 염두에 두고 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-230">WCF was designed with security in mind, in part to address the kinds of vulnerabilities found in .NET Remoting.</span></span> <span data-ttu-id="05ea2-231">WCF에서는 전송 및 메시지 수준 모두에서 보안을 제공하고, 인증, 권한 부여, 암호화 등에 대한 다양한 옵션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-231">WCF offers security at both the transport and message level, and offers many options for authentication, authorization, encryption, and so on.</span></span> <span data-ttu-id="05ea2-232">자세한 내용은 아래 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="05ea2-232">For more information, see the following topics:</span></span>  
  
- [<span data-ttu-id="05ea2-233">보안</span><span class="sxs-lookup"><span data-stu-id="05ea2-233">Security</span></span>](./feature-details/security.md)  
  
- [<span data-ttu-id="05ea2-234">WCF 보안 지침</span><span class="sxs-lookup"><span data-stu-id="05ea2-234">WCF Security Guidance</span></span>](./feature-details/security-guidance-and-best-practices.md)  
  
## <a name="migrating-to-wcf"></a><span data-ttu-id="05ea2-235">WCF로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="05ea2-235">Migrating to WCF</span></span>  
  
### <a name="why-migrate-from-remoting-to-wcf"></a><span data-ttu-id="05ea2-236">Remoting에서 WCF로 마이그레이션하는 이유</span><span class="sxs-lookup"><span data-stu-id="05ea2-236">Why Migrate from Remoting to WCF?</span></span>  
  
- <span data-ttu-id="05ea2-237">**.NET Remoting은 레거시 제품입니다.**</span><span class="sxs-lookup"><span data-stu-id="05ea2-237">**.NET Remoting is a legacy product.**</span></span> <span data-ttu-id="05ea2-238">[.NET Remoting에](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/72x4h507%28v=vs.100%29)설명된 대로 레거시 제품으로 간주되며 새 개발에는 권장되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-238">As described in [.NET Remoting](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/72x4h507%28v=vs.100%29), it is considered a legacy product and is not recommended for new development.</span></span> <span data-ttu-id="05ea2-239">신규 및 기존 애플리케이션에는 WCF 또는 ASP.NET Web API를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-239">WCF or ASP.NET Web API are recommended for new and existing applications.</span></span>  
  
- <span data-ttu-id="05ea2-240">**WCF에서는 플랫폼 간 표준을 사용합니다.**</span><span class="sxs-lookup"><span data-stu-id="05ea2-240">**WCF uses cross-platform standards.**</span></span> <span data-ttu-id="05ea2-241">WCF는 플랫폼 간 상호 운용성을 염두에 두고 설계되었으며, 많은 업계 표준(SOAP, WS-Security, WS-Trust 등)을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-241">WCF was designed with cross-platform interoperability in mind and supports many industry standards (SOAP, WS-Security, WS-Trust, etc.).</span></span> <span data-ttu-id="05ea2-242">WCF 서비스는 Windows 이외의 운영 체제에서 실행되는 클라이언트와 상호 운용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-242">A WCF service can interoperate with clients running on operating systems other than Windows.</span></span> <span data-ttu-id="05ea2-243">원격은 주로 Windows 운영 체제에서 .NET Framework를 사용하여 서버와 클라이언트 응용 프로그램이 실행되는 환경을 위해 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-243">Remoting was designed primarily for environments where both the server and client applications run using .NET Framework on a Windows operating system.</span></span>
  
- <span data-ttu-id="05ea2-244">**WCF에는 기본 제공 보안 기능이 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="05ea2-244">**WCF has built-in security.**</span></span> <span data-ttu-id="05ea2-245">WCF는 보안을 염두에 두고 설계되었으며 인증, 전송 수준 보안, 메시지 수준 보안 등에 대한 다양한 옵션을 제공합니다. 원격은 응용 프로그램이 쉽게 상호 운용할 수 있도록 설계되었지만 신뢰할 수 없는 환경에서는 안전하도록 설계되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-245">WCF was designed with security in mind and offers many options for authentication, transport level security, message level security, etc. Remoting was designed to make it easy for applications to interoperate but was not designed to be secure in non-trusted environments.</span></span> <span data-ttu-id="05ea2-246">WCF는 신뢰할 수 있는 환경과 신뢰할 수 없는 환경 모두에서 작동하도록 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-246">WCF was designed to work in both trusted and non-trusted environments.</span></span>  
  
### <a name="migration-recommendations"></a><span data-ttu-id="05ea2-247">마이그레이션 권장 사항</span><span class="sxs-lookup"><span data-stu-id="05ea2-247">Migration Recommendations</span></span>  
 <span data-ttu-id="05ea2-248">다음은 .NET Remoting에서 WCF로 마이그레이션하기 위해 권장되는 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-248">The following are the recommended steps to migrate from .NET Remoting to WCF:</span></span>  
  
- <span data-ttu-id="05ea2-249">**서비스 계약을 만듭니다.**</span><span class="sxs-lookup"><span data-stu-id="05ea2-249">**Create the service contract.**</span></span> <span data-ttu-id="05ea2-250">서비스 인터페이스 형식을 정의한 다음 [ServiceContract] 특성으로 표시합니다. 클라이언트에서 호출할 수 있는 모든 메서드를 [OperationContract]로 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-250">Define your service interface types, and mark them with the [ServiceContract] attribute.Mark all the methods the clients will be allowed to call with [OperationContract].</span></span>  
  
- <span data-ttu-id="05ea2-251">**데이터 계약을 만듭니다.**</span><span class="sxs-lookup"><span data-stu-id="05ea2-251">**Create the data contract.**</span></span> <span data-ttu-id="05ea2-252">서버와 클라이언트 간에 교환할 데이터 형식을 정의한 다음 [DataContract] 특성으로 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-252">Define the data types that will be exchanged between server and client, and mark them with the [DataContract] attribute.</span></span> <span data-ttu-id="05ea2-253">클라이언트에서 사용할 수 있는 모든 필드와 속성을 [DataMember]로 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-253">Mark all the fields and properties the client will be allowed to use with [DataMember].</span></span>  
  
- <span data-ttu-id="05ea2-254">**오류 계약을 만듭니다(선택 사항).**</span><span class="sxs-lookup"><span data-stu-id="05ea2-254">**Create the fault contract (optional).**</span></span> <span data-ttu-id="05ea2-255">오류가 발생하면 서버와 클라이언트 간에 교환될 유형을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-255">Create the types that will be exchanged between server and client when errors are encountered.</span></span> <span data-ttu-id="05ea2-256">이러한 형식을 직렬화할 수 있도록 [DataContract] 및 [DataMember]로 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-256">Mark these types with [DataContract] and [DataMember] to make them serializable.</span></span> <span data-ttu-id="05ea2-257">[OperationContract]로 표시한 모든 서비스 작업도 [FaultContract]로 표시하여 해당 작업에서 반환할 수 있는 오류를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-257">For all service operations you marked with [OperationContract], also mark them with [FaultContract] to indicate which errors they may return.</span></span>  
  
- <span data-ttu-id="05ea2-258">**서비스를 구성하고 호스트합니다.**</span><span class="sxs-lookup"><span data-stu-id="05ea2-258">**Configure and host the service.**</span></span> <span data-ttu-id="05ea2-259">서비스 계약이 생성되면 다음 단계는 엔드포인트에 서비스를 노출하도록 바인딩을 구성하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-259">Once the service contract has been created, the next step is to configure a binding to expose the service at an endpoint.</span></span> <span data-ttu-id="05ea2-260">자세한 내용은 [끝점: 주소, 바인딩 및 계약을](./feature-details/endpoints-addresses-bindings-and-contracts.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="05ea2-260">For more information, see [Endpoints: Addresses, Bindings, and Contracts](./feature-details/endpoints-addresses-bindings-and-contracts.md).</span></span>  
  
 <span data-ttu-id="05ea2-261">Remoting 애플리케이션이 WCF로 마이그레이션된 후에도 .NET Remoting에서 종속성을 제거하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-261">Once a Remoting application has been migrated to WCF, it is still important to remove dependencies on .NET Remoting.</span></span> <span data-ttu-id="05ea2-262">그러면 애플리케이션에서 Remoting의 취약성이 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-262">This ensures that any Remoting vulnerabilities are removed from the application.</span></span> <span data-ttu-id="05ea2-263">이 단계에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-263">These steps include the following:</span></span>  
  
- <span data-ttu-id="05ea2-264">**MarshalByRefObject 사용을 중단합니다.**</span><span class="sxs-lookup"><span data-stu-id="05ea2-264">**Discontinue use of MarshalByRefObject.**</span></span> <span data-ttu-id="05ea2-265">MarshalByRefObject 형식은 Remoting용으로만 제공되며 WCF에서는 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-265">The MarshalByRefObject type exists only for Remoting and is not used by WCF.</span></span> <span data-ttu-id="05ea2-266">MarshalByRefObject를 하위 클래스로 분류하는 모든 애플리케이션 형식은 제거하거나 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-266">Any application types that sub-class MarshalByRefObject should be removed or changed.</span></span>  
  
- <span data-ttu-id="05ea2-267">**[Serializable] 및 ISerializable 사용을 중단합니다.**</span><span class="sxs-lookup"><span data-stu-id="05ea2-267">**Discontinue use of [Serializable] and ISerializable.**</span></span> <span data-ttu-id="05ea2-268">[Serializable] 특성과 ISerializable 인터페이스는 원래 신뢰할 수 있는 환경에서 형식을 직렬화하도록 설계되었으며 Remoting에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-268">The [Serializable] attribute and ISerializable interface were originally designed to serialize types within trusted environments, and they are used by Remoting.</span></span> <span data-ttu-id="05ea2-269">WCF 직렬화를 수행하려면 [DataContract]와 [DataMember]가 표시된 형식이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-269">WCF serialization relies on types being marked with [DataContract] and [DataMember].</span></span> <span data-ttu-id="05ea2-270">애플리케이션에서 사용하는 데이터 형식은 [DataContract]를 사용하고 ISerializable이나 [Serializable]은 사용하지 않도록 수정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-270">Data types used by an application should be modified to use [DataContract] and not to use ISerializable or [Serializable].</span></span>  
  
### <a name="migration-scenarios"></a><span data-ttu-id="05ea2-271">마이그레이션 시나리오</span><span class="sxs-lookup"><span data-stu-id="05ea2-271">Migration Scenarios</span></span>  
 <span data-ttu-id="05ea2-272">이제 WCF에서 다음과 같은 일반적인 Remoting 시나리오를 수행하는 방법을 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-272">Now let’s see how to accomplish the following common Remoting scenarios in WCF:</span></span>  
  
1. <span data-ttu-id="05ea2-273">서버에서 값 방식으로 클라이언트에 개체를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-273">Server returns an object by-value to the client</span></span>  
  
2. <span data-ttu-id="05ea2-274">서버에서 참조 방식으로 클라이언트에 개체를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-274">Server returns an object by-reference to the client</span></span>  
  
3. <span data-ttu-id="05ea2-275">클라이언트에서 값 방식으로 서버에 개체를 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-275">Client sends an object by-value to the server</span></span>  
  
> [!NOTE]
> <span data-ttu-id="05ea2-276">WCF에서는 클라이언트에서 참조 방식으로 서버에 개체를 전송할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-276">Sending an object by-reference from the client to the server is not allowed in WCF.</span></span>  
  
 <span data-ttu-id="05ea2-277">이러한 시나리오에서는 .NET Remoting의 기준 인터페이스가 다음 예제와 같다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-277">When reading through these scenarios, assume our baseline interfaces for .NET Remoting look like the following example.</span></span> <span data-ttu-id="05ea2-278">여기서는 WCF를 사용하여 해당 기능을 구현하는 방법만 설명하려 하므로, .NET Remoting 구현은 중요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-278">The .NET Remoting implementation is not important here because we want to illustrate only how to use WCF to implement equivalent functionality.</span></span>  
  
```csharp
public class RemotingServer : MarshalByRefObject  
{  
    // Demonstrates server returning object by-value  
    public Customer GetCustomer(int customerId) {…}  
  
    // Demonstrates server returning object by-reference  
    public CustomerReference GetCustomerReference(int customerId) {…}  
  
    // Demonstrates client passing object to server by-value  
    public bool UpdateCustomer(Customer customer) {…}  
}  
```  
  
#### <a name="scenario-1-service-returns-an-object-by-value"></a><span data-ttu-id="05ea2-279">시나리오 1: 서비스에서 값 방식으로 개체 반환</span><span class="sxs-lookup"><span data-stu-id="05ea2-279">Scenario 1: Service Returns an Object by Value</span></span>  
 <span data-ttu-id="05ea2-280">이 시나리오에서는 값 방식으로 클라이언트에 개체를 반환하는 서버를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-280">This scenario demonstrates a server returning an object to the client by value.</span></span> <span data-ttu-id="05ea2-281">WCF에서는 항상 값 방식으로 서버에서 개체를 반환하므로, 다음 단계는 단순히 일반적인 WCF 서비스를 빌드하는 방법만 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-281">WCF always returns objects from the server by value, so the following steps simply describe how to build a normal WCF service.</span></span>  
  
1. <span data-ttu-id="05ea2-282">WCF 서비스의 공용 인터페이스를 정의하여 시작한 다음 [ServiceContract] 특성으로 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-282">Start by defining a public interface for the WCF service and mark it with the [ServiceContract] attribute.</span></span> <span data-ttu-id="05ea2-283">여기서는 [OperationContract]를 사용하여 클라이언트에서 호출할 서버 측 메서드를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-283">We use [OperationContract] to identify the server-side methods our client will call.</span></span>  
  
   ```csharp
   [ServiceContract]  
   public interface ICustomerService  
   {  
       [OperationContract]  
       Customer GetCustomer(int customerId);  
  
       [OperationContract]  
       bool UpdateCustomer(Customer customer);  
   }  
   ```  
  
2. <span data-ttu-id="05ea2-284">다음 단계에서는 이 서비스의 데이터 계약을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-284">The next step is to create the data contract for this service.</span></span> <span data-ttu-id="05ea2-285">[DataContract] 특성으로 표시된 클래스(인터페이스가 아님)를 만들어 이 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-285">We do this by creating classes (not interfaces) marked with the [DataContract] attribute.</span></span> <span data-ttu-id="05ea2-286">클라이언트와 서버 둘 다에 표시할 개별 속성 또는 필드는 [DataMember]로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-286">The individual properties or fields we want visible to both client and server are marked with [DataMember].</span></span> <span data-ttu-id="05ea2-287">파생 형식을 허용하려면 [KnownType] 특성을 사용하여 식별해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-287">If we want derived types to be allowed, we must use the [KnownType] attribute to identify them.</span></span> <span data-ttu-id="05ea2-288">WCF에서 이 서비스용으로 직렬화하거나 역직렬화하도록 허용될 유일한 형식은 서비스 인터페이스에 있는 형식, 즉 "known types"입니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-288">The only types WCF will allow to be serialized or deserialized for this service are those in the service interface and these "known types".</span></span> <span data-ttu-id="05ea2-289">이 목록에 없는 다른 형식을 교환하려고 하면 거부됩니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-289">Attempting to exchange any other type not in this list will be rejected.</span></span>  
  
   ```csharp
   [DataContract]  
   [KnownType(typeof(PremiumCustomer))]  
   public class Customer  
   {  
       [DataMember]  
       public string FirstName { get; set; }  
  
       [DataMember]  
       public string LastName { get; set; }  
  
       [DataMember]  
       public int CustomerId { get; set; }  
   }  
  
   [DataContract]  
   public class PremiumCustomer : Customer
   {  
       [DataMember]  
       public int AccountId { get; set; }  
   }  
   ```  
  
3. <span data-ttu-id="05ea2-290">다음으로 서비스 인터페이스의 구현을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-290">Next, we provide the implementation for the service interface.</span></span>  
  
   ```csharp  
   public class CustomerService : ICustomerService  
   {  
       public Customer GetCustomer(int customerId)  
       {  
           // read from database  
       }  
  
       public bool UpdateCustomer(Customer customer)  
       {  
           // write to database  
       }  
   }  
   ```  
  
4. <span data-ttu-id="05ea2-291">WCF 서비스를 실행하려면 특정 WCF 바인딩을 사용하여 특정 URL에 해당 서비스 인터페이스를 노출하는 엔드포인트를 선언해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-291">To run the WCF service, we need to declare an endpoint that exposes that service interface at a specific URL using a specific WCF binding.</span></span> <span data-ttu-id="05ea2-292">일반적으로 서버 프로젝트의 web.config 파일에 다음 섹션을 추가하여 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-292">This is typically done by adding the following sections to the server project’s web.config file.</span></span>  
  
    ```xml  
    <configuration>  
      <system.serviceModel>  
        <services>  
          <service name="Server.CustomerService">  
            <endpoint address="http://localhost:8083/CustomerService"  
                      binding="basicHttpBinding"  
                      contract="Shared.ICustomerService" />  
          </service>  
        </services>  
      </system.serviceModel>  
    </configuration>  
    ```  
  
5. <span data-ttu-id="05ea2-293">그러면 다음 코드를 사용하여 WCF 서비스를 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-293">The WCF service can then be started with the following code:</span></span>  
  
   ```csharp
   ServiceHost customerServiceHost = new ServiceHost(typeof(CustomerService));  
       customerServiceHost.Open();  
   ```  
  
     <span data-ttu-id="05ea2-294">이 ServiceHost가 시작되고 나면 web.config 파일을 사용하여 적절한 계약, 바인딩 및 엔드포인트를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-294">When this ServiceHost is started, it uses the web.config file to establish the proper contract, binding and endpoint.</span></span> <span data-ttu-id="05ea2-295">구성 파일에 대한 자세한 내용은 [구성 파일을 사용하여 서비스 구성](./configuring-services-using-configuration-files.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="05ea2-295">For more information about configuration files, see [Configuring Services Using Configuration Files](./configuring-services-using-configuration-files.md).</span></span> <span data-ttu-id="05ea2-296">이와 같은 서버 시작 스타일을 자체 호스트라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-296">This style of starting the server is known as self-hosting.</span></span> <span data-ttu-id="05ea2-297">WCF 서비스 호스팅에 대한 다른 선택 사항은 [호스팅 서비스](./hosting-services.md)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="05ea2-297">To learn more about other choices for hosting WCF services, see [Hosting Services](./hosting-services.md).</span></span>  
  
6. <span data-ttu-id="05ea2-298">클라이언트 프로젝트의 app.config에서 서비스 엔드포인트에 일치하는 바인딩 정보를 선언해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-298">The client project’s app.config must declare matching binding information for the service’s endpoint.</span></span> <span data-ttu-id="05ea2-299">Visual Studio에서 이 작업을 수행하는 가장 쉬운 방법은 app.config 파일을 자동으로 업데이트하는 **서비스 참조 추가를**사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-299">The easiest way to do this in Visual Studio is to use **Add Service Reference**, which will automatically update the app.config file.</span></span> <span data-ttu-id="05ea2-300">또는 수동으로 동일한 변경 내용을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-300">Alternatively, these same changes can be added manually.</span></span>  
  
    ```xml  
    <configuration>  
      <system.serviceModel>  
        <client>  
          <endpoint name="customerservice"  
                    address="http://localhost:8083/CustomerService"  
                    binding="basicHttpBinding"  
                    contract="Shared.ICustomerService"/>  
        </client>  
      </system.serviceModel>  
    </configuration>  
    ```  
  
     <span data-ttu-id="05ea2-301">**서비스 참조 추가**사용에 대한 자세한 내용은 서비스 [참조 추가, 업데이트 또는 제거 방법을](/visualstudio/data-tools/how-to-add-update-or-remove-a-wcf-data-service-reference)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="05ea2-301">For more information about using **Add Service Reference**, see [How to: Add, Update, or Remove a Service Reference](/visualstudio/data-tools/how-to-add-update-or-remove-a-wcf-data-service-reference).</span></span>  
  
7. <span data-ttu-id="05ea2-302">이제 클라이언트에서 WCF 서비스를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-302">Now we can call the WCF service from the client.</span></span> <span data-ttu-id="05ea2-303">해당 서비스의 채널 팩터리를 만들고, 채널을 요청한 다음, 해당 채널에서 원하는 메서드를 직접 호출하여 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-303">We do this by creating a channel factory for that service, asking it for a channel, and directly calling the method we want on that channel.</span></span> <span data-ttu-id="05ea2-304">채널에서 서비스의 인터페이스를 구현하고 기본 요청/응답 논리를 처리하므로 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-304">We can do this because the channel implements the service’s interface and handles the underlying request/reply logic for us.</span></span> <span data-ttu-id="05ea2-305">이 메서드 호출의 반환 값은 역직렬화된 서버 응답 복사본입니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-305">The return value from that method call is the deserialized copy of the server’s response.</span></span>  
  
   ```csharp
   ChannelFactory<ICustomerService> factory =  
       new ChannelFactory<ICustomerService>("customerservice");  
   ICustomerService service = factory.CreateChannel();  
   Customer customer = service.GetCustomer(42);  
   Console.WriteLine($"  Customer {customer.FirstName} {customer.LastName} received.");
   ```  
  
 <span data-ttu-id="05ea2-306">WCF를 통해 서버에서 클라이언트에 반환하는 개체는 항상 값 방식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-306">Objects returned by WCF from the server to the client are always by value.</span></span> <span data-ttu-id="05ea2-307">개체는 서버에서 보낸 데이터의 역직렬화된 복사본입니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-307">The objects are deserialized copies of the data sent by the server.</span></span> <span data-ttu-id="05ea2-308">클라이언트에서 콜백을 통해 서버 코드를 호출하는 위험 없이 이러한 로컬 복사본에서 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-308">The client can call methods on these local copies without any danger of invoking server code through callbacks.</span></span>  
  
#### <a name="scenario-2-server-returns-an-object-by-reference"></a><span data-ttu-id="05ea2-309">시나리오 2: 서버에서 참조 방식으로 개체 반환</span><span class="sxs-lookup"><span data-stu-id="05ea2-309">Scenario 2: Server Returns an Object By Reference</span></span>  
 <span data-ttu-id="05ea2-310">이 시나리오에서는 참조 방식으로 클라이언트에 개체를 제공하는 서버를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-310">This scenario demonstrates the server providing an object to the client by reference.</span></span> <span data-ttu-id="05ea2-311">.NET Remoting에서는 참조 방식으로 직렬화되는 MarshalByRefObject에서 파생된 모든 형식에 대해 자동으로 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-311">In .NET Remoting, this is handled automatically for any type derived from MarshalByRefObject, which is serialized by-reference.</span></span> <span data-ttu-id="05ea2-312">이 시나리오의 예제에서는 여러 클라이언트에 개별 세션 서버 측 개체가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-312">An example of this scenario is allowing multiple clients to have independent sessionful server-side objects.</span></span> <span data-ttu-id="05ea2-313">앞서 설명한 것처럼, WCF 서비스에서 반환된 개체는 언제나 값 방식을 사용하므로 직접적으로 대응되는 참조 방식 개체가 없지만 <xref:System.ServiceModel.EndpointAddress10> 개체를 사용하여 참조 방식 의미 체계와 비슷한 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-313">As previously mentioned, objects returned by a WCF service are always by value, so there is no direct equivalent of a by-reference object, but it is possible to achieve something similar to by-reference semantics using an <xref:System.ServiceModel.EndpointAddress10> object.</span></span> <span data-ttu-id="05ea2-314">이는 서버에서 세션 참조 방식 개체를 가져오기 위해 클라이언트에서 사용할 수 있는 직렬화 가능 값 방식 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-314">This is a serializable by-value object that can be used by the client to obtain a sessionful by-reference object on the server.</span></span> <span data-ttu-id="05ea2-315">따라서 개별 세션 서버 측 개체가 있는 클라이언트가 여러 개인 시나리오가 가능하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-315">This enables the scenario of having multiple clients with independent sessionful server-side objects.</span></span>  
  
1. <span data-ttu-id="05ea2-316">먼저 세션 개체 자체에 해당하는 WCF 서비스 계약을 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-316">First, we need to define a WCF service contract that corresponds to the sessionful object itself.</span></span>  
  
   ```csharp
   [ServiceContract(SessionMode = SessionMode.Allowed)]  
       public interface ISessionBoundObject  
       {  
           [OperationContract]  
           string GetCurrentValue();  
  
           [OperationContract]  
           void SetCurrentValue(string value);  
       }  
   ```  
  
    > [!TIP]
    > <span data-ttu-id="05ea2-317">세션 개체는 [ServiceContract]로 표시되어 일반 WCF 서비스 인터페이스가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-317">Notice that the sessionful object is marked with [ServiceContract], making it a normal WCF service interface.</span></span> <span data-ttu-id="05ea2-318">SessionMode 속성을 설정하면 세션 서비스가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-318">Setting the SessionMode property indicates it will be a sessionful service.</span></span> <span data-ttu-id="05ea2-319">WCF에서 세션은 두 엔드포인트 간에 전송된 여러 메시지를 서로 관련시키는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-319">In WCF, a session is a way of correlating multiple messages sent between two endpoints.</span></span> <span data-ttu-id="05ea2-320">즉, 클라이언트가 이 서비스에 대한 연결을 확보하고 나면 클라이언트와 서버 간에 세션이 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-320">This means that once a client obtains a connection to this service, a session will be established between the client and the server.</span></span> <span data-ttu-id="05ea2-321">클라이언트는 이 단일 세션 내에서 수행되는 모든 상호 작용을 수행하는 데 하나의 고유한 서버 쪽 개체 인스턴스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-321">The client will use a single unique instance of the server-side object for all its interactions within this single session.</span></span>  
  
2. <span data-ttu-id="05ea2-322">다음으로 이 서비스 인터페이스의 구현을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-322">Next, we need to provide the implementation of this service interface.</span></span> <span data-ttu-id="05ea2-323">[ServiceBehavior]로 표시하고 InstanceContextMode를 설정하여 WCF에 각 세션에서 이 형식의 고유한 인스턴스를 사용하려 함을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-323">By denoting it with [ServiceBehavior] and setting the InstanceContextMode, we tell WCF we want to use a unique instance of this type for an each session.</span></span>  
  
   ```csharp
   [ServiceBehavior(InstanceContextMode = InstanceContextMode.PerSession)]  
       public class MySessionBoundObject : ISessionBoundObject  
       {  
           private string _value;  
  
           public string GetCurrentValue()  
           {  
               return _value;  
           }  
  
           public void SetCurrentValue(string val)  
           {  
               _value = val;  
           }  
  
       }  
   ```  
  
3. <span data-ttu-id="05ea2-324">이제 이 세션 개체의 인스턴스를 가져올 방법이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-324">Now we need a way to obtain an instance of this sessionful object.</span></span> <span data-ttu-id="05ea2-325">여기서는 EndpointAddress10 개체를 반환하는 또 다른 WCF 서비스 인터페이스를 만들어 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-325">We do this by creating another WCF service interface that returns an EndpointAddress10 object.</span></span> <span data-ttu-id="05ea2-326">이 인터페이스는 클라이언트에서 세션 개체를 만드는 데 사용할 수 있는 직렬화 가능한 형식의 엔드포인트입니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-326">This is a serializable form of an endpoint that the client can use to create the sessionful object.</span></span>  
  
   ```csharp
   [ServiceContract]  
       public interface ISessionBoundFactory  
       {  
           [OperationContract]  
           EndpointAddress10 GetInstanceAddress();  
       }  
   ```  
  
     <span data-ttu-id="05ea2-327">다음과 같이 이 WCF 서비스를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-327">And we implement this WCF service:</span></span>  
  
   ```csharp
   public class SessionBoundFactory : ISessionBoundFactory  
       {  
           public static ChannelFactory<ISessionBoundObject> _factory =
               new ChannelFactory<ISessionBoundObject>("sessionbound");  

           public SessionBoundFactory()  
           {  
           }  
  
           public EndpointAddress10 GetInstanceAddress()  
           {  
               IClientChannel channel = (IClientChannel)_factory.CreateChannel();  
               return EndpointAddress10.FromEndpointAddress(channel.RemoteAddress);  
           }  
       }  
   ```  
  
     <span data-ttu-id="05ea2-328">이 구현에서는 세션 개체를 만들기 위해 단일 채널 팩터리를 유지 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-328">This implementation maintains a singleton channel factory to create sessionful objects.</span></span> <span data-ttu-id="05ea2-329">GetInstanceAddress()를 호출하면 채널을 만들고 이 채널과 연결된 원격 주소를 효과적으로 가리키는 EndpointAddress10 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-329">When GetInstanceAddress() is called, it creates a channel and creates an EndpointAddress10 object that effectively points to the remote address associated with this channel.</span></span> <span data-ttu-id="05ea2-330">EndpointAddress10은 값 방식으로 클라이언트에 반환될 수 있는 데이터 형식일 뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-330">EndpointAddress10 is simply a data type that can be returned to the client by-value.</span></span>  
  
4. <span data-ttu-id="05ea2-331">다음 예제와 같이 다음 두 작업을 수행하여 서버의 구성 파일을 수정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-331">We need to modify the server’s configuration file by doing the following two things as shown in the example below:</span></span>  
  
    1. <span data-ttu-id="05ea2-332">세션 \<개체의 끝점을 설명하는 클라이언트> 섹션을 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-332">Declare a \<client> section that describes the endpoint for the sessionful object.</span></span> <span data-ttu-id="05ea2-333">이 경우 서버는 클라이언트 역할도 수행하므로 이와 같은 선언이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-333">This is necessary because the server also acts as a client in this situation.</span></span>  
  
    2. <span data-ttu-id="05ea2-334">팩터리와 세션 개체의 엔드포인트를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-334">Declare endpoints for the factory and sessionful object.</span></span> <span data-ttu-id="05ea2-335">클라이언트에서 서비스 엔드포인트와 통신하여 EndpointAddress10을 획득하고 세션 채널을 만들 수 있어야 하므로 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-335">This is necessary to allow the client to communicate with the service endpoints to acquire the EndpointAddress10 and to create the sessionful channel.</span></span>  
  
    ```xml  
    <configuration>  
      <system.serviceModel>  
         <client>  
          <endpoint name="sessionbound"  
                    address="net.tcp://localhost:8081/SessionBoundObject"  
                    binding="netTcpBinding"  
                    contract="Shared.ISessionBoundObject"/>  
        </client>  
        <services>  
          <service name="Server.CustomerService">  
            <endpoint address="http://localhost:8083/CustomerService"  
                      binding="basicHttpBinding"  
                      contract="Shared.ICustomerService" />  
          </service>  
          <service name="Server.MySessionBoundObject">  
            <endpoint address="net.tcp://localhost:8081/SessionBoundObject"  
                      binding="netTcpBinding"  
                      contract="Shared.ISessionBoundObject" />  
          </service>  
          <service name="Server.SessionBoundFactory">  
            <endpoint address="net.tcp://localhost:8081/SessionBoundFactory"  
                      binding="netTcpBinding"  
                      contract="Shared.ISessionBoundFactory" />  
          </service>  
        </services>  
      </system.serviceModel>  
    </configuration>  
    ```  
  
     <span data-ttu-id="05ea2-336">그러면 다음과 같은 서비스를 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-336">And then we can start these services:</span></span>  
  
   ```csharp
   ServiceHost factoryHost = new ServiceHost(typeof(SessionBoundFactory));  
   factoryHost.Open();  
  
   ServiceHost sessionHost = new ServiceHost(typeof(MySessionBoundObject));  
   sessionHost.Open();  
   ```  
  
5. <span data-ttu-id="05ea2-337">프로젝트의 app.config 파일에서 이와 같이 동일한 엔드포인트를 선언하여 클라이언트를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-337">We configure the client by declaring these same endpoints in its project’s app.config file.</span></span>  
  
    ```xml  
    <configuration>  
      <system.serviceModel>  
        <client>  
          <endpoint name="customerservice"  
                    address="http://localhost:8083/CustomerService"  
                    binding="basicHttpBinding"  
                    contract="Shared.ICustomerService"/>  
          <endpoint name="sessionbound"  
                    address="net.tcp://localhost:8081/SessionBoundObject"  
                    binding="netTcpBinding"  
                    contract="Shared.ISessionBoundObject"/>  
          <endpoint name="factory"  
                    address="net.tcp://localhost:8081/SessionBoundFactory"  
                    binding="netTcpBinding"  
                    contract="Shared.ISessionBoundFactory"/>  
        </client>  
      </system.serviceModel>  
    </configuration>  
    ```  
  
6. <span data-ttu-id="05ea2-338">이 세션 개체를 만들고 사용하려면 클라이언트에서 다음 단계를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-338">In order to create and use this sessionful object, the client must do the following steps:</span></span>  
  
    1. <span data-ttu-id="05ea2-339">ISessionBoundFactory 서비스에 대한 채널을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-339">Create a channel to the ISessionBoundFactory service.</span></span>  
  
    2. <span data-ttu-id="05ea2-340">이 채널을 통해 해당 서비스를 호출하여 EndpointAddress10을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-340">Use that channel to invoke that service to obtain an EndpointAddress10.</span></span>  
  
    3. <span data-ttu-id="05ea2-341">EndpointAddress10을 사용하여 세션 개체를 가져올 채널을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-341">Use the EndpointAddress10 to create a channel to obtain a sessionful object.</span></span>  
  
    4. <span data-ttu-id="05ea2-342">여러 호출에서 동일한 인스턴스로 남아 있음을 보여주기 위해 세션 개체와 상호 작용합니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-342">Interact with the sessionful object to demonstrate it remains the same instance across multiple calls.</span></span>  
  
   ```csharp
   ChannelFactory<ISessionBoundFactory> channelFactory =
       new ChannelFactory<ISessionBoundFactory>("factory");  
   ISessionBoundFactory sessionFactory = channelFactory.CreateChannel();  
  
   EndpointAddress10 address1 = sessionFactory.GetInstanceAddress();  
   EndpointAddress10 address2 = sessionFactory.GetInstanceAddress();  
  
   ChannelFactory<ISessionBoundObject> sessionObjectFactory1 =
       new ChannelFactory<ISessionBoundObject>(new NetTcpBinding(),
                                               address1.ToEndpointAddress());  
   ChannelFactory<ISessionBoundObject> sessionObjectFactory2 =
       new ChannelFactory<ISessionBoundObject>(new NetTcpBinding(),
                                               address2.ToEndpointAddress());  
  
   ISessionBoundObject sessionInstance1 = sessionObjectFactory1.CreateChannel();  
   ISessionBoundObject sessionInstance2 = sessionObjectFactory2.CreateChannel();  
  
   sessionInstance1.SetCurrentValue("Hello");  
   sessionInstance2.SetCurrentValue("World");  
  
   if (sessionInstance1.GetCurrentValue() == "Hello" &&  
       sessionInstance2.GetCurrentValue() == "World")  
   {  
       Console.WriteLine("sessionful server object works as expected");  
   }  
   ```  
  
 <span data-ttu-id="05ea2-343">WCF에서는 언제나 값 방식으로 개체를 반환하지만, EndpointAddress10을 사용하여 상응하는 참조 방식 의미 체계를 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-343">WCF always returns objects by value, but it is possible to support the equivalent of by-reference semantics through the use of EndpointAddress10.</span></span> <span data-ttu-id="05ea2-344">그러면 클라이언트에서 세션 WCF 서비스 인스턴스를 요청할 수 있으므로 다른 WCF 서비스와 마찬가지로 상호 작용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-344">This permits the client to request a sessionful WCF service instance, after which it can interact with it like any other WCF service.</span></span>  
  
#### <a name="scenario-3-client-sends-server-a-by-value-instance"></a><span data-ttu-id="05ea2-345">시나리오 3: 클라이언트에서 서버에 값 방식 인스턴스 전송</span><span class="sxs-lookup"><span data-stu-id="05ea2-345">Scenario 3: Client Sends Server a By-Value Instance</span></span>  
 <span data-ttu-id="05ea2-346">이 시나리오에서는 기본 형식이 아닌 개체 인스턴스를 값 방식으로 서버에 보내는 클라이언트를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-346">This scenario demonstrates the client sending a non-primitive object instance to the server by value.</span></span> <span data-ttu-id="05ea2-347">WCF에서는 값 방식으로만 개체를 전송하므로 이 시나리오에서는 일반 WCF 사용을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-347">Because WCF only sends objects by value, this scenario demonstrates normal WCF usage.</span></span>  
  
1. <span data-ttu-id="05ea2-348">시나리오 1과 동일한 WCF 서비스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-348">Use the same WCF Service from Scenario 1.</span></span>  
  
2. <span data-ttu-id="05ea2-349">클라이언트를 사용하여 새로운 값 방식 개체(Customer)를 만들고 ICustomerService 서비스와 통신하는 채널을 만든 다음 개체를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-349">Use the client to create a new by-value object (Customer), create a channel to communicate with the ICustomerService service, and send the object to it.</span></span>  
  
   ```csharp
   ChannelFactory<ICustomerService> factory =  
       new ChannelFactory<ICustomerService>("customerservice");  
   ICustomerService service = factory.CreateChannel();  
   PremiumCustomer customer = new PremiumCustomer {
   FirstName = "Bob",
   LastName = "Jones",
   CustomerId = 43,
   AccountId = 99};  
   bool success = service.UpdateCustomer(customer);  
   Console.WriteLine($"  Server returned {success}.");
   ```  
  
     <span data-ttu-id="05ea2-350">Customer 개체가 직렬화되어 서버에 전송되면 이 서버에서 해당 개체의 새 복사본으로 역직렬화됩니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-350">The customer object will be serialized, and sent to the server, where it is deserialized into a new copy of that object.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="05ea2-351">이 코드는 파생 형식(PremiumCustomer) 전송도 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-351">This code also illustrates sending a derived type (PremiumCustomer).</span></span> <span data-ttu-id="05ea2-352">서비스 인터페이스에서는 Customer 개체를 기대하지만, Customer 클래스에 표시된 PremiumCustomer의 [KnownType] 특성도 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-352">The service interface expects a Customer object, but the [KnownType] attribute on the Customer class indicated PremiumCustomer was also allowed.</span></span> <span data-ttu-id="05ea2-353">WCF에서 이 서비스 인터페이스를 통해 다른 형식을 직렬화하거나 역직렬화하려고 하면 모두 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-353">WCF will fail any attempt to serialize or deserialize any other type through this service interface.</span></span>  
  
 <span data-ttu-id="05ea2-354">데이터의 표준 WCF 교환은 값 방식입니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-354">Normal WCF exchanges of data are by value.</span></span> <span data-ttu-id="05ea2-355">이 경우 이러한 데이터 개체 중 하나에서 메서드를 호출하면 로컬에서만 실행되며, 다른 계층에서는 코드를 호출하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-355">This guarantees that invoking methods on one of these data objects executes only locally – it will not invoke code on the other tier.</span></span> <span data-ttu-id="05ea2-356">서버에서 반환된 참조 개체와 같은 *from* 것을 얻을 수는 있지만 클라이언트가 참조 *별* 개체를 서버에 전달할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-356">While it is possible to achieve something like by-reference objects returned *from* the server, it is not possible for a client to pass a by-reference object *to* the server.</span></span> <span data-ttu-id="05ea2-357">클라이언트와 서버 간에 서로 대화하는 데 필요한 시나리오는 WCF에서 이중 서비스를 사용하여 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-357">A scenario that requires a conversation back and forth between client and server can be achieved in WCF using a duplex service.</span></span> <span data-ttu-id="05ea2-358">자세한 내용은 [양면 서비스를](./feature-details/duplex-services.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="05ea2-358">For more information, see [Duplex Services](./feature-details/duplex-services.md).</span></span>  
  
## <a name="summary"></a><span data-ttu-id="05ea2-359">요약</span><span class="sxs-lookup"><span data-stu-id="05ea2-359">Summary</span></span>  
 <span data-ttu-id="05ea2-360">.NET Remoting은 완전히 신뢰할 수 있는 환경에서만 사용하도록 고안된 통신 프레임워크입니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-360">.NET Remoting is a communication framework intended to be used only within fully-trusted environments.</span></span> <span data-ttu-id="05ea2-361">이는 레거시 제품이며 이전 버전과의 호환성을 위해서만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-361">It is a legacy product and supported only for backward compatibility.</span></span> <span data-ttu-id="05ea2-362">새 애플리케이션을 빌드하는 데 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-362">It should not be used to build new applications.</span></span> <span data-ttu-id="05ea2-363">반대로, WCF는 보안을 염두에 두고 설계되었으며, 신규 및 기존 애플리케이션에 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-363">Conversely, WCF was designed with security in mind and is recommended for new and existing applications.</span></span> <span data-ttu-id="05ea2-364">Microsoft에서는 기존 Remoting 애플리케이션을 마이그레이션하여 WCF나 ASP.NET Web API를 대신 사용하도록 권장합니다.</span><span class="sxs-lookup"><span data-stu-id="05ea2-364">Microsoft recommends that existing Remoting applications be migrated to use WCF or ASP.NET Web API instead.</span></span>
