---
title: '방법: 관리형 애플리케이션에서 WCF 서비스 호스트'
ms.date: 09/17/2018
dev_langs:
- csharp
- vb
ms.assetid: 5eb29db0-b6dc-4e77-8c68-0a62f79d743b
ms.openlocfilehash: b6d1c9c38e2cc5f1b1b7b5538af0339987563de6
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65637587"
---
# <a name="how-to-host-a-wcf-service-in-a-managed-app"></a><span data-ttu-id="bf583-102">방법: 관리 되는 앱에서 WCF 서비스 호스팅</span><span class="sxs-lookup"><span data-stu-id="bf583-102">How to: Host a WCF service in a managed app</span></span>

<span data-ttu-id="bf583-103">관리되는 응용 프로그램 내에서 서비스를 호스팅하려면 관리되는 응용 프로그램 코드 내에 서비스에 대한 코드를 포함하고, 코드에서 명령적으로, 구성을 통해 선언적으로 또는 기본 엔드포인트를 사용해 서비스에 대한 엔드포인트를 정의한 다음 <xref:System.ServiceModel.ServiceHost>의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="bf583-103">To host a service inside a managed application, embed the code for the service inside the managed application code, define an endpoint for the service either imperatively in code, declaratively through configuration, or using default endpoints, and then create an instance of <xref:System.ServiceModel.ServiceHost>.</span></span>

<span data-ttu-id="bf583-104">메시지 받기를 시작하려면 <xref:System.ServiceModel.ICommunicationObject.Open%2A>에서 <xref:System.ServiceModel.ServiceHost>을 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="bf583-104">To start receiving messages, call <xref:System.ServiceModel.ICommunicationObject.Open%2A> on <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="bf583-105">이렇게 하면 서비스에 대한 수신기가 만들어지고 열립니다.</span><span class="sxs-lookup"><span data-stu-id="bf583-105">This creates and opens the listener for the service.</span></span> <span data-ttu-id="bf583-106">관리되는 응용 프로그램이 호스팅 작업을 직접 수행하므로 이런 방식으로 서비스를 호스팅하는 것을 "자체 호스팅"이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf583-106">Hosting a service in this way is often referred to as "self-hosting" because the managed application is doing the hosting work itself.</span></span> <span data-ttu-id="bf583-107">서비스를 닫으려면 <xref:System.ServiceModel.Channels.CommunicationObject.Close%2A?displayProperty=nameWithType>에서 <xref:System.ServiceModel.ServiceHost>를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="bf583-107">To close the service, call <xref:System.ServiceModel.Channels.CommunicationObject.Close%2A?displayProperty=nameWithType> on <xref:System.ServiceModel.ServiceHost>.</span></span>

<span data-ttu-id="bf583-108">서비스는 관리되는 Windows 서비스, IIS(인터넷 정보 서비스) 또는 WAS(Windows Process Activation Service)에서 호스팅될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf583-108">A service can also be hosted in a managed Windows service, in Internet Information Services (IIS), or in Windows Process Activation Service (WAS).</span></span> <span data-ttu-id="bf583-109">호스팅 서비스에 대 한 옵션에 대 한 자세한 내용은 참조 하세요. [호스팅 서비스](../../../docs/framework/wcf/hosting-services.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="bf583-109">For more information about hosting options for a service, see [Hosting Services](../../../docs/framework/wcf/hosting-services.md).</span></span>

<span data-ttu-id="bf583-110">관리되는 응용 프로그램에서 서비스를 호스팅할 경우 최소한의 배포 인프라를 필요로 하기 때문에 가장 유연한 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="bf583-110">Hosting a service in a managed application is the most flexible option because it requires the least infrastructure to deploy.</span></span> <span data-ttu-id="bf583-111">관리 되는 응용 프로그램에서 서비스를 호스트 하는 방법에 대 한 자세한 내용은 참조 하세요. [관리 되는 응용 프로그램에서 호스팅](../../../docs/framework/wcf/feature-details/hosting-in-a-managed-application.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="bf583-111">For more information about hosting services in managed applications, see [Hosting in a Managed Application](../../../docs/framework/wcf/feature-details/hosting-in-a-managed-application.md).</span></span>

<span data-ttu-id="bf583-112">다음 절차에서는 콘솔 응용 프로그램에서 자체 호스팅된 서비스를 구현하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bf583-112">The following procedure demonstrates how to implement a self-hosted service in a console application.</span></span>

## <a name="create-a-self-hosted-service"></a><span data-ttu-id="bf583-113">자체 호스팅된 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="bf583-113">Create a self-hosted service</span></span>

1. <span data-ttu-id="bf583-114">새 콘솔 응용 프로그램을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="bf583-114">Create a new console application:</span></span>

   1. <span data-ttu-id="bf583-115">Visual Studio를 열고 선택 **새로 만들기** > **프로젝트** 에서 합니다 **파일** 메뉴.</span><span class="sxs-lookup"><span data-stu-id="bf583-115">Open Visual Studio and select **New** > **Project** from the **File** menu.</span></span>

   2. <span data-ttu-id="bf583-116">에 **설치 된 템플릿** 목록에서 **Visual C#** 또는 **Visual Basic**를 선택한 후 **Windows Desktop**합니다.</span><span class="sxs-lookup"><span data-stu-id="bf583-116">In the **Installed Templates** list, select **Visual C#** or **Visual Basic**, and then select **Windows Desktop**.</span></span>

   3. <span data-ttu-id="bf583-117">선택 된 **콘솔 앱** 템플릿.</span><span class="sxs-lookup"><span data-stu-id="bf583-117">Select the **Console App** template.</span></span> <span data-ttu-id="bf583-118">형식 `SelfHost` 에 **이름** 확인란을 선택한 다음 **확인**합니다.</span><span class="sxs-lookup"><span data-stu-id="bf583-118">Type `SelfHost` in the **Name** box and then choose **OK**.</span></span>

2. <span data-ttu-id="bf583-119">마우스 오른쪽 단추로 클릭 **SelfHost** 에 **솔루션 탐색기** 선택한 **참조 추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="bf583-119">Right-click **SelfHost** in **Solution Explorer** and select **Add Reference**.</span></span> <span data-ttu-id="bf583-120">선택 **System.ServiceModel** 에서 합니다 **.NET** 탭을 선택한 다음 **확인**합니다.</span><span class="sxs-lookup"><span data-stu-id="bf583-120">Select **System.ServiceModel** from the **.NET** tab and then choose **OK**.</span></span>

    > [!TIP]
    > <span data-ttu-id="bf583-121">경우는 **솔루션 탐색기** 창이 표시, 선택 되지 않으면 **솔루션 탐색기** 에서 합니다 **뷰** 메뉴.</span><span class="sxs-lookup"><span data-stu-id="bf583-121">If the **Solution Explorer** window is not visible, select **Solution Explorer** from the **View** menu.</span></span>

3. <span data-ttu-id="bf583-122">두 번 클릭 **Program.cs** 하거나 **Module1.vb** 에서 **솔루션 탐색기** 열려 있지 않으면 코드 창에서 엽니다.</span><span class="sxs-lookup"><span data-stu-id="bf583-122">Double-click **Program.cs** or **Module1.vb** in **Solution Explorer** to open it in the code window, if it's not already open.</span></span> <span data-ttu-id="bf583-123">파일의 맨 위에 다음 문을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf583-123">Add the following statements at the top of the file:</span></span>

     [!code-csharp[CFX_SelfHost4#1](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#1)]
     [!code-vb[CFX_SelfHost4#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#1)]

4. <span data-ttu-id="bf583-124">서비스 계약을 정의 및 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="bf583-124">Define and implement a service contract.</span></span> <span data-ttu-id="bf583-125">이 예제에서는 서비스에 대한 입력을 기준으로 메시지를 반환하는 `HelloWorldService`를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="bf583-125">This example defines a `HelloWorldService` that returns a message based on the input to the service.</span></span>

     [!code-csharp[CFX_SelfHost4#2](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#2)]
     [!code-vb[CFX_SelfHost4#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#2)]

    > [!NOTE]
    > <span data-ttu-id="bf583-126">정의 및 서비스 인터페이스를 구현 하는 방법에 대 한 자세한 내용은 참조 하세요. [방법: 서비스 계약을 정의](../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md) 고 [방법: 서비스 계약을 구현](../../../docs/framework/wcf/how-to-implement-a-wcf-contract.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="bf583-126">For more information about how to define and implement a service interface, see [How to: Define a Service Contract](../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md) and [How to: Implement a Service Contract](../../../docs/framework/wcf/how-to-implement-a-wcf-contract.md).</span></span>

5. <span data-ttu-id="bf583-127">서비스의 기본 주소를 사용하여 `Main` 메서드 맨 위에 <xref:System.Uri> 클래스의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="bf583-127">At the top of the `Main` method, create an instance of the <xref:System.Uri> class with the base address for the service.</span></span>

     [!code-csharp[CFX_SelfHost4#3](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#3)]
     [!code-vb[CFX_SelfHost4#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#3)]

6. <span data-ttu-id="bf583-128"><xref:System.ServiceModel.ServiceHost> 클래스의 인스턴스를 만들어 서비스 형식 및 기본 주소 URI(Uniform Resource Identifier)를 나타내는 <xref:System.Type>을 <xref:System.ServiceModel.ServiceHost.%23ctor%28System.Type%2CSystem.Uri%5B%5D%29>에 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="bf583-128">Create an instance of the <xref:System.ServiceModel.ServiceHost> class, passing a <xref:System.Type> that represents the service type and the base address Uniform Resource Identifier (URI) to the <xref:System.ServiceModel.ServiceHost.%23ctor%28System.Type%2CSystem.Uri%5B%5D%29>.</span></span> <span data-ttu-id="bf583-129">메타데이터 게시를 사용하도록 설정한 다음 <xref:System.ServiceModel.ICommunicationObject.Open%2A>에서 <xref:System.ServiceModel.ServiceHost> 메서드를 호출하여 서비스를 초기화하고 메시지를 받도록 서비스를 준비합니다.</span><span class="sxs-lookup"><span data-stu-id="bf583-129">Enable metadata publishing, and then call the <xref:System.ServiceModel.ICommunicationObject.Open%2A> method on the <xref:System.ServiceModel.ServiceHost> to initialize the service and prepare it to receive messages.</span></span>

     [!code-csharp[CFX_SelfHost4#4](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#4)]
     [!code-vb[CFX_SelfHost4#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#4)]

    > [!NOTE]
    > <span data-ttu-id="bf583-130">이 예제에서는 기본 엔드포인트를 사용하며, 이 서비스에는 구성 파일이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bf583-130">This example uses default endpoints, and no configuration file is required for this service.</span></span> <span data-ttu-id="bf583-131">엔드포인트를 구성하지 않으면 런타임이 서비스에서 구현되는 각 서비스 계약의 각 기본 주소에 대해 엔드포인트를 하나씩 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="bf583-131">If no endpoints are configured, then the runtime creates one endpoint for each base address for each service contract implemented by the service.</span></span> <span data-ttu-id="bf583-132">기본 끝점에 대 한 자세한 내용은 참조 하세요. [Simplified Configuration](../../../docs/framework/wcf/simplified-configuration.md) 하 고 [Simplified Configuration for WCF Services](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="bf583-132">For more information about default endpoints, see [Simplified Configuration](../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>

7. <span data-ttu-id="bf583-133">키를 눌러 **Ctrl**+**Shift**+**B** 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="bf583-133">Press **Ctrl**+**Shift**+**B** to build the solution.</span></span>

## <a name="test-the-service"></a><span data-ttu-id="bf583-134">서비스 테스트</span><span class="sxs-lookup"><span data-stu-id="bf583-134">Test the service</span></span>

1. <span data-ttu-id="bf583-135">키를 눌러 **Ctrl**+**F5** 서비스를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf583-135">Press **Ctrl**+**F5** to run the service.</span></span>

2. <span data-ttu-id="bf583-136">오픈 **WCF 테스트 클라이언트**합니다.</span><span class="sxs-lookup"><span data-stu-id="bf583-136">Open **WCF Test Client**.</span></span>

    > [!TIP]
    > <span data-ttu-id="bf583-137">열려는 **WCF 테스트 클라이언트**, Visual Studio 용 개발자 명령 프롬프트를 열고 및 실행 **WcfTestClient.exe**합니다.</span><span class="sxs-lookup"><span data-stu-id="bf583-137">To open **WCF Test Client**, open Developer Command Prompt for Visual Studio and execute **WcfTestClient.exe**.</span></span>

3. <span data-ttu-id="bf583-138">선택 **추가 서비스** 에서 합니다 **파일** 메뉴.</span><span class="sxs-lookup"><span data-stu-id="bf583-138">Select **Add Service** from the **File** menu.</span></span>

4. <span data-ttu-id="bf583-139">형식 `http://localhost:8080/hello` 주소 상자에 클릭 **확인**합니다.</span><span class="sxs-lookup"><span data-stu-id="bf583-139">Type `http://localhost:8080/hello` into the address box and click **OK**.</span></span>

    > [!TIP]
    > <span data-ttu-id="bf583-140">서비스가 실행 중인지 확인하십시오. 그렇지 않으면 이 단계는 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="bf583-140">Make sure the service is running or else this step fails.</span></span> <span data-ttu-id="bf583-141">코드에서 기본 주소를 변경한 경우에는 이 단계에서 수정된 기본 주소를 사용하십시오.</span><span class="sxs-lookup"><span data-stu-id="bf583-141">If you have changed the base address in the code, then use the modified base address in this step.</span></span>

5. <span data-ttu-id="bf583-142">두 번 클릭 **SayHello** 아래의 합니다 **내 서비스 프로젝트** 노드.</span><span class="sxs-lookup"><span data-stu-id="bf583-142">Double-click **SayHello** under the **My Service Projects** node.</span></span> <span data-ttu-id="bf583-143">에 사용자 이름을 입력 합니다 **값** 열에는 **요청** 목록 및 클릭 **Invoke**합니다.</span><span class="sxs-lookup"><span data-stu-id="bf583-143">Type your name into the **Value** column in the **Request** list, and click **Invoke**.</span></span>

   <span data-ttu-id="bf583-144">회신 메시지에 표시 합니다 **응답** 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="bf583-144">A reply message appears in the **Response** list.</span></span>

## <a name="example"></a><span data-ttu-id="bf583-145">예제</span><span class="sxs-lookup"><span data-stu-id="bf583-145">Example</span></span>

<span data-ttu-id="bf583-146">다음 예제에서는 <xref:System.ServiceModel.ServiceHost> 개체를 만들어 `HelloWorldService` 형식의 서비스를 호스팅한 다음 <xref:System.ServiceModel.ICommunicationObject.Open%2A>에서 <xref:System.ServiceModel.ServiceHost> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="bf583-146">The following example creates a <xref:System.ServiceModel.ServiceHost> object to host a service of type `HelloWorldService`, and then calls the <xref:System.ServiceModel.ICommunicationObject.Open%2A> method on <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="bf583-147">기본 주소는 코드에서 제공되고 메타데이터 게시가 사용하도록 설정되며 기본 엔드포인트가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf583-147">A base address is provided in code, metadata publishing is enabled, and default endpoints are used.</span></span>

[!code-csharp[CFX_SelfHost4#5](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#5)]
[!code-vb[CFX_SelfHost4#5](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#5)]

## <a name="see-also"></a><span data-ttu-id="bf583-148">참고자료</span><span class="sxs-lookup"><span data-stu-id="bf583-148">See also</span></span>

- <xref:System.Uri>
- <xref:System.Configuration.ConfigurationManager.AppSettings%2A>
- <xref:System.Configuration.ConfigurationManager>
- [<span data-ttu-id="bf583-149">방법: IIS에서 WCF 서비스 호스팅</span><span class="sxs-lookup"><span data-stu-id="bf583-149">How to: Host a WCF Service in IIS</span></span>](../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md)
- [<span data-ttu-id="bf583-150">자체 호스팅</span><span class="sxs-lookup"><span data-stu-id="bf583-150">Self-Host</span></span>](../../../docs/framework/wcf/samples/self-host.md)
- [<span data-ttu-id="bf583-151">서비스 호스팅</span><span class="sxs-lookup"><span data-stu-id="bf583-151">Hosting Services</span></span>](../../../docs/framework/wcf/hosting-services.md)
- [<span data-ttu-id="bf583-152">방법: 서비스 계약 정의</span><span class="sxs-lookup"><span data-stu-id="bf583-152">How to: Define a Service Contract</span></span>](../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md)
- [<span data-ttu-id="bf583-153">방법: 서비스 계약 구현</span><span class="sxs-lookup"><span data-stu-id="bf583-153">How to: Implement a Service Contract</span></span>](../../../docs/framework/wcf/how-to-implement-a-wcf-contract.md)
- [<span data-ttu-id="bf583-154">ServiceModel Metadata 유틸리티 도구(Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="bf583-154">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)
- [<span data-ttu-id="bf583-155">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="bf583-155">Using Bindings to Configure Services and Clients</span></span>](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="bf583-156">시스템 제공 바인딩</span><span class="sxs-lookup"><span data-stu-id="bf583-156">System-Provided Bindings</span></span>](../../../docs/framework/wcf/system-provided-bindings.md)
