---
description: '자세한 정보: 방법: LINQ to SQL 데이터 소스를 사용 하 여 데이터 서비스 만들기 (WCF Data Services)'
title: '방법: LINQ to SQL 데이터 원본을 사용하여 데이터 서비스 만들기(WCF Data Services)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, LINQ to SQL
- WCF Data Services, providers
ms.assetid: 3b01c2fd-8c6e-4bf5-b38f-9e61bdc3c328
ms.openlocfilehash: 18c59cc8a067372f2a5c5b4b25d9aec77515ad98
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99766246"
---
# <a name="how-to-create-a-data-service-using-a-linq-to-sql-data-source-wcf-data-services"></a><span data-ttu-id="ce92d-103">방법: LINQ to SQL 데이터 원본을 사용하여 데이터 서비스 만들기(WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="ce92d-103">How to: Create a Data Service Using a LINQ to SQL Data Source (WCF Data Services)</span></span>

[!INCLUDE [wcf-deprecated](~/includes/wcf-deprecated.md)]

<span data-ttu-id="ce92d-104">WCF Data Services 엔터티 데이터를 데이터 서비스로 노출 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce92d-104">WCF Data Services exposes entity data as a data service.</span></span> <span data-ttu-id="ce92d-105">리플렉션 공급자를 사용 하면 구현을 반환 하는 멤버를 노출 하는 클래스를 기반으로 하는 데이터 모델을 정의할 수 있습니다 <xref:System.Linq.IQueryable%601> .</span><span class="sxs-lookup"><span data-stu-id="ce92d-105">The reflection provider enables you to define a data model that is based on any class that exposes members that return an <xref:System.Linq.IQueryable%601> implementation.</span></span> <span data-ttu-id="ce92d-106">데이터 소스의 데이터를 업데이트할 수 있으려면 이러한 클래스도 <xref:System.Data.Services.IUpdatable> 인터페이스를 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce92d-106">To be able to make updates to data in the data source, these classes must also implement the <xref:System.Data.Services.IUpdatable> interface.</span></span> <span data-ttu-id="ce92d-107">자세한 내용은 [데이터 서비스 공급자](data-services-providers-wcf-data-services.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ce92d-107">For more information, see [Data Services Providers](data-services-providers-wcf-data-services.md).</span></span> <span data-ttu-id="ce92d-108">이 항목에서는 리플렉션 공급자를 사용하여 Northwind 샘플 데이터베이스에 액세스하는 LINQ to SQL 클래스를 만드는 방법과 이러한 데이터 클래스를 기반으로 하는 데이터 서비스를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ce92d-108">This topic shows you how to create LINQ to SQL classes that access the Northwind sample database by using the reflection provider, as well as how to create the data service that is based on these data classes.</span></span>

## <a name="to-add-linq-to-sql-classes-to-a-project"></a><span data-ttu-id="ce92d-109">프로젝트에 LINQ to SQL 클래스를 추가하려면</span><span class="sxs-lookup"><span data-stu-id="ce92d-109">To add LINQ to SQL classes to a project</span></span>

1. <span data-ttu-id="ce92d-110">Visual Basic 또는 c # 응용 프로그램에서 **프로젝트** 메뉴의   >  **새 항목** 추가를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce92d-110">From within a Visual Basic or C# application, on the **Project** menu, click **Add** > **New Item**.</span></span>

2. <span data-ttu-id="ce92d-111">**LINQ to SQL 클래스** 템플릿을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce92d-111">Click the **LINQ to SQL Classes** template.</span></span>

3. <span data-ttu-id="ce92d-112">이름을 **Northwind .dbml** 로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce92d-112">Change the name to **Northwind.dbml**.</span></span>

4. <span data-ttu-id="ce92d-113">**추가** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ce92d-113">Click **Add**.</span></span>

     <span data-ttu-id="ce92d-114">Northwind.dbml 파일이 프로젝트에 추가되고 Object Relational Designer(O/R Designer)가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="ce92d-114">The Northwind.dbml file is added to the project and the Object Relational Designer (O/R Designer) opens.</span></span>

5. <span data-ttu-id="ce92d-115">**서버** / **데이터베이스 탐색기** Northwind 아래에서 **테이블** 을 확장 하 고 테이블을 `Customers` 개체 관계형 디자이너 (O/R 디자이너)로 끕니다.</span><span class="sxs-lookup"><span data-stu-id="ce92d-115">In **Server**/**Database Explorer**, under Northwind, expand **Tables** and drag the `Customers` table onto the Object Relational Designer (O/R Designer).</span></span>

     <span data-ttu-id="ce92d-116">`Customer` 엔터티 클래스가 만들어져 디자인 화면에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce92d-116">A `Customer` entity class is created and appears on the design surface.</span></span>

6. <span data-ttu-id="ce92d-117">`Orders`, `Order_Details` 및 `Products` 테이블에 대해 6단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="ce92d-117">Repeat step 6 for the `Orders`, `Order_Details`, and `Products` tables.</span></span>

7. <span data-ttu-id="ce92d-118">LINQ to SQL 클래스를 나타내는 새 .dbml 파일을 마우스 오른쪽 단추로 클릭 하 고 **코드 보기** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce92d-118">Right-click the new .dbml file that represents the LINQ to SQL classes and click **View Code**.</span></span>

     <span data-ttu-id="ce92d-119">이렇게 하면 <xref:System.Data.Linq.DataContext> 클래스에서 상속되는 클래스(이 경우 `NorthwindDataContext`)의 partial 클래스 정의가 포함된 Northwind.cs라는 새 코드 숨김 페이지가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="ce92d-119">This creates a new code-behind page named Northwind.cs that contains a partial class definition for the class that inherits from the <xref:System.Data.Linq.DataContext> class, which in this case is `NorthwindDataContext`.</span></span>

8. <span data-ttu-id="ce92d-120">Northwind.cs 코드 파일의 내용을 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="ce92d-120">Replace the contents of the Northwind.cs code file with the following code.</span></span> <span data-ttu-id="ce92d-121">이 코드는 LINQ to SQL에서 생성된 <xref:System.Data.Linq.DataContext> 및 데이터 클래스를 확장하여 리플렉션 공급자를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="ce92d-121">This code implements the reflection provider by extending the <xref:System.Data.Linq.DataContext> and data classes generated by LINQ to SQL:</span></span>

     [!code-csharp[Astoria Linq Provider#Linq2SqlProvider](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_linq_provider/cs/northwind.cs#linq2sqlprovider)]
     [!code-vb[Astoria Linq Provider#Linq2SqlProvider](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_linq_provider/vb/northwind.vb#linq2sqlprovider)]

### <a name="to-create-a-data-service-by-using-a-linq-to-sql-based-data-model"></a><span data-ttu-id="ce92d-122">LINQ to SQL 기반 데이터 모델을 사용하여 데이터 서비스를 만들려면</span><span class="sxs-lookup"><span data-stu-id="ce92d-122">To create a data service by using a LINQ to SQL-based data model</span></span>

1. <span data-ttu-id="ce92d-123">**솔루션 탐색기** 에서 ASP.NET 프로젝트의 이름을 마우스 오른쪽 단추로 클릭 한 다음   >  **새 항목** 추가를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce92d-123">In **Solution Explorer**, right-click the name of your ASP.NET project, and then click **Add** > **New Item**.</span></span>

2. <span data-ttu-id="ce92d-124">**새 항목 추가** 대화 상자의 **웹** 범주에서 **WCF 데이터 서비스** 템플릿을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce92d-124">In the **Add New Item** dialog box, select the **WCF Data Service** template from the **Web** category.</span></span>

   ![Visual Studio 2015의 WCF 데이터 서비스 항목 템플릿](./media/wcf-data-service-item-template.png)

   > [!NOTE]
   > <span data-ttu-id="ce92d-126">**WCF 데이터 서비스** 템플릿은 visual studio 2015 이상에서 사용할 수 있지만 visual studio 2017 이상에서는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ce92d-126">The **WCF Data Service** template is available in Visual Studio 2015, but not in Visual Studio 2017 or later.</span></span>

3. <span data-ttu-id="ce92d-127">서비스의 이름을 입력 하 고 **확인** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce92d-127">Supply a name for the service, and then click **OK**.</span></span>

     <span data-ttu-id="ce92d-128">Visual Studio에서 새 서비스의 XML 태그 및 코드 파일이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce92d-128">Visual Studio creates the XML markup and code files for the new service.</span></span> <span data-ttu-id="ce92d-129">기본적으로 코드 편집기 창이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="ce92d-129">By default, the code-editor window opens.</span></span>

4. <span data-ttu-id="ce92d-130">데이터 서비스 코드에서 데이터 서비스를 정의하는 클래스 정의의 `/* TODO: put your data source class name here */` 주석을 데이터 모델의 엔터티 컨테이너인 형식(이 경우 `NorthwindDataContext`)으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="ce92d-130">In the code for the data service, replace the comment `/* TODO: put your data source class name here */` in the definition of the class that defines the data service with the type that is the entity container of the data model, which in this case is `NorthwindDataContext`.</span></span>

5. <span data-ttu-id="ce92d-131">데이터 서비스 코드에서 `InitializeService` 함수의 자리 표시자 코드를 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="ce92d-131">In the code for the data service, replace the placeholder code in the `InitializeService` function with the following:</span></span>

     [!code-csharp[Astoria Linq Provider#EnableAccess](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_linq_provider/cs/northwind.svc.cs#enableaccess)]
     [!code-vb[Astoria Linq Provider#EnableAccess](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_linq_provider/vb/northwind.svc.vb#enableaccess)]

     <span data-ttu-id="ce92d-132">이렇게 하면 권한 있는 클라이언트가 지정된 세 개 엔터티 집합의 리소스에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce92d-132">This enables authorized clients to access resources for the three specified entity sets.</span></span>

6. <span data-ttu-id="ce92d-133">웹 브라우저를 사용 하 여 Northwind 데이터 서비스를 테스트 하려면 [웹 브라우저에서 서비스 액세스](accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md)항목의 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="ce92d-133">To test the Northwind.svc data service by using a Web browser, follow the instructions in the topic [Accessing the Service from a Web Browser](accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="ce92d-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ce92d-134">See also</span></span>

- [<span data-ttu-id="ce92d-135">방법: ADO.NET Entity Framework 데이터 원본을 사용하여 데이터 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="ce92d-135">How to: Create a Data Service Using an ADO.NET Entity Framework Data Source</span></span>](create-a-data-service-using-an-adonet-ef-data-wcf.md)
- [<span data-ttu-id="ce92d-136">방법: 리플렉션 공급자를 사용하여 데이터 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="ce92d-136">How to: Create a Data Service Using the Reflection Provider</span></span>](create-a-data-service-using-rp-wcf-data-services.md)
- [<span data-ttu-id="ce92d-137">Data Services 공급자</span><span class="sxs-lookup"><span data-stu-id="ce92d-137">Data Services Providers</span></span>](data-services-providers-wcf-data-services.md)
