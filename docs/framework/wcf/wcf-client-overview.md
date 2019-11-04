---
title: WCF 클라이언트 개요
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- clients [WCF], architecture
ms.assetid: f60d9bc5-8ade-4471-8ecf-5a07a936c82d
ms.openlocfilehash: 180de3f571426441155a19b98ab750fcdbb3888e
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/01/2019
ms.locfileid: "73420654"
---
# <a name="wcf-client-overview"></a><span data-ttu-id="4eb17-102">WCF 클라이언트 개요</span><span class="sxs-lookup"><span data-stu-id="4eb17-102">WCF Client Overview</span></span>
<span data-ttu-id="4eb17-103">이 섹션에서는 클라이언트 응용 프로그램에서 수행 하는 작업, WCF (Windows Communication Foundation) 클라이언트를 구성 하 고 만들고 사용 하는 방법 및 클라이언트 응용 프로그램의 보안을 설정 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="4eb17-103">This section describes what client applications do, how to configure, create, and use a Windows Communication Foundation (WCF) client, and how to secure client applications.</span></span>  
  
## <a name="using-wcf-client-objects"></a><span data-ttu-id="4eb17-104">WCF 클라이언트 개체 사용</span><span class="sxs-lookup"><span data-stu-id="4eb17-104">Using WCF Client Objects</span></span>  
 <span data-ttu-id="4eb17-105">클라이언트 응용 프로그램은 WCF 클라이언트를 사용 하 여 다른 응용 프로그램과 통신 하는 관리 되는 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="4eb17-105">A client application is a managed application that uses a WCF client to communicate with another application.</span></span> <span data-ttu-id="4eb17-106">WCF 서비스에 대 한 클라이언트 응용 프로그램을 만들려면 다음 단계를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4eb17-106">To create a client application for a WCF service requires the following steps:</span></span>  
  
1. <span data-ttu-id="4eb17-107">서비스 엔드포인트에 대한 서비스 계약, 바인딩 및 주소 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="4eb17-107">Obtain the service contract, bindings, and address information for a service endpoint.</span></span>  
  
2. <span data-ttu-id="4eb17-108">해당 정보를 사용 하 여 WCF 클라이언트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4eb17-108">Create a WCF client using that information.</span></span>  
  
3. <span data-ttu-id="4eb17-109">작업을 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="4eb17-109">Call operations.</span></span>  
  
4. <span data-ttu-id="4eb17-110">WCF 클라이언트 개체를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="4eb17-110">Close the WCF client object.</span></span>  
  
 <span data-ttu-id="4eb17-111">다음 단원에서는 이러한 단계에 대해 설명하고 다음과 같은 문제를 간략하게 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="4eb17-111">The following sections discuss these steps and provide brief introductions to the following issues:</span></span>  
  
- <span data-ttu-id="4eb17-112">오류 처리</span><span class="sxs-lookup"><span data-stu-id="4eb17-112">Handling errors.</span></span>  
  
- <span data-ttu-id="4eb17-113">클라이언트 구성 및 보안</span><span class="sxs-lookup"><span data-stu-id="4eb17-113">Configuring and securing clients.</span></span>  
  
- <span data-ttu-id="4eb17-114">이중 서비스에 대한 콜백 개체 만들기</span><span class="sxs-lookup"><span data-stu-id="4eb17-114">Creating callback objects for duplex services.</span></span>  
  
- <span data-ttu-id="4eb17-115">비동기적으로 서비스 호출</span><span class="sxs-lookup"><span data-stu-id="4eb17-115">Calling services asynchronously.</span></span>  
  
- <span data-ttu-id="4eb17-116">클라이언트 채널을 사용하여 서비스 호출</span><span class="sxs-lookup"><span data-stu-id="4eb17-116">Calling services using client channels.</span></span>  
  
## <a name="obtain-the-service-contract-bindings-and-addresses"></a><span data-ttu-id="4eb17-117">서비스 계약, 바인딩 및 주소 가져오기</span><span class="sxs-lookup"><span data-stu-id="4eb17-117">Obtain the Service Contract, Bindings, and Addresses</span></span>  
 <span data-ttu-id="4eb17-118">WCF에서 서비스 및 클라이언트는 관리 되는 특성, 인터페이스 및 메서드를 사용 하 여 계약을 모델링 합니다.</span><span class="sxs-lookup"><span data-stu-id="4eb17-118">In WCF, services and clients model contracts using managed attributes, interfaces, and methods.</span></span> <span data-ttu-id="4eb17-119">클라이언트 애플리케이션에서 서비스에 연결하려면 서비스 계약에 대한 형식 정보를 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4eb17-119">To connect to a service in a client application, you need to obtain the type information for the service contract.</span></span> <span data-ttu-id="4eb17-120">일반적으로이 작업은 서비스에서 메타 데이터를 다운로드 하는 [ServiceModel Metadata 유틸리티 도구 (svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md)를 사용 하 여이 작업을 수행 하 고, 선택한 언어로 관리 되는 소스 코드 파일로 변환 하 고, 클라이언트 응용 프로그램 구성 파일을 만듭니다. WCF 클라이언트 개체를 구성 하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4eb17-120">Typically, you do this by using the [ServiceModel Metadata Utility Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md), which downloads metadata from the service, converts it to a managed source code file in the language of your choice, and creates a client application configuration file that you can use to configure your WCF client object.</span></span> <span data-ttu-id="4eb17-121">예를 들어 `MyCalculatorService`를 호출 하는 WCF 클라이언트 개체를 만들고 해당 서비스에 대 한 메타 데이터가 `http://computerName/MyCalculatorService/Service.svc?wsdl`에 게시 되는 경우 다음 코드 예제에서는 Svcutil.exe를 사용 하 여 서비스 동료가 포함 된 `ClientCode.vb` 파일을 가져오는 방법을 보여 줍니다. 관리 코드에서 ntract.</span><span class="sxs-lookup"><span data-stu-id="4eb17-121">For example, if you are going to create an WCF client object to invoke a `MyCalculatorService`, and you know that the metadata for that service is published at `http://computerName/MyCalculatorService/Service.svc?wsdl`, then the following code example shows how to use Svcutil.exe to obtain a `ClientCode.vb` file that contains the service contract in managed code.</span></span>  
  
```console  
svcutil /language:vb /out:ClientCode.vb /config:app.config http://computerName/MyCalculatorService/Service.svc?wsdl  
```  
  
 <span data-ttu-id="4eb17-122">이 계약 코드를 클라이언트 응용 프로그램으로 컴파일하거나 클라이언트 응용 프로그램에서 WCF 클라이언트 개체를 만드는 데 사용할 수 있는 다른 어셈블리로 컴파일할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4eb17-122">You can either compile this contract code into the client application or into another assembly that the client application can then use to create an WCF client object.</span></span> <span data-ttu-id="4eb17-123">구성 파일을 사용하여 클라이언트 개체가 서비스에 제대로 연결하도록 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4eb17-123">You can use the configuration file to configure the client object to properly connect to the service .</span></span>  
  
 <span data-ttu-id="4eb17-124">이 프로세스에 대 한 예제는 [방법: 클라이언트 만들기](how-to-create-a-wcf-client.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4eb17-124">For an example of this process, see [How to: Create a Client](how-to-create-a-wcf-client.md).</span></span> <span data-ttu-id="4eb17-125">계약에 대 한 자세한 내용은 [계약](./feature-details/contracts.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4eb17-125">For more complete information about contracts, see [Contracts](./feature-details/contracts.md).</span></span>  
  
## <a name="create-a-wcf-client-object"></a><span data-ttu-id="4eb17-126">WCF 클라이언트 개체 만들기</span><span class="sxs-lookup"><span data-stu-id="4eb17-126">Create a WCF Client Object</span></span>  
 <span data-ttu-id="4eb17-127">WCF 클라이언트는 클라이언트가 원격 서비스와 통신 하는 데 사용할 수 있는 형식의 WCF 서비스를 나타내는 로컬 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="4eb17-127">A WCF client is a local object that represents a WCF service in a form that the client can use to communicate with the remote service.</span></span> <span data-ttu-id="4eb17-128">WCF 클라이언트 형식은 대상 서비스 계약을 구현 하기 때문에 대상 서비스 계약을 만들어 구성할 경우 클라이언트 개체를 직접 사용 하 여 서비스 작업을 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4eb17-128">WCF client types implement the target service contract, so when you create one and configure it, you can then use the client object directly to invoke service operations.</span></span> <span data-ttu-id="4eb17-129">WCF 런타임에서는 메서드 호출을 메시지로 변환 하 고, 서비스에 보내고, 회신을 수신 하 고, 해당 값을 WCF 클라이언트 개체에 반환 값 또는 `out` 또는 `ref` 매개 변수로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="4eb17-129">The WCF run time converts the method calls into messages, sends them to the service, listens for the reply, and returns those values to the WCF client object as return values or `out` or `ref` parameters.</span></span>  
  
 <span data-ttu-id="4eb17-130">WCF 클라이언트 채널 개체를 사용 하 여 서비스에 연결 하 고 서비스를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4eb17-130">You can also use WCF client channel objects to connect with and use services.</span></span> <span data-ttu-id="4eb17-131">자세한 내용은 [WCF 클라이언트 아키텍처](./feature-details/client-architecture.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4eb17-131">For details, see [WCF Client Architecture](./feature-details/client-architecture.md).</span></span>  
  
#### <a name="creating-a-new-wcf-object"></a><span data-ttu-id="4eb17-132">새 WCF 개체 만들기</span><span class="sxs-lookup"><span data-stu-id="4eb17-132">Creating a New WCF Object</span></span>  
 <span data-ttu-id="4eb17-133"><xref:System.ServiceModel.ClientBase%601> 클래스 사용을 설명하기 위해 다음 서비스 계약이 생성되어 있는 것으로 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="4eb17-133">To illustrate the use of a <xref:System.ServiceModel.ClientBase%601> class, assume the following simple service contract has been generated from a service application.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4eb17-134">Visual Studio를 사용 하 여 WCF 클라이언트를 만들면 프로젝트에 서비스 참조를 추가할 때 개체가 개체 브라우저에 자동으로 로드 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4eb17-134">If you are using Visual Studio to create your WCF client, objects are loaded automatically into the object browser when you add a service reference to your project.</span></span>  
  
 [!code-csharp[C_GeneratedCodeFiles#12](../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/cs/proxycode.cs#12)]  
  
 <span data-ttu-id="4eb17-135">Visual Studio를 사용 하지 않는 경우 생성 된 계약 코드를 검사 하 여 <xref:System.ServiceModel.ClientBase%601> 및 서비스 계약 인터페이스 `ISampleService`를 확장 하는 형식을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="4eb17-135">If you are not using Visual Studio, examine the generated contract code to find the type that extends <xref:System.ServiceModel.ClientBase%601> and the service contract interface `ISampleService`.</span></span> <span data-ttu-id="4eb17-136">이 경우 형식은 다음 코드와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="4eb17-136">In this case, that type looks like the following code:</span></span>  
  
 [!code-csharp[C_GeneratedCodeFiles#14](../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/cs/proxycode.cs#14)]  
  
 <span data-ttu-id="4eb17-137">생성자 중 하나를 사용하여 이 클래스를 로컬 개체로 만든 다음 구성하여 `ISampleService` 형식 서비스에 연결하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4eb17-137">This class can be created as a local object using one of the constructors, configured, and then used to connect to a service of the type `ISampleService`.</span></span>  
  
 <span data-ttu-id="4eb17-138">WCF 클라이언트 개체를 먼저 만든 다음이 개체를 사용 하 여 단일 try/catch 블록 내에서 닫는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4eb17-138">It is recommended that you create your WCF client object first, and then use it and close it inside a single try/catch block.</span></span> <span data-ttu-id="4eb17-139">특정 오류 모드에서 예외를 마스킹할 수 있으므로 `using` 문 (Visual Basic에서 `Using`)을 사용 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4eb17-139">You should not use the `using` statement (`Using` in Visual Basic) because it may mask exceptions in certain failure modes.</span></span> <span data-ttu-id="4eb17-140">자세한 내용은 다음 섹션을 참조 하 [고 Close 및 Abort를 사용 하 여 WCF 클라이언트 리소스를 해제](./samples/use-close-abort-release-wcf-client-resources.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4eb17-140">For more information, see the following sections as well as [Use Close and Abort to release WCF client resources](./samples/use-close-abort-release-wcf-client-resources.md).</span></span>  
  
### <a name="contracts-bindings-and-addresses"></a><span data-ttu-id="4eb17-141">계약, 바인딩 및 주소</span><span class="sxs-lookup"><span data-stu-id="4eb17-141">Contracts, Bindings, and Addresses</span></span>  
 <span data-ttu-id="4eb17-142">WCF 클라이언트 개체를 만들려면 먼저 client 개체를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4eb17-142">Before you can create a WCF client object, you must configure the client object.</span></span> <span data-ttu-id="4eb17-143">특히 사용할 서비스 *끝점이* 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4eb17-143">Specifically, it must have a service *endpoint* to use.</span></span> <span data-ttu-id="4eb17-144">엔드포인트는 서비스 계약, 바인딩 및 주소의 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="4eb17-144">An endpoint is the combination of a service contract, a binding, and an address.</span></span> <span data-ttu-id="4eb17-145">끝점에 대 한 자세한 내용은 [끝점: 주소, 바인딩 및 계약](./feature-details/endpoints-addresses-bindings-and-contracts.md)을 참조 하세요. 일반적으로이 정보는 클라이언트 응용 프로그램 구성 파일의 [\<endpoint >](../configure-apps/file-schema/wcf/endpoint-of-client.md) 요소 (예: svcutil.exe 도구에서 생성 하는 요소)에 있으며 클라이언트 개체를 만들 때 자동으로 로드 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4eb17-145">(For more information about endpoints, see [Endpoints: Addresses, Bindings, and Contracts](./feature-details/endpoints-addresses-bindings-and-contracts.md).) Typically, this information is located in the [\<endpoint>](../configure-apps/file-schema/wcf/endpoint-of-client.md) element in a client application configuration file, such as the one the Svcutil.exe tool generates, and is loaded automatically when you create your client object.</span></span> <span data-ttu-id="4eb17-146">WCF 클라이언트 형식에는이 정보를 프로그래밍 방식으로 지정할 수 있도록 하는 오버 로드도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4eb17-146">Both WCF client types also have overloads that enable you to programmatically specify this information.</span></span>  
  
 <span data-ttu-id="4eb17-147">예를 들어, 이전 예제에 사용된 `ISampleService`에 대해 생성된 구성 파일에는 다음과 같은 엔드포인트 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4eb17-147">For example, a generated configuration file for an `ISampleService` used in the preceding examples contains the following endpoint information.</span></span>  
  
 [!code-xml[C_GeneratedCodeFiles#19](../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/common/client.exe.config#19)]  
  
 <span data-ttu-id="4eb17-148">이 구성 파일은 `<client>` 요소에서 대상 엔드포인트를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4eb17-148">This configuration file specifies a target endpoint in the `<client>` element.</span></span> <span data-ttu-id="4eb17-149">여러 대상 끝점을 사용 하는 방법에 대 한 자세한 내용은 <xref:System.ServiceModel.ClientBase%601.%23ctor%2A?displayProperty=nameWithType> 또는 <xref:System.ServiceModel.ChannelFactory%601.%23ctor%2A?displayProperty=nameWithType> 생성자를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4eb17-149">For more information about using multiple target endpoints, see the <xref:System.ServiceModel.ClientBase%601.%23ctor%2A?displayProperty=nameWithType> or the <xref:System.ServiceModel.ChannelFactory%601.%23ctor%2A?displayProperty=nameWithType> constructors.</span></span>  
  
## <a name="calling-operations"></a><span data-ttu-id="4eb17-150">작업 호출</span><span class="sxs-lookup"><span data-stu-id="4eb17-150">Calling Operations</span></span>  
 <span data-ttu-id="4eb17-151">클라이언트 개체를 만들고 구성한 후에는 try/catch 블록을 만들고, 개체가 로컬인 것과 같은 방식으로 작업을 호출 하 고, WCF 클라이언트 개체를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="4eb17-151">Once you have a client object created and configured, create a try/catch block, call operations in the same way that you would if the object were local, and close the WCF client object.</span></span> <span data-ttu-id="4eb17-152">클라이언트 응용 프로그램에서 첫 번째 작업을 호출 하면 WCF는 기본 채널을 자동으로 열고 개체를 재활용할 때 기본 채널이 닫힙니다.</span><span class="sxs-lookup"><span data-stu-id="4eb17-152">When the client application calls the first operation, WCF automatically opens the underlying channel, and the underlying channel is closed when the object is recycled.</span></span> <span data-ttu-id="4eb17-153">또는 다른 작업을 호출하기 이전 또는 이후에 채널을 명시적으로 열었다가 닫을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4eb17-153">(Alternatively, you can also explicitly open and close the channel prior to or subsequent to calling other operations.)</span></span>  
  
 <span data-ttu-id="4eb17-154">예를 들어, 다음과 같은 서비스 계약을 가정해 봅니다.</span><span class="sxs-lookup"><span data-stu-id="4eb17-154">For example, if you have the following service contract:</span></span>  
  
```csharp  
namespace Microsoft.ServiceModel.Samples  
{  
    using System;  
    using System.ServiceModel;  
  
    [ServiceContract(Namespace = "http://Microsoft.ServiceModel.Samples")]  
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
}  
```  
  
```vb  
Namespace Microsoft.ServiceModel.Samples  
  
    Imports System  
    Imports System.ServiceModel  
  
    <ServiceContract(Namespace:= _  
    "http://Microsoft.ServiceModel.Samples")> _   
   Public Interface ICalculator  
        <OperationContract> _   
        Function Add(n1 As Double, n2 As Double) As Double  
        <OperationContract> _   
        Function Subtract(n1 As Double, n2 As Double) As Double  
        <OperationContract> _   
        Function Multiply(n1 As Double, n2 As Double) As Double  
        <OperationContract> _   
     Function Divide(n1 As Double, n2 As Double) As Double  
End Interface  
```  
  
 <span data-ttu-id="4eb17-155">다음 코드 예제에서 보여 주는 것 처럼 WCF 클라이언트 개체를 만들고 해당 메서드를 호출 하 여 작업을 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4eb17-155">You can call operations by creating a WCF client object and calling its methods, as the following code example demonstrates.</span></span> <span data-ttu-id="4eb17-156">WCF 클라이언트 개체의 열기, 호출 및 닫기는 단일 try/catch 블록 내에서 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="4eb17-156">Note that the opening, calling, and closing of the WCF client object occurs within a single try/catch block.</span></span> <span data-ttu-id="4eb17-157">자세한 내용은 [Wcf 클라이언트를 사용 하 여 서비스 액세스](./feature-details/accessing-services-using-a-client.md) 및 [Close 및 Abort를 사용 하 여 wcf 클라이언트 리소스 릴리스를](./samples/use-close-abort-release-wcf-client-resources.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4eb17-157">For more information, see [Accessing Services Using a WCF Client](./feature-details/accessing-services-using-a-client.md) and [Use Close and Abort to release WCF client resources](./samples/use-close-abort-release-wcf-client-resources.md).</span></span>  
  
 [!code-csharp[C_GeneratedCodeFiles#20](../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/cs/proxycode.cs#20)]  
  
## <a name="handling-errors"></a><span data-ttu-id="4eb17-158">오류 처리</span><span class="sxs-lookup"><span data-stu-id="4eb17-158">Handling Errors</span></span>  
 <span data-ttu-id="4eb17-159">기본 클라이언트 채널을 명시적으로 열거나 작업을 호출하여 자동으로 열 때, 클라이언트 또는 채널 개체를 사용하여 작업을 호출할 경우 또는 기본 클라이언트 채널을 닫을 때 클라이언트 애플리케이션에서 예외가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4eb17-159">Exceptions can occur in a client application when opening the underlying client channel (whether explicitly or automatically by calling an operation), using the client or channel object to call operations, or when closing the underlying client channel.</span></span> <span data-ttu-id="4eb17-160">적어도 애플리케이션에서 가능한 <xref:System.TimeoutException?displayProperty=nameWithType> 및 <xref:System.ServiceModel.CommunicationException?displayProperty=nameWithType> 예외를 비롯하여 작업에서 반환되는 SOAP 오류로 인해 throw되는 <xref:System.ServiceModel.FaultException?displayProperty=nameWithType> 개체를 처리하도록 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4eb17-160">It is recommended at a minimum that applications expect to handle possible <xref:System.TimeoutException?displayProperty=nameWithType> and <xref:System.ServiceModel.CommunicationException?displayProperty=nameWithType> exceptions in addition to any <xref:System.ServiceModel.FaultException?displayProperty=nameWithType> objects thrown as a result of SOAP faults returned by operations.</span></span> <span data-ttu-id="4eb17-161">작업 계약에 지정된 SOAP 오류는 형식 매개 변수가 SOAP 오류의 세부 유형인 <xref:System.ServiceModel.FaultException%601?displayProperty=nameWithType>으로, 클라이언트 애플리케이션에서 발생됩니다.</span><span class="sxs-lookup"><span data-stu-id="4eb17-161">SOAP faults specified in the operation contract are raised to client applications as a <xref:System.ServiceModel.FaultException%601?displayProperty=nameWithType> where the type parameter is the detail type of the SOAP fault.</span></span> <span data-ttu-id="4eb17-162">클라이언트 응용 프로그램에서 오류 조건을 처리 하는 방법에 대 한 자세한 내용은 오류 [보내기 및 받기](sending-and-receiving-faults.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="4eb17-162">For more information about handling error conditions in a client application, see [Sending and Receiving Faults](sending-and-receiving-faults.md).</span></span> <span data-ttu-id="4eb17-163">전체 샘플은 클라이언트에서 오류를 처리 하는 방법을 보여 줍니다. [예상 되는 예외](./samples/expected-exceptions.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4eb17-163">For a complete sample the shows how to handle errors in a client, see [Expected Exceptions](./samples/expected-exceptions.md).</span></span>  
  
## <a name="configuring-and-securing-clients"></a><span data-ttu-id="4eb17-164">클라이언트 구성 및 보안</span><span class="sxs-lookup"><span data-stu-id="4eb17-164">Configuring and Securing Clients</span></span>  
 <span data-ttu-id="4eb17-165">클라이언트를 구성하려면 클라이언트 생성자와 속성을 사용하여 클라이언트 또는 채널 개체에 대한 대상 엔드포인트 정보를 프로그래밍 방식으로 로드할 수도 있지만, 일반적으로 구성 파일에서 이 정보를 로드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4eb17-165">Configuring a client starts with the required loading of target endpoint information for the client or channel object, usually from a configuration file, although you can also load this information programmatically using the client constructors and properties.</span></span> <span data-ttu-id="4eb17-166">그러나 다양한 보안 시나리오에 대해 특정 클라이언트 동작을 활성화하는 추가 구성 단계를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4eb17-166">However, additional configuration steps are required to enable certain client behavior and for many security scenarios.</span></span>  
  
 <span data-ttu-id="4eb17-167">예를 들어, 서비스 계약에 대한 보안 요구 사항이 서비스 계약 인터페이스에 선언되어 있고, Svcutil.exe에서 구성 파일을 만든 경우 해당 파일에는 일반적으로 서비스의 보안 요구 사항을 지원할 수 있는 바인딩이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4eb17-167">For example, security requirements for service contracts are declared in the service contract interface, and if Svcutil.exe created a configuration file, that file usually contains a binding that is capable of supporting the security requirements of the service.</span></span> <span data-ttu-id="4eb17-168">그러나, 클라이언트 자격 증명 구성처럼 추가 보안 구성이 필요한 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4eb17-168">In some cases, however, more security configuration may be required, such as configuring client credentials.</span></span> <span data-ttu-id="4eb17-169">WCF 클라이언트의 보안 구성에 대 한 자세한 내용은 [클라이언트 보안](securing-clients.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4eb17-169">For complete information about the configuration of security for WCF clients, see [Securing Clients](securing-clients.md).</span></span>  
  
 <span data-ttu-id="4eb17-170">또한 클라이언트 애플리케이션에서 사용자 지정 런타임 동작과 같은 사용자 지정 수정을 사용할 수 있는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4eb17-170">In addition, some custom modifications can be enabled in client applications, such as custom run-time behaviors.</span></span> <span data-ttu-id="4eb17-171">사용자 지정 클라이언트 동작을 구성 하는 방법에 대 한 자세한 내용은 [클라이언트 동작 구성](configuring-client-behaviors.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4eb17-171">For more information about how to configure a custom client behavior, see [Configuring Client Behaviors](configuring-client-behaviors.md).</span></span>  
  
## <a name="creating-callback-objects-for-duplex-services"></a><span data-ttu-id="4eb17-172">이중 서비스에 대한 콜백 개체 만들기</span><span class="sxs-lookup"><span data-stu-id="4eb17-172">Creating Callback Objects for Duplex Services</span></span>  
 <span data-ttu-id="4eb17-173">이중 서비스는 계약 요구 사항에 따라 서비스를 호출하도록 콜백 개체를 제공하기 위해 클라이언트 애플리케이션에서 구현해야 하는 콜백 계약을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4eb17-173">Duplex services specify a callback contract that the client application must implement in order to provide a callback object for the service to call according to the requirements of the contract.</span></span> <span data-ttu-id="4eb17-174">콜백 개체는 정식 서비스가 아니지만(예를 들어, 콜백 개체를 사용하여 채널을 시작할 수 없음) 구현 및 구성을 위해 일종의 서비스로 간주될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4eb17-174">Although callback objects are not full services (for example, you cannot initiate a channel with a callback object), for the purposes of implementation and configuration they can be thought of as a kind of service.</span></span>  
  
 <span data-ttu-id="4eb17-175">이중 서비스의 클라이언트는 다음을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4eb17-175">Clients of duplex services must:</span></span>  
  
- <span data-ttu-id="4eb17-176">콜백 계약 클래스 구현</span><span class="sxs-lookup"><span data-stu-id="4eb17-176">Implement a callback contract class.</span></span>  
  
- <span data-ttu-id="4eb17-177">콜백 계약 구현 클래스의 인스턴스를 만들고이를 사용 하 여 WCF 클라이언트 생성자에 전달 하는 <xref:System.ServiceModel.InstanceContext?displayProperty=nameWithType> 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4eb17-177">Create an instance of the callback contract implementation class and use it to create the <xref:System.ServiceModel.InstanceContext?displayProperty=nameWithType> object that you pass to the WCF client constructor.</span></span>  
  
- <span data-ttu-id="4eb17-178">작업 호출 및 작업 콜백 처리</span><span class="sxs-lookup"><span data-stu-id="4eb17-178">Invoke operations and handle operation callbacks.</span></span>  
  
 <span data-ttu-id="4eb17-179">이중 WCF 클라이언트 개체는 콜백 서비스의 구성을 비롯 하 여 콜백을 지 원하는 데 필요한 기능을 노출 하는 것을 제외 하 고 비 이중 WCF 클라이언트 개체와 동일 하 게 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="4eb17-179">Duplex WCF client objects function like their nonduplex counterparts, with the exception that they expose the functionality necessary to support callbacks, including the configuration of the callback service.</span></span>  
  
 <span data-ttu-id="4eb17-180">예를 들어, 콜백 클래스에서 <xref:System.ServiceModel.CallbackBehaviorAttribute?displayProperty=nameWithType> 특성의 속성을 사용하여 콜백 개체 런타임 동작을 다양하게 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4eb17-180">For example, you can control various aspects of callback object runtime behavior by using properties of the <xref:System.ServiceModel.CallbackBehaviorAttribute?displayProperty=nameWithType> attribute on the callback class.</span></span> <span data-ttu-id="4eb17-181">또 다른 예로, <xref:System.ServiceModel.Description.CallbackDebugBehavior?displayProperty=nameWithType> 클래스를 사용하여 콜백 개체를 호출하는 서비스에 예외 정보를 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4eb17-181">Another example is the use of the <xref:System.ServiceModel.Description.CallbackDebugBehavior?displayProperty=nameWithType> class to enable the return of exception information to services that call the callback object.</span></span> <span data-ttu-id="4eb17-182">자세한 내용은 [이중 서비스](./feature-details/duplex-services.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4eb17-182">For more information, see [Duplex Services](./feature-details/duplex-services.md).</span></span> <span data-ttu-id="4eb17-183">전체 샘플은 [이중](./samples/duplex.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4eb17-183">For a complete sample, see [Duplex](./samples/duplex.md).</span></span>  
  
 <span data-ttu-id="4eb17-184">IIS(인터넷 정보 서비스) 5.1을 실행하는 Windows XP 컴퓨터에서 이중 클라이언트는 <xref:System.ServiceModel.WSDualHttpBinding?displayProperty=nameWithType> 클래스를 사용하여 클라이언트 기본 주소를 지정해야 합니다. 그렇지 않으면 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="4eb17-184">On Windows XP computers running Internet Information Services (IIS) 5.1, duplex clients must specify a client base address using the <xref:System.ServiceModel.WSDualHttpBinding?displayProperty=nameWithType> class or an exception is thrown.</span></span> <span data-ttu-id="4eb17-185">다음 코드 예제에서는 코드에서 이 작업을 수행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4eb17-185">The following code example shows how to do this in code.</span></span>  
  
 [!code-csharp[S_DualHttp#8](../../../samples/snippets/csharp/VS_Snippets_CFX/s_dualhttp/cs/program.cs#8)]
 [!code-vb[S_DualHttp#8](../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_dualhttp/vb/module1.vb#8)]  
  
 <span data-ttu-id="4eb17-186">다음 코드에서는 구성 파일에서 이 작업을 수행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4eb17-186">The following code shows how to do this in a configuration file</span></span>  
  
 [!code-csharp[S_DualHttp#134](../../../samples/snippets/csharp/VS_Snippets_CFX/s_dualhttp/cs/program.cs#134)]  
  
## <a name="calling-services-asynchronously"></a><span data-ttu-id="4eb17-187">비동기적으로 서비스 호출</span><span class="sxs-lookup"><span data-stu-id="4eb17-187">Calling Services Asynchronously</span></span>  
 <span data-ttu-id="4eb17-188">작업이 호출되는 방법은 클라이언트 개발자에 의해 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="4eb17-188">How operations are called is entirely up to the client developer.</span></span> <span data-ttu-id="4eb17-189">작업을 구성하는 메시지는 관리되는 코드에 표시될 때 동기 메서드나 비동기 메서드에 매핑될 수 있기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="4eb17-189">This is because the messages that make up an operation can be mapped to either synchronous or asynchronous methods when expressed in managed code.</span></span> <span data-ttu-id="4eb17-190">따라서 작업을 비동기적으로 호출하는 클라이언트를 빌드하려면 Svcutil.exe에서 `/async` 옵션을 사용하여 비동기 클라이언트 코드를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4eb17-190">Therefore, if you want to build a client that calls operations asynchronously, you can use Svcutil.exe to generate asynchronous client code using the `/async` option.</span></span> <span data-ttu-id="4eb17-191">자세한 내용은 [방법: 비동기적으로 서비스 작업 호출](./feature-details/how-to-call-wcf-service-operations-asynchronously.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4eb17-191">For more information, see [How to: Call Service Operations Asynchronously](./feature-details/how-to-call-wcf-service-operations-asynchronously.md).</span></span>  
  
## <a name="calling-services-using-wcf-client-channels"></a><span data-ttu-id="4eb17-192">WCF 클라이언트 채널을 사용하여 서비스 호출</span><span class="sxs-lookup"><span data-stu-id="4eb17-192">Calling Services Using WCF Client Channels</span></span>  
 <span data-ttu-id="4eb17-193">WCF 클라이언트 형식은 <xref:System.ServiceModel.IClientChannel?displayProperty=nameWithType> 인터페이스에서 파생 되는 <xref:System.ServiceModel.ClientBase%601>확장 하 여 기본 채널 시스템을 노출 합니다.</span><span class="sxs-lookup"><span data-stu-id="4eb17-193">WCF client types extend <xref:System.ServiceModel.ClientBase%601>, which itself derives from <xref:System.ServiceModel.IClientChannel?displayProperty=nameWithType> interface to expose the underlying channel system.</span></span> <span data-ttu-id="4eb17-194"><xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType> 클래스와의 대상 서비스 계약을 사용하여 서비스를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4eb17-194">You can invoke services by using the target service contract with the <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="4eb17-195">자세한 내용은 [WCF 클라이언트 아키텍처](./feature-details/client-architecture.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4eb17-195">For details, see [WCF Client Architecture](./feature-details/client-architecture.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4eb17-196">참조</span><span class="sxs-lookup"><span data-stu-id="4eb17-196">See also</span></span>

- <xref:System.ServiceModel.ClientBase%601?displayProperty=nameWithType>
- <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType>
