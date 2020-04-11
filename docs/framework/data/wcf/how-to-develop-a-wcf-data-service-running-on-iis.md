---
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
ms.openlocfilehash: 8a1a0c2c55267940463e2c9ab82bb52345269260
ms.sourcegitcommit: 43cbde34970f5f38f30c43cd63b9c7e2e83717ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/11/2020
ms.locfileid: "81121609"
---
# <a name="how-to-develop-a-wcf-data-service-running-on-iis"></a><span data-ttu-id="5faaf-102">방법: IIS에서 실행되는 WCF 데이터 서비스 개발</span><span class="sxs-lookup"><span data-stu-id="5faaf-102">How to: Develop a WCF data service running on IIS</span></span>

<span data-ttu-id="5faaf-103">이 문서에서는 WCF 데이터 서비스를 사용하여 IIS(인터넷 정보 서비스)에서 실행되는 ASP.NET 웹 앱에서 호스팅하는 Northwind 샘플 데이터베이스를 기반으로 하는 데이터 서비스를 만드는 방법을 보여 주며, 이 문서에서는</span><span class="sxs-lookup"><span data-stu-id="5faaf-103">This article shows how to use WCF Data Services to create a data service that's based on the Northwind sample database that's hosted by an ASP.NET Web app running on Internet Information Services (IIS).</span></span> <span data-ttu-id="5faaf-104">ASP.NET 개발 서버에서 실행되는 ASP.NET 웹 앱과 동일한 Northwind 데이터 서비스를 만드는 방법에 대한 예는 [WCF 데이터 서비스 퀵스타트를](quickstart-wcf-data-services.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="5faaf-104">For an example of how to create the same Northwind data service as an ASP.NET Web app that runs on the ASP.NET Development Server, see the [WCF Data Services quickstart](quickstart-wcf-data-services.md).</span></span>

> [!NOTE]
> <span data-ttu-id="5faaf-105">Northwind 데이터 서비스를 만들려면 먼저 로컬 컴퓨터에 Northwind 샘플 데이터베이스를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="5faaf-105">To create the Northwind data service, first install the Northwind sample database on the local computer.</span></span> <span data-ttu-id="5faaf-106">데이터베이스를 설치하려면 [노스윈드에서](https://github.com/Microsoft/sql-server-samples/tree/master/samples/databases/northwind-pubs)Transact-SQL 스크립트를 실행하고 Microsoft SQL Server에 대한 펍 샘플 데이터베이스를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="5faaf-106">To install the database, run the Transact-SQL script from [Northwind and pubs sample databases for Microsoft SQL Server](https://github.com/Microsoft/sql-server-samples/tree/master/samples/databases/northwind-pubs).</span></span>

<span data-ttu-id="5faaf-107">이 문서에서는 Entity Framework 공급자를 사용하여 데이터 서비스를 만드는 방법을 보여 주며 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5faaf-107">This article shows how to create a data service by using the Entity Framework provider.</span></span> <span data-ttu-id="5faaf-108">다른 데이터 서비스 공급자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5faaf-108">Other data services providers are available.</span></span> <span data-ttu-id="5faaf-109">자세한 내용은 [데이터 서비스 공급자](data-services-providers-wcf-data-services.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5faaf-109">For more information, see [Data Services Providers](data-services-providers-wcf-data-services.md).</span></span>

<span data-ttu-id="5faaf-110">서비스를 만든 후 데이터 서비스 리소스에 대한 액세스 권한을 명시적으로 부여해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5faaf-110">After you create the service, you must explicitly provide access to data service resources.</span></span> <span data-ttu-id="5faaf-111">자세한 내용은 [데이터 서비스에 대한 액세스 사용 방법을](how-to-enable-access-to-the-data-service-wcf-data-services.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="5faaf-111">For more information, see [How to: Enable Access to the Data Service](how-to-enable-access-to-the-data-service-wcf-data-services.md).</span></span>

## <a name="create-the-aspnet-web-application-that-runs-on-iis"></a><span data-ttu-id="5faaf-112">IIS에서 실행되는 ASP.NET 웹 응용 프로그램 만들기</span><span class="sxs-lookup"><span data-stu-id="5faaf-112">Create the ASP.NET web application that runs on IIS</span></span>

1. <span data-ttu-id="5faaf-113">Visual Studio의 **파일** 메뉴에서 **새로 만들기** > **프로젝트**를 차례로 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5faaf-113">In Visual Studio, on the **File** menu, select **New** > **Project**.</span></span>

2. <span data-ttu-id="5faaf-114">새 **프로젝트** 대화 상자에서 **설치된** >**[시각적 C#** 또는 **시각적 기본]**> **웹** 범주를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5faaf-114">In the **New Project** dialog box, select the **Installed** > [**Visual C#** or **Visual Basic**] > **Web** category.</span></span>

3. <span data-ttu-id="5faaf-115">**ASP.NET 웹 애플리케이션** 템플릿을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5faaf-115">Select the **ASP.NET Web Application** template.</span></span>

4. <span data-ttu-id="5faaf-116">프로젝트 `NorthwindService` 이름으로 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="5faaf-116">Enter `NorthwindService` as the name of the project.</span></span>

5. <span data-ttu-id="5faaf-117">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5faaf-117">Click **OK**.</span></span>

6. <span data-ttu-id="5faaf-118">**프로젝트** 메뉴에서 **노스윈드서비스 속성을**선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5faaf-118">On the **Project** menu, select **NorthwindService Properties**.</span></span>

7. <span data-ttu-id="5faaf-119">**웹** 탭을 선택한 다음 **로컬 IIS 웹 서버 사용을**선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5faaf-119">Select the **Web** tab, and then select **Use Local IIS Web Server**.</span></span>

8. <span data-ttu-id="5faaf-120">**가상 디렉터리 만들기를** 클릭한 다음 **확인을**클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5faaf-120">Click **Create Virtual Directory** and then click **OK**.</span></span>

9. <span data-ttu-id="5faaf-121">관리자 권한으로 실행되는 명령 프롬프트에서 운영 체제에 따라 다음 명령 중 하나를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="5faaf-121">From the command prompt with administrator privileges, execute one of the following commands (depending on the operating system):</span></span>

    - <span data-ttu-id="5faaf-122">32비트 시스템:</span><span class="sxs-lookup"><span data-stu-id="5faaf-122">32-bit systems:</span></span>

        ```console
        "%windir%\Microsoft.NET\Framework\v3.0\Windows Communication Foundation\ServiceModelReg.exe" -i
        ```

    - <span data-ttu-id="5faaf-123">64비트 시스템:</span><span class="sxs-lookup"><span data-stu-id="5faaf-123">64-bit systems:</span></span>

        ```console
        "%windir%\Microsoft.NET\Framework64\v3.0\Windows Communication Foundation\ServiceModelReg.exe" -i
        ```

     <span data-ttu-id="5faaf-124">이렇게 하면 WCF(Windows Communication Foundation)가 컴퓨터에 등록됩니다.</span><span class="sxs-lookup"><span data-stu-id="5faaf-124">This makes sure that Windows Communication Foundation (WCF) is registered on the computer.</span></span>

10. <span data-ttu-id="5faaf-125">관리자 권한으로 실행되는 명령 프롬프트에서 운영 체제에 따라 다음 명령 중 하나를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="5faaf-125">From the command prompt with administrator privileges, execute one of the following commands (depending on the operating system):</span></span>

    - <span data-ttu-id="5faaf-126">32비트 시스템:</span><span class="sxs-lookup"><span data-stu-id="5faaf-126">32-bit systems:</span></span>

        ```console
        "%windir%\Microsoft.NET\Framework\v4.0.30319\aspnet_regiis.exe" -i -enable
        ```

    - <span data-ttu-id="5faaf-127">64비트 시스템:</span><span class="sxs-lookup"><span data-stu-id="5faaf-127">64-bit systems:</span></span>

        ```console
        "%windir%\Microsoft.NET\Framework64\v4.0.30319\aspnet_regiis.exe" -i -enable
        ```

     <span data-ttu-id="5faaf-128">이렇게 하면 WCF가 컴퓨터에 설치된 후 IIS가 제대로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="5faaf-128">This makes sure that IIS runs correctly after WCF has been installed on the computer.</span></span> <span data-ttu-id="5faaf-129">또한 IIS를 다시 시작해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5faaf-129">You might have to also restart IIS.</span></span>

11. <span data-ttu-id="5faaf-130">ASP.NET 애플리케이션이 IIS7에서 실행되는 경우 다음 단계도 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5faaf-130">When the ASP.NET application runs on IIS7, you must also perform the following steps:</span></span>

    1. <span data-ttu-id="5faaf-131">IIS 관리자를 열고 기본 웹 **사이트에서**PhotoService 응용 프로그램으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="5faaf-131">Open IIS Manager and navigate to the PhotoService application under **Default Web Site**.</span></span>

    2. <span data-ttu-id="5faaf-132">**기능 보기**에서 **인증**을 두 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5faaf-132">In **Features View**, double-click **Authentication**.</span></span>

    3. <span data-ttu-id="5faaf-133">**인증** 페이지에서 **익명 인증**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5faaf-133">On the **Authentication** page, select **Anonymous Authentication**.</span></span>

    4. <span data-ttu-id="5faaf-134">**작업** 창에서 **편집을** 클릭하여 익명 사용자가 사이트에 연결할 보안 주체를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="5faaf-134">In the **Actions** pane, click **Edit** to set the security principal under which anonymous users will connect to the site.</span></span>

    5. <span data-ttu-id="5faaf-135">익명 **인증 자격 증명 편집** 대화 상자에서 **응용 프로그램 풀 ID를**선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5faaf-135">In the **Edit Anonymous Authentication Credentials** dialog box, select **Application pool identity**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="5faaf-136">Network Service 계정을 사용하는 경우 해당 계정과 연결된 모든 내부 네트워크 액세스 권한이 익명 사용자에게 부여됩니다.</span><span class="sxs-lookup"><span data-stu-id="5faaf-136">When you use the Network Service account, you grant anonymous users all the internal network access associated with that account.</span></span>

12. <span data-ttu-id="5faaf-137">SQL Server Management Studio, sqlcmd.exe 유틸리티 또는 Visual Studio의 Transact-SQL 편집기를 사용하여 Northwind 데이터베이스가 연결된 SQL Server 인스턴스에 대해 다음 Transact-SQL 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="5faaf-137">By using SQL Server Management Studio, the sqlcmd.exe utility, or the Transact-SQL Editor in Visual Studio, execute the following Transact-SQL command against the instance of SQL Server that has the Northwind database attached:</span></span>

    ```sql
    CREATE LOGIN [NT AUTHORITY\NETWORK SERVICE] FROM WINDOWS;
    GO
    ```

    <span data-ttu-id="5faaf-138">이렇게 하면 IIS를 실행하는 데 사용되는 Windows 계정에 대한 로그인이 SQL Server 인스턴스에서 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="5faaf-138">This creates a login in the SQL Server instance for the Windows account used to run IIS.</span></span> <span data-ttu-id="5faaf-139">이에 따라 IIS에서 SQL Server 인스턴스에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5faaf-139">This enables IIS to connect to the SQL Server instance.</span></span>

13. <span data-ttu-id="5faaf-140">Northwind 데이터베이스가 연결된 상태에서 다음 Transact-SQL 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="5faaf-140">With the Northwind database attached, execute the following Transact-SQL commands:</span></span>

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

    <span data-ttu-id="5faaf-141">이렇게 하면 새 로그인에 권한이 부여되어 IIS에서 Northwind 데이터베이스에 있는 데이터를 읽고 Northwind 데이터베이스에 데이터를 쓸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5faaf-141">This grants rights to the new login, which enables IIS to read data from and write data to the Northwind database.</span></span>

## <a name="define-the-data-model"></a><span data-ttu-id="5faaf-142">데이터 모델 정의</span><span class="sxs-lookup"><span data-stu-id="5faaf-142">Define the data model</span></span>

1. <span data-ttu-id="5faaf-143">**솔루션 탐색기에서**ASP.NET 프로젝트의 이름을 마우스 오른쪽 단추로 클릭한 다음**새 항목** **추가를** > 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5faaf-143">In **Solution Explorer**, right-click the name of the ASP.NET project, and then click **Add** > **New Item**.</span></span>

2. <span data-ttu-id="5faaf-144">새 **항목 추가** 대화 상자에서 **엔터티 데이터 모델 ADO.NET**선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5faaf-144">In the **Add New Item** dialog box, select **ADO.NET Entity Data Model**.</span></span>

3. <span data-ttu-id="5faaf-145">데이터 모델의 이름에 대해 `Northwind.edmx`을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="5faaf-145">For the name of the data model, type `Northwind.edmx`.</span></span>

4. <span data-ttu-id="5faaf-146">엔터티 데이터 모델 **마법사에서 데이터베이스에서 생성을**선택한 다음 다음 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="5faaf-146">In the Entity Data Model Wizard, select **Generate from Database**, and then click **Next**.</span></span>

5. <span data-ttu-id="5faaf-147">다음 단계 중 하나를 수행하여 데이터 모델을 데이터베이스에 연결한 다음 **다음을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="5faaf-147">Connect the data model to the database by doing one of the following steps, and then click **Next**:</span></span>

    - <span data-ttu-id="5faaf-148">데이터베이스 연결이 이미 구성되지 않은 경우 **새 연결을** 클릭하고 새 연결을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5faaf-148">If you do not have a database connection already configured, click **New Connection** and create a new connection.</span></span> <span data-ttu-id="5faaf-149">자세한 내용은 [How to: Create Connections to SQL Server Databases](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/s4yys16a(v=vs.90))을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="5faaf-149">For more information, see [How to: Create Connections to SQL Server Databases](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/s4yys16a(v=vs.90)).</span></span> <span data-ttu-id="5faaf-150">이 SQL Server 인스턴스에는 Northwind 샘플 데이터베이스가 연결되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5faaf-150">This SQL Server instance must have the Northwind sample database attached.</span></span>

         <span data-ttu-id="5faaf-151">\- 또는-</span><span class="sxs-lookup"><span data-stu-id="5faaf-151">\- or -</span></span>

    - <span data-ttu-id="5faaf-152">Northwind 데이터베이스에 연결할 수 있도록 데이터베이스 연결이 이미 구성되어 있는 경우 연결 목록에서 해당 연결을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5faaf-152">If you have a database connection already configured to connect to the Northwind database, select that connection from the list of connections.</span></span>

6. <span data-ttu-id="5faaf-153">마법사의 마지막 페이지에서 데이터베이스의 모든 테이블에 대한 확인란을 선택하고 뷰 및 저장 프로시저에 대한 확인란의 선택을 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="5faaf-153">On the final page of the wizard, select the check boxes for all tables in the database, and clear the check boxes for views and stored procedures.</span></span>

7. <span data-ttu-id="5faaf-154">**마침** 을 클릭하여 마법사를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="5faaf-154">Click **Finish** to close the wizard.</span></span>

## <a name="create-the-data-service"></a><span data-ttu-id="5faaf-155">데이터 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="5faaf-155">Create the data service</span></span>

1. <span data-ttu-id="5faaf-156">**솔루션 탐색기에서**ASP.NET 프로젝트의 이름을 마우스 오른쪽 단추로 클릭한 다음**새 항목** **추가를** > 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5faaf-156">In **Solution Explorer**, right-click the name of your ASP.NET project, and then click **Add** > **New Item**.</span></span>

2. <span data-ttu-id="5faaf-157">새 **항목 추가** 대화 상자에서 **WCF 데이터 서비스**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5faaf-157">In the **Add New Item** dialog box, select **WCF Data Service**.</span></span>

   ![비주얼 스튜디오 2015의 WCF 데이터 서비스 항목 템플릿](./media/wcf-data-service-item-template.png)

   > [!NOTE]
   > <span data-ttu-id="5faaf-159">**WCF 데이터 서비스** 템플릿은 Visual Studio 2015에서 사용할 수 있지만 Visual Studio 2017 이상에서는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5faaf-159">The **WCF Data Service** template is available in Visual Studio 2015, but not in Visual Studio 2017 or later.</span></span>

3. <span data-ttu-id="5faaf-160">서비스 이름을 보려면 을 `Northwind`입력합니다.</span><span class="sxs-lookup"><span data-stu-id="5faaf-160">For the name of the service, enter `Northwind`.</span></span>

     <span data-ttu-id="5faaf-161">Visual Studio에서 새 서비스의 XML 태그 및 코드 파일이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="5faaf-161">Visual Studio creates the XML markup and code files for the new service.</span></span> <span data-ttu-id="5faaf-162">기본적으로 코드 편집기 창이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="5faaf-162">By default, the code-editor window opens.</span></span> <span data-ttu-id="5faaf-163">**솔루션 탐색기에서**서비스에는 이름, Northwind 및 확장 .svc.cs 또는 .svc.vb가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5faaf-163">In **Solution Explorer**, the service has the name, Northwind, and the extension .svc.cs or .svc.vb.</span></span>

4. <span data-ttu-id="5faaf-164">데이터 서비스 코드에서 데이터 서비스를 정의하는 클래스 정의의 `/* TODO: put your data source class name here */` 주석을 데이터 모델의 엔터티 컨테이너인 형식(이 경우 `NorthwindEntities`)으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="5faaf-164">In the code for the data service, replace the comment `/* TODO: put your data source class name here */` in the definition of the class that defines the data service with the type that is the entity container of the data model, which in this case is `NorthwindEntities`.</span></span> <span data-ttu-id="5faaf-165">클래스 정의는 다음과 같이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="5faaf-165">The class definition should look this the following:</span></span>

     [!code-csharp[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_quickstart_service/cs/northwind.svc.cs#servicedefinition)]
     [!code-vb[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_service/vb/northwind.svc.vb#servicedefinition)]

## <a name="see-also"></a><span data-ttu-id="5faaf-166">참조</span><span class="sxs-lookup"><span data-stu-id="5faaf-166">See also</span></span>

- [<span data-ttu-id="5faaf-167">서비스로 데이터 공개</span><span class="sxs-lookup"><span data-stu-id="5faaf-167">Exposing Your Data as a Service</span></span>](exposing-your-data-as-a-service-wcf-data-services.md)
