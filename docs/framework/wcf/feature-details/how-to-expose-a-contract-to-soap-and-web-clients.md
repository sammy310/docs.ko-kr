---
title: '방법: SOAP 및 웹 클라이언트에 계약 공개'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: bb765a48-12f2-430d-a54d-6f0c20f2a23a
ms.openlocfilehash: fa02260976c710401a05cce3d723cc0f66804c6e
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84593135"
---
# <a name="how-to-expose-a-contract-to-soap-and-web-clients"></a><span data-ttu-id="ccbab-102">방법: SOAP 및 웹 클라이언트에 계약 공개</span><span class="sxs-lookup"><span data-stu-id="ccbab-102">How to: Expose a Contract to SOAP and Web Clients</span></span>

<span data-ttu-id="ccbab-103">기본적으로 WCF (Windows Communication Foundation)는 SOAP 클라이언트 에서만 사용할 수 있는 끝점을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ccbab-103">By default, Windows Communication Foundation (WCF) makes endpoints available only to SOAP clients.</span></span> <span data-ttu-id="ccbab-104">[방법: 기본 WCF 웹 HTTP 서비스 만들기](how-to-create-a-basic-wcf-web-http-service.md)에서는 비 SOAP 클라이언트에서 끝점을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ccbab-104">In [How to: Create a Basic WCF Web HTTP Service](how-to-create-a-basic-wcf-web-http-service.md), an endpoint is made available to non-SOAP clients.</span></span> <span data-ttu-id="ccbab-105">동일한 계약을 웹 엔드포인트 및 SOAP 엔드포인트로 모두 사용해야 하는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ccbab-105">There may be times when you want to make the same contract available both ways, as a Web endpoint and as a SOAP endpoint.</span></span> <span data-ttu-id="ccbab-106">이 항목에서는 이 작업을 수행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ccbab-106">This topic shows an example of how to do this.</span></span>

## <a name="to-define-the-service-contract"></a><span data-ttu-id="ccbab-107">서비스 계약을 정의하려면</span><span class="sxs-lookup"><span data-stu-id="ccbab-107">To define the service contract</span></span>

1. <span data-ttu-id="ccbab-108"><xref:System.ServiceModel.ServiceContractAttribute> <xref:System.ServiceModel.Web.WebInvokeAttribute> <xref:System.ServiceModel.Web.WebGetAttribute> 다음 코드에 표시 된 것 처럼, 및 특성으로 표시 된 인터페이스를 사용 하 여 서비스 계약을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="ccbab-108">Define a service contract using an interface marked with the <xref:System.ServiceModel.ServiceContractAttribute>, <xref:System.ServiceModel.Web.WebInvokeAttribute> and the <xref:System.ServiceModel.Web.WebGetAttribute> attributes, as shown in the following code:</span></span>

    [!code-csharp[htSoapWeb#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#0)]
    [!code-vb[htSoapWeb#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#0)]

    > [!NOTE]
    > <span data-ttu-id="ccbab-109">기본적으로 <xref:System.ServiceModel.Web.WebInvokeAttribute>는 POST 호출을 작업에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="ccbab-109">By default <xref:System.ServiceModel.Web.WebInvokeAttribute> maps POST calls to the operation.</span></span> <span data-ttu-id="ccbab-110">그러나 "method=" 매개 변수를 지정하여 작업에 매핑할 메서드를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ccbab-110">You can, however, specify the method to map to the operation by specifying a "method=" parameter.</span></span> <span data-ttu-id="ccbab-111"><xref:System.ServiceModel.Web.WebGetAttribute>는 "method=" 매개 변수를 사용하지 않고 GET 호출만 서비스 작업에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="ccbab-111"><xref:System.ServiceModel.Web.WebGetAttribute> does not have a "method=" parameter and only maps GET calls to the service operation.</span></span>

2. <span data-ttu-id="ccbab-112">다음 코드와 같이 서비스 계약을 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="ccbab-112">Implement the service contract, as shown in the following code:</span></span>

     [!code-csharp[htSoapWeb#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#1)]
     [!code-vb[htSoapWeb#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#1)]

## <a name="to-host-the-service"></a><span data-ttu-id="ccbab-113">서비스를 호스트하려면</span><span class="sxs-lookup"><span data-stu-id="ccbab-113">To host the service</span></span>

1. <span data-ttu-id="ccbab-114"><xref:System.ServiceModel.ServiceHost>다음 코드와 같이 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ccbab-114">Create a <xref:System.ServiceModel.ServiceHost> object, as shown in the following code:</span></span>

     [!code-csharp[htSoapWeb#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#2)]
     [!code-vb[htSoapWeb#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#2)]

2. <span data-ttu-id="ccbab-115"><xref:System.ServiceModel.Description.ServiceEndpoint>다음 코드와 같이를 사용 하 여 <xref:System.ServiceModel.BasicHttpBinding> SOAP 끝점에 대해를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="ccbab-115">Add a <xref:System.ServiceModel.Description.ServiceEndpoint> with <xref:System.ServiceModel.BasicHttpBinding> for the SOAP endpoint, as shown in the following code:</span></span>

     [!code-csharp[htSoapWeb#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#3)]
     [!code-vb[htSoapWeb#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#3)]

3. <span data-ttu-id="ccbab-116">다음 코드와 같이를 사용 하 여 <xref:System.ServiceModel.Description.ServiceEndpoint> <xref:System.ServiceModel.WebHttpBinding> 비 SOAP 끝점에 대해를 추가 하 고를 <xref:System.ServiceModel.Description.WebHttpBehavior> 끝점에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="ccbab-116">Add a <xref:System.ServiceModel.Description.ServiceEndpoint> with <xref:System.ServiceModel.WebHttpBinding> for the non-SOAP endpoint and add the <xref:System.ServiceModel.Description.WebHttpBehavior> to the endpoint, as shown in the following code:</span></span>

     [!code-csharp[htSoapWeb#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#4)]
     [!code-vb[htSoapWeb#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#4)]

4. <span data-ttu-id="ccbab-117">`Open()` <xref:System.ServiceModel.ServiceHost> 다음 코드와 같이 인스턴스에서를 호출 하 여 서비스 호스트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="ccbab-117">Call `Open()` on a <xref:System.ServiceModel.ServiceHost> instance to open the service host, as shown in the following code:</span></span>

     [!code-csharp[htSoapWeb#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#5)]
     [!code-vb[htSoapWeb#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#5)]

## <a name="to-call-service-operations-mapped-to-get-in-internet-explorer"></a><span data-ttu-id="ccbab-118">Internet Explorer에서 GET에 매핑된 서비스 작업을 호출하려면</span><span class="sxs-lookup"><span data-stu-id="ccbab-118">To call service operations mapped to GET in Internet Explorer</span></span>

1. <span data-ttu-id="ccbab-119">Internet Explorer를 열고 ""를 입력 `http://localhost:8000/Web/EchoWithGet?s=Hello, world!` 한 다음 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="ccbab-119">Open Internet Explorer and type "`http://localhost:8000/Web/EchoWithGet?s=Hello, world!`" and press ENTER.</span></span> <span data-ttu-id="ccbab-120">URL에는 서비스의 기준 주소 ( `http://localhost:8000/` ), 끝점의 상대 주소 (""), 호출할 서비스 작업 ("EchoWithGet") 및 앰퍼샌드 (&)로 구분 된 명명 된 매개 변수 목록이 표시 된 다음 물음표가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ccbab-120">The URL contains the base address of the service (`http://localhost:8000/`), the relative address of the endpoint (""), the service operation to call ("EchoWithGet"), and a question mark followed by a list of named parameters separated by an ampersand (&).</span></span>

## <a name="to-call-service-operations-on-the-web-endpoint-in-code"></a><span data-ttu-id="ccbab-121">코드의 웹 엔드포인트에서 서비스 작업을 호출하려면</span><span class="sxs-lookup"><span data-stu-id="ccbab-121">To call service operations on the Web endpoint in code</span></span>

1. <span data-ttu-id="ccbab-122">다음 코드와 같이 <xref:System.ServiceModel.Web.WebChannelFactory%601> 블록 내에서 `using` 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ccbab-122">Create an instance of <xref:System.ServiceModel.Web.WebChannelFactory%601> within a `using` block, as shown in the following code.</span></span>

     [!code-csharp[htSoapWeb#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#6)]
     [!code-vb[htSoapWeb#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#6)]

> [!NOTE]
> <span data-ttu-id="ccbab-123">`Close()`는 `using` 블록의 끝에 있는 채널에서 자동으로 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="ccbab-123">`Close()` is automatically called on the channel at the end of the `using` block.</span></span>

1. <span data-ttu-id="ccbab-124">다음 코드와 같이 채널을 만들고 서비스를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="ccbab-124">Create the channel and call the service, as shown in the following code.</span></span>

     [!code-csharp[htSoapWeb#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#8)]
     [!code-vb[htSoapWeb#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#8)]

## <a name="to-call-service-operations-on-the-soap-endpoint"></a><span data-ttu-id="ccbab-125">SOAP 엔드포인트에서 서비스 작업을 호출하려면</span><span class="sxs-lookup"><span data-stu-id="ccbab-125">To call service operations on the SOAP endpoint</span></span>

1. <span data-ttu-id="ccbab-126">다음 코드와 같이 <xref:System.ServiceModel.ChannelFactory> 블록 내에서 `using` 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ccbab-126">Create an instance of <xref:System.ServiceModel.ChannelFactory> within a `using` block, as shown in the following code.</span></span>

    [!code-csharp[htSoapWeb#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#10)]
    [!code-vb[htSoapWeb#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#10)]

2. <span data-ttu-id="ccbab-127">다음 코드와 같이 채널을 만들고 서비스를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="ccbab-127">Create the channel and call the service, as shown in the following code.</span></span>

    [!code-csharp[htSoapWeb#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#11)]
    [!code-vb[htSoapWeb#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#11)]

## <a name="to-close-the-service-host"></a><span data-ttu-id="ccbab-128">서비스 호스트를 닫으려면</span><span class="sxs-lookup"><span data-stu-id="ccbab-128">To close the service host</span></span>

1. <span data-ttu-id="ccbab-129">다음 코드와 같이 서비스 호스트를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="ccbab-129">Close the service host, as shown in the following code.</span></span>

    [!code-csharp[htSoapWeb#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#9)]
    [!code-vb[htSoapWeb#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#9)]

## <a name="example"></a><span data-ttu-id="ccbab-130">예제</span><span class="sxs-lookup"><span data-stu-id="ccbab-130">Example</span></span>

<span data-ttu-id="ccbab-131">다음은이 항목에 대 한 전체 코드 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="ccbab-131">The following is the full code listing for this topic:</span></span>

[!code-csharp[htSoapWeb#13](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#13)]
[!code-vb[htSoapWeb#13](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#13)]

## <a name="compiling-the-code"></a><span data-ttu-id="ccbab-132">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="ccbab-132">Compiling the code</span></span>

 <span data-ttu-id="ccbab-133">Service.cs를 컴파일할 때 System.ServiceModel.dll 및 System.ServiceModel.Web.dll을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="ccbab-133">When compiling Service.cs, reference System.ServiceModel.dll and System.ServiceModel.Web.dll.</span></span>

## <a name="see-also"></a><span data-ttu-id="ccbab-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ccbab-134">See also</span></span>

- <xref:System.ServiceModel.WebHttpBinding>
- <xref:System.ServiceModel.Web.WebGetAttribute>
- <xref:System.ServiceModel.Web.WebInvokeAttribute>
- <xref:System.ServiceModel.Web.WebServiceHost>
- <xref:System.ServiceModel.ChannelFactory>
- <xref:System.ServiceModel.Description.WebHttpBehavior>
- [<span data-ttu-id="ccbab-135">WCF 웹 HTTP 프로그래밍 모델</span><span class="sxs-lookup"><span data-stu-id="ccbab-135">WCF Web HTTP Programming Model</span></span>](wcf-web-http-programming-model.md)
