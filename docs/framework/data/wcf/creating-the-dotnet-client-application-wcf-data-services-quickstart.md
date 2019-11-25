---
title: .NET Framework 클라이언트 애플리케이션 만들기(WCF Data Services 빠른 시작)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 41ade767-eeab-437d-9121-9797e8fb8045
ms.openlocfilehash: 4beaba24e42b15ebc45ece6e5319a2b14df54ab6
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/12/2019
ms.locfileid: "73975388"
---
# <a name="creating-the-net-framework-client-application-wcf-data-services-quickstart"></a><span data-ttu-id="5c034-102">.NET Framework 클라이언트 애플리케이션 만들기(WCF Data Services 빠른 시작)</span><span class="sxs-lookup"><span data-stu-id="5c034-102">Creating the .NET Framework Client Application (WCF Data Services Quickstart)</span></span>

<span data-ttu-id="5c034-103">WCF Data Services 빠른 시작의 최종 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="5c034-103">This is the final task of the WCF Data Services quickstart.</span></span> <span data-ttu-id="5c034-104">이 작업에서는 솔루션에 콘솔 응용 프로그램을 추가 하 고,이 새 클라이언트 응용 프로그램에 Open Data Protocol (OData) 피드에 대 한 참조를 추가 하 고, 생성 된 클라이언트 데이터 서비스 클래스와 클라이언트를 사용 하 여 클라이언트 응용 프로그램에서 OData 피드에 액세스 합니다. 라이브러리인.</span><span class="sxs-lookup"><span data-stu-id="5c034-104">In this task, you will add a console application to the solution, add a reference to the Open Data Protocol (OData) feed into this new client application, and access the OData feed from the client application by using the generated client data service classes and client libraries.</span></span>

> [!NOTE]
> <span data-ttu-id="5c034-105">데이터 피드에 액세스하기 위해 .NET Framework 기반 클라이언트 애플리케이션이 필요하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5c034-105">A .NET Framework-based client application is not required to access a data feed.</span></span> <span data-ttu-id="5c034-106">데이터 서비스는 OData 피드를 사용 하는 모든 응용 프로그램 구성 요소에서 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c034-106">The data service can be accessed by any application component that consumes an OData feed.</span></span> <span data-ttu-id="5c034-107">자세한 내용은 [클라이언트 응용 프로그램에서 데이터 서비스 사용](using-a-data-service-in-a-client-application-wcf-data-services.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5c034-107">For more information, see [Using a Data Service in a Client Application](using-a-data-service-in-a-client-application-wcf-data-services.md).</span></span>

## <a name="to-create-the-client-application-by-using-visual-studio"></a><span data-ttu-id="5c034-108">Visual Studio를 사용하여 클라이언트 애플리케이션을 만들려면</span><span class="sxs-lookup"><span data-stu-id="5c034-108">To create the client application by using Visual Studio</span></span>

1. <span data-ttu-id="5c034-109">**솔루션 탐색기**에서 솔루션을 마우스 오른쪽 단추로 클릭 하 고 **추가**를 클릭 한 다음 **새 프로젝트**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c034-109">In **Solution Explorer**, right-click the solution, click **Add**, and then click **New Project**.</span></span>

2. <span data-ttu-id="5c034-110">왼쪽 창에서 **설치 됨** > [**Visual C#**  or **Visual Basic**] > **Windows 바탕 화면**을 선택 하 고 **WPF 앱** 템플릿을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c034-110">In the left pane, select **Installed** > [**Visual C#** or **Visual Basic**] > **Windows Desktop**, and then select the **WPF App** template.</span></span>

3. <span data-ttu-id="5c034-111">프로젝트 이름에 `NorthwindClient`를 입력 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c034-111">Enter `NorthwindClient` for the project name, and then click **OK**.</span></span>

4. <span data-ttu-id="5c034-112">MainWindow.xaml 파일을 열고 XAML 코드를 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="5c034-112">Open the file MainWindow.xaml and replace the XAML code with the following code:</span></span>

     [!code-xaml[Astoria Quickstart Client#Window1Xaml](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_client/vb/window1.xaml#window1xaml)]

## <a name="to-add-a-data-service-reference-to-the-project"></a><span data-ttu-id="5c034-113">프로젝트에 데이터 서비스 참조를 추가하려면</span><span class="sxs-lookup"><span data-stu-id="5c034-113">To add a data service reference to the project</span></span>

1. <span data-ttu-id="5c034-114">**솔루션 탐색기**에서 NorthwindClient 프로젝트를 마우스 오른쪽 단추로 클릭 하 > **서비스 참조** **추가** 를 클릭 한 다음 **검색**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c034-114">In **Solution Explorer**, right-click the NorthwindClient project, click **Add** > **Service Reference**, and then click **Discover**.</span></span>

     <span data-ttu-id="5c034-115">첫 번째 작업에서 만든 Northwind 데이터 서비스가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="5c034-115">This displays the Northwind data service that you created in the first task.</span></span>

2. <span data-ttu-id="5c034-116">**네임 스페이스** 텍스트 상자에 `Northwind`를 입력 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c034-116">In the **Namespace** text box, type `Northwind`, and then click **OK**.</span></span>

     <span data-ttu-id="5c034-117">데이터 서비스 리소스에 개체로 액세스하고 상호 작용하는 데 사용되는 데이터 클래스가 포함된 새 코드 파일이 프로젝트에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="5c034-117">This adds a new code file to the project, which contains the data classes that are used to access and interact with data service resources as objects.</span></span> <span data-ttu-id="5c034-118">데이터 클래스는 `NorthwindClient.Northwind` 네임스페이스에 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="5c034-118">The data classes are created in the namespace `NorthwindClient.Northwind`.</span></span>

## <a name="to-access-data-service-data-in-the-wpf-application"></a><span data-ttu-id="5c034-119">WPF 애플리케이션에서 데이터 서비스 데이터에 액세스하려면</span><span class="sxs-lookup"><span data-stu-id="5c034-119">To access data service data in the WPF application</span></span>

1. <span data-ttu-id="5c034-120">**NorthwindClient**아래의 **솔루션 탐색기** 에서 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 **참조 추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c034-120">In **Solution Explorer** under **NorthwindClient**, right-click the project and click **Add Reference**.</span></span>

2. <span data-ttu-id="5c034-121">**참조 추가** 대화 상자에서 **.net** 탭을 클릭 하 고, system.web. .dll 어셈블리를 선택한 후 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c034-121">In the **Add Reference** dialog box, click the **.NET** tab, select the System.Data.Services.Client.dll assembly, and then click **OK**.</span></span>

3. <span data-ttu-id="5c034-122">**NorthwindClient**아래의 **솔루션 탐색기** 에서 mainwindow.xaml 파일에 대 한 코드 페이지를 열고 다음 `using` 문 (Visual Basic의`Imports`)을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c034-122">In **Solution Explorer** under **NorthwindClient**, open the code page for the MainWindow.xaml file, and add the following `using` statement (`Imports` in Visual Basic).</span></span>

    [!code-csharp[Astoria Quickstart Client#Using](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_quickstart_client/cs/window1.xaml.cs#using)]
    [!code-vb[Astoria Quickstart Client#Using](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_client/vb/window1.xaml.vb#using)]

4. <span data-ttu-id="5c034-123">해당 데이터 서비스를 쿼리하고 결과를 <xref:System.Data.Services.Client.DataServiceCollection%601>에 바인딩하는 다음 코드를 `MainWindow` 클래스에 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="5c034-123">Insert the following code that queries that data service and binds the result to a <xref:System.Data.Services.Client.DataServiceCollection%601> into the `MainWindow` class:</span></span>

    > [!NOTE]
    > <span data-ttu-id="5c034-124">Northwind 데이터 서비스 인스턴스를 호스트하는 서버 및 포트로 호스트 이름 `localhost:12345`를 바꾸어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c034-124">You must replace the host name `localhost:12345` with the server and port that is hosting your instance of the Northwind data service.</span></span>

     [!code-csharp[Astoria Quickstart Client#QueryCode](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_quickstart_client/cs/window1.xaml.cs#querycode)]
     [!code-vb[Astoria Quickstart Client#QueryCode](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_client/vb/window1.xaml.vb#querycode)]

5. <span data-ttu-id="5c034-125">변경 내용을 저장하는 다음 코드를 `MainWindow` 클래스에 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="5c034-125">Insert the following code that saves changes into the `MainWindow` class:</span></span>

     [!code-csharp[Astoria Quickstart Client#SaveChanges](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_quickstart_client/cs/window1.xaml.cs#savechanges)]
     [!code-vb[Astoria Quickstart Client#SaveChanges](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_client/vb/window1.xaml.vb#savechanges)]

## <a name="to-build-and-run-the-northwindclient-application"></a><span data-ttu-id="5c034-126">NorthwindClient 애플리케이션을 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="5c034-126">To build and run the NorthwindClient application</span></span>

1. <span data-ttu-id="5c034-127">**솔루션 탐색기**에서 NorthwindClient 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 **시작 프로젝트로 설정**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c034-127">In **Solution Explorer**, right-click the NorthwindClient project and select **Set as startup project**.</span></span>

2. <span data-ttu-id="5c034-128">**F5** 키를 눌러 응용 프로그램을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c034-128">Press **F5** to start the application.</span></span>

     <span data-ttu-id="5c034-129">솔루션이 빌드되고 클라이언트 애플리케이션이 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="5c034-129">This builds the solution and starts the client application.</span></span> <span data-ttu-id="5c034-130">서비스에서 데이터가 요청되고 콘솔에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="5c034-130">Data is requested from the service and displayed in the console.</span></span>

3. <span data-ttu-id="5c034-131">데이터 표의 **수량** 열에서 값을 편집 하 고 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c034-131">Edit a value in the **Quantity** column of the data grid, and then click **Save**.</span></span>

     <span data-ttu-id="5c034-132">변경 내용이 데이터 서비스에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="5c034-132">Changes are saved to the data service.</span></span>

    > [!NOTE]
    > <span data-ttu-id="5c034-133">이 버전의 NorthwindClient 애플리케이션은 엔터티의 추가와 삭제를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5c034-133">This version of the NorthwindClient application does not support adding and deleting of entities.</span></span>

## <a name="next-steps"></a><span data-ttu-id="5c034-134">다음 단계</span><span class="sxs-lookup"><span data-stu-id="5c034-134">Next Steps</span></span>

<span data-ttu-id="5c034-135">Sample Northwind OData 피드에 액세스 하는 클라이언트 응용 프로그램을 성공적으로 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="5c034-135">You have successfully created the client application that accesses the sample Northwind OData feed.</span></span> <span data-ttu-id="5c034-136">WCF Data Services 퀵 스타트도 완료 했습니다.</span><span class="sxs-lookup"><span data-stu-id="5c034-136">You've also completed the WCF Data Services quickstart!</span></span>

<span data-ttu-id="5c034-137">.NET Framework 응용 프로그램에서 OData 피드에 액세스 하는 방법에 대 한 자세한 내용은 [WCF Data Services 클라이언트 라이브러리](wcf-data-services-client-library.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5c034-137">For more information about accessing an OData feed from a .NET Framework application, see [WCF Data Services Client Library](wcf-data-services-client-library.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="5c034-138">참조</span><span class="sxs-lookup"><span data-stu-id="5c034-138">See also</span></span>

- [<span data-ttu-id="5c034-139">시작</span><span class="sxs-lookup"><span data-stu-id="5c034-139">Getting Started</span></span>](getting-started-with-wcf-data-services.md)
- [<span data-ttu-id="5c034-140">리소스</span><span class="sxs-lookup"><span data-stu-id="5c034-140">Resources</span></span>](wcf-data-services-resources.md)
