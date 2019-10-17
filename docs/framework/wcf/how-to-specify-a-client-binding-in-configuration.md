---
title: '방법: 구성에서 클라이언트 바인딩 지정'
ms.date: 03/30/2017
ms.assetid: 4a7c79aa-50ee-4991-891e-adc0599323a7
ms.openlocfilehash: b16f4b062f7f97a5855b06bdcf348911ee0497d2
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72320857"
---
# <a name="how-to-specify-a-client-binding-in-configuration"></a><span data-ttu-id="e9287-102">방법: 구성에서 클라이언트 바인딩 지정</span><span class="sxs-lookup"><span data-stu-id="e9287-102">How to: Specify a Client Binding in Configuration</span></span>
<span data-ttu-id="e9287-103">이 예제에서는 계산기 서비스를 사용할 클라이언트 콘솔 애플리케이션을 만들고 해당 클라이언트에 대한 바인딩을 구성에 선언적으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e9287-103">In this example, a client console application is created to use a calculator service, and the binding for that client is specified declaratively in configuration.</span></span> <span data-ttu-id="e9287-104">클라이언트는 `CalculatorService` 인터페이스를 구현하는 `ICalculator`에 액세스하고, 서비스 및 클라이언트 모두 <xref:System.ServiceModel.BasicHttpBinding> 클래스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e9287-104">The client accesses the `CalculatorService`, which implements the `ICalculator` interface, and both the service and the client use the <xref:System.ServiceModel.BasicHttpBinding> class.</span></span>  
  
 <span data-ttu-id="e9287-105">설명된 프로시저에서는 계산기 서비스를 실행 중인 것으로 간주합니다.</span><span class="sxs-lookup"><span data-stu-id="e9287-105">The procedure outlined assumes that the calculator service is running.</span></span> <span data-ttu-id="e9287-106">서비스를 빌드하는 방법에 대 한 자세한 내용은 [방법: 구성에서 서비스 바인딩 지정](how-to-specify-a-service-binding-in-configuration.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e9287-106">For information about how to build the service, see [How to: Specify a Service Binding in Configuration](how-to-specify-a-service-binding-in-configuration.md).</span></span> <span data-ttu-id="e9287-107">또한 WCF (Windows Communication Foundation)에서 제공 하는 [ServiceModel Metadata 유틸리티 도구 (svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) 를 사용 하 여 클라이언트 구성 요소를 자동으로 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9287-107">It also uses the [ServiceModel Metadata Utility Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) that Windows Communication Foundation (WCF) provides to automatically generate the client components.</span></span> <span data-ttu-id="e9287-108">도구는 서비스 액세스를 위해 클라이언트 코드 및 구성을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="e9287-108">The tool generates the client code and configuration for accessing the service.</span></span>  
  
 <span data-ttu-id="e9287-109">클라이언트는 두 가지 부분에 빌드됩니다.</span><span class="sxs-lookup"><span data-stu-id="e9287-109">The client is built in two parts.</span></span> <span data-ttu-id="e9287-110">Svcutil.exe는 `ClientCalculator` 인터페이스를 구현하는 `ICalculator`를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="e9287-110">Svcutil.exe generates the `ClientCalculator` that implements the `ICalculator` interface.</span></span> <span data-ttu-id="e9287-111">그런 다음 `ClientCalculator`의 인스턴스를 생성하여 이 클라이언트 애플리케이션을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="e9287-111">This client application is then constructed by constructing an instance of `ClientCalculator`.</span></span>  
  
 <span data-ttu-id="e9287-112">일반적으로 바인딩 및 주소 정보를 코드에서 명령적으로 지정하지 않고 구성에서 선언적으로 지정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e9287-112">It is usually the best practice to specify the binding and address information declaratively in configuration rather than imperatively in code.</span></span> <span data-ttu-id="e9287-113">일반적으로 배포 된 서비스에 대 한 바인딩 및 주소가 서비스를 개발 하는 동안 사용 된 것과 다르기 때문에 일반적으로 코드에서 끝점을 정의 하는 것은 실용적이 지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e9287-113">Defining endpoints in code is usually not practical because the bindings and addresses for a deployed service are typically different from those used while the service is being developed.</span></span> <span data-ttu-id="e9287-114">일반적으로 바인딩 및 주소 지정 정보를 코드와 구분하면 애플리케이션을 다시 컴파일하거나 다시 배포할 필요 없이 해당 정보를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9287-114">More generally, keeping the binding and addressing information out of the code allows them to change without having to recompile or redeploy the application.</span></span>  
  
 <span data-ttu-id="e9287-115">[구성 편집기 도구 (SvcConfigEditor)](configuration-editor-tool-svcconfigeditor-exe.md)를 사용 하 여 다음 구성 단계를 모두 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9287-115">You can perform all of the following configuration steps by using the [Configuration Editor Tool (SvcConfigEditor.exe)](configuration-editor-tool-svcconfigeditor-exe.md).</span></span>  
  
 <span data-ttu-id="e9287-116">이 예제의 소스 복사에 대해서는 [Basicbinding](./samples/basicbinding.md) 샘플을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e9287-116">For the source copy of this example, see the [BasicBinding](./samples/basicbinding.md) sample.</span></span>  
  
### <a name="specifying-a-client-binding-in-configuration"></a><span data-ttu-id="e9287-117">구성에서 클라이언트 바인딩 지정</span><span class="sxs-lookup"><span data-stu-id="e9287-117">Specifying a client binding in configuration</span></span>  
  
1. <span data-ttu-id="e9287-118">명령줄에서 Svcutil.exe를 사용하여 서비스 메타데이터에서 코드를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="e9287-118">Use Svcutil.exe from the command line to generate code from service metadata.</span></span>  
  
    ```console  
    Svcutil.exe <service's Metadata Exchange (MEX) address or HTTP GET address>   
    ```  
  
2. <span data-ttu-id="e9287-119">생성된 클라이언트에는 클라이언트 구현에서 충족해야 하는 서비스 계약을 정의하는 `ICalculator` 인터페이스가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9287-119">The client that is generated contains the `ICalculator` interface that defines the service contract that the client implementation must satisfy.</span></span>  
  
     [!code-csharp[C_HowTo_ConfigureClientBinding#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_configureclientbinding/cs/generatedclient.cs#1)]
     [!code-csharp[C_HowTo_ConfigureClientBinding#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_configureclientbinding/cs/source.cs#1)]  
  
3. <span data-ttu-id="e9287-120">또한 생성된 클라이언트에는 `ClientCalculator`의 구현이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9287-120">The generated client also contains the implementation of the `ClientCalculator`.</span></span>  
  
     [!code-csharp[C_HowTo_ConfigureClientBinding#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_configureclientbinding/cs/generatedclient.cs#2)]
     [!code-csharp[C_HowTo_ConfigureClientBinding#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_configureclientbinding/cs/source.cs#2)]  
  
4. <span data-ttu-id="e9287-121">또한 Svcutil.exe는 <xref:System.ServiceModel.BasicHttpBinding> 클래스를 사용하는 클라이언트의 구성도 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="e9287-121">Svcutil.exe also generates the configuration for the client that uses the <xref:System.ServiceModel.BasicHttpBinding> class.</span></span> <span data-ttu-id="e9287-122">Visual Studio를 사용 하는 경우이 파일의 이름을 App.config로 합니다. 주소 및 바인딩 정보는 서비스 구현 내에서 지정 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e9287-122">When using Visual Studio, name this file App.config. Note that the address and binding information are not specified anywhere inside the implementation of the service.</span></span> <span data-ttu-id="e9287-123">또한 구성 파일에서 해당 정보를 검색하기 위해 코드를 쓰지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e9287-123">Also, code does not have to be written to retrieve that information from the configuration file.</span></span>  
  
     [!code-xml[C_HowTo_ConfigureClientBinding#100](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_configureclientbinding/common/client.exe.config#100)]   
            
5. <span data-ttu-id="e9287-124">애플리케이션에서 `ClientCalculator`의 인스턴스를 만든 다음 서비스 작업을 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="e9287-124">Create an instance of the `ClientCalculator` in an application, and then call the service operations.</span></span>  
  
     [!code-csharp[C_HowTo_ConfigureClientBinding#3](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_configureclientbinding/cs/client.cs#3)]  
  
6. <span data-ttu-id="e9287-125">클라이언트를 컴파일하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e9287-125">Compile and run the client.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9287-126">참조</span><span class="sxs-lookup"><span data-stu-id="e9287-126">See also</span></span>

- [<span data-ttu-id="e9287-127">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="e9287-127">Using Bindings to Configure Services and Clients</span></span>](using-bindings-to-configure-services-and-clients.md)
