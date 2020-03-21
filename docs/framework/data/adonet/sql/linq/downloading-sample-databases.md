---
title: ADO.NET 코드 샘플에 대한 샘플 SQL Server 데이터베이스 받기
description: ADO.NET 설명서의 코드 샘플에 사용된 SQL Server 데이터베이스와 SQL Server 및 관리 도구 다운로드
ms.date: 01/11/2019
ms.assetid: ef9d69a1-9461-43fe-94bb-7c836754bcb5
ms.openlocfilehash: 19d659cbe8f39d27b71dc59c738355f12fce92a0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79148389"
---
# <a name="get-the-sample-databases-for-adonet-code-samples"></a><span data-ttu-id="da682-103">ADO.NET 코드 샘플에 대한 샘플 데이터베이스 받기</span><span class="sxs-lookup"><span data-stu-id="da682-103">Get the sample databases for ADO.NET code samples</span></span>

<span data-ttu-id="da682-104">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 설명서의 여러 예제 및 연습에서는 샘플 SQL Server 데이터베이스 및 SQL Server Express를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="da682-104">A number of examples and walkthroughs in the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] documentation use sample SQL Server databases and SQL Server Express.</span></span> <span data-ttu-id="da682-105">이러한 제품은 Microsoft에서 무료로 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da682-105">You can download these products free of charge from Microsoft.</span></span>

## <a name="get-the-northwind-sample-database-for-sql-server"></a><span data-ttu-id="da682-106">SQL Server용 Northwind 샘플 데이터베이스 받기</span><span class="sxs-lookup"><span data-stu-id="da682-106">Get the Northwind sample database for SQL Server</span></span>

<span data-ttu-id="da682-107">다음 GitHub 리포지토리에서 스크립트를 `instnwnd.sql` 다운로드하여 SQL Server용 Northwind 샘플 데이터베이스를 만들고 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="da682-107">Download the script `instnwnd.sql` from the following GitHub repository to create and load the Northwind sample database for SQL Server:</span></span>

[<span data-ttu-id="da682-108">마이크로소프트 SQL 서버에 대 한 노스 윈드 및 술집 샘플 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="da682-108">Northwind and pubs sample databases for Microsoft SQL Server</span></span>](https://github.com/Microsoft/sql-server-samples/tree/master/samples/databases/northwind-pubs)

<span data-ttu-id="da682-109">Northwind 데이터베이스를 사용하려면 다운로드한 `instnwnd.sql` 스크립트 파일을 실행하여 SQL Server 관리 [스튜디오](#get_ssms) 또는 유사한 도구를 사용하여 SQL Server 인스턴스에서 데이터베이스를 다시 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="da682-109">Before you can use the Northwind database, you have to run the downloaded `instnwnd.sql` script file to recreate the database on an instance of SQL Server by using [SQL Server Management Studio](#get_ssms) or a similar tool.</span></span> <span data-ttu-id="da682-110">저장소의 Readme 파일의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="da682-110">Follow the instructions in the Readme file in the repository.</span></span>

> [!TIP]
> <span data-ttu-id="da682-111">Microsoft Access에 대한 노스윈드 데이터베이스를 찾고 있는 경우 [Microsoft Access에 대한 노스윈드 샘플 데이터베이스 설치를](#northwind_access)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="da682-111">If you're looking for the Northwind database for Microsoft Access, see [Install the Northwind sample database for Microsoft Access](#northwind_access).</span></span>

## <a name="get-the-northwind-sample-database-for-microsoft-access"></a><a name="northwind_access"></a><span data-ttu-id="da682-112">마이크로 소프트 액세스에 대한 노스 윈드 샘플 데이터베이스 받기</span><span class="sxs-lookup"><span data-stu-id="da682-112">Get the Northwind sample database for Microsoft Access</span></span>

<span data-ttu-id="da682-113">Microsoft 액세스에 대한 노스윈드 샘플 데이터베이스는 Microsoft 다운로드 센터에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="da682-113">The Northwind sample database for Microsoft Access is not available on the Microsoft Download Center.</span></span> <span data-ttu-id="da682-114">Access 내에서 직접 Northwind를 설치하려면 다음 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="da682-114">To install Northwind directly from within Access, do the following things:</span></span>

1. <span data-ttu-id="da682-115">오픈 액세스.</span><span class="sxs-lookup"><span data-stu-id="da682-115">Open Access.</span></span>

1. <span data-ttu-id="da682-116">**온라인 템플릿 검색** 상자에 **Northwind를** 입력한 다음 **Enter**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="da682-116">Enter **Northwind** in the **Search for Online Templates** box, and then select **Enter**.</span></span>

1. <span data-ttu-id="da682-117">결과 화면에서 **노스윈드를**선택합니다.</span><span class="sxs-lookup"><span data-stu-id="da682-117">On the results screen, select **Northwind**.</span></span> <span data-ttu-id="da682-118">Northwind 데이터베이스에 대한 설명과 함께 새 창이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="da682-118">A new window opens with a description of the Northwind database.</span></span>

1. <span data-ttu-id="da682-119">새 창에서 파일 **이름** 텍스트 상자에 Northwind 데이터베이스 복사본에 대 한 파일 이름을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="da682-119">In the new window, in the **File Name** text box, provide a filename for your copy of the Northwind database.</span></span>

1. <span data-ttu-id="da682-120">**만들기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="da682-120">Select **Create**.</span></span> <span data-ttu-id="da682-121">Access는 Northwind 데이터베이스를 다운로드하고 파일을 준비합니다.</span><span class="sxs-lookup"><span data-stu-id="da682-121">Access downloads the Northwind database and prepares the file.</span></span>

1. <span data-ttu-id="da682-122">이 프로세스가 완료되면 시작 화면으로 데이터베이스가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="da682-122">When this process is complete, the database opens with a Welcome screen.</span></span>

## <a name="get-the-adventureworks-sample-database-for-sql-server"></a><span data-ttu-id="da682-123">SQL 서버에 대한 AdventureWorks 샘플 데이터베이스 받기</span><span class="sxs-lookup"><span data-stu-id="da682-123">Get the AdventureWorks sample database for SQL Server</span></span>

<span data-ttu-id="da682-124">다음 GitHub 리포지토리에서 SQL Server용 AdventureWorks 샘플 데이터베이스를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="da682-124">Download the AdventureWorks sample database for SQL Server from the following GitHub repository:</span></span>

[<span data-ttu-id="da682-125">AdventureWorks 예제 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="da682-125">AdventureWorks sample databases</span></span>](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks)

<span data-ttu-id="da682-126">데이터베이스 백업(.bak)\*파일 중 하나를 다운로드한 후 SSMS(SQL Server 관리 스튜디오)를 사용하여 SQL Server 인스턴스에 백업을 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="da682-126">After you download one of the database backup (\*.bak) files, restore the backup to an instance of SQL Server by using SQL Server Management Studio (SSMS).</span></span> <span data-ttu-id="da682-127">[SQL 서버 관리 스튜디오 받기를](#get_ssms)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="da682-127">See [Get SQL Server Management Studio](#get_ssms).</span></span>

## <a name="get-sql-server-management-studio"></a><a name="get_ssms"></a><span data-ttu-id="da682-128">SQL 서버 관리 스튜디오 받기</span><span class="sxs-lookup"><span data-stu-id="da682-128">Get SQL Server Management Studio</span></span>
<span data-ttu-id="da682-129">다운로드한 데이터베이스를 보거나 수정하려면 Sql Server 관리 스튜디오(SSMS)를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da682-129">If you want to view or modify a database that you've downloaded, you can use SQL Server Management Studio (SSMS).</span></span> <span data-ttu-id="da682-130">다음 페이지에서 SSMS를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="da682-130">Download SSMS from the following page:</span></span>

[<span data-ttu-id="da682-131">SSMS(SQL Server Management Studio) 다운로드</span><span class="sxs-lookup"><span data-stu-id="da682-131">Download SQL Server Management Studio (SSMS)</span></span>](/sql/ssms/download-sql-server-management-studio-ssms)

<span data-ttu-id="da682-132">IDE(Visual Studio 통합 개발 환경)에서 데이터베이스를 보고 관리할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da682-132">You can also view and manage databases in the Visual Studio integrated development environment (IDE).</span></span> <span data-ttu-id="da682-133">[Visual Studio에서](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)SQL Server **개체 탐색기에서**데이터베이스에 연결하거나 **서버 탐색기**의 데이터베이스에 대한 데이터 연결을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="da682-133">In [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017), connect to the database from **SQL Server Object Explorer**, or create a Data Connection to the database in **Server Explorer**.</span></span> <span data-ttu-id="da682-134">**보기** 메뉴에서 이러한 탐색기 창을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="da682-134">Open these explorer panes from the **View** menu.</span></span>

## <a name="get-sql-server-express"></a><a name="get_sql"></a><span data-ttu-id="da682-135">SQL 서버 익스프레스 받기</span><span class="sxs-lookup"><span data-stu-id="da682-135">Get SQL Server Express</span></span>

<span data-ttu-id="da682-136">SQL Server Express는 응용 프로그램과 함께 재배포할 수 있는 무료 엔트리 레벨 버전의 SQL Server입니다.</span><span class="sxs-lookup"><span data-stu-id="da682-136">SQL Server Express is a free, entry-level edition of SQL Server that you can redistribute with applications.</span></span> <span data-ttu-id="da682-137">다음 페이지에서 SQL Server 익스프레스 다운로드:</span><span class="sxs-lookup"><span data-stu-id="da682-137">Download SQL Server Express from the following page:</span></span>
  
[<span data-ttu-id="da682-138">SQL Server Express Edition</span><span class="sxs-lookup"><span data-stu-id="da682-138">SQL Server Express Edition</span></span>](https://www.microsoft.com/sql-server/sql-server-editions-express)

<span data-ttu-id="da682-139">[비주얼 스튜디오를](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)사용하는 경우 SQL Server Express LocalDB는 비주얼 스튜디오의 무료 커뮤니티 버전뿐만 아니라 전문 및 상위 버전에도 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da682-139">If you're using [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017), SQL Server Express LocalDB is included in the free Community edition of Visual Studio, as well as the Professional and higher editions.</span></span>  

## <a name="see-also"></a><span data-ttu-id="da682-140">참고 항목</span><span class="sxs-lookup"><span data-stu-id="da682-140">See also</span></span>

- [<span data-ttu-id="da682-141">시작</span><span class="sxs-lookup"><span data-stu-id="da682-141">Getting Started</span></span>](getting-started.md)
