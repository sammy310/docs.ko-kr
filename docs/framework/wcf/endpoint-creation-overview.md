---
title: 엔드포인트 만들기 개요
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- endpoints [WCF], overview
ms.assetid: f4dce0fb-6f54-47e6-8054-86d7f574b91c
ms.openlocfilehash: bf6bfb10123223bf689945ef93ff09219a68092c
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319920"
---
# <a name="endpoint-creation-overview"></a><span data-ttu-id="a11fd-102">엔드포인트 만들기 개요</span><span class="sxs-lookup"><span data-stu-id="a11fd-102">Endpoint Creation Overview</span></span>

<span data-ttu-id="a11fd-103">WCF (Windows Communication Foundation) 서비스와의 모든 통신은 서비스의 *끝점* 을 통해 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a11fd-103">All communication with a Windows Communication Foundation (WCF) service occurs through the *endpoints* of the service.</span></span> <span data-ttu-id="a11fd-104">끝점은 WCF 서비스에서 제공 하는 기능에 대 한 액세스를 클라이언트에 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a11fd-104">Endpoints provide the clients access to the functionality that a WCF service offers.</span></span> <span data-ttu-id="a11fd-105">이 단원에서는 엔드포인트의 구조에 대해 설명하고 구성 및 코드에서 엔드포인트를 정의하는 방법을 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a11fd-105">This section describes the structure of an endpoint and outlines how to define an endpoint in configuration and in code.</span></span>

## <a name="the-structure-of-an-endpoint"></a><span data-ttu-id="a11fd-106">엔드포인트의 구조</span><span class="sxs-lookup"><span data-stu-id="a11fd-106">The Structure of an Endpoint</span></span>

<span data-ttu-id="a11fd-107">각 엔드포인트에는 엔드포인트를 찾을 위치를 나타내는 주소, 클라이언트가 엔드포인트와 통신할 수 있는 방법을 지정하는 바인딩, 그리고 사용 가능한 메서드를 식별하는 계약이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a11fd-107">Each endpoint contains an address that indicates where to find the endpoint, a binding that specifies how a client can communicate with the endpoint, and a contract that identifies the methods available.</span></span>

- <span data-ttu-id="a11fd-108">**주소**입니다.</span><span class="sxs-lookup"><span data-stu-id="a11fd-108">**Address**.</span></span> <span data-ttu-id="a11fd-109">주소는 엔드포인트를 고유하게 식별하고 잠재 고객에게 서비스가 있는 위치를 알려 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a11fd-109">The address uniquely identifies the endpoint and tells potential consumers where the service is located.</span></span> <span data-ttu-id="a11fd-110">이는 URI (Uniform Resource Identifier) 및 id를 포함 하는 주소 속성, 일부 WSDL (웹 서비스 기술 언어) 요소 및 선택적 헤더의 컬렉션을 포함 하는 <xref:System.ServiceModel.EndpointAddress> 주소로 WCF 개체 모델에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a11fd-110">It is represented in the WCF object model by the <xref:System.ServiceModel.EndpointAddress> address, which contains a Uniform Resource Identifier (URI) and address properties that include an identity, some Web Services Description Language (WSDL) elements, and a collection of optional headers.</span></span> <span data-ttu-id="a11fd-111">선택적 헤더는 엔드포인트를 확인하거나 상호 작용하는 데 필요한 자세한 주소 지정 정보를 추가로 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a11fd-111">The optional headers provide additional detailed addressing information to identify or interact with the endpoint.</span></span> <span data-ttu-id="a11fd-112">자세한 내용은 [끝점 주소 지정](specifying-an-endpoint-address.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a11fd-112">For more information, see [Specifying an Endpoint Address](specifying-an-endpoint-address.md).</span></span>

- <span data-ttu-id="a11fd-113">**바인딩입니다**.</span><span class="sxs-lookup"><span data-stu-id="a11fd-113">**Binding**.</span></span> <span data-ttu-id="a11fd-114">바인딩은 엔드포인트와 통신하는 방법을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a11fd-114">The binding specifies how to communicate with the endpoint.</span></span> <span data-ttu-id="a11fd-115">바인딩은 사용할 전송 프로토콜(예: TCP 또는 HTTP), 메시지에 사용할 인코딩(예: 텍스트 또는 이진), 필요한 보안 요구 사항(예: SSL[Secure Sockets Layer] 또는 SOAP 메시지 보안) 등을 포함하여 엔드포인트가 대상과 통신하는 방법을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a11fd-115">The binding specifies how the endpoint communicates with the world, including which transport protocol to use (for example, TCP or HTTP), which encoding to use for the messages (for example, text or binary), and which security requirements are necessary (for example, Secure Sockets Layer [SSL] or SOAP message security).</span></span> <span data-ttu-id="a11fd-116">자세한 내용은 [바인딩을 사용 하 여 서비스 및 클라이언트 구성](using-bindings-to-configure-services-and-clients.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a11fd-116">For more information, see [Using Bindings to Configure Services and Clients](using-bindings-to-configure-services-and-clients.md).</span></span>

- <span data-ttu-id="a11fd-117">**서비스 계약**.</span><span class="sxs-lookup"><span data-stu-id="a11fd-117">**Service contract**.</span></span> <span data-ttu-id="a11fd-118">서비스 계약에서는 엔드포인트가 클라이언트에 노출하는 기능을 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a11fd-118">The service contract outlines what functionality the endpoint exposes to the client.</span></span> <span data-ttu-id="a11fd-119">계약은 클라이언트가 호출할 수 있는 작업, 작업을 호출하는 데 필요한 입력 매개 변수 또는 데이터의 형식 및 메시지 형식, 클라이언트가 기대할 수 있는 처리 또는 응답 메시지의 종류 등을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a11fd-119">A contract specifies the operations that a client can call, the form of the message and the type of input parameters or data required to call the operation, and the kind of processing or response message the client can expect.</span></span> <span data-ttu-id="a11fd-120">계약의 세 가지 기본 유형은 기본 MEP(메시지 교환 패턴)인 데이터 그램(단방향), 요청/응답 및 이중(양방향)과 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="a11fd-120">Three basic types of contracts correspond to basic message exchange patterns (MEPs): datagram (one-way), request/reply, and duplex (bidirectional).</span></span> <span data-ttu-id="a11fd-121">또한 서비스 계약은 액세스할 때 데이터 및 메시지 계약을 사용하여 특정 데이터 형식과 메시지 형식을 요구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a11fd-121">The service contract can also employ data and message contracts to require specific data types and message formats when being accessed.</span></span> <span data-ttu-id="a11fd-122">서비스 계약을 정의 하는 방법에 대 한 자세한 내용은 [서비스 계약 디자인](designing-service-contracts.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a11fd-122">For more information about how to define a service contract, see [Designing Service Contracts](designing-service-contracts.md).</span></span> <span data-ttu-id="a11fd-123">클라이언트가 이중 MEP의 서비스로부터 메시지를 받으려면 콜백 계약이라는 서비스 정의 계약을 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a11fd-123">Note that a client may also be required to implement a service-defined contract, called a callback contract, to receive messages from the service in a duplex MEP.</span></span> <span data-ttu-id="a11fd-124">자세한 내용은 [이중 서비스](./feature-details/duplex-services.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a11fd-124">For more information, see [Duplex Services](./feature-details/duplex-services.md).</span></span>

<span data-ttu-id="a11fd-125">서비스의 엔드포인트를 코드를 사용하여 명령적으로 지정하거나 구성을 통해 선언적으로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a11fd-125">The endpoint for a service can be specified either imperatively by using code or declaratively through configuration.</span></span> <span data-ttu-id="a11fd-126">엔드포인트를 지정하지 않으면 런타임이 서비스에서 구현되는 각 서비스 계약의 각 기본 주소에 대해 기본 엔드포인트를 하나씩 추가하여 기본 엔드포인트를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a11fd-126">If no endpoints are specified then the runtime provides default endpoints by adding one default endpoint for each base address for each service contract implemented by the service.</span></span> <span data-ttu-id="a11fd-127">일반적으로 배포 된 서비스에 대 한 바인딩 및 주소가 서비스를 개발 하는 동안 사용 된 것과 다르기 때문에 일반적으로 코드에서 끝점을 정의 하는 것은 실용적이 지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a11fd-127">Defining endpoints in code is usually not practical because the bindings and addresses for a deployed service are typically different from those used while the service is being developed.</span></span> <span data-ttu-id="a11fd-128">일반적으로 코드 대신 구성을 사용하여 서비스 엔드포인트를 정의하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a11fd-128">Generally, it is more practical to define service endpoints using configuration rather than code.</span></span> <span data-ttu-id="a11fd-129">바인딩 및 주소 지정 정보를 코드와 구분하면 애플리케이션을 다시 컴파일하여 재배포할 필요 없이 해당 정보를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a11fd-129">Keeping the binding and addressing information out of the code allows them to change without having to recompile and redeploy the application.</span></span>

> [!NOTE]
> <span data-ttu-id="a11fd-130">가장을 수행하는 서비스 엔드포인트를 추가할 때는 <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A> 메서드 또는 <xref:System.ServiceModel.Description.ContractDescription.GetContract%28System.Type%2CSystem.Type%29> 메서드 중 하나를 사용하여 계약을 새 <xref:System.ServiceModel.Description.ServiceDescription> 개체로 적절하게 로드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a11fd-130">When adding a service endpoint that performs impersonation, you must either use one of the <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A> methods or the <xref:System.ServiceModel.Description.ContractDescription.GetContract%28System.Type%2CSystem.Type%29> method to properly load the contract into a new <xref:System.ServiceModel.Description.ServiceDescription> object.</span></span>

## <a name="defining-endpoints-in-code"></a><span data-ttu-id="a11fd-131">코드로 엔드포인트 정의</span><span class="sxs-lookup"><span data-stu-id="a11fd-131">Defining Endpoints in Code</span></span>

<span data-ttu-id="a11fd-132">다음 예제에서는 코드로 엔드포인트를 지정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a11fd-132">The following example illustrates how to specify an endpoint in code with the following:</span></span>

- <span data-ttu-id="a11fd-133">"Hello \<name >!" 응답과 함께 사용자의 이름과 에코를 수락 하는 서비스의 `IEcho` 형식에 대 한 계약을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="a11fd-133">Define a contract for an `IEcho` type of service that accepts someone's name and echo with the response "Hello \<name>!".</span></span>

- <span data-ttu-id="a11fd-134">`Echo` 계약에 정의된 유형의 `IEcho` 서비스를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="a11fd-134">Implement an `Echo` service of the type defined by the `IEcho` contract.</span></span>

- <span data-ttu-id="a11fd-135">서비스에 대 한 `http://localhost:8000/Echo`의 끝점 주소를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a11fd-135">Specify an endpoint address of `http://localhost:8000/Echo` for the service.</span></span>

- <span data-ttu-id="a11fd-136">`Echo` 바인딩을 사용하여 <xref:System.ServiceModel.WSHttpBinding> 서비스를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="a11fd-136">Configure the `Echo` service using a <xref:System.ServiceModel.WSHttpBinding> binding.</span></span>

```csharp
namespace Echo
{
   // Define the contract for the IEcho service
   [ServiceContract]
   public interface IEcho
   {
       [OperationContract]
       String Hello(string name)
   }

   // Create an Echo service that implements IEcho contract
   class Echo : IEcho
   {
      public string Hello(string name)
      {
         return "Hello" + name + "!";
      }
      public static void Main ()
      {
          //Specify the base address for Echo service.
          Uri echoUri = new Uri("http://localhost:8000/");

          //Create a ServiceHost for the Echo service.
          ServiceHost serviceHost = new ServiceHost(typeof(Echo),echoUri);

          // Use a predefined WSHttpBinding to configure the service.
          WSHttpBinding binding = new WSHttpBinding();

          // Add the endpoint for this service to the service host.
          serviceHost.AddServiceEndpoint(
             typeof(IEcho),
             binding,
             echoUri
           );

          // Open the service host to run it.
          serviceHost.Open();
     }
  }
}
```

```vb
' Define the contract for the IEcho service
    <ServiceContract()> _
    Public Interface IEcho
        <OperationContract()> _
        Function Hello(ByVal name As String) As String
    End Interface

' Create an Echo service that implements IEcho contract
    Public Class Echo
        Implements IEcho
        Public Function Hello(ByVal name As String) As String _
 Implements ICalculator.Hello
            Dim result As String = "Hello" + name + "!"
            Return result
        End Function

' Specify the base address for Echo service.
Dim echoUri As Uri = New Uri("http://localhost:8000/")

' Create a ServiceHost for the Echo service.
Dim svcHost As ServiceHost = New ServiceHost(GetType(HelloWorld), echoUri)

' Use a predefined WSHttpBinding to configure the service.
Dim binding As New WSHttpBinding()

' Add the endpoint for this service to the service host.
serviceHost.AddServiceEndpoint(GetType(IEcho), binding, echoUri)

' Open the service host to run it.
serviceHost.Open()
```

> [!NOTE]
> <span data-ttu-id="a11fd-137">서비스 호스트가 기본 주소로 만들어집니다. 나머지 주소는 기본 주소를 기준으로 엔드포인트의 일부로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="a11fd-137">The service host is created with a base address and then the rest of the address, relative to the base address, is specified as part of an endpoint.</span></span> <span data-ttu-id="a11fd-138">이 주소 분할을 통해 호스트에서 서비스에 대해 여러 엔드포인트를 쉽게 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a11fd-138">This partitioning of the address allows multiple endpoints to be defined more conveniently for services at a host.</span></span>

> [!NOTE]
> <span data-ttu-id="a11fd-139"><xref:System.ServiceModel.Description.ServiceDescription>에서 <xref:System.ServiceModel.Channels.CommunicationObject.OnOpening%2A> 메서드 이후에는 서비스 애플리케이션의 <xref:System.ServiceModel.ServiceHostBase> 속성을 수정해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a11fd-139">Properties of <xref:System.ServiceModel.Description.ServiceDescription> in the service application must not be modified subsequent to the <xref:System.ServiceModel.Channels.CommunicationObject.OnOpening%2A> method on <xref:System.ServiceModel.ServiceHostBase>.</span></span> <span data-ttu-id="a11fd-140"><xref:System.ServiceModel.ServiceHostBase.Credentials%2A> 및 `AddServiceEndpoint`에서 <xref:System.ServiceModel.ServiceHostBase> 속성 및 <xref:System.ServiceModel.ServiceHost> 메서드와 같은 일부 멤버는 해당 지점을 지나서 수정할 경우 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="a11fd-140">Some members, such as the <xref:System.ServiceModel.ServiceHostBase.Credentials%2A> property and the `AddServiceEndpoint` methods on <xref:System.ServiceModel.ServiceHostBase> and <xref:System.ServiceModel.ServiceHost>, throw an exception if modified past that point.</span></span> <span data-ttu-id="a11fd-141">다른 멤버에서는 이를 수정할 수 있지만 그 결과는 예측할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a11fd-141">Others permit you to modify them, but the result is undefined.</span></span>
>
> <span data-ttu-id="a11fd-142">마찬가지로 클라이언트에서 <xref:System.ServiceModel.Description.ServiceEndpoint>의 <xref:System.ServiceModel.Channels.CommunicationObject.OnOpening%2A>을 호출한 이후에는 <xref:System.ServiceModel.ChannelFactory> 값을 수정해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a11fd-142">Similarly, on the client the <xref:System.ServiceModel.Description.ServiceEndpoint> values must not be modified after the call to <xref:System.ServiceModel.Channels.CommunicationObject.OnOpening%2A> on the <xref:System.ServiceModel.ChannelFactory>.</span></span> <span data-ttu-id="a11fd-143"><xref:System.ServiceModel.ChannelFactory.Credentials%2A> 속성은 해당 지점을 지나서 수정할 경우 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="a11fd-143">The <xref:System.ServiceModel.ChannelFactory.Credentials%2A> property throws an exception if modified past that point.</span></span> <span data-ttu-id="a11fd-144">다른 클라이언트 설명 값은 수정해도 오류가 발생하지 않지만 결과가 정의되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a11fd-144">The other client description values can be modified without error, but the result is undefined.</span></span>
>
> <span data-ttu-id="a11fd-145">서비스와 클라이언트 모두에 대해 <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A>을 호출하기 이전에 설명을 수정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a11fd-145">Whether for the service or client, it is recommended that you modify the description prior to calling <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A>.</span></span>

## <a name="defining-endpoints-in-configuration"></a><span data-ttu-id="a11fd-146">구성에서 엔드포인트 정의</span><span class="sxs-lookup"><span data-stu-id="a11fd-146">Defining Endpoints in Configuration</span></span>

<span data-ttu-id="a11fd-147">애플리케이션을 만들 때 애플리케이션을 배포하는 관리자에게 결정을 넘겨야 할 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a11fd-147">When creating an application, you often want to defer decisions to the administrator who is deploying the application.</span></span> <span data-ttu-id="a11fd-148">예를 들어, 서비스 주소(URI)가 무엇인지 미리 알 수 없는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a11fd-148">For example, there is often no way of knowing in advance what a service address (a URI) will be.</span></span> <span data-ttu-id="a11fd-149">주소를 하드 코딩하는 대신 관리자가 서비스를 작성한 후에 이를 수행하도록 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a11fd-149">Instead of hard-coding an address, it is preferable to allow an administrator to do so after creating a service.</span></span> <span data-ttu-id="a11fd-150">이러한 유연성은 구성을 통해 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="a11fd-150">This flexibility is accomplished through configuration.</span></span> <span data-ttu-id="a11fd-151">자세한 내용은 [서비스 구성](configuring-services.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a11fd-151">For details, see [Configuring Services](configuring-services.md).</span></span>

> [!NOTE]
> <span data-ttu-id="a11fd-152">[ServiceModel Metadata 유틸리티 도구 (svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) 를 `/config:`*파일* 이름 `[,`*파일 이름* 으로 사용 하 `]` 스위치를 사용 하 여 구성 파일을 신속 하 게 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a11fd-152">Use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) with the `/config:`*filename*`[,`*filename*`]` switch to quickly create configuration files.</span></span>

## <a name="using-default-endpoints"></a><span data-ttu-id="a11fd-153">기본 엔드포인트 사용</span><span class="sxs-lookup"><span data-stu-id="a11fd-153">Using Default Endpoints</span></span>

<span data-ttu-id="a11fd-154">코드 또는 구성에서 엔드포인트를 지정하지 않으면 런타임이 서비스에서 구현되는 각 서비스 계약의 각 기본 주소에 대해 기본 엔드포인트를 하나씩 추가하여 기본 엔드포인트를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a11fd-154">If no endpoints are specified in code or in configuration then the runtime provides default endpoints by adding one default endpoint for each base address for each service contract implemented by the service.</span></span> <span data-ttu-id="a11fd-155">기본 주소는 코드 또는 구성에서 지정할 수 있으며 기본 엔드포인트는 <xref:System.ServiceModel.ICommunicationObject.Open>에서 <xref:System.ServiceModel.ServiceHost>을 호출하면 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="a11fd-155">The base address can be specified in code or in configuration, and the default endpoints are added when <xref:System.ServiceModel.ICommunicationObject.Open> is called on the <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="a11fd-156">다음 예제는 이전 단원과 같은 예제이지만 엔드포인트가 지정되지 않았으므로 기본 엔드포인트가 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="a11fd-156">This example is the same example from the previous section, but since no endpoints are specified, the default endpoints are added.</span></span>

```csharp
namespace Echo
{
   // Define the contract for the IEcho service
   [ServiceContract]
   public interface IEcho
   {
       [OperationContract]
       String Hello(string name)
   }

   // Create an Echo service that implements IEcho contract
   public class Echo : IEcho
   {
      public string Hello(string name)
      {
         return "Hello" + name + "!";
      }
      public static void Main ()
      {
          //Specify the base address for Echo service.
          Uri echoUri = new Uri("http://localhost:8000/");

          //Create a ServiceHost for the Echo service.
          ServiceHost serviceHost = new ServiceHost(typeof(Echo),echoUri);

          // Open the service host to run it. Default endpoints
          // are added when the service is opened.
          serviceHost.Open();
     }
  }
}
```

```vb
' Define the contract for the IEcho service
    <ServiceContract()> _
    Public Interface IEcho
        <OperationContract()> _
        Function Hello(ByVal name As String) As String
    End Interface

' Create an Echo service that implements IEcho contract
    Public Class Echo
        Implements IEcho
        Public Function Hello(ByVal name As String) As String _
 Implements ICalculator.Hello
            Dim result As String = "Hello" + name + "!"
            Return result
        End Function

' Specify the base address for Echo service.
Dim echoUri As Uri = New Uri("http://localhost:8000/")

' Open the service host to run it. Default endpoints
' are added when the service is opened.
serviceHost.Open()
```

 <span data-ttu-id="a11fd-157">엔드포인트를 명시적으로 제공하는 경우에도 <xref:System.ServiceModel.ServiceHostBase.AddDefaultEndpoints%2A>을 호출하기 전에 <xref:System.ServiceModel.ServiceHost>에서 <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A>를 호출하여 기본 엔드포인트를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a11fd-157">If endpoints are explicitly provided, the default endpoints can still be added by calling <xref:System.ServiceModel.ServiceHostBase.AddDefaultEndpoints%2A> on the <xref:System.ServiceModel.ServiceHost> before calling <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A>.</span></span> <span data-ttu-id="a11fd-158">기본 끝점에 대 한 자세한 내용은 [WCF 서비스에 대 한](./samples/simplified-configuration-for-wcf-services.md) [간소화 된 구성](simplified-configuration.md) 및 단순화 된 구성을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a11fd-158">For more information about default endpoints, see [Simplified Configuration](simplified-configuration.md) and [Simplified Configuration for WCF Services](./samples/simplified-configuration-for-wcf-services.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a11fd-159">참조</span><span class="sxs-lookup"><span data-stu-id="a11fd-159">See also</span></span>

- [<span data-ttu-id="a11fd-160">서비스 계약 구현</span><span class="sxs-lookup"><span data-stu-id="a11fd-160">Implementing Service Contracts</span></span>](implementing-service-contracts.md)
