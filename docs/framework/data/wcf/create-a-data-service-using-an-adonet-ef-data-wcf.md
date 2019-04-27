---
title: '방법: ADO.NET Entity Framework 데이터 원본을 (WCF Data Services)를 사용 하 여 데이터 서비스 만들기'
ms.date: 08/24/2018
helpviewer_keywords:
- WCF Data Services, providers
- WCF Data Services, Entity Framework
ms.assetid: 6d11fec8-0108-42f5-8719-2a7866d04428
ms.openlocfilehash: b2adf4fe0d510f65db5bded715f084a4d7e016b6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61935774"
---
# <a name="how-to-create-a-data-service-using-an-adonet-entity-framework-data-source-wcf-data-services"></a><span data-ttu-id="c0aae-102">방법: ADO.NET Entity Framework 데이터 원본을 (WCF Data Services)를 사용 하 여 데이터 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="c0aae-102">How to: Create a Data Service Using an ADO.NET Entity Framework Data Source (WCF Data Services)</span></span>

<span data-ttu-id="c0aae-103">WCF Data Services에서는 엔터티 데이터를 데이터 서비스로 노출 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0aae-103">WCF Data Services exposes entity data as a data service.</span></span> <span data-ttu-id="c0aae-104">이 엔터티 데이터는 데이터 소스가 관계형 데이터베이스일 때 [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)][!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)]에 의해 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0aae-104">This entity data is provided by the [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)][!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] when the data source is a relational database.</span></span> <span data-ttu-id="c0aae-105">이 항목에서는 만드는 방법을 보여 줍니다.는 [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)]-기존 데이터베이스를 기반으로 하며이 데이터 모델을 사용 하 여 새 데이터 서비스를 만들려면 Visual Studio 웹 응용 프로그램에서 데이터 모델을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0aae-105">This topic shows you how to create an [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)]-based data model in a Visual Studio Web application that is based on an existing database and use this data model to create a new data service.</span></span>

<span data-ttu-id="c0aae-106">합니다 [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] 생성할 수 있는 명령줄 도구도 제공는 [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] Visual Studio 프로젝트 외부의 모델입니다.</span><span class="sxs-lookup"><span data-stu-id="c0aae-106">The [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] also provides a command line tool that can generate an [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] model outside of a Visual Studio project.</span></span> <span data-ttu-id="c0aae-107">자세한 내용은 [방법: EdmGen.exe를 사용 하 여 모델 및 매핑 파일 생성](../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c0aae-107">For more information, see [How to: Use EdmGen.exe to Generate the Model and Mapping Files](../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span></span>

## <a name="to-add-an-entity-framework-model-that-is-based-on-an-existing-database-to-an-existing-web-application"></a><span data-ttu-id="c0aae-108">기존 웹 응용 프로그램에 기존 데이터베이스를 기반으로 하는 Entity Framework 모델을 추가하려면</span><span class="sxs-lookup"><span data-stu-id="c0aae-108">To add an Entity Framework model that is based on an existing database to an existing Web application</span></span>

1. <span data-ttu-id="c0aae-109">에 **프로젝트** 메뉴에서 클릭 **추가** > **새 항목**합니다.</span><span class="sxs-lookup"><span data-stu-id="c0aae-109">On the **Project** menu, click **Add** > **New Item**.</span></span>

2. <span data-ttu-id="c0aae-110">에 **템플릿을** 창 클릭 합니다 **데이터** 범주를 선택한 후 **ADO.NET 엔터티 데이터 모델**합니다.</span><span class="sxs-lookup"><span data-stu-id="c0aae-110">In the **Templates** pane, click the **Data** category, and then select **ADO.NET Entity Data Model**.</span></span>

3. <span data-ttu-id="c0aae-111">모델 이름을 입력 한 다음 클릭 **추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="c0aae-111">Enter the model name and then click **Add**.</span></span>

     <span data-ttu-id="c0aae-112">[!INCLUDE[adonet_edm](../../../../includes/adonet-edm-md.md)] 마법사의 첫 페이지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0aae-112">The first page of the [!INCLUDE[adonet_edm](../../../../includes/adonet-edm-md.md)] Wizard is displayed.</span></span>

4. <span data-ttu-id="c0aae-113">에 **모델 콘텐츠 선택** 대화 상자에서 **데이터베이스에서 생성**합니다.</span><span class="sxs-lookup"><span data-stu-id="c0aae-113">In the **Choose Model Contents** dialog box, select **Generate from database**.</span></span> <span data-ttu-id="c0aae-114">**다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c0aae-114">Then click **Next**.</span></span>

5. <span data-ttu-id="c0aae-115">클릭 합니다 **새 연결** 단추입니다.</span><span class="sxs-lookup"><span data-stu-id="c0aae-115">Click the **New Connection** button.</span></span>

6. <span data-ttu-id="c0aae-116">에 **연결 속성** 대화 상자에서 서버 이름을 입력, 인증 방법을 선택, 데이터베이스 이름으로 입력 및 클릭 **확인**합니다.</span><span class="sxs-lookup"><span data-stu-id="c0aae-116">In the **Connection Properties** dialog box, type your server name, select the authentication method, type the database name, and then click **OK**.</span></span>

     <span data-ttu-id="c0aae-117">합니다 **데이터 연결 선택** 대화 상자가 데이터베이스 연결 설정을 사용 하 여 업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0aae-117">The **Choose Your Data Connection** dialog box is updated with your database connection settings.</span></span>

7. <span data-ttu-id="c0aae-118">있는지 확인 합니다 **으로 App.Config의 entity 연결 설정 저장:** 확인란이 선택 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0aae-118">Ensure that the **Save entity connection settings in App.Config as:** checkbox is checked.</span></span> <span data-ttu-id="c0aae-119">**다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c0aae-119">Then click **Next**.</span></span>

8. <span data-ttu-id="c0aae-120">에 **데이터베이스 개체 선택** 대화 상자에서 선택한 모든 데이터베이스의 데이터 서비스에 노출 하려는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="c0aae-120">In the **Choose Your Database Objects** dialog box, select all of database objects that you plan to expose in the data service.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c0aae-121">데이터 모델에 포함된 개체는 데이터 서비스에 의해 자동으로 노출되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c0aae-121">Objects included in the data model are not automatically exposed by the data service.</span></span> <span data-ttu-id="c0aae-122">서비스 자체에서 해당 개체를 명시적으로 노출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0aae-122">They must be explicitly exposed by the service itself.</span></span> <span data-ttu-id="c0aae-123">자세한 내용은 [데이터 서비스 구성](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c0aae-123">For more information, see [Configuring the Data Service](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md).</span></span>

9. <span data-ttu-id="c0aae-124">클릭 **완료** 마법사를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0aae-124">Click **Finish** to complete the wizard.</span></span>

     <span data-ttu-id="c0aae-125">특정 데이터베이스를 기반으로 하는 기본 데이터 모델이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="c0aae-125">This creates a default data model based on the specific database.</span></span> <span data-ttu-id="c0aae-126">[!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)]에서는 데이터 모델을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0aae-126">The [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] enables to customize the data model.</span></span> <span data-ttu-id="c0aae-127">자세한 내용은 [엔터티 데이터 모델 도구 작업](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738480(v=vs.100))합니다.</span><span class="sxs-lookup"><span data-stu-id="c0aae-127">For more information, see [Entity Data Model Tools Tasks](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738480(v=vs.100)).</span></span>

## <a name="to-create-the-data-service-by-using-the-new-data-model"></a><span data-ttu-id="c0aae-128">새 데이터 모델을 사용하여 데이터 서비스를 만들려면</span><span class="sxs-lookup"><span data-stu-id="c0aae-128">To create the data service by using the new data model</span></span>

1. <span data-ttu-id="c0aae-129">Visual Studio에서 데이터 모델을 나타내는 .edmx 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="c0aae-129">In Visual Studio, open the .edmx file that represents the data model.</span></span>

2. <span data-ttu-id="c0aae-130">에 **Model 브라우저**모델을 마우스 오른쪽 단추로 클릭, 클릭 **속성**, 다음 엔터티 컨테이너의 이름을 기록해 둡니다.</span><span class="sxs-lookup"><span data-stu-id="c0aae-130">In the **Model Browser**, right-click the model, click **Properties**, and then note the name of the entity container.</span></span>

3. <span data-ttu-id="c0aae-131">**솔루션 탐색기**의 이름을 마우스 오른쪽 단추로 클릭 하 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 프로젝트를 마우스 클릭 **추가** > **새 항목**합니다.</span><span class="sxs-lookup"><span data-stu-id="c0aae-131">In **Solution Explorer**, right-click the name of your [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] project, and then click **Add** > **New Item**.</span></span>

4. <span data-ttu-id="c0aae-132">에 **새 항목 추가** 대화 상자에서를 **WCF 데이터 서비스** 에서 서식 파일을 **웹** 범주.</span><span class="sxs-lookup"><span data-stu-id="c0aae-132">In the **Add New Item** dialog box, select the **WCF Data Service** template in the **Web** category.</span></span>

   ![Visual Studio 2015에서 WCF 데이터 서비스 항목 템플릿](media/wcf-data-service-item-template.png)

   > [!NOTE]
   > <span data-ttu-id="c0aae-134">합니다 **WCF 데이터 서비스** 서식 파일은 Visual Studio 2015 하지만 되지에 Visual Studio 2017에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0aae-134">The **WCF Data Service** template is available in Visual Studio 2015, but not in Visual Studio 2017.</span></span>

5. <span data-ttu-id="c0aae-135">서비스에 대 한 이름을 입력 한 다음 클릭 **확인**합니다.</span><span class="sxs-lookup"><span data-stu-id="c0aae-135">Supply a name for the service, and then click **OK**.</span></span>

     <span data-ttu-id="c0aae-136">Visual Studio에서 새 서비스의 XML 태그 및 코드 파일이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0aae-136">Visual Studio creates the XML markup and code files for the new service.</span></span> <span data-ttu-id="c0aae-137">기본적으로 코드 편집기 창이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="c0aae-137">By default, the code-editor window opens.</span></span>

6. <span data-ttu-id="c0aae-138">데이터 서비스 코드에서 데이터 서비스를 정의하는 클래스 정의의 `/* TODO: put your data source class name here */` 주석을 <xref:System.Data.Objects.ObjectContext> 클래스에서 상속되고 2단계에서 적어 둔 데이터 모델의 엔터티 컨테이너인 형식으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="c0aae-138">In the code for the data service, replace the comment `/* TODO: put your data source class name here */` in the definition of the class that defines the data service with the type that inherits from the <xref:System.Data.Objects.ObjectContext> class and that is the entity container of the data model, which was noted in step 2.</span></span>

7. <span data-ttu-id="c0aae-139">데이터 서비스 코드에서 권한 있는 클라이언트가 데이터 서비스에서 노출하는 엔터티 집합에 액세스할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0aae-139">In the code for the data service, enable authorized clients to access the entity sets that the data service exposes.</span></span> <span data-ttu-id="c0aae-140">자세한 내용은 [데이터 서비스 만들기](../../../../docs/framework/data/wcf/creating-the-data-service.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c0aae-140">For more information, see [Creating the Data Service](../../../../docs/framework/data/wcf/creating-the-data-service.md).</span></span>

8. <span data-ttu-id="c0aae-141">웹 브라우저를 사용 하 여 Northwind.svc 데이터 서비스를 테스트 하려면 항목의 지침을 따릅니다 [웹 브라우저에서 서비스 액세스](../../../../docs/framework/data/wcf/accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c0aae-141">To test the Northwind.svc data service by using a Web browser, follow the instructions in the topic [Accessing the Service from a Web Browser](../../../../docs/framework/data/wcf/accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c0aae-142">참고자료</span><span class="sxs-lookup"><span data-stu-id="c0aae-142">See also</span></span>

- [<span data-ttu-id="c0aae-143">WCF Data Services 정의</span><span class="sxs-lookup"><span data-stu-id="c0aae-143">Defining WCF Data Services</span></span>](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)
- [<span data-ttu-id="c0aae-144">Data Services 공급자</span><span class="sxs-lookup"><span data-stu-id="c0aae-144">Data Services Providers</span></span>](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md)
- [<span data-ttu-id="c0aae-145">방법: 리플렉션 공급자를 사용 하 여 데이터 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="c0aae-145">How to: Create a Data Service Using the Reflection Provider</span></span>](../../../../docs/framework/data/wcf/create-a-data-service-using-rp-wcf-data-services.md)
- [<span data-ttu-id="c0aae-146">방법: LINQ to SQL 데이터 원본을 사용 하 여 데이터 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="c0aae-146">How to: Create a Data Service Using a LINQ to SQL Data Source</span></span>](../../../../docs/framework/data/wcf/create-a-data-service-using-linq-to-sql-wcf.md)