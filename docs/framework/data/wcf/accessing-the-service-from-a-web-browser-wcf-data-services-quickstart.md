---
title: 웹 브라우저에서 서비스 액세스(WCF Data Services 빠른 시작)
description: Visual Studio에서 WCF Data Services를 시작 하 고 브라우저에서 피드 읽기를 사용 하지 않도록 설정 하는 방법을 알아봅니다. 서비스 정의 문서를 가져오고 데이터 서비스 리소스에 액세스 합니다.
ms.date: 03/30/2017
ms.assetid: 5a6fa180-3094-4e6e-ba2b-8c80975d18d1
ms.openlocfilehash: 713436c31bc3f622c4f44a83e33fff3fcbba1c1c
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85247780"
---
# <a name="accessing-the-service-from-a-web-browser-wcf-data-services-quickstart"></a><span data-ttu-id="2944f-104">웹 브라우저에서 서비스 액세스(WCF Data Services 빠른 시작)</span><span class="sxs-lookup"><span data-stu-id="2944f-104">Accessing the Service from a Web Browser (WCF Data Services Quickstart)</span></span>

<span data-ttu-id="2944f-105">WCF Data Services 빠른 시작의 두 번째 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="2944f-105">This is the second task of the WCF Data Services quickstart.</span></span> <span data-ttu-id="2944f-106">이 작업에서는 Visual Studio에서 WCF Data Services를 시작 하 고 웹 브라우저에서 선택적으로 피드 읽기를 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2944f-106">In this task, you start the WCF Data Services from Visual Studio and optionally disable feed reading in the Web browser.</span></span> <span data-ttu-id="2944f-107">그런 다음 웹 브라우저를 통해 HTTP GET 요청을 노출 된 리소스로 전송 하 여 서비스 정의 문서를 검색 하 고 데이터 서비스 리소스에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="2944f-107">You then retrieve the service definition document as well as access data service resources by submitting HTTP GET requests through a Web browser to the exposed resources.</span></span>

> [!NOTE]
> <span data-ttu-id="2944f-108">기본적으로 Visual Studio에서는 사용자 컴퓨터에서 `localhost` URI에 포트 번호를 자동으로 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="2944f-108">By default, Visual Studio auto-assigns a port number to the `localhost` URI on your computer.</span></span> <span data-ttu-id="2944f-109">이 작업에서는 URI 예제에서 포트 번호 `12345`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2944f-109">This task uses the port number `12345` in the URI examples.</span></span> <span data-ttu-id="2944f-110">Visual Studio 프로젝트에서 특정 포트 번호를 설정 하는 방법에 대 한 자세한 내용은 [데이터 서비스 만들기](creating-the-data-service.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2944f-110">For more information about how to set a specific port number in your Visual Studio project see [Creating the Data Service](creating-the-data-service.md).</span></span>

## <a name="to-request-the-default-service-document-by-using-internet-explorer"></a><span data-ttu-id="2944f-111">Internet Explorer를 사용하여 기본 서비스 문서를 요청하려면</span><span class="sxs-lookup"><span data-stu-id="2944f-111">To request the default service document by using Internet Explorer</span></span>

1. <span data-ttu-id="2944f-112">Internet Explorer의 **도구** 메뉴에서 **인터넷 옵션**을 선택 하 고 **콘텐츠** 탭을 클릭 한 다음 **설정**을 클릭 하 고 **피드 보기 켜기**를 선택 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="2944f-112">In Internet Explorer, from the **Tools** menu, select **Internet Options**, click the **Content** tab, click **Settings**, and clear **Turn on feed viewing**.</span></span>

     <span data-ttu-id="2944f-113">이렇게 하면 피드 읽기가 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2944f-113">This makes sure that feed reading is disabled.</span></span> <span data-ttu-id="2944f-114">이 기능을 사용하지 않도록 설정하지 않으면 웹 브라우저에서 원시 XML 데이터를 표시하지 않고 반환된 AtomPub 인코딩 문서를 XML 피드로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="2944f-114">If you do not disable this functionality, then the Web browser will treat the returned AtomPub encoded document as an XML feed instead of displaying the raw XML data.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2944f-115">브라우저에서 피드를 원시 XML 데이터로 표시할 수 없는 경우 피드를 페이지의 소스 코드로 볼 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2944f-115">If your browser cannot display the feed as raw XML data, you should still be able to view the feed as the source code for the page.</span></span>

2. <span data-ttu-id="2944f-116">Visual Studio에서 **f5** 키를 눌러 응용 프로그램 디버깅을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="2944f-116">In Visual Studio, press the **F5** key to start debugging the application.</span></span>

3. <span data-ttu-id="2944f-117">로컬 컴퓨터에서 웹 브라우저를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="2944f-117">Open a Web browser on the local computer.</span></span> <span data-ttu-id="2944f-118">주소 표시줄에 다음 URI를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="2944f-118">In the address bar, enter the following URI:</span></span>

    ```http
    http://localhost:12345/northwind.svc
    ```

     <span data-ttu-id="2944f-119">이 데이터 서비스에서 노출하는 엔터티 집합 목록을 포함하는 기본 서비스 문서가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="2944f-119">This returns the default service document, which contains a list of entity sets that are exposed by this data service.</span></span>

## <a name="to-access-entity-set-resources-from-a-web-browser"></a><span data-ttu-id="2944f-120">웹 브라우저에서 엔터티 집합 리소스에 액세스하려면</span><span class="sxs-lookup"><span data-stu-id="2944f-120">To access entity set resources from a Web browser</span></span>

1. <span data-ttu-id="2944f-121">웹 브라우저의 주소 표시줄에 다음 URI를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="2944f-121">In the address bar of your Web browser, enter the following URI:</span></span>

    ```http
    http://localhost:12345/northwind.svc/Customers
    ```

     <span data-ttu-id="2944f-122">Northwind 샘플 데이터베이스의 모든 고객 집합이 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="2944f-122">This returns a set of all customers in the Northwind sample database.</span></span>

2. <span data-ttu-id="2944f-123">웹 브라우저의 주소 표시줄에 다음 URI를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="2944f-123">In the address bar of your Web browser, enter the following URI:</span></span>

    ```http
    http://localhost:12345/northwind.svc/Customers('ALFKI')
    ```

     <span data-ttu-id="2944f-124">특정 고객 `ALFKI`의 엔터티 인스턴스가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="2944f-124">This returns an entity instance for the specific customer, `ALFKI`.</span></span>

3. <span data-ttu-id="2944f-125">웹 브라우저의 주소 표시줄에 다음 URI를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="2944f-125">In the address bar of your Web browser, enter the following URI:</span></span>

    ```http
    http://localhost:12345/northwind.svc/Customers('ALFKI')/Orders
    ```

     <span data-ttu-id="2944f-126">고객과 주문 간의 관계가 이동되어 특정 고객 `ALFKI`에 대한 모든 주문 집합이 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="2944f-126">This traverses the relationship between customers and orders to return a set of all orders for the specific customer `ALFKI`.</span></span>

4. <span data-ttu-id="2944f-127">웹 브라우저의 주소 표시줄에 다음 URI를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="2944f-127">In the address bar of your Web browser, enter the following URI:</span></span>

    ```http
    http://localhost:12345/northwind.svc/Customers('ALFKI')/Orders?$filter=OrderID eq 10643
    ```

     <span data-ttu-id="2944f-128">제공한 `ALFKI` 값을 기반으로 특정 주문만 반환되도록 특정 고객 `OrderID`에 속하는 주문이 필터링됩니다.</span><span class="sxs-lookup"><span data-stu-id="2944f-128">This filters orders that belong to the specific customer `ALFKI` so that only a specific order is returned based on the supplied `OrderID` value.</span></span>

## <a name="next-steps"></a><span data-ttu-id="2944f-129">다음 단계</span><span class="sxs-lookup"><span data-stu-id="2944f-129">Next Steps</span></span>

<span data-ttu-id="2944f-130">브라우저에서 지정 된 리소스에 대 한 HTTP GET 요청을 실행 하 여 웹 브라우저에서 WCF Data Services에 성공적으로 액세스 했습니다.</span><span class="sxs-lookup"><span data-stu-id="2944f-130">You have successfully accessed the WCF Data Services from a Web browser, with the browser issuing HTTP GET requests to specified resources.</span></span> <span data-ttu-id="2944f-131">웹 브라우저를 사용하면 간편하게 요청의 주소 지정 구문을 실행해 보고 그 결과를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2944f-131">A Web browser provides an easy way to experiment with the addressing syntax of requests and view the results.</span></span> <span data-ttu-id="2944f-132">그러나 프로덕션 데이터 서비스는 대개 이 방법으로 액세스되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2944f-132">However, a production data service is not generally accessed by this method.</span></span> <span data-ttu-id="2944f-133">애플리케이션은 일반적으로 애플리케이션 코드나 스크립트 언어를 통해 데이터 서비스와 상호 작용합니다.</span><span class="sxs-lookup"><span data-stu-id="2944f-133">Typically, applications interact with the data service through application code or scripting languages.</span></span> <span data-ttu-id="2944f-134">다음에는 클라이언트 라이브러리를 사용하여 CLR(공용 언어 런타임) 개체인 것처럼 데이터 서비스 리소스에 액세스하는 클라이언트 애플리케이션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2944f-134">Next, you will create a client application that uses client libraries to access data service resources as if they were common language runtime (CLR) objects:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="2944f-135">.NET Framework 클라이언트 애플리케이션 만들기</span><span class="sxs-lookup"><span data-stu-id="2944f-135">Creating the .NET Framework Client Application</span></span>](creating-the-dotnet-client-application-wcf-data-services-quickstart.md)

## <a name="see-also"></a><span data-ttu-id="2944f-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2944f-136">See also</span></span>

- [<span data-ttu-id="2944f-137">데이터 서비스 리소스 액세스</span><span class="sxs-lookup"><span data-stu-id="2944f-137">Accessing Data Service Resources</span></span>](accessing-data-service-resources-wcf-data-services.md)
