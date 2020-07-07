---
title: '방법: 관리 코드 DCOM을 WCF로 마이그레이션'
description: 서버와 클라이언트 간 DCOM(Distributed Component Object Model) 관리 코드 호출을 WCF(Windows Communication Foundation)로 마이그레이션합니다.
ms.date: 03/30/2017
ms.assetid: 52961ffc-d1c7-4f83-832c-786444b951ba
ms.openlocfilehash: cc6ac1dd01e17bb184d1f1faca372134d6130d33
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85619093"
---
# <a name="how-to-migrate-managed-code-dcom-to-wcf"></a><span data-ttu-id="aa040-103">방법: 관리 코드 DCOM을 WCF로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="aa040-103">How to: Migrate Managed-Code DCOM to WCF</span></span>
<span data-ttu-id="aa040-104">WCF(Windows Communication Foundation)는 분산 환경에서 서버와 클라이언트 간에 관리 코드 호출에 대해 DCOM(Distributed Component Object Model)보다 권장되는 안전한 선택 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="aa040-104">Windows Communication Foundation (WCF) is the recommended and secure choice over Distributed Component Object Model (DCOM) for managed code calls between servers and clients in a distributed environment.</span></span> <span data-ttu-id="aa040-105">이 문서에서는 다음과 같은 시나리오에 대해 코드를 DCOM에서 WCF로 마이그레이션하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="aa040-105">This article shows how you to migrate code from DCOM to WCF for the following scenarios.</span></span>  
  
- <span data-ttu-id="aa040-106">원격 서비스에서 값 방식으로 클라이언트에 개체를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="aa040-106">The remote service returns an object by-value to the client</span></span>  
  
- <span data-ttu-id="aa040-107">클라이언트에서 값 방식으로 원격 서비스에 개체를 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="aa040-107">The client sends an object by-value to the remote service</span></span>  
  
- <span data-ttu-id="aa040-108">보안상 클라이언트에서 값 방식으로 서비스에 개체를 전송하는 기능은 WCF에서 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="aa040-108">The remote service returns an object by-reference to the client</span></span>  
  
 <span data-ttu-id="aa040-109">보안상 클라이언트에서 참조 방식으로 서비스에 개체를 전송하는 기능은 WCF에서 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="aa040-109">For security reasons, sending an object by-reference from the client to the service is not allowed in WCF.</span></span> <span data-ttu-id="aa040-110">클라이언트와 서버 간에 서로 대화하는 데 필요한 시나리오는 WCF에서 이중 서비스를 사용하여 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa040-110">A scenario that requires a conversation back and forth between client and server can be achieved in WCF using a duplex service.</span></span>  <span data-ttu-id="aa040-111">이중 서비스에 대한 자세한 내용은 [이중 서비스](../wcf/feature-details/duplex-services.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aa040-111">For more information about duplex services, see [Duplex Services](../wcf/feature-details/duplex-services.md).</span></span>  
  
 <span data-ttu-id="aa040-112">WCF 서비스와 해당 서비스에 대한 클라이언트를 만드는 방법에 대한 자세한 내용은 [기본 WCF 프로그래밍](../wcf/basic-wcf-programming.md), [서비스 디자인 및 구현](../wcf/designing-and-implementing-services.md) 및 [클라이언트 빌드](../wcf/building-clients.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aa040-112">For more details about creating WCF services and clients for those services, see [Basic WCF Programming](../wcf/basic-wcf-programming.md), [Designing and Implementing Services](../wcf/designing-and-implementing-services.md), and [Building Clients](../wcf/building-clients.md).</span></span>  
  
## <a name="dcom-example-code"></a><span data-ttu-id="aa040-113">DCOM 예제 코드</span><span class="sxs-lookup"><span data-stu-id="aa040-113">DCOM example code</span></span>  
 <span data-ttu-id="aa040-114">이러한 시나리오에서 WCF를 사용하여 설명한 DCOM 인터페이스의 구조는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="aa040-114">For these scenarios, the DCOM interfaces that are illustrated using WCF have the following structure:</span></span>  
  
```csharp  
[ComVisible(true)]  
[Guid("AA9C4CDB-55EA-4413-90D2-843F1A49E6E6")]  
public interface IRemoteService  
{  
   Customer GetObjectByValue();  
   IRemoteObject GetObjectByReference();  
   void SendObjectByValue(Customer customer);  
}  
  
[ComVisible(true)]  
[Guid("A12C98DE-B6A1-463D-8C24-81E4BBC4351B")]  
public interface IRemoteObject  
{  
}  
  
public class Customer  
{  
}  
```  
  
## <a name="the-service-returns-an-object-by-value"></a><span data-ttu-id="aa040-115">서비스에서 값 방식으로 개체 반환</span><span class="sxs-lookup"><span data-stu-id="aa040-115">The service returns an object by-value</span></span>  
 <span data-ttu-id="aa040-116">이 시나리오에서는 서비스를 호출하고 해당 메서드가 개체를 반환한 다음 서버에서 값 방식으로 클라이언트에 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa040-116">For this scenario, you make a call to a service and it method returns an object, which is passed by-value from the server to the client.</span></span> <span data-ttu-id="aa040-117">이 시나리오는 다음과 같은 COM 호출을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="aa040-117">This scenario represents the following COM call:</span></span>  
  
```csharp  
public interface IRemoteService  
{  
    Customer GetObjectByValue();  
}  
```  
  
 <span data-ttu-id="aa040-118">이 시나리오에서 클라이언트는 원격 서비스에서 개체의 역직렬화된 복사본을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="aa040-118">In this scenario, the client receives a deserialized copy of an object from the remote service.</span></span> <span data-ttu-id="aa040-119">클라이언트는 서비스를 콜백하지 않고 이 로컬 복사본과 상호 작용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa040-119">The client can interact with this local copy without calling back to the service.</span></span>  <span data-ttu-id="aa040-120">즉, 로컬 복사본에 대해 메서드를 호출할 때 서비스가 어떤 방식으로도 관련되지 않음을 클라이언트가 확신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa040-120">In other words, the client is guaranteed the service will not be involved in any way when methods on the local copy are called.</span></span> <span data-ttu-id="aa040-121">WCF는 항상 값 방식으로 서비스에서 개체를 반환하므로, 다음 단계에서는 일반 WCF 서비스를 만드는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="aa040-121">WCF always returns objects from the service by value, so the following steps describe creating a regular WCF service.</span></span>  
  
### <a name="step-1-define-the-wcf-service-interface"></a><span data-ttu-id="aa040-122">1단계: WCF 서비스 인터페이스 정의</span><span class="sxs-lookup"><span data-stu-id="aa040-122">Step 1: Define the WCF service interface</span></span>  
 <span data-ttu-id="aa040-123">WCF 서비스에 대한 공용 인터페이스를 정의하고 [<xref:System.ServiceModel.ServiceContractAttribute>] 특성으로 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="aa040-123">Define a public interface for the WCF service and mark it with the [<xref:System.ServiceModel.ServiceContractAttribute>] attribute.</span></span>  <span data-ttu-id="aa040-124">클라이언트에 노출하려는 메서드를 [<xref:System.ServiceModel.OperationContractAttribute>] 특성으로 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="aa040-124">Mark the methods you want to expose to clients with the [<xref:System.ServiceModel.OperationContractAttribute>] attribute.</span></span> <span data-ttu-id="aa040-125">다음 예제에서는 이러한 특성을 사용하여 클라이언트가 호출할 수 있는 서버 쪽 인터페이스 및 인터페이스 메서드를 식별하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="aa040-125">The following example shows using these attributes to identify the server-side interface and interface methods a client can call.</span></span> <span data-ttu-id="aa040-126">이 시나리오에 사용되는 메서드는 굵게 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa040-126">The method used for this scenario is shown in bold.</span></span>  
  
```csharp  
using System.Runtime.Serialization;  
using System.ServiceModel;  
using System.ServiceModel.Web;
. . .  
[ServiceContract]  
public interface ICustomerManager  
{  
    [OperationContract]  
    void StoreCustomer(Customer customer);  
  
    [OperationContract]     Customer GetCustomer(string firstName, string lastName);
  
}  
```  
  
### <a name="step-2-define-the-data-contract"></a><span data-ttu-id="aa040-127">2단계: 데이터 계약 정의</span><span class="sxs-lookup"><span data-stu-id="aa040-127">Step 2: Define the data contract</span></span>  
 <span data-ttu-id="aa040-128">다음에는 서비스와 해당 클라이언트 간에 데이터를 교환하는 방법을 설명하는 서비스에 대한 데이터 계약을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa040-128">Next you should create a data contract for the service, which will describe how the data will be exchanged between the service and its clients.</span></span>  <span data-ttu-id="aa040-129">데이터 계약에 설명된 클래스는 [<xref:System.Runtime.Serialization.DataContractAttribute>] 특성으로 표시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa040-129">Classes described in the data contract should be marked with the [<xref:System.Runtime.Serialization.DataContractAttribute>] attribute.</span></span> <span data-ttu-id="aa040-130">클라이언트와 서버 둘 다에 표시할 개별 속성 또는 필드는 [<xref:System.Runtime.Serialization.DataMemberAttribute>] 특성으로 표시되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa040-130">The individual properties or fields you want visible to both client and server should be marked with the [<xref:System.Runtime.Serialization.DataMemberAttribute>] attribute.</span></span> <span data-ttu-id="aa040-131">데이터 계약의 클래스에서 파생된 형식을 허용하려면 [<xref:System.Runtime.Serialization.KnownTypeAttribute>] 특성을 사용하여 식별해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa040-131">If you want types derived from a class in the data contract to be allowed, you must identify them with the [<xref:System.Runtime.Serialization.KnownTypeAttribute>] attribute.</span></span> <span data-ttu-id="aa040-132">WCF는 서비스 인터페이스의 형식 및 알려진 형식으로 식별된 형식만 직렬화하거나 역직렬화합니다.</span><span class="sxs-lookup"><span data-stu-id="aa040-132">WCF will only serialize or deserialize types in the service interface and types identified as known types.</span></span> <span data-ttu-id="aa040-133">알려진 형식이 아닌 형식을 사용하려고 하면 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="aa040-133">If you attempt to use a type that is not a known type, an exception will occur.</span></span>  
  
 <span data-ttu-id="aa040-134">데이터 계약에 대한 자세한 내용은 [데이터 계약](../wcf/samples/data-contracts.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aa040-134">For more information about data contracts, see [Data Contracts](../wcf/samples/data-contracts.md).</span></span>  
  
```csharp  
[DataContract]  
[KnownType(typeof(PremiumCustomer))]  
public class Customer  
{  
    [DataMember]  
    public string Firstname;  
    [DataMember]  
    public string Lastname;  
    [DataMember]  
    public Address DefaultDeliveryAddress;  
    [DataMember]  
    public Address DefaultBillingAddress;  
}  
 [DataContract]  
public class PremiumCustomer : Customer  
{  
    [DataMember]  
    public int AccountID;  
}  
  
 [DataContract]  
public class Address  
{  
    [DataMember]  
    public string Street;  
    [DataMember]  
    public string Zipcode;  
    [DataMember]  
    public string City;  
    [DataMember]  
    public string State;  
    [DataMember]  
    public string Country;  
}  
```  
  
### <a name="step-3-implement-the-wcf-service"></a><span data-ttu-id="aa040-135">3단계: WCF 서비스 구현</span><span class="sxs-lookup"><span data-stu-id="aa040-135">Step 3: Implement the WCF service</span></span>  
 <span data-ttu-id="aa040-136">다음에는 이전 단계에서 정의한 인터페이스를 구현하는 WCF 서비스 클래스를 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa040-136">Next, you should implement the WCF service class that implements the interface you defined in the previous step.</span></span>  
  
```csharp  
public class CustomerService: ICustomerManager
{  
    public void StoreCustomer(Customer customer)  
    {  
        // write to a database  
    }  
    public Customer GetCustomer(string firstName, string lastName)  
    {  
        // read from a database  
    }  
}  
```  
  
### <a name="step-4-configure-the-service-and-the-client"></a><span data-ttu-id="aa040-137">4단계: 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="aa040-137">Step 4: Configure the service and the client</span></span>  
 <span data-ttu-id="aa040-138">WCF 서비스를 실행하려면 특정 WCF 바인딩을 사용하여 특정 URL에 해당 서비스 인터페이스를 노출하는 엔드포인트를 선언해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa040-138">To run a WCF service, you need to declare an endpoint that exposes that service interface at a specific URL using a specific WCF binding.</span></span> <span data-ttu-id="aa040-139">바인딩은 클라이언트와 서버가 통신하는 데 필요한 전송, 인코딩 및 프로토콜 세부 정보를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="aa040-139">A binding specifies the transport, encoding and protocol details for the clients and server to communicate.</span></span> <span data-ttu-id="aa040-140">일반적으로 서비스 프로젝트의 구성 파일(web.config)에 바인딩을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="aa040-140">You typically add bindings to the service project’s configuration file (web.config).</span></span> <span data-ttu-id="aa040-141">다음은 예제 서비스에 대한 바인딩 항목을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="aa040-141">The following shows a binding entry for the example service:</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <services>  
      <service name="Server.CustomerService">  
        <endpoint address="http://localhost:8083/CustomerManager"
                  binding="basicHttpBinding"  
                  contract="Shared.ICustomerManager" />  
      </service>  
    </services>  
  </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="aa040-142">다음에는 서비스에서 지정된 바인딩 정보와 일치하도록 클라이언트를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa040-142">Next, you need to configure the client to match the binding information specified by the service.</span></span> <span data-ttu-id="aa040-143">이렇게 하려면 클라이언트의 애플리케이션 구성 파일(app.config)에 다음을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="aa040-143">To do so, add the following to the client’s application configuration (app.config) file.</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <client>  
      <endpoint name="customermanager"
                address="http://localhost:8083/CustomerManager"
                binding="basicHttpBinding"
                contract="Shared.ICustomerManager"/>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
### <a name="step-5-run-the-service"></a><span data-ttu-id="aa040-144">5단계: 서비스 실행</span><span class="sxs-lookup"><span data-stu-id="aa040-144">Step 5: Run the service</span></span>  
 <span data-ttu-id="aa040-145">끝으로, 서비스 앱에 다음 줄을 추가하고 앱을 시작하여 콘솔 애플리케이션에서 자체 호스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa040-145">Finally, you can self-host it in a console application by adding the following lines to the service app, and starting the app.</span></span> <span data-ttu-id="aa040-146">WCF 서비스 애플리케이션을 호스트하는 다른 방법에 대한 자세한 내용은 [호스팅 서비스](../wcf/hosting-services.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aa040-146">For more information about other ways to host a WCF service application, [Hosting Services](../wcf/hosting-services.md).</span></span>  
  
```csharp  
ServiceHost customerServiceHost = new ServiceHost(typeof(CustomerService));  
customerServiceHost.Open();  
```  
  
### <a name="step-6-call-the-service-from-the-client"></a><span data-ttu-id="aa040-147">6단계: 클라이언트에서 서비스 호출</span><span class="sxs-lookup"><span data-stu-id="aa040-147">Step 6: Call the service from the client</span></span>  
 <span data-ttu-id="aa040-148">클라이언트에서 서비스를 호출하려면 서비스에 대한 채널 팩터리를 만들고 채널을 요청해야 합니다. 그러면 클라이언트에서 직접 `GetCustomer` 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa040-148">To call the service from the client, you need to create a channel factory for the service, and request a channel, which will enable you to directly call the `GetCustomer` method directly from the client.</span></span> <span data-ttu-id="aa040-149">채널은 서비스의 인터페이스를 구현하고 내부 요청/응답 논리를 자동으로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="aa040-149">The channel implements the service’s interface and handles the underlying request/reply logic for you.</span></span>  <span data-ttu-id="aa040-150">해당 메서드 호출의 반환 값은 역직렬화된 서비스 응답 복사본입니다.</span><span class="sxs-lookup"><span data-stu-id="aa040-150">The return value from that method call is the deserialized copy of the service response.</span></span>  
  
```csharp  
ChannelFactory<ICustomerManager> factory =
     new ChannelFactory<ICustomerManager>("customermanager");  
ICustomerManager service = factory.CreateChannel();  
Customer customer = service.GetCustomer("Mary", "Smith");  
```  
  
## <a name="the-client-sends-a-by-value-object-to-the-server"></a><span data-ttu-id="aa040-151">클라이언트에서 값 방식으로 서버에 개체 전송</span><span class="sxs-lookup"><span data-stu-id="aa040-151">The client sends a by-value object to the server</span></span>  
 <span data-ttu-id="aa040-152">이 시나리오에서는 클라이언트가 값 방식으로 서버에 개체를 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="aa040-152">In this scenario, the client sends an object to the server, by-value.</span></span> <span data-ttu-id="aa040-153">즉, 서버가 개체의 역직렬화된 복사본을 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa040-153">This means that the server will receive a deserialized copy of the object.</span></span>  <span data-ttu-id="aa040-154">서버는 해당 복사본에 대해 메서드를 호출할 수 있으며 클라이언트 코드에 대한 콜백이 없음을 확신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa040-154">The server can call methods on that copy and be guaranteed there is no callback into client code.</span></span> <span data-ttu-id="aa040-155">앞에서 설명한 것처럼 데이터의 일반 WCF 교환은 값 방식입니다.</span><span class="sxs-lookup"><span data-stu-id="aa040-155">As mentioned previously, normal WCF exchanges of data are by-value.</span></span>  <span data-ttu-id="aa040-156">이 경우 이러한 개체 중 하나에 대해 메서드를 호출하면 로컬에서만 실행되며 클라이언트에서 코드를 호출하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="aa040-156">This guarantees that calling methods on one of these objects executes locally only – it will not invoke code on the client.</span></span>  
  
 <span data-ttu-id="aa040-157">이 시나리오는 다음과 같은 COM 메서드 호출을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="aa040-157">This scenario represents the following COM method call:</span></span>  
  
```csharp  
public interface IRemoteService  
{  
    void SendObjectByValue(Customer customer);  
}  
```  
  
 <span data-ttu-id="aa040-158">이 시나리오에서는 첫 번째 예제에 표시된 것과 동일한 서비스 인터페이스 및 데이터 계약을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="aa040-158">This scenario uses the same service interface and data contract as shown in the first example.</span></span> <span data-ttu-id="aa040-159">또한 클라이언트와 서비스가 동일한 방식으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa040-159">In addition, the client and service will be configured in the same way.</span></span> <span data-ttu-id="aa040-160">이 예제에서는 동일한 방식으로 개체를 전송 및 실행하기 위해 채널을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="aa040-160">In this example, a channel is created to send the object and run the same way.</span></span> <span data-ttu-id="aa040-161">그러나 이 예제의 경우 값 방식으로 개체를 전달하여 서비스를 호출하는 클라이언트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="aa040-161">However, for this example, you will create a client that calls the service, passing an object by-value.</span></span> <span data-ttu-id="aa040-162">클라이언트가 서비스 계약에서 호출하는 서비스 메서드는 굵게 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa040-162">The service method the client will call in the service contract is shown in bold:</span></span>  
  
```csharp  
[ServiceContract]  
public interface ICustomerManager  
{  
    [OperationContract]     void StoreCustomer(Customer customer);  
  
    [OperationContract]  
    Customer GetCustomer(string firstName, string lastName);  
}  
```  
  
### <a name="add-code-to-the-client-that-sends-a-by-value-object"></a><span data-ttu-id="aa040-163">클라이언트에 값 방식으로 개체를 전송하는 코드 추가</span><span class="sxs-lookup"><span data-stu-id="aa040-163">Add code to the client that sends a by-value object</span></span>  
 <span data-ttu-id="aa040-164">다음 코드에서는 클라이언트가 새로운 값 방식 customer 개체를 만들고, `ICustomerManager` 서비스와 통신하는 채널을 만든 다음 customer 개체를 전송하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="aa040-164">The following code shows how the client creates a new by-value customer object, creates a channel to communicate with the `ICustomerManager` service, and sends the customer object to it.</span></span>  
  
 <span data-ttu-id="aa040-165">customer 개체가 직렬화되어 서비스로 전송되며, 서비스에서 해당 개체의 새 복사본으로 역직렬화됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa040-165">The customer object will be serialized, and sent to the service, where it is deserialized by the service into a new copy of that object.</span></span>  <span data-ttu-id="aa040-166">이 개체에 대한 서비스를 호출하는 모든 메서드는 서버에서 로컬로만 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa040-166">Any methods the service calls on this object will execute only locally on the server.</span></span> <span data-ttu-id="aa040-167">이 코드는 파생된 형식(`PremiumCustomer`)을 보내는 것을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="aa040-167">It’s important to note that this code illustrates sending a derived type (`PremiumCustomer`).</span></span>  <span data-ttu-id="aa040-168">서비스 계약에는 `Customer` 개체가 필요하지만 서비스 데이터 계약에서 [<xref:System.Runtime.Serialization.KnownTypeAttribute>] 특성을 사용하여 `PremiumCustomer`도 허용됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="aa040-168">The service contract expects a `Customer` object, but the service data contract uses the [<xref:System.Runtime.Serialization.KnownTypeAttribute>] attribute to indicate that `PremiumCustomer` is also allowed.</span></span>  <span data-ttu-id="aa040-169">WCF에서 이 서비스 인터페이스를 통해 다른 형식을 직렬화하거나 역직렬화하려고 하면 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="aa040-169">WCF will fail attempts to serialize or deserialize any other type via this service interface.</span></span>  
  
```csharp  
PremiumCustomer customer = new PremiumCustomer();  
customer.Firstname = "John";  
customer.Lastname = "Doe";  
customer.DefaultBillingAddress = new Address();  
customer.DefaultBillingAddress.Street = "One Microsoft Way";  
customer.DefaultDeliveryAddress = customer.DefaultBillingAddress;  
customer.AccountID = 42;  
  
ChannelFactory<ICustomerManager> factory =  
   new ChannelFactory<ICustomerManager>("customermanager");  
ICustomerManager customerManager = factory.CreateChannel();  
customerManager.StoreCustomer(customer);  
```  
  
## <a name="the-service-returns-an-object-by-reference"></a><span data-ttu-id="aa040-170">서비스에서 참조 방식으로 개체 반환</span><span class="sxs-lookup"><span data-stu-id="aa040-170">The service returns an object by reference</span></span>  
 <span data-ttu-id="aa040-171">이 시나리오에서는 클라이언트 앱이 원격 서비스를 호출하고 해당 메서드가 개체를 반환한 다음 서비스에서 참조 방식으로 클라이언트에 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa040-171">For this scenario, the client app makes a call to the remote service and the method returns an object, which is passed by reference from the service to the client.</span></span>  
  
 <span data-ttu-id="aa040-172">앞에서 설명한 것처럼 WCF 서비스는 항상 값 방식으로 개체를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="aa040-172">As mentioned previously, WCF services always return object by value.</span></span>  <span data-ttu-id="aa040-173">그러나 <xref:System.ServiceModel.EndpointAddress10> 클래스를 사용하여 비슷한 결과를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa040-173">However, you can achieve a similar result by using the <xref:System.ServiceModel.EndpointAddress10> class.</span></span>  <span data-ttu-id="aa040-174"><xref:System.ServiceModel.EndpointAddress10>은 서버에서 세션 참조 방식 개체를 가져오기 위해 클라이언트가 사용할 수 있는 직렬화 가능 값 방식 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="aa040-174">The <xref:System.ServiceModel.EndpointAddress10> is a serializable by-value object that can be used by the client to obtain a sessionful by-reference object on the server.</span></span>  
  
 <span data-ttu-id="aa040-175">이 시나리오에 표시된 WCF의 참조 방식 개체 동작은 DCOM과 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="aa040-175">The behavior of the by-reference object in WCF shown in this scenario is different than DCOM.</span></span>  <span data-ttu-id="aa040-176">DCOM에서는 서버가 참조 방식 개체를 클라이언트에 직접 반환할 수 있으며, 클라이언트가 서버에서 실행되는 해당 개체의 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa040-176">In DCOM, the server can return a by-reference object to the client directly, and the client can call that object’s methods, which execute on the server.</span></span>  <span data-ttu-id="aa040-177">그러나 WCF에서는 반환된 개체가 항상 값 방식입니다.</span><span class="sxs-lookup"><span data-stu-id="aa040-177">In WCF, however, the object returned is always by-value.</span></span>  <span data-ttu-id="aa040-178">클라이언트는 <xref:System.ServiceModel.EndpointAddress10>으로 표시된 해당 값 방식 개체를 사용하여 고유한 세션 참조 방식 개체를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa040-178">The client must take that by-value object, represented by <xref:System.ServiceModel.EndpointAddress10> and use it to create its own sessionful by-reference object.</span></span>  <span data-ttu-id="aa040-179">세션 개체에 대한 클라이언트 메서드 호출은 서버에서 실행됩니다. 즉, WCF의 이 참조 방식 개체는 세션으로 구성된 일반 WCF 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="aa040-179">The client method calls on the sessionful object execute on the server.In other words, this by-reference object in WCF is a normal WCF service that is configured to be sessionful.</span></span>  
  
 <span data-ttu-id="aa040-180">WCF에서 세션은 두 엔드포인트 간에 전송된 여러 메시지를 서로 관련시키는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="aa040-180">In WCF, a session is a way of correlating multiple messages sent between two endpoints.</span></span>  <span data-ttu-id="aa040-181">즉, 클라이언트가 이 서비스에 대한 연결을 확보하고 나면 클라이언트와 서버 간에 세션이 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa040-181">This means that once a client obtains a connection to this service, a session will be established between the client and the server.</span></span>  <span data-ttu-id="aa040-182">클라이언트는 이 단일 세션 내에서 수행되는 모든 상호 작용을 수행하는 데 하나의 고유한 서버 쪽 개체 인스턴스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="aa040-182">The client will use a single unique instance of the server-side object for all its interactions within this single session.</span></span> <span data-ttu-id="aa040-183">세션 WCF 계약은 연결 지향 네트워크 요청/응답 패턴과 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="aa040-183">Sessionful WCF contracts are similar to connection-oriented network request/response patterns.</span></span>  
  
 <span data-ttu-id="aa040-184">이 시나리오는 다음과 같은 DCOM 메서드로 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="aa040-184">This scenario is represented by the following DCOM method.</span></span>  
  
```csharp  
public interface IRemoteService  
{  
    IRemoteObject GetObjectByReference();  
}  
```  
  
### <a name="step-1-define-the-sessionful-wcf-service-interface-and-implementation"></a><span data-ttu-id="aa040-185">1단계: 세션 WCF 서비스 인터페이스와 구현 정의</span><span class="sxs-lookup"><span data-stu-id="aa040-185">Step 1: Define the Sessionful WCF service interface and implementation</span></span>  
 <span data-ttu-id="aa040-186">먼저 세션 개체를 포함하는 WCF 서비스 인터페이스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="aa040-186">First, define a WCF service interface that contains the sessionful object.</span></span>  
  
 <span data-ttu-id="aa040-187">이 코드에서 세션 개체는 `ServiceContract` 특성으로 표시됩니다.이 경우 개체는 일반 WCF 서비스 인터페이스로 식별됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa040-187">In this code, the sessionful object is marked with the `ServiceContract` attribute, which identifies it as a regular WCF service interface.</span></span>  <span data-ttu-id="aa040-188">또한 <xref:System.ServiceModel.ServiceContractAttribute.SessionMode%2A> 속성이 세션 서비스를 나타내도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa040-188">In addition, the <xref:System.ServiceModel.ServiceContractAttribute.SessionMode%2A> property is set to indicate it will be a sessionful service.</span></span>  
  
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
  
 <span data-ttu-id="aa040-189">다음 코드에서는 서비스 구현을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="aa040-189">The following code shows the service implementation.</span></span>  
  
 <span data-ttu-id="aa040-190">서비스가 [ServiceBehavior] 특성으로 표시되고 해당 InstanceContextMode 속성이 InstanceContextMode.PerSessions로 설정되어 각 세션에 대해 이 형식의 고유 인스턴스를 만들어야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="aa040-190">The service is marked with the [ServiceBehavior] attribute, and its InstanceContextMode property set to InstanceContextMode.PerSessions to indicate that a unique instance of this type should be created for each session.</span></span>  
  
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
  
### <a name="step-2-define-the-wcf-factory-service-for-the-sessionful-object"></a><span data-ttu-id="aa040-191">2단계: 세션 개체에 대한 WCF 팩터리 서비스 정의</span><span class="sxs-lookup"><span data-stu-id="aa040-191">Step 2: Define the WCF factory service for the sessionful object</span></span>  
 <span data-ttu-id="aa040-192">세션 개체를 만드는 서비스를 정의 및 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa040-192">The service that creates the sessionful object must be defined and implemented.</span></span> <span data-ttu-id="aa040-193">다음 코드에서는 이 작업을 수행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="aa040-193">The following code shows how to do this.</span></span> <span data-ttu-id="aa040-194">이 코드에서는 <xref:System.ServiceModel.EndpointAddress10> 개체를 반환하는 다른 WCF 서비스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="aa040-194">This code creates another WCF service that returns an <xref:System.ServiceModel.EndpointAddress10> object.</span></span>  <span data-ttu-id="aa040-195">이는 세션 개체를 만드는 데 사용할 수 있는 직렬화 가능한 형식의 엔드포인트입니다.</span><span class="sxs-lookup"><span data-stu-id="aa040-195">This is a serializable form of an endpoint the can use to create the session-full object.</span></span>  
  
```csharp  
[ServiceContract]  
    public interface ISessionBoundFactory  
    {  
        [OperationContract]  
        EndpointAddress10 GetInstanceAddress();  
    }  
```  
  
 <span data-ttu-id="aa040-196">이 서비스의 구현은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="aa040-196">The following is the implementation of this service.</span></span> <span data-ttu-id="aa040-197">이 구현에서는 세션 개체를 만들기 위해 단일 채널 팩터리를 유지 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="aa040-197">This implementation maintains a singleton channel factory to create sessionful objects.</span></span>  <span data-ttu-id="aa040-198">`GetInstanceAddress`를 호출하면 채널을 만들고 이 채널과 연결된 원격 주소를 가리키는 <xref:System.ServiceModel.EndpointAddress10> 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="aa040-198">When `GetInstanceAddress` is called, it creates a channel and creates an <xref:System.ServiceModel.EndpointAddress10> object that points to the remote address associated with this channel.</span></span>   <span data-ttu-id="aa040-199"><xref:System.ServiceModel.EndpointAddress10>은 값 방식으로 클라이언트에 반환될 수 있는 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="aa040-199"><xref:System.ServiceModel.EndpointAddress10> is a data type that can be returned to the client by-value.</span></span>
  
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
  
### <a name="step-3-configure-and-start-the-wcf-services"></a><span data-ttu-id="aa040-200">3단계: WCF 서비스 구성 및 시작</span><span class="sxs-lookup"><span data-stu-id="aa040-200">Step 3: Configure and start the WCF services</span></span>  
 <span data-ttu-id="aa040-201">이러한 서비스를 호스트하려면 서버의 구성 파일(web.config)에 다음 내용을 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa040-201">To host these services, you will need to make the following additions to the server’s configuration file (web.config).</span></span>  
  
1. <span data-ttu-id="aa040-202">세션 개체의 엔드포인트를 설명하는 `<client>` 섹션을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="aa040-202">Add a `<client>` section that describes the endpoint for the sessionful object.</span></span>  <span data-ttu-id="aa040-203">이 시나리오에서는 서버가 클라이언트 역할도 하며 이 기능을 사용할 수 있도록 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa040-203">In this scenario, the server also acts as a client and must be configured to enable this.</span></span>  
  
2. <span data-ttu-id="aa040-204">`<services>` 섹션에서 팩터리와 세션 개체의 서비스 엔드포인트를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="aa040-204">In the `<services>` section, declare service endpoints for the factory and sessionful object.</span></span>  <span data-ttu-id="aa040-205">그러면 클라이언트가 서비스 엔드포인트와 통신하고 <xref:System.ServiceModel.EndpointAddress10>을 확보한 다음 세션 채널을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa040-205">This enables the client to communicate with the service endpoints, acquire the <xref:System.ServiceModel.EndpointAddress10> and create the sessionful channel.</span></span>  
  
 <span data-ttu-id="aa040-206">다음은 이러한 설정을 포함하는 예제 구성 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="aa040-206">The following is an example configuration file with these settings:</span></span>  
  
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
  
 <span data-ttu-id="aa040-207">서비스를 자체 호스트하고 앱을 시작하려면 콘솔 애플리케이션에 다음 줄을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="aa040-207">Add the following lines to a console application, to self-host the service, and start the app.</span></span>  
  
```csharp  
ServiceHost factoryHost = new ServiceHost(typeof(SessionBoundFactory));  
factoryHost.Open();  
  
ServiceHost sessionBoundServiceHost = new ServiceHost(  
typeof(MySessionBoundObject));  
sessionBoundServiceHost.Open();  
```  
  
### <a name="step-4-configure-the-client-and-call-the-service"></a><span data-ttu-id="aa040-208">4단계: 클라이언트 구성 및 서비스 호출</span><span class="sxs-lookup"><span data-stu-id="aa040-208">Step 4: Configure the client and call the service</span></span>  
 <span data-ttu-id="aa040-209">프로젝트의 애플리케이션 구성 파일(app.config)에 다음 항목을 만들어 WCF 서비스와 통신하도록 클라이언트를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="aa040-209">Configure the client to communicate with the WCF services by making the following entries in the project’s application configuration file (app.config).</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <client>  
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
  
 <span data-ttu-id="aa040-210">서비스를 호출하려면 다음을 수행하는 코드를 클라이언트에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="aa040-210">To call the service, add the code to the client to do the following:</span></span>  
  
1. <span data-ttu-id="aa040-211">`ISessionBoundFactory` 서비스에 대한 채널을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="aa040-211">Create a channel to the `ISessionBoundFactory` service.</span></span>  
  
2. <span data-ttu-id="aa040-212">채널을 사용하여 `ISessionBoundFactory` 서비스를 호출하고 <xref:System.ServiceModel.EndpointAddress10> 개체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="aa040-212">Use the channel to invoke the `ISessionBoundFactory` service an obtain an <xref:System.ServiceModel.EndpointAddress10> object.</span></span>  
  
3. <span data-ttu-id="aa040-213"><xref:System.ServiceModel.EndpointAddress10>을 사용하여 세션 개체를 가져올 채널을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="aa040-213">Use the <xref:System.ServiceModel.EndpointAddress10> to create a channel to obtain a sessionful object.</span></span>  
  
4. <span data-ttu-id="aa040-214">`SetCurrentValue` 및 `GetCurrentValue` 메서드를 호출하여 여러 호출에서 동일한 개체 인스턴스가 사용됨을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="aa040-214">Call the `SetCurrentValue` and `GetCurrentValue` methods to demonstrate it remains the same object instance is used across multiple calls.</span></span>  
  
```csharp  
ChannelFactory<ISessionBoundFactory> factory =  
        new ChannelFactory<ISessionBoundFactory>("factory");  
  
ISessionBoundFactory sessionBoundFactory = factory.CreateChannel();  
  
EndpointAddress10 address = sessionBoundFactory.GetInstanceAddress();  
  
ChannelFactory<ISessionBoundObject> sessionBoundObjectFactory =  
    new ChannelFactory<ISessionBoundObject>(  
        new NetTcpBinding(),  
        address.ToEndpointAddress());  
  
ISessionBoundObject sessionBoundObject =  
        sessionBoundObjectFactory.CreateChannel();  
  
sessionBoundObject.SetCurrentValue("Hello");  
if (sessionBoundObject.GetCurrentValue() == "Hello")  
{  
    Console.WriteLine("Session-full instance management works as expected");  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="aa040-215">참조</span><span class="sxs-lookup"><span data-stu-id="aa040-215">See also</span></span>

- [<span data-ttu-id="aa040-216">기본 WCF 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="aa040-216">Basic WCF Programming</span></span>](../wcf/basic-wcf-programming.md)
- [<span data-ttu-id="aa040-217">서비스 디자인 및 구현</span><span class="sxs-lookup"><span data-stu-id="aa040-217">Designing and Implementing Services</span></span>](../wcf/designing-and-implementing-services.md)
- [<span data-ttu-id="aa040-218">클라이언트 빌드</span><span class="sxs-lookup"><span data-stu-id="aa040-218">Building Clients</span></span>](../wcf/building-clients.md)
- [<span data-ttu-id="aa040-219">이중 서비스</span><span class="sxs-lookup"><span data-stu-id="aa040-219">Duplex Services</span></span>](../wcf/feature-details/duplex-services.md)
