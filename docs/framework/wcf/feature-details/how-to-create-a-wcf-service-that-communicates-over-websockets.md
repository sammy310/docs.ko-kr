---
description: '자세한 정보: 방법: Websocket을 통해 통신 하는 WCF 서비스 만들기'
title: '방법: WebSocket을 통해 통신하는 WCF 서비스 만들기'
ms.date: 03/30/2017
ms.assetid: bafbbd89-eab8-4e9a-b4c3-b7b0178e12d8
ms.openlocfilehash: b2d755080f982c575f18269b3d103301aa7317e2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99802920"
---
# <a name="how-to-create-a-wcf-service-that-communicates-over-websockets"></a><span data-ttu-id="c36f8-103">방법: WebSocket을 통해 통신하는 WCF 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="c36f8-103">How to: Create a WCF Service that Communicates over WebSockets</span></span>

<span data-ttu-id="c36f8-104">WCF 서비스 및 클라이언트는 <xref:System.ServiceModel.NetHttpBinding> 바인딩을 사용하여 WebSocket에서 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c36f8-104">WCF services and clients can use the <xref:System.ServiceModel.NetHttpBinding> binding to communicate over WebSockets.</span></span>  <span data-ttu-id="c36f8-105">WebSocket은 <xref:System.ServiceModel.NetHttpBinding>에서 서비스 계약이 콜백 계약을 정의한다고 판단할 때 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c36f8-105">WebSockets will be used when the <xref:System.ServiceModel.NetHttpBinding> determines the service contract defines a callback contract.</span></span> <span data-ttu-id="c36f8-106">이 항목은 WebSocket에서 통신하기 위해 <xref:System.ServiceModel.NetHttpBinding>을 사용하는 WCF 서비스와 클라이언트를 구현하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c36f8-106">This topic describes how to implement a WCF service and client that uses the <xref:System.ServiceModel.NetHttpBinding> to communicate over WebSockets.</span></span>  
  
### <a name="define-the-service"></a><span data-ttu-id="c36f8-107">서비스 정의</span><span class="sxs-lookup"><span data-stu-id="c36f8-107">Define the Service</span></span>  
  
1. <span data-ttu-id="c36f8-108">콜백 계약 정의</span><span class="sxs-lookup"><span data-stu-id="c36f8-108">Define a callback contract</span></span>  
  
    ```csharp  
    [ServiceContract]  
        public interface IStockQuoteCallback  
        {  
            [OperationContract(IsOneWay = true)]  
            Task SendQuote(string code, double value);  
        }  
    ```  
  
     <span data-ttu-id="c36f8-109">이 계약은 클라이언트 애플리케이션에서 서비스가 메시지를 다시 클라이언트로 보낼 수 있도록 허용하기 위해 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="c36f8-109">This contract will be implemented by the client application to allow the service to send messages back to the client.</span></span>  
  
2. <span data-ttu-id="c36f8-110">서비스 계약을 정의하고 `IStockQuoteCallback` 인터페이스를 콜백 계약으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c36f8-110">Define the service contract and specify the `IStockQuoteCallback` interface as the callback contract.</span></span>  
  
    ```csharp  
    [ServiceContract(CallbackContract = typeof(IStockQuoteCallback))]  
        public interface IStockQuoteService  
        {  
            [OperationContract(IsOneWay = true)]  
            Task StartSendingQuotes();  
        }  
    ```  
  
3. <span data-ttu-id="c36f8-111">서비스 계약을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="c36f8-111">Implement the service contract.</span></span>  
  
    ```csharp
    public class StockQuoteService : IStockQuoteService  
    {  
        public async Task StartSendingQuotes()  
        {  
            var callback = OperationContext.Current.GetCallbackChannel<IStockQuoteCallback>();  
            var random = new Random();  
            double price = 29.00;  

            while (((IChannel)callback).State == CommunicationState.Opened)  
            {  
                await callback.SendQuote("MSFT", price);  
                price += random.NextDouble();  
                await Task.Delay(1000);  
            }  
        }  
    }  
    ```  
  
     <span data-ttu-id="c36f8-112">서비스 작업 `StartSendingQuotes`는 비동기 호출로 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="c36f8-112">The service operation `StartSendingQuotes` is implemented as an asynchronous call.</span></span> <span data-ttu-id="c36f8-113">`OperationContext`를 사용하여 콜백 채널을 검색하고 채널이 열려 있을 경우 콜백 채널에 대해 비동기 호출을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="c36f8-113">We retrieve the callback channel using the `OperationContext` and if the channel is open, we make an async call on the callback channel.</span></span>  
  
4. <span data-ttu-id="c36f8-114">서비스 구성</span><span class="sxs-lookup"><span data-stu-id="c36f8-114">Configure the service</span></span>  
  
    ```xml  
    <configuration>  
        <appSettings>  
          <add key="aspnet:UseTaskFriendlySynchronizationContext" value="true" />
        </appSettings>  
        <system.web>  
          <compilation debug="true" targetFramework="4.5" />
        </system.web>  
        <system.serviceModel>  
            <protocolMapping>  
              <add scheme="http" binding="netHttpBinding"/>  
              <add scheme="https" binding="netHttpsBinding"/>  
            </protocolMapping>  
            <behaviors>  
                <serviceBehaviors>  
                    <behavior name="">  
                        <serviceMetadata httpGetEnabled="true" httpsGetEnabled="true" />  
                        <serviceDebug includeExceptionDetailInFaults="false" />  
                    </behavior>  
                </serviceBehaviors>  
            </behaviors>  
            <serviceHostingEnvironment aspNetCompatibilityEnabled="true"  
                multipleSiteBindingsEnabled="true" />  
        </system.serviceModel>  
    </configuration>  
    ```  
  
     <span data-ttu-id="c36f8-115">서비스 구성 파일은 WCF의 기본 엔드포인트에 의존합니다.</span><span class="sxs-lookup"><span data-stu-id="c36f8-115">The service’s configuration file relies on WCF’s default endpoints.</span></span> <span data-ttu-id="c36f8-116">ph x="1" /&gt; 섹션은 생성된 기본 엔드포인트에 `NetHttpBinding`을 사용해야 함을 지정하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c36f8-116">The `<protocolMapping>` section is used to specify that the `NetHttpBinding` should be used for the default endpoints created.</span></span>  
  
### <a name="define-the-client"></a><span data-ttu-id="c36f8-117">클라이언트 정의</span><span class="sxs-lookup"><span data-stu-id="c36f8-117">Define the Client</span></span>  
  
1. <span data-ttu-id="c36f8-118">콜백 계약을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="c36f8-118">Implement the callback contract.</span></span>  
  
    ```csharp  
    private class CallbackHandler : StockQuoteServiceReference.IStockQuoteServiceCallback  
            {  
                public async Task SendQuoteAsync(string code, double value)  
                {  
                    Console.WriteLine("{0}: {1:f2}", code, value);  
                }  
            }  
    ```  
  
     <span data-ttu-id="c36f8-119">콜백 계약 작업은 비동기 메서드로 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="c36f8-119">The callback contract operation is implemented as an asynchronous method.</span></span>  
  
    1. <span data-ttu-id="c36f8-120">클라이언트 코드를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="c36f8-120">Implement the client code.</span></span>  
  
        ```csharp  
        class Program  
        {  
            static void Main(string[] args)  
            {  
                var context = new InstanceContext(new CallbackHandler());  
                var client = new StockQuoteServiceReference.StockQuoteServiceClient(context);  
                client.StartSendingQuotes();
                Console.ReadLine();  
            }  
  
            private class CallbackHandler : StockQuoteServiceReference.IStockQuoteServiceCallback  
            {  
                public async Task SendQuoteAsync(string code, double value)  
                {  
                    Console.WriteLine("{0}: {1:f2}", code, value);  
                }  
            }  
        }  
        ```  
  
         <span data-ttu-id="c36f8-121">여기서 쉽게 구분할 수 있도록 CallbackHandler가 반복되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c36f8-121">The CallbackHandler is repeated here for clarity.</span></span> <span data-ttu-id="c36f8-122">클라이언트 애플리케이션은 새 InstanceContext를 만들고 콜백 인스턴스의 구현을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c36f8-122">The client application creates a new InstanceContext and specifies the implementation of the callback interface.</span></span> <span data-ttu-id="c36f8-123">그런 다음 새로 만들어진 InstanceContext에 참조를 보내는 프록시 클래스의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c36f8-123">Next it creates an instance of the proxy class sending a reference to the newly created InstanceContext.</span></span> <span data-ttu-id="c36f8-124">클라이언트가 서비스를 호출하면 서비스는 지정된 콜백 계약을 사용하여 클라이언트를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="c36f8-124">When the client calls the service, the service will call the client using the callback contract specified.</span></span>  
  
    2. <span data-ttu-id="c36f8-125">클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="c36f8-125">Configure the client</span></span>  
  
        ```xml  
        <?xml version="1.0" encoding="utf-8" ?>  
        <configuration>  
            <startup>
                <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.5" />  
            </startup>  
            <system.serviceModel>  
                <bindings>  
                    <netHttpBinding>  
                        <binding name="NetHttpBinding_IStockQuoteService">  
                            <webSocketSettings transportUsage="Always" />  
                        </binding>  
                    </netHttpBinding>  
                </bindings>  
                <client>  
                    <endpoint address="ws://localhost/NetHttpSampleServer/StockQuoteService.svc"  
                        binding="netHttpBinding" bindingConfiguration="NetHttpBinding_IStockQuoteService"  
                        contract="StockQuoteServiceReference.IStockQuoteService" name="NetHttpBinding_IStockQuoteService" />  
                </client>  
            </system.serviceModel>  
        </configuration>  
        ```  
  
         <span data-ttu-id="c36f8-126">클라이언트 구성에서 특별한 작업이 필요하지 않습니다. `NetHttpBinding`을 사용하여 클라이언트 측 엔드포인트를 지정하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c36f8-126">There is nothing special you need to do in the client configuration, just specify the client side endpoint using the `NetHttpBinding`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c36f8-127">예제</span><span class="sxs-lookup"><span data-stu-id="c36f8-127">Example</span></span>  

 <span data-ttu-id="c36f8-128">다음은 이 항목에서 사용되는 전체 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="c36f8-128">The following is the complete code used in this topic.</span></span>  
  
```csharp  
// IStockQuoteService.cs  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Runtime.Serialization;  
using System.ServiceModel;  
using System.Text;  
using System.Threading.Tasks;  
  
namespace Server  
{  
    [ServiceContract(CallbackContract = typeof(IStockQuoteCallback))]  
    public interface IStockQuoteService  
    {  
        [OperationContract(IsOneWay = true)]  
        Task StartSendingQuotes();  
    }  
  
    [ServiceContract]  
    public interface IStockQuoteCallback  
    {  
        [OperationContract(IsOneWay = true)]  
        Task SendQuote(string code, double value);  
    }  
}  
```  
  
```csharp
// StockQuoteService.svc.cs  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Runtime.Serialization;  
using System.ServiceModel;  
using System.ServiceModel.Channels;  
using System.Text;  
using System.Threading.Tasks;  
  
namespace Server  
{  
    public class StockQuoteService : IStockQuoteService  
    {  
        public async Task StartSendingQuotes()  
        {  
            var callback = OperationContext.Current.GetCallbackChannel<IStockQuoteCallback>();  
            var random = new Random();  
            double price = 29.00;  
  
            while (((IChannel)callback).State == CommunicationState.Opened)  
            {  
                await callback.SendQuote("MSFT", price);  
                price += random.NextDouble();  
                await Task.Delay(1000);  
            }  
        }  
    }  
}  
```  
  
```xml  
<?xml version="1.0"?>  
  
<!--  
  For more information on how to configure your ASP.NET application, please visit  
  https://go.microsoft.com/fwlink/?LinkId=169433  
  -->  
  
<configuration>  
    <appSettings>  
      <add key="aspnet:UseTaskFriendlySynchronizationContext" value="true" />
    </appSettings>  
    <system.web>  
      <compilation debug="true" targetFramework="4.5" />
    </system.web>  
    <system.serviceModel>  
        <protocolMapping>  
          <add scheme="http" binding="netHttpBinding"/>  
          <add scheme="https" binding="netHttpsBinding"/>  
        </protocolMapping>  
        <behaviors>  
            <serviceBehaviors>  
                <behavior name="">  
                    <serviceMetadata httpGetEnabled="true" httpsGetEnabled="true" />  
                    <serviceDebug includeExceptionDetailInFaults="false" />  
                </behavior>  
            </serviceBehaviors>  
        </behaviors>  
        <serviceHostingEnvironment aspNetCompatibilityEnabled="true"  
            multipleSiteBindingsEnabled="true" />  
    </system.serviceModel>  
</configuration>  
```  
  
```aspx-csharp
<!-- StockQuoteService.svc -->  
<%@ ServiceHost Language="C#" Debug="true" Service="Server.StockQuoteService" CodeBehind="StockQuoteService.svc.cs" %>  
```  
  
```csharp  
// Client.cs  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.ServiceModel;  
using System.Text;  
using System.Threading.Tasks;  
  
namespace Client  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            var context = new InstanceContext(new CallbackHandler());  
            var client = new StockQuoteServiceReference.StockQuoteServiceClient(context);  
            client.StartSendingQuotes();
            Console.ReadLine();  
        }  
  
        private class CallbackHandler : StockQuoteServiceReference.IStockQuoteServiceCallback  
        {  
            public async Task SendQuoteAsync(string code, double value)  
            {  
                Console.WriteLine("{0}: {1:f2}", code, value);  
            }  
        }  
    }  
}  
```  
  
```xml  
<!--App.config -->  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
    <startup>
        <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.5" />  
    </startup>  
    <system.serviceModel>  
        <bindings>  
            <netHttpBinding>  
                <binding name="NetHttpBinding_IStockQuoteService">  
                    <webSocketSettings transportUsage="Always" />  
                </binding>  
            </netHttpBinding>  
        </bindings>  
        <client>  
            <endpoint address="ws://localhost/NetHttpSampleServer/StockQuoteService.svc"  
                binding="netHttpBinding" bindingConfiguration="NetHttpBinding_IStockQuoteService"  
                contract="StockQuoteServiceReference.IStockQuoteService" name="NetHttpBinding_IStockQuoteService" />  
        </client>  
    </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c36f8-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c36f8-129">See also</span></span>

- [<span data-ttu-id="c36f8-130">동기 및 비동기 작업</span><span class="sxs-lookup"><span data-stu-id="c36f8-130">Synchronous and Asynchronous Operations</span></span>](../synchronous-and-asynchronous-operations.md)
- [<span data-ttu-id="c36f8-131">NetHttpBinding 사용</span><span class="sxs-lookup"><span data-stu-id="c36f8-131">Using the NetHttpBinding</span></span>](using-the-nethttpbinding.md)
