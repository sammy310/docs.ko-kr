---
description: '자세한 정보: 방법: IIS에서 실행 되는 WCF 데이터 서비스 개발'
title: '방법: IIS에서 실행되는 WCF Data Service 개발'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, developing
- WCF Data Services, deploying
- WCF Data Services, hosting
ms.assetid: f6f768c5-4989-49e3-a36f-896ab4ded86e
ms.openlocfilehash: b4d7b322a00e3c9c43005a416c608e1b98f1ce51
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99765479"
---
# <a name="how-to-develop-a-wcf-data-service-running-on-iis"></a><span data-ttu-id="9d68b-103">방법: IIS에서 실행 되는 WCF 데이터 서비스 개발</span><span class="sxs-lookup"><span data-stu-id="9d68b-103">How to: Develop a WCF data service running on IIS</span></span>

[!INCLUDE [wcf-deprecated](~/includes/wcf-deprecated.md)]

<span data-ttu-id="9d68b-104">이 문서에서는 WCF Data Services를 사용 하 여 인터넷 정보 서비스 (IIS)에서 실행 되는 ASP.NET 웹 앱에서 호스트 되는 Northwind 샘플 데이터베이스를 기반으로 하는 데이터 서비스를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9d68b-104">This article shows how to use WCF Data Services to create a data service that's based on the Northwind sample database that's hosted by an ASP.NET Web app running on Internet Information Services (IIS).</span></span> <span data-ttu-id="9d68b-105">ASP.NET 개발 서버에서 실행 되는 ASP.NET 웹 앱으로 동일한 Northwind 데이터 서비스를 만드는 방법에 대 한 예제는 [WCF Data Services 빠른](quickstart-wcf-data-services.md)시작을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9d68b-105">For an example of how to create the same Northwind data service as an ASP.NET Web app that runs on the ASP.NET Development Server, see the [WCF Data Services quickstart](quickstart-wcf-data-services.md).</span></span>

> [!NOTE]
> <span data-ttu-id="9d68b-106">Northwind 데이터 서비스를 만들려면 먼저 로컬 컴퓨터에 Northwind 샘플 데이터베이스를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d68b-106">To create the Northwind data service, first install the Northwind sample database on the local computer.</span></span> <span data-ttu-id="9d68b-107">데이터베이스를 설치 하려면 [Northwind 및 pubs 예제 데이터베이스에서 Microsoft SQL Server에 대 한](https://github.com/Microsoft/sql-server-samples/tree/master/samples/databases/northwind-pubs)transact-sql 스크립트를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d68b-107">To install the database, run the Transact-SQL script from [Northwind and pubs sample databases for Microsoft SQL Server](https://github.com/Microsoft/sql-server-samples/tree/master/samples/databases/northwind-pubs).</span></span>

<span data-ttu-id="9d68b-108">이 문서에서는 Entity Framework 공급자를 사용 하 여 데이터 서비스를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9d68b-108">This article shows how to create a data service by using the Entity Framework provider.</span></span> <span data-ttu-id="9d68b-109">다른 데이터 서비스 공급자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d68b-109">Other data services providers are available.</span></span> <span data-ttu-id="9d68b-110">자세한 내용은 [데이터 서비스 공급자](data-services-providers-wcf-data-services.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9d68b-110">For more information, see [Data Services Providers](data-services-providers-wcf-data-services.md).</span></span>

<span data-ttu-id="9d68b-111">서비스를 만든 후 데이터 서비스 리소스에 대한 액세스 권한을 명시적으로 부여해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d68b-111">After you create the service, you must explicitly provide access to data service resources.</span></span> <span data-ttu-id="9d68b-112">자세한 내용은 [방법: 데이터 서비스에 대 한 액세스 사용](how-to-enable-access-to-the-data-service-wcf-data-services.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9d68b-112">For more information, see [How to: Enable Access to the Data Service](how-to-enable-access-to-the-data-service-wcf-data-services.md).</span></span>

## <a name="create-the-aspnet-web-application-that-runs-on-iis"></a><span data-ttu-id="9d68b-113">IIS에서 실행 되는 ASP.NET 웹 응용 프로그램 만들기</span><span class="sxs-lookup"><span data-stu-id="9d68b-113">Create the ASP.NET web application that runs on IIS</span></span>

1. <span data-ttu-id="9d68b-114">Visual Studio의 **파일** 메뉴에서 **새로 만들기** > **프로젝트** 를 차례로 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9d68b-114">In Visual Studio, on the **File** menu, select **New** > **Project**.</span></span>

2. <span data-ttu-id="9d68b-115">**새 프로젝트** 대화 상자에서 **설치** 된 > [**Visual c #** 또는 **Visual Basic**] > **웹** 범주를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d68b-115">In the **New Project** dialog box, select the **Installed** > [**Visual C#** or **Visual Basic**] > **Web** category.</span></span>

3. <span data-ttu-id="9d68b-116">**ASP.NET 웹 애플리케이션** 템플릿을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9d68b-116">Select the **ASP.NET Web Application** template.</span></span>

4. <span data-ttu-id="9d68b-117">`NorthwindService`프로젝트의 이름으로를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d68b-117">Enter `NorthwindService` as the name of the project.</span></span>

5. <span data-ttu-id="9d68b-118">**확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9d68b-118">Click **OK**.</span></span>

6. <span data-ttu-id="9d68b-119">**프로젝트** 메뉴에서 **NorthwindService 속성** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d68b-119">On the **Project** menu, select **NorthwindService Properties**.</span></span>

7. <span data-ttu-id="9d68b-120">**웹** 탭을 선택한 다음 **로컬 IIS 웹 서버 사용** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d68b-120">Select the **Web** tab, and then select **Use Local IIS Web Server**.</span></span>

8. <span data-ttu-id="9d68b-121">**가상 디렉터리 만들기** 를 클릭 한 다음 **확인을** 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d68b-121">Click **Create Virtual Directory** and then click **OK**.</span></span>

9. <span data-ttu-id="9d68b-122">관리자 권한으로 실행되는 명령 프롬프트에서 운영 체제에 따라 다음 명령 중 하나를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="9d68b-122">From the command prompt with administrator privileges, execute one of the following commands (depending on the operating system):</span></span>

    - <span data-ttu-id="9d68b-123">32비트 시스템:</span><span class="sxs-lookup"><span data-stu-id="9d68b-123">32-bit systems:</span></span>

        ```console
        "%windir%\Microsoft.NET\Framework\v3.0\Windows Communication Foundation\ServiceModelReg.exe" -i
        ```

    - <span data-ttu-id="9d68b-124">64비트 시스템:</span><span class="sxs-lookup"><span data-stu-id="9d68b-124">64-bit systems:</span></span>

        ```console
        "%windir%\Microsoft.NET\Framework64\v3.0\Windows Communication Foundation\ServiceModelReg.exe" -i
        ```

     <span data-ttu-id="9d68b-125">이렇게 하면 WCF(Windows Communication Foundation)가 컴퓨터에 등록됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d68b-125">This makes sure that Windows Communication Foundation (WCF) is registered on the computer.</span></span>

10. <span data-ttu-id="9d68b-126">관리자 권한으로 실행되는 명령 프롬프트에서 운영 체제에 따라 다음 명령 중 하나를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="9d68b-126">From the command prompt with administrator privileges, execute one of the following commands (depending on the operating system):</span></span>

    - <span data-ttu-id="9d68b-127">32비트 시스템:</span><span class="sxs-lookup"><span data-stu-id="9d68b-127">32-bit systems:</span></span>

        ```console
        "%windir%\Microsoft.NET\Framework\v4.0.30319\aspnet_regiis.exe" -i -enable
        ```

    - <span data-ttu-id="9d68b-128">64비트 시스템:</span><span class="sxs-lookup"><span data-stu-id="9d68b-128">64-bit systems:</span></span>

        ```console
        "%windir%\Microsoft.NET\Framework64\v4.0.30319\aspnet_regiis.exe" -i -enable
        ```

     <span data-ttu-id="9d68b-129">이렇게 하면 WCF가 컴퓨터에 설치된 후 IIS가 제대로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d68b-129">This makes sure that IIS runs correctly after WCF has been installed on the computer.</span></span> <span data-ttu-id="9d68b-130">또한 IIS를 다시 시작해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d68b-130">You might have to also restart IIS.</span></span>

11. <span data-ttu-id="9d68b-131">ASP.NET 애플리케이션이 IIS7에서 실행되는 경우 다음 단계도 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d68b-131">When the ASP.NET application runs on IIS7, you must also perform the following steps:</span></span>

    1. <span data-ttu-id="9d68b-132">IIS 관리자를 열고 **기본 웹 사이트** 아래에 있는 사진 서비스 응용 프로그램으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d68b-132">Open IIS Manager and navigate to the PhotoService application under **Default Web Site**.</span></span>

    2. <span data-ttu-id="9d68b-133">**기능 보기** 에서 **인증** 을 두 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9d68b-133">In **Features View**, double-click **Authentication**.</span></span>

    3. <span data-ttu-id="9d68b-134">**인증** 페이지에서 **익명 인증** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9d68b-134">On the **Authentication** page, select **Anonymous Authentication**.</span></span>

    4. <span data-ttu-id="9d68b-135">**작업** 창에서 **편집** 을 클릭 하 여 익명 사용자가 사이트에 연결 하는 보안 주체를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d68b-135">In the **Actions** pane, click **Edit** to set the security principal under which anonymous users will connect to the site.</span></span>

    5. <span data-ttu-id="9d68b-136">**익명 인증 자격 증명 편집** 대화 상자에서 **응용 프로그램 풀 id** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d68b-136">In the **Edit Anonymous Authentication Credentials** dialog box, select **Application pool identity**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="9d68b-137">Network Service 계정을 사용하는 경우 해당 계정과 연결된 모든 내부 네트워크 액세스 권한이 익명 사용자에게 부여됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d68b-137">When you use the Network Service account, you grant anonymous users all the internal network access associated with that account.</span></span>

12. <span data-ttu-id="9d68b-138">SQL Server Management Studio, sqlcmd.exe 유틸리티 또는 Visual Studio의 Transact-SQL 편집기를 사용하여 Northwind 데이터베이스가 연결된 SQL Server 인스턴스에 대해 다음 Transact-SQL 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="9d68b-138">By using SQL Server Management Studio, the sqlcmd.exe utility, or the Transact-SQL Editor in Visual Studio, execute the following Transact-SQL command against the instance of SQL Server that has the Northwind database attached:</span></span>

    ```sql
    CREATE LOGIN [NT AUTHORITY\NETWORK SERVICE] FROM WINDOWS;
    GO
    ```

    <span data-ttu-id="9d68b-139">이렇게 하면 IIS를 실행하는 데 사용되는 Windows 계정에 대한 로그인이 SQL Server 인스턴스에서 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="9d68b-139">This creates a login in the SQL Server instance for the Windows account used to run IIS.</span></span> <span data-ttu-id="9d68b-140">이에 따라 IIS에서 SQL Server 인스턴스에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d68b-140">This enables IIS to connect to the SQL Server instance.</span></span>

13. <span data-ttu-id="9d68b-141">Northwind 데이터베이스가 연결된 상태에서 다음 Transact-SQL 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="9d68b-141">With the Northwind database attached, execute the following Transact-SQL commands:</span></span>

    ```sql
    USE Northwind
    GO
    CREATE USER [NT AUTHORITY\NETWORK SERVICE]
    FOR LOGIN [NT AUTHORITY\NETWORK SERVICE] WITH DEFAULT_SCHEMA=[dbo];
    GO
    ALTER LOGIN [NT AUTHORITY\NETWORK SERVICE]
    WITH DEFAULT_DATABASE=[Northwind];
    GO
    EXEC sp_addrolemember 'db_datareader', 'NT AUTHORITY\NETWORK SERVICE'
    GO
    EXEC sp_addrolemember 'db_datawriter', 'NT AUTHORITY\NETWORK SERVICE'
    GO
    ```

    <span data-ttu-id="9d68b-142">이렇게 하면 새 로그인에 권한이 부여되어 IIS에서 Northwind 데이터베이스에 있는 데이터를 읽고 Northwind 데이터베이스에 데이터를 쓸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d68b-142">This grants rights to the new login, which enables IIS to read data from and write data to the Northwind database.</span></span>

## <a name="define-the-data-model"></a><span data-ttu-id="9d68b-143">데이터 모델 정의</span><span class="sxs-lookup"><span data-stu-id="9d68b-143">Define the data model</span></span>

1. <span data-ttu-id="9d68b-144">**솔루션 탐색기** 에서 ASP.NET 프로젝트의 이름을 마우스 오른쪽 단추로 클릭 한 다음   >  **새 항목** 추가를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d68b-144">In **Solution Explorer**, right-click the name of the ASP.NET project, and then click **Add** > **New Item**.</span></span>

2. <span data-ttu-id="9d68b-145">**새 항목 추가** 대화 상자에서 **ADO.NET 엔터티 데이터 모델** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d68b-145">In the **Add New Item** dialog box, select **ADO.NET Entity Data Model**.</span></span>

3. <span data-ttu-id="9d68b-146">데이터 모델의 이름에을 입력 `Northwind.edmx` 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d68b-146">For the name of the data model, type `Northwind.edmx`.</span></span>

4. <span data-ttu-id="9d68b-147">엔터티 데이터 모델 마법사에서 **데이터베이스에서 생성** 을 선택 하 고 **다음** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d68b-147">In the Entity Data Model Wizard, select **Generate from Database**, and then click **Next**.</span></span>

5. <span data-ttu-id="9d68b-148">다음 단계 중 하나를 수행 하 여 데이터 모델을 데이터베이스에 연결한 **후 다음을 클릭 합니다**.</span><span class="sxs-lookup"><span data-stu-id="9d68b-148">Connect the data model to the database by doing one of the following steps, and then click **Next**:</span></span>

    - <span data-ttu-id="9d68b-149">데이터베이스 연결이 이미 구성 되어 있지 않은 경우 **새 연결** 을 클릭 하 고 새 연결을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9d68b-149">If you do not have a database connection already configured, click **New Connection** and create a new connection.</span></span> <span data-ttu-id="9d68b-150">자세한 내용은 [How to: Create Connections to SQL Server Databases](/previous-versions/visualstudio/visual-studio-2008/s4yys16a(v=vs.90))을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="9d68b-150">For more information, see [How to: Create Connections to SQL Server Databases](/previous-versions/visualstudio/visual-studio-2008/s4yys16a(v=vs.90)).</span></span> <span data-ttu-id="9d68b-151">이 SQL Server 인스턴스에는 Northwind 샘플 데이터베이스가 연결되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d68b-151">This SQL Server instance must have the Northwind sample database attached.</span></span>

         <span data-ttu-id="9d68b-152">\- 또는 -</span><span class="sxs-lookup"><span data-stu-id="9d68b-152">\- or -</span></span>

    - <span data-ttu-id="9d68b-153">Northwind 데이터베이스에 연결할 수 있도록 데이터베이스 연결이 이미 구성되어 있는 경우 연결 목록에서 해당 연결을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9d68b-153">If you have a database connection already configured to connect to the Northwind database, select that connection from the list of connections.</span></span>

6. <span data-ttu-id="9d68b-154">마법사의 마지막 페이지에서 데이터베이스의 모든 테이블에 대한 확인란을 선택하고 뷰 및 저장 프로시저에 대한 확인란의 선택을 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="9d68b-154">On the final page of the wizard, select the check boxes for all tables in the database, and clear the check boxes for views and stored procedures.</span></span>

7. <span data-ttu-id="9d68b-155">**마침** 을 클릭 하 여 마법사를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="9d68b-155">Click **Finish** to close the wizard.</span></span>

## <a name="create-the-data-service"></a><span data-ttu-id="9d68b-156">데이터 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="9d68b-156">Create the data service</span></span>

1. <span data-ttu-id="9d68b-157">**솔루션 탐색기** 에서 ASP.NET 프로젝트의 이름을 마우스 오른쪽 단추로 클릭 한 다음   >  **새 항목** 추가를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d68b-157">In **Solution Explorer**, right-click the name of your ASP.NET project, and then click **Add** > **New Item**.</span></span>

2. <span data-ttu-id="9d68b-158">**새 항목 추가** 대화 상자에서 **WCF Data Service** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d68b-158">In the **Add New Item** dialog box, select **WCF Data Service**.</span></span>

   ![Visual Studio 2015의 WCF 데이터 서비스 항목 템플릿](./media/wcf-data-service-item-template.png)

   > [!NOTE]
   > <span data-ttu-id="9d68b-160">**WCF 데이터 서비스** 템플릿은 visual studio 2015 이상에서 사용할 수 있지만 visual studio 2017 이상에서는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9d68b-160">The **WCF Data Service** template is available in Visual Studio 2015, but not in Visual Studio 2017 or later.</span></span>

3. <span data-ttu-id="9d68b-161">서비스의 이름으로을 입력 `Northwind` 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d68b-161">For the name of the service, enter `Northwind`.</span></span>

     <span data-ttu-id="9d68b-162">Visual Studio에서 새 서비스의 XML 태그 및 코드 파일이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d68b-162">Visual Studio creates the XML markup and code files for the new service.</span></span> <span data-ttu-id="9d68b-163">기본적으로 코드 편집기 창이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="9d68b-163">By default, the code-editor window opens.</span></span> <span data-ttu-id="9d68b-164">**솔루션 탐색기** 에서 서비스에는 이름, Northwind 및 확장명이 svc.cs 또는. n b n이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d68b-164">In **Solution Explorer**, the service has the name, Northwind, and the extension .svc.cs or .svc.vb.</span></span>

4. <span data-ttu-id="9d68b-165">데이터 서비스 코드에서 데이터 서비스를 정의하는 클래스 정의의 `/* TODO: put your data source class name here */` 주석을 데이터 모델의 엔터티 컨테이너인 형식(이 경우 `NorthwindEntities`)으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="9d68b-165">In the code for the data service, replace the comment `/* TODO: put your data source class name here */` in the definition of the class that defines the data service with the type that is the entity container of the data model, which in this case is `NorthwindEntities`.</span></span> <span data-ttu-id="9d68b-166">클래스 정의는 다음과 같이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="9d68b-166">The class definition should look this the following:</span></span>

     [!code-csharp[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_quickstart_service/cs/northwind.svc.cs#servicedefinition)]
     [!code-vb[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_service/vb/northwind.svc.vb#servicedefinition)]

## <a name="see-also"></a><span data-ttu-id="9d68b-167">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9d68b-167">See also</span></span>

- [<span data-ttu-id="9d68b-168">서비스로 데이터 공개</span><span class="sxs-lookup"><span data-stu-id="9d68b-168">Exposing Your Data as a Service</span></span>](exposing-your-data-as-a-service-wcf-data-services.md)
