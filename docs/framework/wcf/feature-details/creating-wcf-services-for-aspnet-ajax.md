---
description: '자세한 정보: ASP.NET AJAX 용 WCF 서비스 만들기'
title: ASP.NET AJAX용 WCF 서비스 만들기
ms.date: 03/30/2017
ms.assetid: 04c0402c-e617-4ba5-aedf-d17692234776
ms.openlocfilehash: e4ab977db5632de0c9e825e03369506d4917709f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99705124"
---
# <a name="creating-wcf-services-for-aspnet-ajax"></a><span data-ttu-id="5ae8b-103">ASP.NET AJAX용 WCF 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="5ae8b-103">Creating WCF Services for ASP.NET AJAX</span></span>

<span data-ttu-id="5ae8b-104">Microsoft ASP.NET AJAX를 사용하면 응답성이 높고 친숙한 사용자 인터페이스 요소를 통해 풍부한 사용자 경험을 제공하는 웹 페이지를 빠르게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ae8b-104">Microsoft ASP.NET AJAX enables you to quickly create Web pages that include a rich user experience with responsive and familiar user interface elements.</span></span> <span data-ttu-id="5ae8b-105">ASP.NET AJAX는 크로스 브라우저 ECMAScript(JavaScript) 및 DHTML(동적 HTML) 기술을 통합하는 클라이언트 스크립트 라이브러리를 제공하며 ASP.NET 2.0 서버 기반 개발 플랫폼과 통합됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ae8b-105">ASP.NET AJAX provides client-script libraries that incorporate cross-browser ECMAScript (JavaScript) and dynamic HTML (DHTML) technologies, and it integrates them with the ASP.NET 2.0 server-based development platform.</span></span> <span data-ttu-id="5ae8b-106">ASP.NET AJAX를 사용하여 사용자 환경 및 웹 애플리케이션의 효율성을 개선할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ae8b-106">By using ASP.NET AJAX, you can improve the user experience and the efficiency of your Web applications.</span></span>

<span data-ttu-id="5ae8b-107">ASP.NET AJAX는 강력한 개발 프레임워크를 제공하기 위해 통합된 서버 구성 요소와 클라이언트 스크립트 라이브러리로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ae8b-107">ASP.NET AJAX consists of client-script libraries and of server components that are integrated to provide a robust development framework.</span></span> <span data-ttu-id="5ae8b-108">ASP.NET 페이지에서 서비스에 액세스하려는 경우 일단, 서비스 URL을 페이지의 ASP.NET 스크립트 관리자 컨트롤에 추가하면 일반 JavaScript 기능 호출과 똑같은 JavaScript 코드를 사용하여 서비스 작업을 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ae8b-108">To access a service from an ASP.NET page: once the service URL is added to the ASP.NET Script Manager control on the page, service operations may be invoked using JavaScript code that looks exactly like a regular JavaScript function call.</span></span>

<span data-ttu-id="5ae8b-109">가장 Windows Communication Foundation (WCF) 서비스는 적절 한 ASP.NET AJAX 끝점을 추가 하 여 ASP.NET AJAX와 호환 되는 서비스로 노출 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ae8b-109">Most Windows Communication Foundation (WCF) services may be exposed as a service compatible with ASP.NET AJAX by adding an appropriate ASP.NET AJAX endpoint.</span></span>

<span data-ttu-id="5ae8b-110">Visual Studio를 사용 하는 경우 ASP.NET 웹 사이트 또는 웹 응용 프로그램으로 작업할 때 **새 항목 추가** 대화 상자에서 사용할 수 있는 AJAX 사용 WCF 서비스에 대해 미리 작성 된 템플릿을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ae8b-110">If you are using Visual Studio, you may use a pre-built template for AJAX-enabled WCF services, available in the **Add New Item** dialog when working with ASP.NET Web Sites or Web Applications.</span></span>

<span data-ttu-id="5ae8b-111">Visual Studio 템플릿을 사용하지 않는 경우 다음 두 가지 방법으로 ASP.NET AJAX 엔드포인트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5ae8b-111">If you are not using the Visual Studio templates, there are two ways to create an ASP.NET AJAX endpoint:</span></span>

- <span data-ttu-id="5ae8b-112">구성을 사용하지 않고 동적 호스트 활성화를 사용하여 엔드포인트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5ae8b-112">Create the endpoint using dynamic host activation without using any configuration.</span></span> <span data-ttu-id="5ae8b-113">이 방법은 WCF 구성 시스템에 익숙하지 않은 경우 사용할 수 있는 가장 기본적인 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="5ae8b-113">This is the most basic approach if you are unfamiliar with the WCF configuration system.</span></span> <span data-ttu-id="5ae8b-114">자세한 내용은 [방법: 구성을 사용 하지 않고 ASP.NET AJAX 끝점 추가](how-to-add-an-aspnet-ajax-endpoint-without-using-configuration.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5ae8b-114">For more information, see [How to: Add an ASP.NET AJAX Endpoint Without Using Configuration](how-to-add-an-aspnet-ajax-endpoint-without-using-configuration.md).</span></span>

- <span data-ttu-id="5ae8b-115">구성을 사용 하 여 WCF 서비스에 AJAX 사용 끝점을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ae8b-115">Add an AJAX-enabled endpoint to a WCF service using configuration.</span></span> <span data-ttu-id="5ae8b-116">자세한 내용은 [방법: 구성을 사용 하 여 ASP.NET AJAX 끝점 추가](how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5ae8b-116">For more information, see [How to: Use Configuration to Add an ASP.NET AJAX Endpoint](how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md).</span></span>

<span data-ttu-id="5ae8b-117">[WCF 웹 HTTP 프로그래밍 모델 개요](wcf-web-http-programming-model-overview.md) 에 설명 된 웹 프로그래밍 모델은 ASP.NET AJAX 서비스와 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ae8b-117">The Web Programming Model described in the [WCF Web HTTP Programming Model Overview](wcf-web-http-programming-model-overview.md) may be used with ASP.NET AJAX services.</span></span> <span data-ttu-id="5ae8b-118">특히:</span><span class="sxs-lookup"><span data-stu-id="5ae8b-118">Specifically:</span></span>

- <span data-ttu-id="5ae8b-119"><xref:System.ServiceModel.Web.WebGetAttribute> 및 <xref:System.ServiceModel.Web.WebInvokeAttribute> 특성을 사용하여 HTTP GET 및 HTTP POST 동사 중에서 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ae8b-119">You can use the <xref:System.ServiceModel.Web.WebGetAttribute> and <xref:System.ServiceModel.Web.WebInvokeAttribute> attributes to select between HTTP GET and HTTP POST verbs.</span></span> <span data-ttu-id="5ae8b-120">이 기능을 올바르게 사용하면 애플리케이션의 성능이 크게 향상될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ae8b-120">If used correctly, this may significantly improve your application’s performance.</span></span> <span data-ttu-id="5ae8b-121">자세한 내용은 [방법: ASP.NET AJAX 끝점에 대 한 HTTP POST 및 HTTP GET 요청 중에서 선택](http-post-and-http-get-requests-for-aspnet-ajax-endpoints.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5ae8b-121">For more information, see [How to: Choose between HTTP POST and HTTP GET requests for ASP.NET AJAX Endpoints](http-post-and-http-get-requests-for-aspnet-ajax-endpoints.md).</span></span>

- <span data-ttu-id="5ae8b-122"><xref:System.ServiceModel.Web.WebGetAttribute.ResponseFormat%2A> 및 <xref:System.ServiceModel.Web.WebInvokeAttribute.ResponseFormat%2A> 속성을 사용하여 서비스에서 기본 JSON(JavaScript Object Notation) 대신 XML 데이터를 반환하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ae8b-122">You can use the <xref:System.ServiceModel.Web.WebGetAttribute.ResponseFormat%2A> and <xref:System.ServiceModel.Web.WebInvokeAttribute.ResponseFormat%2A> properties to cause your service to return XML data instead of the default JavaScript Object Notation (JSON).</span></span> <span data-ttu-id="5ae8b-123">ASP.NET AJAX 프레임워크를 사용하여 이 작업을 수행하면 JavaScript 클라이언트가 XML DOM 개체를 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ae8b-123">Doing this with the ASP.NET AJAX framework causes the JavaScript client to receive an XML DOM object.</span></span>

  > [!WARNING]
  > <span data-ttu-id="5ae8b-124">이 작업을 수행하려면 콘텐츠 형식을 text/xml로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ae8b-124">Your operation must set the content type to text/xml for this to work.</span></span> <span data-ttu-id="5ae8b-125">그렇지 않으면 JavaScript 클라이언트가 XML DOM 개체 대신 XML이 들어 있는 문자열을 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ae8b-125">Otherwise, the JavaScript client will receive a string containing the XML instead of an XML DOM object.</span></span>

    <span data-ttu-id="5ae8b-126">다음은 콘텐츠 형식이 적절하게 설정된 XML 데이터를 반환하는 작업의 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="5ae8b-126">The following is an example of an operation that returns XML data with the content type set appropriately:</span></span>

  ```csharp
  [OperationContract, WebGet(ResponseFormat=WebMessageFormat.Xml)]
  public XElement GetData()
  {
      XElement x;
      //Get some data here...

      WebOperationContext.Current.OutgoingResponse.ContentType = "text/xml";
      return x;
  }
  ```

- <span data-ttu-id="5ae8b-127">ASP.NET AJAX와의 호환성이 필요한 경우에는 <xref:System.ServiceModel.Web.WebGetAttribute> 및 <xref:System.ServiceModel.Web.WebInvokeAttribute> 특성의 다른 속성을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5ae8b-127">No other properties on the <xref:System.ServiceModel.Web.WebGetAttribute> and <xref:System.ServiceModel.Web.WebInvokeAttribute> attributes can be changed if compatibility with ASP.NET AJAX is required.</span></span> <span data-ttu-id="5ae8b-128">ASP.NET AJAX 호출 규칙을 위반하지 않는 한 웹 프로그래밍 모델의 다른 부분을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ae8b-128">Other aspects of the Web Programming Model can be used as long as the ASP.NET AJAX calling conventions are not violated.</span></span>

 <span data-ttu-id="5ae8b-129">고급 시나리오의 경우 WCF의 AJAX 지원에 대 한 추가 정보를 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ae8b-129">More advanced scenarios require some additional details of AJAX support in WCF be understood:</span></span>

- <span data-ttu-id="5ae8b-130">JavaScript를 사용 하 여 AJAX 페이지 클라이언트와 WCF 서비스 간에 데이터를 전송 하는 방법을 이해 하 고 .NET Framework 형식이 JavaScript 형식에 매핑되는 방법에 대 한 자세한 내용은 [JSON 및 기타 데이터 전송 형식에 대 한 지원](support-for-json-and-other-data-transfer-formats.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5ae8b-130">To understand how data is transferred between an AJAX page client and a WCF service using JavaScript, and for details on how .NET Framework types map to JavaScript types, see [Support for JSON and Other Data Transfer Formats](support-for-json-and-other-data-transfer-formats.md).</span></span>

- <span data-ttu-id="5ae8b-131">URL 기반 인증 및 ASP.NET 세션 정보 액세스 등 ASP.NET 기능을 사용하려면 구성을 통해 ASP.NET 호환 모드를 활성화하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5ae8b-131">To take advantage of ASP.NET features, for example, URL-based authentication and accessing the ASP.NET session information, you may want to enable the ASP.NET Compatibility Mode through configuration.</span></span>

<span data-ttu-id="5ae8b-132">WCF의 AJAX 끝점은 ASP.NET AJAX 프레임 워크 없이도 사용 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ae8b-132">AJAX endpoints in WCF may even be consumed without the ASP.NET AJAX framework.</span></span> <span data-ttu-id="5ae8b-133">이렇게 하려면 WCF에서 AJAX 지원의 지원 아키텍처를 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ae8b-133">Doing so requires an understanding of the support architecture of AJAX support in WCF.</span></span> <span data-ttu-id="5ae8b-134">이 아키텍처에 대 한 자세한 내용은 [WCF 웹 HTTP 프로그래밍 개체 모델](wcf-web-http-programming-object-model.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5ae8b-134">For a discussion of this architecture, see [WCF Web HTTP Programming Object Model](wcf-web-http-programming-object-model.md).</span></span> <span data-ttu-id="5ae8b-135">이 방법을 보여 주는 코드 샘플은 [JSON 및 XML을 사용 하는 AJAX 서비스](../samples/ajax-service-with-json-and-xml-sample.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5ae8b-135">For a code sample demonstrating this approach, see the [AJAX Service with JSON and XML](../samples/ajax-service-with-json-and-xml-sample.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="5ae8b-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5ae8b-136">See also</span></span>

- [<span data-ttu-id="5ae8b-137">WCF 웹 HTTP 프로그래밍 모델</span><span class="sxs-lookup"><span data-stu-id="5ae8b-137">WCF Web HTTP Programming Model</span></span>](wcf-web-http-programming-model.md)
- [<span data-ttu-id="5ae8b-138">방법: 구성을 사용하지 않고 ASP.NET AJAX 엔드포인트 추가</span><span class="sxs-lookup"><span data-stu-id="5ae8b-138">How to: Add an ASP.NET AJAX Endpoint Without Using Configuration</span></span>](how-to-add-an-aspnet-ajax-endpoint-without-using-configuration.md)
- [<span data-ttu-id="5ae8b-139">방법: 구성을 사용하여 ASP.NET AJAX 엔드포인트 추가</span><span class="sxs-lookup"><span data-stu-id="5ae8b-139">How to: Use Configuration to Add an ASP.NET AJAX Endpoint</span></span>](how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md)
- [<span data-ttu-id="5ae8b-140">방법: ASP.NET AJAX 엔드포인트에 대한 HTTP POST 및 HTTP GET 요청 중에서 선택</span><span class="sxs-lookup"><span data-stu-id="5ae8b-140">How to: Choose between HTTP POST and HTTP GET requests for ASP.NET AJAX Endpoints</span></span>](http-post-and-http-get-requests-for-aspnet-ajax-endpoints.md)
