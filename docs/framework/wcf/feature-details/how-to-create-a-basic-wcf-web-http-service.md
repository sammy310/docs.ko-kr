---
title: '방법: 기본 WCF 웹 HTTP 서비스 만들기'
description: WCF에서 웹 끝점을 노출 하는 서비스를 만드는 방법에 대해 알아봅니다. 웹 끝점은 XML 또는 JSON을 사용 하 여 데이터를 보냅니다. SOAP 봉투가 없습니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 877662d3-d372-4e08-b417-51f66a0095cd
ms.openlocfilehash: 7481367f27d973ba809dff5ca1c4a4f168fbbb98
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85247106"
---
# <a name="how-to-create-a-basic-wcf-web-http-service"></a><span data-ttu-id="7c6cd-105">방법: 기본 WCF 웹 HTTP 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="7c6cd-105">How to: Create a Basic WCF Web HTTP Service</span></span>

<span data-ttu-id="7c6cd-106">WCF (Windows Communication Foundation)를 사용 하면 웹 끝점을 노출 하는 서비스를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c6cd-106">Windows Communication Foundation (WCF) allows you to create a service that exposes a Web endpoint.</span></span> <span data-ttu-id="7c6cd-107">웹 엔드포인트는 XML 또는 JSON으로 데이터를 보내며 SOAP 봉투가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7c6cd-107">Web endpoints send data by XML or JSON, there is no SOAP envelope.</span></span> <span data-ttu-id="7c6cd-108">이 항목에서는 이러한 엔드포인트를 노출하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7c6cd-108">This topic demonstrates how to expose such an endpoint.</span></span>

> [!NOTE]
> <span data-ttu-id="7c6cd-109">웹 엔드포인트의 보안을 유지하는 유일한 방법은 전송 보안을 사용하여 HTTPS를 통해 웹 엔드포인트를 노출하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7c6cd-109">The only way to secure a Web endpoint is to expose it through HTTPS, using transport security.</span></span> <span data-ttu-id="7c6cd-110">메시지 기반 보안을 사용하는 경우 보안 정보는 일반적으로 SOAP 헤더에 배치되고 비 SOAP 엔드포인트에 보낸 메시지에 SOAP 봉투가 없기 때문에 보안 정보를 배치할 장소가 없으며 전송 보안을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c6cd-110">When using message-based security, security information is usually placed in SOAP headers and because the messages sent to non-SOAP endpoints contain no SOAP envelope, there is nowhere to place the security information and you must rely on transport security.</span></span>

## <a name="to-create-a-web-endpoint"></a><span data-ttu-id="7c6cd-111">웹 엔드포인트를 만들려면</span><span class="sxs-lookup"><span data-stu-id="7c6cd-111">To create a Web endpoint</span></span>

1. <span data-ttu-id="7c6cd-112"><xref:System.ServiceModel.ServiceContractAttribute>, <xref:System.ServiceModel.Web.WebInvokeAttribute> 및 <xref:System.ServiceModel.Web.WebGetAttribute> 특성으로 표시된 인터페이스를 사용하여 서비스 계약을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="7c6cd-112">Define a service contract using an interface marked with the <xref:System.ServiceModel.ServiceContractAttribute>, <xref:System.ServiceModel.Web.WebInvokeAttribute> and the <xref:System.ServiceModel.Web.WebGetAttribute> attributes.</span></span>

     [!code-csharp[htBasicService#0](~/samples/snippets/csharp/VS_Snippets_CFX/htbasicservice/cs/service.cs#0)]
     [!code-vb[htBasicService#0](~/samples/snippets/visualbasic/VS_Snippets_CFX/htbasicservice/vb/service.vb#0)]

    > [!NOTE]
    > <span data-ttu-id="7c6cd-113">기본적으로 <xref:System.ServiceModel.Web.WebInvokeAttribute>는 POST 호출을 작업에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="7c6cd-113">By default, <xref:System.ServiceModel.Web.WebInvokeAttribute> maps POST calls to the operation.</span></span> <span data-ttu-id="7c6cd-114">그러나 "method=" 매개 변수를 지정하여 작업에 매핑할 HTTP 메서드(예: HEAD, PUT 또는 DELETE)를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c6cd-114">You can, however, specify the HTTP method (for example, HEAD, PUT, or DELETE) to map to the operation by specifying a "method=" parameter.</span></span> <span data-ttu-id="7c6cd-115"><xref:System.ServiceModel.Web.WebGetAttribute>는 "method=" 매개 변수를 사용하지 않고 GET 호출만 서비스 작업에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="7c6cd-115"><xref:System.ServiceModel.Web.WebGetAttribute> does not have a "method=" parameter and only maps GET calls to the service operation.</span></span>

2. <span data-ttu-id="7c6cd-116">서비스 계약을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="7c6cd-116">Implement the service contract.</span></span>

     [!code-csharp[htBasicService#1](~/samples/snippets/csharp/VS_Snippets_CFX/htbasicservice/cs/service.cs#1)]
     [!code-vb[htBasicService#1](~/samples/snippets/visualbasic/VS_Snippets_CFX/htbasicservice/vb/service.vb#1)]

## <a name="to-host-the-service"></a><span data-ttu-id="7c6cd-117">서비스를 호스트하려면</span><span class="sxs-lookup"><span data-stu-id="7c6cd-117">To host the service</span></span>

1. <span data-ttu-id="7c6cd-118"><xref:System.ServiceModel.Web.WebServiceHost> 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7c6cd-118">Create a <xref:System.ServiceModel.Web.WebServiceHost> object.</span></span>

     [!code-csharp[htBasicService#2](~/samples/snippets/csharp/VS_Snippets_CFX/htbasicservice/cs/service.cs#2)]
     [!code-vb[htBasicService#2](~/samples/snippets/visualbasic/VS_Snippets_CFX/htbasicservice/vb/service.vb#2)]

2. <span data-ttu-id="7c6cd-119"><xref:System.ServiceModel.Description.ServiceEndpoint>를 <xref:System.ServiceModel.Description.WebHttpBehavior>와 함께 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7c6cd-119">Add a <xref:System.ServiceModel.Description.ServiceEndpoint> with the <xref:System.ServiceModel.Description.WebHttpBehavior>.</span></span>

     [!code-csharp[htBasicService#3](~/samples/snippets/csharp/VS_Snippets_CFX/htbasicservice/cs/service.cs#3)]
     [!code-vb[htBasicService#3](~/samples/snippets/visualbasic/VS_Snippets_CFX/htbasicservice/vb/service.vb#3)]

    > [!NOTE]
    > <span data-ttu-id="7c6cd-120">엔드포인트를 추가하지 않으면 <xref:System.ServiceModel.Web.WebServiceHost>는 자동으로 기본 엔드포인트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7c6cd-120">If you do not add an endpoint, <xref:System.ServiceModel.Web.WebServiceHost> automatically creates a default endpoint.</span></span> <span data-ttu-id="7c6cd-121"><xref:System.ServiceModel.Web.WebServiceHost>는 또한 <xref:System.ServiceModel.Description.WebHttpBehavior>를 추가하고 메타데이터 엔드포인트가 기본 HTTP 엔드포인트와 간섭하지 않도록 HTTP 도움말 페이지 및 WSDL(웹 서비스 기술 언어) GET 기능을 비활성화합니다.</span><span class="sxs-lookup"><span data-stu-id="7c6cd-121"><xref:System.ServiceModel.Web.WebServiceHost> also adds <xref:System.ServiceModel.Description.WebHttpBehavior> and disables the HTTP Help page and the Web Services Description Language (WSDL) GET functionality so the metadata endpoint does not interfere with the default HTTP endpoint.</span></span>
    >
    >  <span data-ttu-id="7c6cd-122">비 SOAP 엔드포인트를 ""의 URL과 함께 추가하면 엔드포인트에서 작업 호출 시도 시 예기치 못한 동작이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="7c6cd-122">Adding a non-SOAP endpoint with a URL of "" causes unexpected behavior when an attempt is made to call an operation on the endpoint.</span></span> <span data-ttu-id="7c6cd-123">이는 끝점의 수신 대기 URI가 도움말 페이지의 URI (WCF 서비스의 기본 주소를 찾아볼 때 표시 되는 페이지)와 동일 하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="7c6cd-123">The reason for this is the listen URI of the endpoint is the same as the URI for the help page (the page that is displayed when you browse to the base address of a WCF service).</span></span>

     <span data-ttu-id="7c6cd-124">이러한 동작이 발생되지 않도록 하기 위해 다음 작업 중 하나를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c6cd-124">You can do one of the following actions to prevent this from happening:</span></span>

    - <span data-ttu-id="7c6cd-125">항상 비 SOAP 엔드포인트에 공백 없는 URI를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7c6cd-125">Always specify a non-blank URI for a non-SOAP endpoint.</span></span>

    - <span data-ttu-id="7c6cd-126">도움말 페이지를 끕니다.</span><span class="sxs-lookup"><span data-stu-id="7c6cd-126">Turn off the help page.</span></span> <span data-ttu-id="7c6cd-127">다음 코드를 사용 하 여이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c6cd-127">This can be done with the following code:</span></span>

     [!code-csharp[htBasicService#4](~/samples/snippets/csharp/VS_Snippets_CFX/htbasicservice/cs/snippets.cs#4)]
     [!code-vb[htBasicService#4](~/samples/snippets/visualbasic/VS_Snippets_CFX/htbasicservice/vb/snippets.vb#4)]

3. <span data-ttu-id="7c6cd-128">서비스 호스트를 열고 사용자가 Enter 키를 누를 때까지 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="7c6cd-128">Open the service host and wait until the user presses ENTER.</span></span>

     [!code-csharp[htBasicService#5](~/samples/snippets/csharp/VS_Snippets_CFX/htbasicservice/cs/snippets.cs#5)]
     [!code-vb[htBasicService#5](~/samples/snippets/visualbasic/VS_Snippets_CFX/htbasicservice/vb/snippets.vb#5)]

     <span data-ttu-id="7c6cd-129">이 샘플에서는 콘솔 애플리케이션에서 웹 스타일 서비스를 호스팅하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7c6cd-129">This sample demonstrates how to host a Web-Style service with a console application.</span></span> <span data-ttu-id="7c6cd-130">IIS 내에서도 이러한 서비스를 호스팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c6cd-130">You can also host such a service within IIS.</span></span> <span data-ttu-id="7c6cd-131">이 작업을 수행하려면 다음 코드에서처럼 .svc 파일에서 <xref:System.ServiceModel.Activation.WebServiceHostFactory> 클래스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7c6cd-131">To do this, specify the <xref:System.ServiceModel.Activation.WebServiceHostFactory> class in a .svc file as the following code demonstrates.</span></span>

    ```text
    <%ServiceHost
        language=c#
        Debug="true"
        Service="Microsoft.Samples.Service"
        Factory=System.ServiceModel.Activation.WebServiceHostFactory%>
    ```

## <a name="to-call-service-operations-mapped-to-get-in-internet-explorer"></a><span data-ttu-id="7c6cd-132">Internet Explorer에서 GET에 매핑된 서비스 작업을 호출하려면</span><span class="sxs-lookup"><span data-stu-id="7c6cd-132">To call service operations mapped to GET in Internet Explorer</span></span>

1. <span data-ttu-id="7c6cd-133">Internet Explorer를 열고 ""를 입력 `http://localhost:8000/EchoWithGet?s=Hello, world!` 한 다음 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="7c6cd-133">Open Internet Explorer and type "`http://localhost:8000/EchoWithGet?s=Hello, world!`" and press ENTER.</span></span> <span data-ttu-id="7c6cd-134">URL에는 서비스의 기준 주소 ( `http://localhost:8000/` ), 끝점의 상대 주소 (""), 호출할 서비스 작업 ("EchoWithGet") 및 앰퍼샌드 (&)로 구분 된 명명 된 매개 변수 목록이 표시 된 다음 물음표가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c6cd-134">The URL contains the base address of the service (`http://localhost:8000/`), the relative address of the endpoint (""), the service operation to call ("EchoWithGet"), and a question mark followed by a list of named parameters separated by an ampersand (&).</span></span>

## <a name="to-call-service-operations-in-code"></a><span data-ttu-id="7c6cd-135">코드에서 서비스 작업을 호출하려면</span><span class="sxs-lookup"><span data-stu-id="7c6cd-135">To call service operations in code</span></span>

1. <span data-ttu-id="7c6cd-136"><xref:System.ServiceModel.ChannelFactory%601> 블록 내에서 `using` 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7c6cd-136">Create an instance of <xref:System.ServiceModel.ChannelFactory%601> within a `using` block.</span></span>

     [!code-csharp[htBasicService#6](~/samples/snippets/csharp/VS_Snippets_CFX/htbasicservice/cs/service.cs#6)]
     [!code-vb[htBasicService#6](~/samples/snippets/visualbasic/VS_Snippets_CFX/htbasicservice/vb/service.vb#6)]

2. <span data-ttu-id="7c6cd-137"><xref:System.ServiceModel.Description.WebHttpBehavior>가 호출하는 엔드포인트에 <xref:System.ServiceModel.ChannelFactory%601>를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7c6cd-137">Add <xref:System.ServiceModel.Description.WebHttpBehavior> to the endpoint the <xref:System.ServiceModel.ChannelFactory%601> calls.</span></span>

     [!code-csharp[htBasicService#7](~/samples/snippets/csharp/VS_Snippets_CFX/htbasicservice/cs/service.cs#7)]
     [!code-vb[htBasicService#7](~/samples/snippets/visualbasic/VS_Snippets_CFX/htbasicservice/vb/service.vb#7)]

3. <span data-ttu-id="7c6cd-138">채널을 만들고 서비스를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="7c6cd-138">Create the channel and call the service.</span></span>

     [!code-csharp[htBasicService#8](~/samples/snippets/csharp/VS_Snippets_CFX/htbasicservice/cs/service.cs#8)]
     [!code-vb[htBasicService#8](~/samples/snippets/visualbasic/VS_Snippets_CFX/htbasicservice/vb/service.vb#8)]

4. <span data-ttu-id="7c6cd-139"><xref:System.ServiceModel.Web.WebServiceHost>를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="7c6cd-139">Close the <xref:System.ServiceModel.Web.WebServiceHost>.</span></span>

     [!code-csharp[htBasicService#9](~/samples/snippets/csharp/VS_Snippets_CFX/htbasicservice/cs/service.cs#9)]
     [!code-vb[htBasicService#9](~/samples/snippets/visualbasic/VS_Snippets_CFX/htbasicservice/vb/service.vb#9)]

## <a name="example"></a><span data-ttu-id="7c6cd-140">예제</span><span class="sxs-lookup"><span data-stu-id="7c6cd-140">Example</span></span>

<span data-ttu-id="7c6cd-141">다음은 이 예제에 해당되는 전체 코드 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="7c6cd-141">The following is the full code listing for this example.</span></span>

[!code-csharp[htBasicService#10](~/samples/snippets/csharp/VS_Snippets_CFX/htbasicservice/cs/service.cs#10)]
[!code-vb[htBasicService#10](~/samples/snippets/visualbasic/VS_Snippets_CFX/htbasicservice/vb/service.vb#10)]

## <a name="compiling-the-code"></a><span data-ttu-id="7c6cd-142">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="7c6cd-142">Compiling the code</span></span>

<span data-ttu-id="7c6cd-143">Service.cs를 컴파일할 때 System.ServiceModel.dll 및 System.ServiceModel.Web.dll을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="7c6cd-143">When compiling Service.cs reference System.ServiceModel.dll and System.ServiceModel.Web.dll.</span></span>

## <a name="see-also"></a><span data-ttu-id="7c6cd-144">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7c6cd-144">See also</span></span>

- <xref:System.ServiceModel.WebHttpBinding>
- <xref:System.ServiceModel.Web.WebGetAttribute>
- <xref:System.ServiceModel.Web.WebInvokeAttribute>
- <xref:System.ServiceModel.Web.WebServiceHost>
- <xref:System.ServiceModel.Description.WebHttpBehavior>
- [<span data-ttu-id="7c6cd-145">WCF 웹 HTTP 프로그래밍 모델</span><span class="sxs-lookup"><span data-stu-id="7c6cd-145">WCF Web HTTP Programming Model</span></span>](wcf-web-http-programming-model.md)
