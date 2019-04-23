---
title: 웹 브라우저에서 서비스 액세스(WCF Data Services 빠른 시작)
ms.date: 03/30/2017
ms.assetid: 5a6fa180-3094-4e6e-ba2b-8c80975d18d1
ms.openlocfilehash: ebeda2805f3393b298e43aa4dcc601298ce176f6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59330326"
---
# <a name="accessing-the-service-from-a-web-browser-wcf-data-services-quickstart"></a><span data-ttu-id="b04a8-102">웹 브라우저에서 서비스 액세스(WCF Data Services 빠른 시작)</span><span class="sxs-lookup"><span data-stu-id="b04a8-102">Accessing the Service from a Web Browser (WCF Data Services Quickstart)</span></span>

<span data-ttu-id="b04a8-103">WCF Data Services 빠른 시작의 두 번째 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="b04a8-103">This is the second task of the WCF Data Services quickstart.</span></span> <span data-ttu-id="b04a8-104">이 작업에서는 Visual Studio에서 WCF Data Services를 시작 하 고 필요에 따라 웹 브라우저에서 피드 읽기를 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b04a8-104">In this task, you start the WCF Data Services from Visual Studio and optionally disable feed reading in the Web browser.</span></span> <span data-ttu-id="b04a8-105">그런 다음 서비스 정의 문서를 검색 뿐만 있습니다 노출 된 리소스로 웹 브라우저를 통해 HTTP GET 요청을 제출 하 여 데이터 서비스 리소스에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="b04a8-105">You then retrieve the service definition document as well as access data service resources by submitting HTTP GET requests through a Web browser to the exposed resources.</span></span>

> [!NOTE]
> <span data-ttu-id="b04a8-106">기본적으로 Visual Studio에서는 사용자 컴퓨터에서 `localhost` URI에 포트 번호를 자동으로 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="b04a8-106">By default, Visual Studio auto-assigns a port number to the `localhost` URI on your computer.</span></span> <span data-ttu-id="b04a8-107">이 작업에서는 URI 예제에서 포트 번호 `12345`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b04a8-107">This task uses the port number `12345` in the URI examples.</span></span> <span data-ttu-id="b04a8-108">Visual Studio 프로젝트에서 특정 포트 번호를 설정 하는 방법에 대 한 자세한 내용은 참조 하세요. [데이터 서비스 만들기](../../../../docs/framework/data/wcf/creating-the-data-service.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b04a8-108">For more information about how to set a specific port number in your Visual Studio project see [Creating the Data Service](../../../../docs/framework/data/wcf/creating-the-data-service.md).</span></span>

## <a name="to-request-the-default-service-document-by-using-internet-explorer"></a><span data-ttu-id="b04a8-109">Internet Explorer를 사용하여 기본 서비스 문서를 요청하려면</span><span class="sxs-lookup"><span data-stu-id="b04a8-109">To request the default service document by using Internet Explorer</span></span>

1. <span data-ttu-id="b04a8-110">Internet Explorer에서에서 **도구** 메뉴를 선택 **인터넷 옵션**를 클릭 합니다 **콘텐츠** 탭을 클릭 **설정**, 선택을취소하고 **피드 보기를 켜려면**합니다.</span><span class="sxs-lookup"><span data-stu-id="b04a8-110">In Internet Explorer, from the **Tools** menu, select **Internet Options**, click the **Content** tab, click **Settings**, and clear **Turn on feed viewing**.</span></span>

     <span data-ttu-id="b04a8-111">이렇게 하면 피드 읽기가 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b04a8-111">This makes sure that feed reading is disabled.</span></span> <span data-ttu-id="b04a8-112">이 기능을 사용하지 않도록 설정하지 않으면 웹 브라우저에서 원시 XML 데이터를 표시하지 않고 반환된 AtomPub 인코딩 문서를 XML 피드로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="b04a8-112">If you do not disable this functionality, then the Web browser will treat the returned AtomPub encoded document as an XML feed instead of displaying the raw XML data.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b04a8-113">브라우저에서 피드를 원시 XML 데이터로 표시할 수 없는 경우 피드를 페이지의 소스 코드로 볼 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b04a8-113">If your browser cannot display the feed as raw XML data, you should still be able to view the feed as the source code for the page.</span></span>

2. <span data-ttu-id="b04a8-114">키를 눌러 Visual Studio에서의 **F5** 응용 프로그램 디버깅을 시작 하는 키입니다.</span><span class="sxs-lookup"><span data-stu-id="b04a8-114">In Visual Studio, press the **F5** key to start debugging the application.</span></span>

3. <span data-ttu-id="b04a8-115">로컬 컴퓨터에서 웹 브라우저를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="b04a8-115">Open a Web browser on the local computer.</span></span> <span data-ttu-id="b04a8-116">주소 표시줄에 다음 URI를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="b04a8-116">In the address bar, enter the following URI:</span></span>

    ```
    http://localhost:12345/northwind.svc
    ```

     <span data-ttu-id="b04a8-117">이 데이터 서비스에서 노출하는 엔터티 집합 목록을 포함하는 기본 서비스 문서가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="b04a8-117">This returns the default service document, which contains a list of entity sets that are exposed by this data service.</span></span>

## <a name="to-access-entity-set-resources-from-a-web-browser"></a><span data-ttu-id="b04a8-118">웹 브라우저에서 엔터티 집합 리소스에 액세스하려면</span><span class="sxs-lookup"><span data-stu-id="b04a8-118">To access entity set resources from a Web browser</span></span>

1. <span data-ttu-id="b04a8-119">웹 브라우저의 주소 표시줄에 다음 URI를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="b04a8-119">In the address bar of your Web browser, enter the following URI:</span></span>

    ```
    http://localhost:12345/northwind.svc/Customers
    ```

     <span data-ttu-id="b04a8-120">Northwind 샘플 데이터베이스의 모든 고객 집합이 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="b04a8-120">This returns a set of all customers in the Northwind sample database.</span></span>

2. <span data-ttu-id="b04a8-121">웹 브라우저의 주소 표시줄에 다음 URI를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="b04a8-121">In the address bar of your Web browser, enter the following URI:</span></span>

    ```
    http://localhost:12345/northwind.svc/Customers('ALFKI')
    ```

     <span data-ttu-id="b04a8-122">특정 고객 `ALFKI`의 엔터티 인스턴스가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="b04a8-122">This returns an entity instance for the specific customer, `ALFKI`.</span></span>

3. <span data-ttu-id="b04a8-123">웹 브라우저의 주소 표시줄에 다음 URI를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="b04a8-123">In the address bar of your Web browser, enter the following URI:</span></span>

    ```
    http://localhost:12345/northwind.svc/Customers('ALFKI')/Orders
    ```

     <span data-ttu-id="b04a8-124">고객과 주문 간의 관계가 이동되어 특정 고객 `ALFKI`에 대한 모든 주문 집합이 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="b04a8-124">This traverses the relationship between customers and orders to return a set of all orders for the specific customer `ALFKI`.</span></span>

4. <span data-ttu-id="b04a8-125">웹 브라우저의 주소 표시줄에 다음 URI를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="b04a8-125">In the address bar of your Web browser, enter the following URI:</span></span>

    ```
    http://localhost:12345/northwind.svc/Customers('ALFKI')/Orders?$filter=OrderID eq 10643
    ```

     <span data-ttu-id="b04a8-126">제공한 `ALFKI` 값을 기반으로 특정 주문만 반환되도록 특정 고객 `OrderID`에 속하는 주문이 필터링됩니다.</span><span class="sxs-lookup"><span data-stu-id="b04a8-126">This filters orders that belong to the specific customer `ALFKI` so that only a specific order is returned based on the supplied `OrderID` value.</span></span>

## <a name="next-steps"></a><span data-ttu-id="b04a8-127">다음 단계</span><span class="sxs-lookup"><span data-stu-id="b04a8-127">Next Steps</span></span>

<span data-ttu-id="b04a8-128">WCF Data Services는 브라우저가 HTTP GET 요청을 보냅니다 지정 된 리소스를 사용 하 여 웹 브라우저에서 성공적으로 액세스 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="b04a8-128">You have successfully accessed the WCF Data Services from a Web browser, with the browser issuing HTTP GET requests to specified resources.</span></span> <span data-ttu-id="b04a8-129">웹 브라우저를 사용하면 간편하게 요청의 주소 지정 구문을 실행해 보고 그 결과를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b04a8-129">A Web browser provides an easy way to experiment with the addressing syntax of requests and view the results.</span></span> <span data-ttu-id="b04a8-130">그러나 프로덕션 데이터 서비스는 대개 이 방법으로 액세스되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b04a8-130">However, a production data service is not generally accessed by this method.</span></span> <span data-ttu-id="b04a8-131">응용 프로그램은 일반적으로 응용 프로그램 코드나 스크립트 언어를 통해 데이터 서비스와 상호 작용합니다.</span><span class="sxs-lookup"><span data-stu-id="b04a8-131">Typically, applications interact with the data service through application code or scripting languages.</span></span> <span data-ttu-id="b04a8-132">다음에는 클라이언트 라이브러리를 사용하여 CLR(공용 언어 런타임) 개체인 것처럼 데이터 서비스 리소스에 액세스하는 클라이언트 응용 프로그램을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b04a8-132">Next, you will create a client application that uses client libraries to access data service resources as if they were common language runtime (CLR) objects:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="b04a8-133">.NET Framework 클라이언트 애플리케이션 만들기</span><span class="sxs-lookup"><span data-stu-id="b04a8-133">Creating the .NET Framework Client Application</span></span>](../../../../docs/framework/data/wcf/creating-the-dotnet-client-application-wcf-data-services-quickstart.md)

## <a name="see-also"></a><span data-ttu-id="b04a8-134">참고자료</span><span class="sxs-lookup"><span data-stu-id="b04a8-134">See also</span></span>

- [<span data-ttu-id="b04a8-135">데이터 서비스 리소스에 액세스</span><span class="sxs-lookup"><span data-stu-id="b04a8-135">Accessing Data Service Resources</span></span>](../../../../docs/framework/data/wcf/accessing-data-service-resources-wcf-data-services.md)
