---
title: Visual Studio에서 WCF 데이터 서비스 만들기
description: WCF Data Services를 사용 하 여 샘플 데이터베이스를 기반으로 하는 OData 피드를 노출 하는 샘플 데이터 서비스를 만드는 방법에 대해 알아봅니다.
ms.date: 08/24/2018
dev_langs:
- csharp
- vb
ms.assetid: 34d1d971-5e18-4c22-9bf6-d3612e27ea59
ms.openlocfilehash: f6e95ce58e055f0c745b781c664309e4ef91ffc6
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90554015"
---
# <a name="create-the-data-service"></a><span data-ttu-id="dab64-103">데이터 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="dab64-103">Create the data service</span></span>

<span data-ttu-id="dab64-104">이 항목에서는 WCF Data Services를 사용 하 여 Northwind 샘플 데이터베이스를 기반으로 하는 OData (Open Data Protocol) 피드를 노출 하는 샘플 데이터 서비스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="dab64-104">In this topic, you create a sample data service that uses WCF Data Services to expose an Open Data Protocol (OData) feed that's based on the Northwind sample database.</span></span> <span data-ttu-id="dab64-105">작업에 필요한 기본 단계는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="dab64-105">The task involves the following basic steps:</span></span>

1. <span data-ttu-id="dab64-106">ASP.NET 웹 애플리케이션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="dab64-106">Create an ASP.NET Web application.</span></span>

2. <span data-ttu-id="dab64-107">엔터티 데이터 모델 도구를 사용하여 데이터 모델을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="dab64-107">Define the data model by using the Entity Data Model tools.</span></span>

3. <span data-ttu-id="dab64-108">웹 애플리케이션에 데이터 서비스를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="dab64-108">Add the data service to the Web application.</span></span>

4. <span data-ttu-id="dab64-109">데이터 서비스에 액세스할 수 있도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="dab64-109">Enable access to the data service.</span></span>

## <a name="create-the-aspnet-web-app"></a><span data-ttu-id="dab64-110">ASP.NET 웹 앱 만들기</span><span class="sxs-lookup"><span data-stu-id="dab64-110">Create the ASP.NET web app</span></span>

1. <span data-ttu-id="dab64-111">Visual Studio의 **파일** 메뉴에서 **새로 만들기** > **프로젝트**를 차례로 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="dab64-111">In Visual Studio, on the **File** menu, select **New** > **Project**.</span></span>

1. <span data-ttu-id="dab64-112">**새 프로젝트** 대화 상자의 Visual Basic 또는 Visual c #에서 **웹** 범주를 선택한 다음 **ASP.NET 웹 응용 프로그램**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="dab64-112">In the **New Project** dialog box, under either Visual Basic or Visual C# select the **Web** category, and then select **ASP.NET Web Application**.</span></span>

1. <span data-ttu-id="dab64-113">`NorthwindService`프로젝트의 이름으로를 입력 한 다음 **확인을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="dab64-113">Enter `NorthwindService` as the name of the project and then select **OK**.</span></span>

1. <span data-ttu-id="dab64-114">**새 ASP.NET 웹 응용 프로그램** 대화 상자에서 **비어 있음** 을 선택 하 고 **확인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="dab64-114">In the **New ASP.NET Web Application** dialog, select **Empty** and then select **OK**.</span></span>

1. <span data-ttu-id="dab64-115">(선택 사항) 웹 애플리케이션의 특정 포트 번호를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="dab64-115">(Optional) Specify a specific port number for your Web application.</span></span> <span data-ttu-id="dab64-116">참고: 포트 번호는 `12345` 이 일련의 빠른 시작 항목에서 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dab64-116">Note: the port number `12345` is used in this series of quickstart topics.</span></span>

    1. <span data-ttu-id="dab64-117">**솔루션 탐색기**에서 방금 만든 ASP.NET 프로젝트를 마우스 오른쪽 단추로 클릭 한 다음 **속성**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="dab64-117">In **Solution Explorer**, right-click on the ASP.NET project that you just created, and then choose **Properties**.</span></span>

    2. <span data-ttu-id="dab64-118">**웹** 탭을 선택 하 고 **특정 포트** 텍스트 상자의 값을로 설정 `12345` 합니다.</span><span class="sxs-lookup"><span data-stu-id="dab64-118">Select the **Web** tab, and set the value of the **Specific port** text box to `12345`.</span></span>

## <a name="define-the-data-model"></a><span data-ttu-id="dab64-119">데이터 모델 정의</span><span class="sxs-lookup"><span data-stu-id="dab64-119">Define the data model</span></span>

1. <span data-ttu-id="dab64-120">**솔루션 탐색기**에서 ASP.NET 프로젝트의 이름을 마우스 오른쪽 단추로 클릭 한 다음 **Add**  >  **새 항목**추가를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="dab64-120">In **Solution Explorer**, right-click the name of the ASP.NET project, and then click **Add** > **New Item**.</span></span>

2. <span data-ttu-id="dab64-121">**새 항목 추가** 대화 상자에서 **데이터** 범주를 선택 하 고 **ADO.NET 엔터티 데이터 모델**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="dab64-121">In the **Add New Item** dialog box, select the **Data** category, and then select **ADO.NET Entity Data Model**.</span></span>

3. <span data-ttu-id="dab64-122">데이터 모델의 이름에을 입력 `Northwind.edmx` 합니다.</span><span class="sxs-lookup"><span data-stu-id="dab64-122">For the name of the data model, enter `Northwind.edmx`.</span></span>

4. <span data-ttu-id="dab64-123">**엔터티 데이터 모델 마법사**에서 **데이터베이스에서 EF Designer**를 선택 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="dab64-123">In the **Entity Data Model Wizard**, select **EF Designer from Database**, and then click **Next**.</span></span>

5. <span data-ttu-id="dab64-124">다음 단계 중 하나를 수행 하 여 데이터 모델을 데이터베이스에 연결한 **후 다음을 클릭 합니다**.</span><span class="sxs-lookup"><span data-stu-id="dab64-124">Connect the data model to the database by doing one of the following steps, and then click **Next**:</span></span>

    - <span data-ttu-id="dab64-125">데이터베이스 연결이 이미 구성 되어 있지 않은 경우 **새 연결** 을 클릭 하 고 새 연결을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="dab64-125">If you don't have a database connection already configured, click **New Connection** and create a new connection.</span></span> <span data-ttu-id="dab64-126">자세한 내용은 [How to: Create Connections to SQL Server Databases](/previous-versions/visualstudio/visual-studio-2008/s4yys16a(v=vs.90))을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="dab64-126">For more information, see [How to: Create Connections to SQL Server Databases](/previous-versions/visualstudio/visual-studio-2008/s4yys16a(v=vs.90)).</span></span> <span data-ttu-id="dab64-127">이 SQL Server 인스턴스에는 Northwind 샘플 데이터베이스가 연결되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dab64-127">This SQL Server instance must have the Northwind sample database attached.</span></span>

         <span data-ttu-id="dab64-128">\- 또는 -</span><span class="sxs-lookup"><span data-stu-id="dab64-128">\- or -</span></span>

    - <span data-ttu-id="dab64-129">Northwind 데이터베이스에 연결할 수 있도록 데이터베이스 연결이 이미 구성되어 있는 경우 연결 목록에서 해당 연결을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="dab64-129">If you have a database connection already configured to connect to the Northwind database, select that connection from the list of connections.</span></span>

6. <span data-ttu-id="dab64-130">마법사의 마지막 페이지에서 데이터베이스의 모든 테이블에 대한 확인란을 선택하고 뷰 및 저장 프로시저에 대한 확인란의 선택을 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="dab64-130">On the final page of the wizard, select the check boxes for all tables in the database, and clear the check boxes for views and stored procedures.</span></span>

7. <span data-ttu-id="dab64-131">**마침** 을 클릭 하 여 마법사를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="dab64-131">Click **Finish** to close the wizard.</span></span>

## <a name="create-the-wcf-data-service"></a><span data-ttu-id="dab64-132">WCF 데이터 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="dab64-132">Create the WCF data service</span></span>

1. <span data-ttu-id="dab64-133">**솔루션 탐색기**에서 ASP.NET 프로젝트를 마우스 오른쪽 단추로 클릭 한 다음 **Add**  >  **새 항목**추가를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="dab64-133">In **Solution Explorer**, right-click on the ASP.NET project, and then choose **Add** > **New Item**.</span></span>

2. <span data-ttu-id="dab64-134">**새 항목 추가** 대화 상자의 **웹** 범주에서 **WCF 데이터 서비스** 항목 템플릿을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="dab64-134">In the **Add New Item** dialog box, select the **WCF Data Service** item template from the **Web** category.</span></span>

   ![Visual Studio 2015의 WCF 데이터 서비스 항목 템플릿](./media/wcf-data-service-item-template.png)

   > [!NOTE]
   > <span data-ttu-id="dab64-136">**WCF 데이터 서비스** 템플릿은 visual studio 2015 이상에서 사용할 수 있지만 visual studio 2017 이상에서는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dab64-136">The **WCF Data Service** template is available in Visual Studio 2015, but not in Visual Studio 2017 or later.</span></span>

3. <span data-ttu-id="dab64-137">서비스의 이름에을 입력 `Northwind` 합니다.</span><span class="sxs-lookup"><span data-stu-id="dab64-137">For the name of the service, type `Northwind`.</span></span>

     <span data-ttu-id="dab64-138">Visual Studio에서 새 서비스의 XML 태그 및 코드 파일이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="dab64-138">Visual Studio creates the XML markup and code files for the new service.</span></span> <span data-ttu-id="dab64-139">기본적으로 코드 편집기 창이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="dab64-139">By default, the code-editor window opens.</span></span> <span data-ttu-id="dab64-140">**솔루션 탐색기**서비스에는 이름이 *svc.cs* 또는. n a n *.vb*인 Northwind 이름이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dab64-140">In **Solution Explorer**, the service has the name Northwind with the extension *.svc.cs* or *.svc.vb*.</span></span>

4. <span data-ttu-id="dab64-141">데이터 서비스 코드에서 데이터 서비스를 정의하는 클래스 정의의 `/* TODO: put your data source class name here */` 주석을 데이터 모델의 엔터티 컨테이너인 형식(이 경우 `NorthwindEntities`)으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="dab64-141">In the code for the data service, replace the comment `/* TODO: put your data source class name here */` in the definition of the class that defines the data service with the type that is the entity container of the data model, which in this case is `NorthwindEntities`.</span></span> <span data-ttu-id="dab64-142">클래스 정의는 다음과 같이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="dab64-142">The class definition should look this the following:</span></span>

     [!code-csharp[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_quickstart_service/cs/northwind.svc.cs#servicedefinition)]
     [!code-vb[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_service/vb/northwind.svc.vb#servicedefinition)]

## <a name="enable-access-to-data-service-resources"></a><span data-ttu-id="dab64-143">데이터 서비스 리소스에 대 한 액세스 사용</span><span class="sxs-lookup"><span data-stu-id="dab64-143">Enable access to data service resources</span></span>

1. <span data-ttu-id="dab64-144">데이터 서비스 코드에서 `InitializeService` 함수의 자리 표시자 코드를 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="dab64-144">In the code for the data service, replace the placeholder code in the `InitializeService` function with the following:</span></span>

     [!code-csharp[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_quickstart_service/cs/northwind.svc.cs#allreadconfig)]
     [!code-vb[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_service/vb/northwind.svc.vb#allreadconfig)]

     <span data-ttu-id="dab64-145">이렇게 하면 권한 있는 클라이언트가 지정된 엔터티 집합의 리소스에 대한 읽기 및 쓰기 액세스 권한을 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dab64-145">This enables authorized clients to have read and write access to resources for the specified entity sets.</span></span>

    > [!NOTE]
    > <span data-ttu-id="dab64-146">ASP.NET 애플리케이션에 액세스할 수 있는 클라이언트는 데이터 서비스에 의해 노출되는 리소스에도 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dab64-146">Any client that can access the ASP.NET application can also access the resources exposed by the data service.</span></span> <span data-ttu-id="dab64-147">리소스에 무단으로 액세스할 수 없도록 하려면 프로덕션 데이터 서비스에서 애플리케이션 자체에도 보안을 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dab64-147">In a production data service, to prevent unauthorized access to resources you should also secure the application itself.</span></span> <span data-ttu-id="dab64-148">자세한 내용은 [Securing WCF Data Services](securing-wcf-data-services.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dab64-148">For more information, see [Securing WCF Data Services](securing-wcf-data-services.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="dab64-149">다음 단계</span><span class="sxs-lookup"><span data-stu-id="dab64-149">Next steps</span></span>

<span data-ttu-id="dab64-150">Northwind 샘플 데이터베이스를 기반으로 하는 OData 피드를 노출 하는 새 데이터 서비스를 성공적으로 만들었으며 ASP.NET 웹 응용 프로그램에 대 한 사용 권한이 있는 클라이언트의 피드에 대 한 액세스를 사용 하도록 설정 했습니다.</span><span class="sxs-lookup"><span data-stu-id="dab64-150">You have successfully created a new data service that exposes an OData feed that is based on the Northwind sample database, and you have enabled access to the feed for clients that have permissions on the ASP.NET Web application.</span></span> <span data-ttu-id="dab64-151">다음으로, Visual Studio에서 데이터 서비스를 시작 하 고 웹 브라우저를 통해 HTTP GET 요청을 제출 하 여 OData 피드에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="dab64-151">Next, you'll start the data service from Visual Studio and access the OData feed by submitting HTTP GET requests through a Web browser:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="dab64-152">웹 브라우저에서 서비스 액세스</span><span class="sxs-lookup"><span data-stu-id="dab64-152">Access the service from a web browser</span></span>](accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md)

## <a name="see-also"></a><span data-ttu-id="dab64-153">참조</span><span class="sxs-lookup"><span data-stu-id="dab64-153">See also</span></span>

- <span data-ttu-id="dab64-154">[ADO.NET 엔터티 데이터 모델 도구](/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="dab64-154">[ADO.NET Entity Data Model Tools](/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span></span>
