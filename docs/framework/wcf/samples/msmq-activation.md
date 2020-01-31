---
title: MSMQ 활성화
ms.date: 03/30/2017
ms.assetid: e3834149-7b8c-4a54-806b-b4296720f31d
ms.openlocfilehash: 805ab78908b4d1146cce94cac5357bafbb35c832
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744795"
---
# <a name="msmq-activation"></a><span data-ttu-id="bae3f-102">MSMQ 활성화</span><span class="sxs-lookup"><span data-stu-id="bae3f-102">MSMQ Activation</span></span>

<span data-ttu-id="bae3f-103">이 샘플에서는 메시지 큐에서 읽은 WAS(Windows Process Activation Service)에서 애플리케이션을 호스트하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bae3f-103">This sample demonstrates how to host applications in Windows Process Activation Service (WAS) that are read from a message queue.</span></span> <span data-ttu-id="bae3f-104">이 샘플은 `netMsmqBinding`를 사용 하 고 [양방향 통신](../../../../docs/framework/wcf/samples/two-way-communication.md) 샘플을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="bae3f-104">This sample uses the `netMsmqBinding` and is based on the [Two-Way Communication](../../../../docs/framework/wcf/samples/two-way-communication.md) sample.</span></span> <span data-ttu-id="bae3f-105">이 경우 서비스는 웹 호스팅 애플리케이션이고 클라이언트는 자체 호스트되며 전송된 구매 주문의 상태를 확인하기 위해 콘솔에 출력됩니다.</span><span class="sxs-lookup"><span data-stu-id="bae3f-105">The service in this case is a Web-hosted application and the client is self-hosted and outputs to the console to observe the status of purchase orders submitted.</span></span>

> [!NOTE]
> <span data-ttu-id="bae3f-106">이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bae3f-106">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>

> [!NOTE]
> <span data-ttu-id="bae3f-107">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bae3f-107">The samples may already be installed on your computer.</span></span> <span data-ttu-id="bae3f-108">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="bae3f-108">Check for the following (default) directory before continuing.</span></span>
>
> <span data-ttu-id="bae3f-109">\<InstallDrive>:\WF_WCF_Samples</span><span class="sxs-lookup"><span data-stu-id="bae3f-109">\<InstallDrive>:\WF_WCF_Samples</span></span>
>
> <span data-ttu-id="bae3f-110">이 디렉터리가 없으면 [.NET Framework 4에 대 한 Windows Communication Foundation (wcf) 및 Windows Workflow Foundation (WF) 샘플](https://www.microsoft.com/download/details.aspx?id=21459) 로 이동 하 여 모든 WCF 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="bae3f-110">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all WCF and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="bae3f-111">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bae3f-111">This sample is located in the following directory.</span></span>
>
> <span data-ttu-id="bae3f-112">\<InstallDrive>:\Samples\WCFWFCardSpace\WCF\Basic\Services\Hosting\WASHost\MsmqActivation.</span><span class="sxs-lookup"><span data-stu-id="bae3f-112">\<InstallDrive>:\Samples\WCFWFCardSpace\WCF\Basic\Services\Hosting\WASHost\MsmqActivation.</span></span>

<span data-ttu-id="bae3f-113">WAS (windows Process Activation Service), Windows Server 2008에 대 한 새로운 프로세스 활성화 메커니즘인 이전에는 http 기반 응용 프로그램에서 HTTP가 아닌 프로토콜을 사용 하는 응용 프로그램에만 사용할 수 있었던 IIS와 같은 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="bae3f-113">Windows Process Activation Service (WAS), the new process activation mechanism for Windows Server 2008, provides IIS-like features that were previously only available to HTTP-based applications to applications that use non-HTTP protocols.</span></span> <span data-ttu-id="bae3f-114">WCF (Windows Communication Foundation)는 수신기 어댑터 인터페이스를 사용 하 여 WCF (예: TCP, 명명 된 파이프 및 MSMQ)에서 지 원하는 HTTP가 아닌 프로토콜을 통해 수신 되는 활성화 요청을 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="bae3f-114">Windows Communication Foundation (WCF) uses the Listener Adapter interface to communicate activation requests that are received over the non-HTTP protocols supported by WCF, such as TCP, Named Pipes, and MSMQ.</span></span> <span data-ttu-id="bae3f-115">HTTP가 아닌 프로토콜을 통해 요청을 수신하는 기능은 SMSvcHost.exe에서 실행되는 관리되는 Windows 서비스에 의해 호스트됩니다.</span><span class="sxs-lookup"><span data-stu-id="bae3f-115">The functionality for receiving requests over non-HTTP protocols is hosted by managed Windows services running in SMSvcHost.exe.</span></span>

<span data-ttu-id="bae3f-116">Net.Msmq Listener Adapter 서비스(NetMsmqActivator)는 큐의 메시지에 기초하여 큐에 대기 중인 애플리케이션을 활성화합니다.</span><span class="sxs-lookup"><span data-stu-id="bae3f-116">The Net.Msmq Listener Adapter service (NetMsmqActivator) activates queued applications based on messages in the queue.</span></span>

<span data-ttu-id="bae3f-117">클라이언트는 트랜잭션의 범위 내에서 서비스에 구매 주문을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="bae3f-117">The client sends purchase orders to the service from within the scope of a transaction.</span></span> <span data-ttu-id="bae3f-118">서비스는 트랜잭션의 주문을 수신하고 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="bae3f-118">The service receives the orders in a transaction and processes them.</span></span> <span data-ttu-id="bae3f-119">그런 다음 서비스는 주문 상태와 함께 클라이언트를 콜백합니다.</span><span class="sxs-lookup"><span data-stu-id="bae3f-119">The service then calls back the client with the status of the order.</span></span> <span data-ttu-id="bae3f-120">양방향 통신을 쉽게 수행하기 위해 클라이언트와 서비스는 둘 다 큐를 사용하여 구매 주문과 주문 상태를 큐에 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="bae3f-120">To facilitate two-way communication the client and service both use queues to enqueue purchase orders and order status.</span></span>

<span data-ttu-id="bae3f-121">서비스 계약 `IOrderProcessor`는 큐를 사용하는 단방향 서비스 작업을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="bae3f-121">The service contract `IOrderProcessor` defines the one-way service operations that work with queuing.</span></span> <span data-ttu-id="bae3f-122">이 서비스 작업은 회신 엔드포인트를 사용하여 주문 상태를 클라이언트에게 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="bae3f-122">The service operation uses the reply endpoint to send order statuses to the client.</span></span> <span data-ttu-id="bae3f-123">회신 엔드포인트의 주소는 주문 상태를 클라이언트에게 다시 보내는 데 사용되는 큐의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="bae3f-123">The reply endpoint's address is the URI of the queue used to send the order status back to the client.</span></span> <span data-ttu-id="bae3f-124">주문 처리 애플리케이션에서 이 계약을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="bae3f-124">The order processing application implements this contract.</span></span>

```csharp
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]
public interface IOrderProcessor
{
    [OperationContract(IsOneWay = true)]
    void SubmitPurchaseOrder(PurchaseOrder po,
                                           string reportOrderStatusTo);
}
```

<span data-ttu-id="bae3f-125">주문 상태를 보낼 회신 계약은 클라이언트에 의해 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="bae3f-125">The reply contract to send order status to is specified by the client.</span></span> <span data-ttu-id="bae3f-126">클라이언트는 주문 상태 계약을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="bae3f-126">The client implements the order status contract.</span></span> <span data-ttu-id="bae3f-127">서비스는 이 계약의 생성된 클라이언트를 사용하여 주문 상태를 다시 클라이언트에게 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="bae3f-127">The service uses the generated client of this contract to send order status back to the client.</span></span>

```csharp
[ServiceContract]
public interface IOrderStatus
{
    [OperationContract(IsOneWay = true)]
    void OrderStatus(string poNumber, string status);
}
```

<span data-ttu-id="bae3f-128">서비스 작업은 전송된 구매 주문을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="bae3f-128">The service operation processes the submitted purchase order.</span></span> <span data-ttu-id="bae3f-129">큐에서 메시지를 수신하는 데 사용되는 트랜잭션의 자동 인리스트먼트 및 서비스 작업 완료 시의 트랜잭션의 자동 완료를 지정하기 위해 <xref:System.ServiceModel.OperationBehaviorAttribute>가 서비스 작업에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="bae3f-129">The <xref:System.ServiceModel.OperationBehaviorAttribute> is applied to the service operation to specify automatic enlistment in the transaction that is used to receive the message from the queue and automatic completion of the transaction on completion of the service operation.</span></span> <span data-ttu-id="bae3f-130">`Orders` 클래스는 주문 처리 기능을 캡슐화합니다.</span><span class="sxs-lookup"><span data-stu-id="bae3f-130">The `Orders` class encapsulates order processing functionality.</span></span> <span data-ttu-id="bae3f-131">이 경우에는 구매 주문을 사전에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="bae3f-131">In this case, it adds the purchase order to a dictionary.</span></span> <span data-ttu-id="bae3f-132">서비스 작업이 참여하는 트랜잭션은 `Orders` 클래스의 작업에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bae3f-132">The transaction that the service operation enlisted in is available to the operations in the `Orders` class.</span></span>

<span data-ttu-id="bae3f-133">전송된 구매 주문을 처리하는 것 외에도 서비스 작업은 주문 상태에 대해 클라이언트에 의존합니다.</span><span class="sxs-lookup"><span data-stu-id="bae3f-133">The service operation, in addition to processing the submitted purchase order, replies back to the client about the status of the order.</span></span>

```csharp
public class OrderProcessorService : IOrderProcessor
{
    [OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = true)]
    public void SubmitPurchaseOrder(PurchaseOrder po, string reportOrderStatusTo)
    {
        Orders.Add(po);
        Console.WriteLine("Processing {0} ", po);
        Console.WriteLine("Sending back order status information");
        NetMsmqBinding msmqCallbackBinding = new NetMsmqBinding();
        msmqCallbackBinding.Security.Mode = NetMsmqSecurityMode.None;
        OrderStatusClient client = new OrderStatusClient(msmqCallbackBinding, new EndpointAddress(reportOrderStatusTo));
        // please note that the same transaction that is used to dequeue purchase order is used
        // to send back order status
        using (TransactionScope scope = new TransactionScope(TransactionScopeOption.Required))
        {
            client.OrderStatus(po.PONumber, po.Status);
            scope.Complete();
        }
    }
}
```

<span data-ttu-id="bae3f-134">사용할 클라이언트 바인딩은 구성 파일을 사용하여 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="bae3f-134">The client binding to use is specified using a configuration file.</span></span>

<span data-ttu-id="bae3f-135">MSMQ 큐 이름은 구성 파일의 appSettings 섹션에 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="bae3f-135">The MSMQ queue name is specified in an appSettings section of the configuration file.</span></span> <span data-ttu-id="bae3f-136">서비스의 엔드포인트는 구성 파일의 System.serviceModel 섹션에 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="bae3f-136">The endpoint for the service is defined in the System.serviceModel section of the configuration file.</span></span>

> [!NOTE]
> <span data-ttu-id="bae3f-137">MSMQ 큐 이름 및 엔드포인트 주소는 약간 다른 주소 지정 규칙을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="bae3f-137">The MSMQ queue name and endpoint address use slightly different addressing conventions.</span></span> <span data-ttu-id="bae3f-138">MSMQ 큐 이름은 로컬 컴퓨터에 점(.)을, 그 경로에는 백슬래시 구분 기호를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="bae3f-138">The MSMQ queue name uses a dot (.) for the local computer and backslash separators in its path.</span></span> <span data-ttu-id="bae3f-139">WCF 끝점 주소는 net.pipe: scheme을 지정 하 고, 로컬 컴퓨터에 "localhost"를 사용 하며, 경로에 슬래시를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="bae3f-139">The WCF endpoint address specifies a net.msmq: scheme, uses "localhost" for the local computer, and uses forward slashes in its path.</span></span> <span data-ttu-id="bae3f-140">원격 컴퓨터에서 호스트되는 큐에서 읽으려면 "." 및 "localhost"를 원격 컴퓨터 이름으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="bae3f-140">To read from a queue that is hosted on the remote computer, replace the "." and "localhost" to the remote computer name.</span></span>

<span data-ttu-id="bae3f-141">클래스 이름을 가진 .svc 파일은 WAS에서 서비스 코드를 호스트하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="bae3f-141">A .svc file with the name of the class is used to host the service code in WAS.</span></span>

<span data-ttu-id="bae3f-142">Service.svc 파일 자체는 `OrderProcessorService`를 만들기 위한 지시문을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="bae3f-142">The Service.svc file itself contains a directive to create the `OrderProcessorService`.</span></span>

`<%@ServiceHost language="c#" Debug="true" Service="Microsoft.ServiceModel.Samples.OrderProcessorService"%>`

<span data-ttu-id="bae3f-143">또한 Service.svc 파일은 System.Transactions.dll이 로드되도록 하는 어셈블리 지시문을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="bae3f-143">The Service.svc file also contains an assembly directive to ensure that System.Transactions.dll is loaded.</span></span>

`<%@Assembly name="System.Transactions, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"%>`

<span data-ttu-id="bae3f-144">클라이언트는 트랜잭션 범위를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="bae3f-144">The client creates a transaction scope.</span></span> <span data-ttu-id="bae3f-145">서비스와의 통신이 트랜잭션 범위 내에서 발생하므로 트랜잭션 범위는 모든 메시지가 성공하거나 실패하는 원자 단위로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="bae3f-145">Communication with the service takes place within the scope of the transaction, causing it to be treated as an atomic unit where all messages succeed or fail.</span></span> <span data-ttu-id="bae3f-146">트랜잭션은 트랜잭션 범위에서 `Complete`를 호출하여 커밋합니다.</span><span class="sxs-lookup"><span data-stu-id="bae3f-146">The transaction is committed by calling `Complete` on the transaction scope.</span></span>

```csharp
using (ServiceHost serviceHost = new ServiceHost(typeof(OrderStatusService)))
{
    // Open the ServiceHostBase to create listeners and start listening
    // for order status messages.
    serviceHost.Open();

    // Create a proxy with given client endpoint configuration
    OrderProcessorClient client = new OrderProcessorClient();

    // Create the purchase order
    PurchaseOrder po = new PurchaseOrder();
    po.CustomerId = "somecustomer.com";
    po.PONumber = Guid.NewGuid().ToString();

    PurchaseOrderLineItem lineItem1 = new PurchaseOrderLineItem();
    lineItem1.ProductId = "Blue Widget";
    lineItem1.Quantity = 54;
    lineItem1.UnitCost = 29.99F;

    PurchaseOrderLineItem lineItem2 = new PurchaseOrderLineItem();
    lineItem2.ProductId = "Red Widget";
    lineItem2.Quantity = 890;
    lineItem2.UnitCost = 45.89F;

    po.orderLineItems = new PurchaseOrderLineItem[2];
    po.orderLineItems[0] = lineItem1;
    po.orderLineItems[1] = lineItem2;

    //Create a transaction scope.
    using (TransactionScope scope = new
        TransactionScope(TransactionScopeOption.Required))
    {
        // Make a queued call to submit the purchase order
        client.SubmitPurchaseOrder(po,
       "net.msmq://localhost/private/ServiceModelSamplesOrder/OrderStatus");
        // Complete the transaction.
        scope.Complete();
    }

    //Closing the client gracefully closes the connection and cleans up
    //resources
    client.Close();

    Console.WriteLine();
    Console.WriteLine("Press <ENTER> to terminate client.");
    Console.ReadLine();

    // Close the ServiceHostBase to shutdown the service.
    serviceHost.Close();
    }
```

<span data-ttu-id="bae3f-147">클라이언트 코드는 서비스로부터 주문 상태를 수신하기 위해 `IOrderStatus` 계약을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="bae3f-147">The client code implements the `IOrderStatus` contract to receive order status from the service.</span></span> <span data-ttu-id="bae3f-148">이 경우 주문 상태가 출력됩니다.</span><span class="sxs-lookup"><span data-stu-id="bae3f-148">In this case, it prints out the order status.</span></span>

```csharp
[ServiceBehavior]
public class OrderStatusService : IOrderStatus
{
    [OperationBehavior(TransactionAutoComplete = true,
                        TransactionScopeRequired = true)]
    public void OrderStatus(string poNumber, string status)
    {
        Console.WriteLine("Status of order {0}:{1} ",
                                         poNumber , status);
    }
}
```

<span data-ttu-id="bae3f-149">주문 상태 큐는 `Main` 메서드에 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="bae3f-149">The order status queue is created in the `Main` method.</span></span> <span data-ttu-id="bae3f-150">다음 샘플 구성과 같이 클라이언트 구성에는 주문 상태 서비스를 호스트하는 주문 상태 서비스 구성이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="bae3f-150">The client configuration includes the order status service configuration to host the order status service, as shown in the following sample configuration.</span></span>

```xml
<appSettings>
    <!-- use appSetting to configure MSMQ queue name -->
    <add key="targetQueueName" value=".\private$\ServiceModelSamples/service.svc" />
    <add key="responseQueueName" value=".\private$\ServiceModelSamples/OrderStatus" />
  </appSettings>

<system.serviceModel>

    <services>
      <service
         name="Microsoft.ServiceModel.Samples.OrderStatusService">
        <!-- Define NetMsmqEndpoint -->
        <endpoint address="net.msmq://localhost/private/ServiceModelSamples/OrderStatus"
                  binding="netMsmqBinding"
                  contract="Microsoft.ServiceModel.Samples.IOrderStatus" />
      </service>
    </services>

    <client>
      <!-- Define NetMsmqEndpoint -->
      <endpoint name="OrderProcessorEndpoint"
                address="net.msmq://localhost/private/ServiceModelSamples/service.svc"
                binding="netMsmqBinding"
                contract="Microsoft.ServiceModel.Samples.IOrderProcessor" />
    </client>

  </system.serviceModel>
```

<span data-ttu-id="bae3f-151">샘플을 실행하면 클라이언트 및 서비스 동작이 서버 콘솔 창과 클라이언트 콘솔 창에 모두 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="bae3f-151">When you run the sample, the client and service activities are displayed in both the server and client console windows.</span></span> <span data-ttu-id="bae3f-152">클라이언트에서 서버 수신 메시지를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bae3f-152">You can see the server receive messages from the client.</span></span> <span data-ttu-id="bae3f-153">서버와 클라이언트를 종료하려면 각 콘솔 창에서 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="bae3f-153">Press ENTER in each console window to shut down the server and client.</span></span>

<span data-ttu-id="bae3f-154">클라이언트는 서버가 보낸 주문 상태 정보를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="bae3f-154">The client displays the order status information sent by the server:</span></span>

```console
Press <ENTER> to terminate client.
Status of order 70cf9d63-3dfa-4e69-81c2-23aa4478ebed :Pending
```

### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="bae3f-155">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="bae3f-155">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="bae3f-156">WAS 활성화에 필요한 IIS 7.0이 설치 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="bae3f-156">Ensure that IIS 7.0 is installed, as it is required for WAS activation.</span></span>

2. <span data-ttu-id="bae3f-157">[Windows Communication Foundation 샘플에 대 한 일회성 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)를 수행 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="bae3f-157">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span> <span data-ttu-id="bae3f-158">또한 WCF 비 HTTP 활성화 구성 요소를 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bae3f-158">In addition, you must install the WCF non-HTTP activation components:</span></span>

    1. <span data-ttu-id="bae3f-159">**시작** 메뉴에서 **제어판**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bae3f-159">From the **Start** menu, choose **Control Panel**.</span></span>

    2. <span data-ttu-id="bae3f-160">**프로그램 및 기능**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bae3f-160">Select **Programs and Features**.</span></span>

    3. <span data-ttu-id="bae3f-161">**Windows 기능 사용/사용 안 함을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="bae3f-161">Click **Turn Windows Features on or off**.</span></span>

    4. <span data-ttu-id="bae3f-162">**기능 요약**에서 **기능 추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="bae3f-162">Under **Features Summary**, click **Add Features**.</span></span>

    5. <span data-ttu-id="bae3f-163">**Microsoft .NET Framework 3.0** 노드를 확장 하 고 **Windows Communication Foundation 비 HTTP 활성화** 기능을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="bae3f-163">Expand the **Microsoft .NET Framework 3.0** node and check the **Windows Communication Foundation Non-HTTP Activation** feature.</span></span>

3. <span data-ttu-id="bae3f-164">C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="bae3f-164">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>

4. <span data-ttu-id="bae3f-165">명령 창에서 client.exe를 실행하여 클라이언트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="bae3f-165">Run the client by executing client.exe from a command window.</span></span> <span data-ttu-id="bae3f-166">이렇게 하면 큐가 만들어지고 메시지가 큐에 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="bae3f-166">This creates the queue and sends a message to it.</span></span> <span data-ttu-id="bae3f-167">메시지를 읽는 서비스의 결과를 확인하기 위해 클라이언트를 실행된 상태로 둡니다.</span><span class="sxs-lookup"><span data-stu-id="bae3f-167">Leave the client running to see the result of the service reading the message</span></span>

5. <span data-ttu-id="bae3f-168">MSMQ 활성화 서비스는 기본적으로 네트워크 서비스로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="bae3f-168">The MSMQ activation service runs as Network Service by default.</span></span> <span data-ttu-id="bae3f-169">따라서 애플리케이션을 활성화하는 데 사용되는 큐는 네트워크 서비스에 대한 수신 및 피킹 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bae3f-169">Therefore, the queue that is used to activate the application must have receive and peek permissions for Network Service.</span></span> <span data-ttu-id="bae3f-170">다음과 같이 메시지 큐 MMC를 사용하여 이러한 권한을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bae3f-170">This can be added by using the Message Queuing MMC:</span></span>

    1. <span data-ttu-id="bae3f-171">**시작** 메뉴에서 **실행**을 클릭 한 다음 `Compmgmt.msc`를 입력 하 고 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="bae3f-171">From the **Start** menu, click **Run**, then type `Compmgmt.msc` and press ENTER.</span></span>

    2. <span data-ttu-id="bae3f-172">**서비스 및 응용 프로그램**에서 **메시지 큐**를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="bae3f-172">Under **Services and Applications**, expand **Message Queuing**.</span></span>

    3. <span data-ttu-id="bae3f-173">**개인 큐**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="bae3f-173">Click **Private Queues**.</span></span>

    4. <span data-ttu-id="bae3f-174">큐 (servicemodelsamples/서비스 .svc)를 마우스 오른쪽 단추로 클릭 하 고 **속성**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bae3f-174">Right-click the queue (servicemodelsamples/Service.svc) and choose **Properties**.</span></span>

    5. <span data-ttu-id="bae3f-175">**보안** 탭에서 **추가** 를 클릭 하 고 네트워크 서비스에 대 한 피킹 (peeking) 및 수신 권한을 부여 합니다.</span><span class="sxs-lookup"><span data-stu-id="bae3f-175">On the **Security** tab, click **Add** and give peek and receive permissions to Network Service.</span></span>

6. <span data-ttu-id="bae3f-176">MSMQ 활성화를 지원하도록 WAS(Windows Process Activation Service)를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="bae3f-176">Configure the Windows Process Activation Service (WAS) to support MSMQ activation.</span></span>

    <span data-ttu-id="bae3f-177">편의를 위해 다음 단계는 샘플 디렉터리에 있는 AddMsmqSiteBinding.cmd라는 배치 파일에서 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="bae3f-177">As a convenience, the following steps are implemented in a batch file called AddMsmqSiteBinding.cmd located in the sample directory.</span></span>

    1. <span data-ttu-id="bae3f-178">net.msmq 활성화를 지원하려면 먼저 기본 웹 사이트를 net.msmq 프로토콜에 바인딩해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bae3f-178">To support net.msmq activation, the default Web site must first be bound to the net.msmq protocol.</span></span> <span data-ttu-id="bae3f-179">이 작업은 IIS 7.0 관리 도구 집합과 함께 설치되는 appcmd.exe를 사용하여 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bae3f-179">This can be done using appcmd.exe, which is installed with the IIS 7.0 management toolset.</span></span> <span data-ttu-id="bae3f-180">권한이 높은 명령 프롬프트에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="bae3f-180">From an elevated (administrator) command prompt, run the following command.</span></span>

        ```console
        %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site"
        -+bindings.[protocol='net.msmq',bindingInformation='localhost']
        ```

        > [!NOTE]
        > <span data-ttu-id="bae3f-181">이 명령은 줄 바꿈 없이 한 줄로 입력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bae3f-181">This command is a single line of text.</span></span>

        <span data-ttu-id="bae3f-182">이 명령은 기본 웹 사이트에 net.msmq 사이트 바인딩을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="bae3f-182">This command adds a net.msmq site binding to the default Web site.</span></span>

    2. <span data-ttu-id="bae3f-183">사이트 내의 모든 애플리케이션이 공통된 net.msmq 바인딩을 공유하지만 각 애플리케이션에서 개별적으로 net.msmq 지원을 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bae3f-183">Although all applications within a site share a common net.msmq binding, each application can enable net.msmq support individually.</span></span> <span data-ttu-id="bae3f-184">/servicemodelsamples 애플리케이션에서 net.msmq를 사용하도록 설정하려면 권한이 높은 명령 프롬프트에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="bae3f-184">To enable net.msmq for the /servicemodelsamples application, run the following command from an elevated command prompt.</span></span>

        ```console
        %windir%\system32\inetsrv\appcmd.exe set app "Default Web Site/servicemodelsamples" /enabledProtocols:http,net.msmq
        ```

        > [!NOTE]
        > <span data-ttu-id="bae3f-185">이 명령은 줄 바꿈 없이 한 줄로 입력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bae3f-185">This command is a single line of text.</span></span>

        <span data-ttu-id="bae3f-186">이 명령을 사용 하면 `http://localhost/servicemodelsamples` 및 `net.msmq://localhost/servicemodelsamples`를 사용 하 여/servicemodelsamples 응용 프로그램에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bae3f-186">This command enables the /servicemodelsamples application to be accessed using `http://localhost/servicemodelsamples` and `net.msmq://localhost/servicemodelsamples`.</span></span>

7. <span data-ttu-id="bae3f-187">아직 설정하지 않은 경우 MSMQ 활성화 서비스를 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="bae3f-187">If you have not done so previously, ensure that the MSMQ activation service is enabled.</span></span> <span data-ttu-id="bae3f-188">**시작** 메뉴에서 **실행**을 클릭 하 고 `Services.msc`를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="bae3f-188">From the **Start** menu, click **Run**, and type `Services.msc`.</span></span> <span data-ttu-id="bae3f-189">**Net. Msmq 수신기 어댑터**에 대 한 서비스 목록을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="bae3f-189">Search the list of services for the **Net.Msmq Listener Adapter**.</span></span> <span data-ttu-id="bae3f-190">마우스 오른쪽 단추를 클릭 하 고 **속성**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bae3f-190">Right-click and select **Properties**.</span></span> <span data-ttu-id="bae3f-191">**시작 유형** 을 **자동**으로 설정 하 고 **적용** 을 클릭 한 다음 **시작** 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="bae3f-191">Set the **Startup Type** to **Automatic**, click **Apply** and click the **Start** button.</span></span> <span data-ttu-id="bae3f-192">이 단계는 Net.Msmq Listener Adapter 서비스를 처음 사용하기 전에 한 번만 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bae3f-192">This step must only be done once prior to the first usage of the Net.Msmq Listener Adapter service.</span></span>

8. <span data-ttu-id="bae3f-193">단일 컴퓨터 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)의 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="bae3f-193">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span> <span data-ttu-id="bae3f-194">또한 구매 주문 전송 시에 큐의 URI에서 컴퓨터 이름이 반영되도록 구매 주문을 전송하는 클라이언트에서 코드를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="bae3f-194">Additionally, change the code on the client that submits the purchase order to reflect the computer name in the URI of the queue when submitting the purchase order.</span></span> <span data-ttu-id="bae3f-195">다음 코드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="bae3f-195">Use the following code:</span></span>

    ```csharp
    client.SubmitPurchaseOrder(po, "net.msmq://localhost/private/ServiceModelSamples/OrderStatus");
    ```

9. <span data-ttu-id="bae3f-196">이 샘플에 대해 추가한 net.msmq 사이트 바인딩을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="bae3f-196">Remove the net.msmq site binding you added for this sample.</span></span>

    <span data-ttu-id="bae3f-197">편의를 위해 다음 단계는 샘플 디렉터리에 있는 RemoveMsmqSiteBinding.cmd라는 배치 파일에서 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="bae3f-197">As a convenience, the following steps are implemented in a batch file called RemoveMsmqSiteBinding.cmd located in the sample directory:</span></span>

    1. <span data-ttu-id="bae3f-198">권한이 높은 명령 프롬프트에서 다음 명령을 실행하여 사용된 프로토콜 목록에서 net.msmq를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="bae3f-198">Remove net.msmq from the list of enabled protocols by running the following command from an elevated command prompt.</span></span>

        ```console
        %windir%\system32\inetsrv\appcmd.exe set app "Default Web Site/servicemodelsamples" /enabledProtocols:http
        ```

        > [!NOTE]
        > <span data-ttu-id="bae3f-199">이 명령은 줄 바꿈 없이 한 줄로 입력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bae3f-199">This command is a single line of text.</span></span>

    2. <span data-ttu-id="bae3f-200">권한이 높은 명령 프롬프트에서 다음 명령을 실행하여 net.msmq 사이트 바인딩을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="bae3f-200">Remove the net.msmq site binding by running the following command from an elevated command prompt.</span></span>

        ```console
        %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site" --bindings.[protocol='net.msmq',bindingInformation='localhost']
        ```

        > [!NOTE]
        > <span data-ttu-id="bae3f-201">이 명령은 줄 바꿈 없이 한 줄로 입력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bae3f-201">This command is a single line of text.</span></span>

    > [!WARNING]
    > <span data-ttu-id="bae3f-202">배치 파일을 실행하면 DefaultAppPool이 .NET Framework 버전 2.0을 사용하여 실행되도록 다시 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="bae3f-202">Running the batch file will reset the DefaultAppPool to run using .NET Framework version 2.0.</span></span>

<span data-ttu-id="bae3f-203">기본적으로 `netMsmqBinding` 바인딩 전송을 사용하여 보안이 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="bae3f-203">By default with the `netMsmqBinding` binding transport, security is enabled.</span></span> <span data-ttu-id="bae3f-204">`MsmqAuthenticationMode` 및 `MsmqProtectionLevel` 속성은 모두 전송 보안의 형식을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="bae3f-204">Two properties, `MsmqAuthenticationMode` and `MsmqProtectionLevel`, together determine the type of transport security.</span></span> <span data-ttu-id="bae3f-205">기본적으로 인증 모드는 `Windows`로 설정되고 보호 수준은 `Sign`으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="bae3f-205">By default the authentication mode is set to `Windows` and the protection level is set to `Sign`.</span></span> <span data-ttu-id="bae3f-206">MSMQ에서 인증 및 서명 기능을 제공하려면 도메인에 속해 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bae3f-206">For MSMQ to provide the authentication and signing feature, it must be part of a domain.</span></span> <span data-ttu-id="bae3f-207">도메인에 속하지 않은 컴퓨터에서 이 샘플을 실행할 경우 "사용자의 내부 메시지 큐 인증서가 없습니다."라는 오류 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="bae3f-207">If you run this sample on a computer that is not part of a domain, the following error is received: "User's internal message queuing certificate does not exist".</span></span>

### <a name="to-run-the-sample-on-a-computer-joined-to-a-workgroup"></a><span data-ttu-id="bae3f-208">작업 그룹에 가입된 컴퓨터에서 샘플을 실행하려면</span><span class="sxs-lookup"><span data-stu-id="bae3f-208">To run the sample on a computer joined to a workgroup</span></span>

1. <span data-ttu-id="bae3f-209">컴퓨터가 도메인의 일부가 아닌 경우 다음 샘플 구성과 같이 인증 모드와 보호 수준을 none으로 설정하여 전송 보안을 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="bae3f-209">If your computer is not part of a domain, turn off transport security by setting the authentication mode and protection level to none as shown in the following sample configuration.</span></span>

    ```xml
    <bindings>
        <netMsmqBinding>
            <binding configurationName="TransactedBinding">
                <security mode="None"/>
            </binding>
        </netMsmqBinding>
    </bindings>
    ```

2. <span data-ttu-id="bae3f-210">샘플을 실행하기 전에 서버와 클라이언트 모두에서 구성을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="bae3f-210">Change the configuration on both the server and the client before you run the sample.</span></span>

    > [!NOTE]
    > <span data-ttu-id="bae3f-211">`security mode`를 `None`으로 설정하는 것은 `MsmqAuthenticationMode`, `MsmqProtectionLevel` 및 `Message` 보안을 `None`으로 설정하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="bae3f-211">Setting `security mode` to `None` is equivalent to setting `MsmqAuthenticationMode`, `MsmqProtectionLevel` and `Message` security to `None`.</span></span>

3. <span data-ttu-id="bae3f-212">작업 그룹에 가입된 컴퓨터에서 활성화를 사용하려면 활성화 서비스와 작업자 프로세스가 둘 다 특정 사용자 계정(두 경우에 동일해야 함)으로 실행되어야 하고 큐에는 해당 사용자 계정에 대한 ACL이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bae3f-212">To enable activation in a computer joined to a workgroup, both the activation service and the worker process must be run with a specific user account (must be same for both) and the queue must have ACLs for the specific user account.</span></span>

     <span data-ttu-id="bae3f-213">작업자 프로세스가 실행될 때 사용되는 ID를 변경하려면</span><span class="sxs-lookup"><span data-stu-id="bae3f-213">To change the identity that the worker process runs under:</span></span>

    1. <span data-ttu-id="bae3f-214">Inetmgr.exe를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="bae3f-214">Run Inetmgr.exe.</span></span>

    2. <span data-ttu-id="bae3f-215">**응용 프로그램 풀**에서 **AppPool** (일반적으로 **DefaultAppPool**)을 마우스 오른쪽 단추로 클릭 하 고 **응용 프로그램 풀 기본값 설정**...을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bae3f-215">Under **Application Pools**, right-click the **AppPool** (typically **DefaultAppPool**) and choose **Set Application Pool Defaults…**.</span></span>

    3. <span data-ttu-id="bae3f-216">특정 사용자 계정을 사용하도록 ID 속성을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="bae3f-216">Change the Identity properties to use the specific user account.</span></span>

     <span data-ttu-id="bae3f-217">활성화 서비스가 실행될 때 사용되는 ID를 변경하려면</span><span class="sxs-lookup"><span data-stu-id="bae3f-217">To change the identity that the Activation Service runs under:</span></span>

    1. <span data-ttu-id="bae3f-218">Services.msc를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="bae3f-218">Run Services.msc.</span></span>

    2. <span data-ttu-id="bae3f-219">**MsmqListener 어댑터**를 마우스 오른쪽 단추로 클릭 하 고 **속성**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bae3f-219">Right-click the **Net.MsmqListener Adapter**, and choose **Properties**.</span></span>

4. <span data-ttu-id="bae3f-220">**로그온** 탭에서 계정을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="bae3f-220">Change the account in the **LogOn** tab.</span></span>

5. <span data-ttu-id="bae3f-221">작업 그룹에서 서비스는 또한 제한되지 않은 토큰을 사용하여 실행되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bae3f-221">In workgroup, the service must also run using an unrestricted token.</span></span> <span data-ttu-id="bae3f-222">이렇게 하려면 명령 창에서 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="bae3f-222">To do this, run the following in a command window:</span></span>

    ```console
    sc sidtype netmsmqactivator unrestricted
    ```

## <a name="see-also"></a><span data-ttu-id="bae3f-223">참조</span><span class="sxs-lookup"><span data-stu-id="bae3f-223">See also</span></span>

- <span data-ttu-id="bae3f-224">[AppFabric 호스팅 및 지 속성 샘플](https://docs.microsoft.com/previous-versions/appfabric/ff383418(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="bae3f-224">[AppFabric Hosting and Persistence Samples](https://docs.microsoft.com/previous-versions/appfabric/ff383418(v=azure.10))</span></span>
