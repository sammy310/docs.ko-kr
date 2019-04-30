---
title: ADO.NET 코드 샘플에 대 한 샘플 SQL Server 데이터베이스를 가져옵니다.
description: SQL Server 및 관리 도구 뿐만 아니라 ADO.NET 설명서의 코드 샘플에 사용 된 샘플 SQL Server 데이터베이스를 다운로드 합니다.
ms.date: 01/11/2019
ms.assetid: ef9d69a1-9461-43fe-94bb-7c836754bcb5
ms.openlocfilehash: 5580f06f3d28ed6d70f75b619498ac8de7bc3326
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62037936"
---
# <a name="get-the-sample-databases-for-adonet-code-samples"></a><span data-ttu-id="20e52-103">ADO.NET 코드 샘플에 대 한 샘플 데이터베이스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="20e52-103">Get the sample databases for ADO.NET code samples</span></span>

<span data-ttu-id="20e52-104">다양 한 예제 및 연습에는 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 설명서 샘플 SQL Server 데이터베이스 및 SQL Server Express를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="20e52-104">A number of examples and walkthroughs in the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] documentation use sample SQL Server databases and SQL Server Express.</span></span> <span data-ttu-id="20e52-105">Microsoft에서 이러한 제품을 무료로 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20e52-105">You can download these products free of charge from Microsoft.</span></span>

## <a name="get-the-northwind-sample-database-for-sql-server"></a><span data-ttu-id="20e52-106">SQL Server 용 Northwind 샘플 데이터베이스를 가져오려면</span><span class="sxs-lookup"><span data-stu-id="20e52-106">Get the Northwind sample database for SQL Server</span></span>

<span data-ttu-id="20e52-107">스크립트를 다운로드 `instnwnd.sql` 다음 GitHub 리포지토리를 만들고 SQL Server 용 Northwind 샘플 데이터베이스 로드에서:</span><span class="sxs-lookup"><span data-stu-id="20e52-107">Download the script `instnwnd.sql` from the following GitHub repository to create and load the Northwind sample database for SQL Server:</span></span>

[<span data-ttu-id="20e52-108">Microsoft SQL Server 용 Northwind 및 pubs 샘플 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="20e52-108">Northwind and pubs sample databases for Microsoft SQL Server</span></span>](https://github.com/Microsoft/sql-server-samples/tree/master/samples/databases/northwind-pubs)

<span data-ttu-id="20e52-109">다운로드 한 실행 해야 하는 Northwind 데이터베이스를 사용 하려면 먼저 `instnwnd.sql` 스크립트 파일을 사용 하 여 SQL Server 인스턴스에서 데이터베이스를 다시 만드는 [SQL Server Management Studio](#get_ssms) 또는 유사한 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="20e52-109">Before you can use the Northwind database, you have to run the downloaded `instnwnd.sql` script file to recreate the database on an instance of SQL Server by using [SQL Server Management Studio](#get_ssms) or a similar tool.</span></span> <span data-ttu-id="20e52-110">리포지토리의 추가 정보 파일의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="20e52-110">Follow the instructions in the Readme file in the repository.</span></span>

> [!TIP]
> <span data-ttu-id="20e52-111">Microsoft Access 용 Northwind 데이터베이스에 대 한 찾고 볼 [Microsoft Access 용 Northwind 샘플 데이터베이스 설치](#northwind_access)합니다.</span><span class="sxs-lookup"><span data-stu-id="20e52-111">If you're looking for the Northwind database for Microsoft Access, see [Install the Northwind sample database for Microsoft Access](#northwind_access).</span></span>

## <a name="northwind_access"></a> <span data-ttu-id="20e52-112">Microsoft Access 용 Northwind 샘플 데이터베이스를 가져오려면</span><span class="sxs-lookup"><span data-stu-id="20e52-112">Get the Northwind sample database for Microsoft Access</span></span>

<span data-ttu-id="20e52-113">Microsoft Access 용 Northwind 샘플 데이터베이스는 Microsoft 다운로드 센터에서 사용할 수 없는 경우</span><span class="sxs-lookup"><span data-stu-id="20e52-113">The Northwind sample database for Microsoft Access is not available on the Microsoft Download Center.</span></span> <span data-ttu-id="20e52-114">Access 내에서 직접 Northwind를 설치 하려면 다음 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="20e52-114">To install Northwind directly from within Access, do the following things:</span></span>

1. <span data-ttu-id="20e52-115">액세스를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="20e52-115">Open Access.</span></span>

1. <span data-ttu-id="20e52-116">Enter **Northwind** 에 **온라인 템플릿 검색** 상자를 선택한 후 **Enter**합니다.</span><span class="sxs-lookup"><span data-stu-id="20e52-116">Enter **Northwind** in the **Search for Online Templates** box, and then select **Enter**.</span></span>

1. <span data-ttu-id="20e52-117">결과 화면에서 선택 **Northwind**합니다.</span><span class="sxs-lookup"><span data-stu-id="20e52-117">On the results screen, select **Northwind**.</span></span> <span data-ttu-id="20e52-118">Northwind 데이터베이스에 대 한 설명을 사용 하 여 새 창이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="20e52-118">A new window opens with a description of the Northwind database.</span></span>

1. <span data-ttu-id="20e52-119">새 창에서에 **파일 이름** 텍스트 상자에서 Northwind 데이터베이스에 대 한 파일 이름을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="20e52-119">In the new window, in the **File Name** text box, provide a filename for your copy of the Northwind database.</span></span>

1. <span data-ttu-id="20e52-120">**만들기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="20e52-120">Select **Create**.</span></span> <span data-ttu-id="20e52-121">액세스는 Northwind 데이터베이스를 다운로드 하 고 파일을 준비 합니다.</span><span class="sxs-lookup"><span data-stu-id="20e52-121">Access downloads the Northwind database and prepares the file.</span></span>

1. <span data-ttu-id="20e52-122">이 프로세스가 완료 되 면 데이터베이스가 시작 화면이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="20e52-122">When this process is complete, the database opens with a Welcome screen.</span></span>

## <a name="get-the-adventureworks-sample-database-for-sql-server"></a><span data-ttu-id="20e52-123">SQL Server에 대 한 AdventureWorks 예제 데이터베이스를 가져오려면</span><span class="sxs-lookup"><span data-stu-id="20e52-123">Get the AdventureWorks sample database for SQL Server</span></span>

<span data-ttu-id="20e52-124">다음 GitHub 리포지토리에서 SQL Server 용 AdventureWorks 샘플 데이터베이스를 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="20e52-124">Download the AdventureWorks sample database for SQL Server from the following GitHub repository:</span></span>

[<span data-ttu-id="20e52-125">AdventureWorks 예제 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="20e52-125">AdventureWorks sample databases</span></span>](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks)

<span data-ttu-id="20e52-126">데이터베이스 백업 중 하나를 다운로드 한 후 (\*.bak) 파일을 SQL Server Management Studio (SSMS)를 사용 하 여 SQL Server 인스턴스에 백업을 복원 합니다.</span><span class="sxs-lookup"><span data-stu-id="20e52-126">After you download one of the database backup (\*.bak) files, restore the backup to an instance of SQL Server by using SQL Server Management Studio (SSMS).</span></span> <span data-ttu-id="20e52-127">참조 [SQL Server Management Studio를 가져오려면](#get_ssms)합니다.</span><span class="sxs-lookup"><span data-stu-id="20e52-127">See [Get SQL Server Management Studio](#get_ssms).</span></span>

## <a name="get_ssms"></a> <span data-ttu-id="20e52-128">Get SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="20e52-128">Get SQL Server Management Studio</span></span>
<span data-ttu-id="20e52-129">보기 또는 다운로드 한 데이터베이스를 수정 하려는 경우에 SQL Server Management Studio (SSMS)를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20e52-129">If you want to view or modify a database that you've downloaded, you can use SQL Server Management Studio (SSMS).</span></span> <span data-ttu-id="20e52-130">다음 페이지에서 SSMS를 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="20e52-130">Download SSMS from the following page:</span></span>

[<span data-ttu-id="20e52-131">SSMS(SQL Server Management Studio) 다운로드</span><span class="sxs-lookup"><span data-stu-id="20e52-131">Download SQL Server Management Studio (SSMS)</span></span>](/sql/ssms/download-sql-server-management-studio-ssms) 

<span data-ttu-id="20e52-132">볼 수 있으며 Visual Studio 통합된 개발 환경 (IDE)에서 데이터베이스를 관리할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20e52-132">You can also view and manage databases in the Visual Studio integrated development environment (IDE).</span></span> <span data-ttu-id="20e52-133">[Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)에서 데이터베이스에 연결 **SQL Server 개체 탐색기**, 데이터베이스에 데이터 연결을 만들거나 **서버 탐색기**합니다.</span><span class="sxs-lookup"><span data-stu-id="20e52-133">In [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017), connect to the database from **SQL Server Object Explorer**, or create a Data Connection to the database in **Server Explorer**.</span></span> <span data-ttu-id="20e52-134">이러한 탐색기 창에서 엽니다는 **보기** 메뉴.</span><span class="sxs-lookup"><span data-stu-id="20e52-134">Open these explorer panes from the **View** menu.</span></span>

## <a name="get_sql"></a> <span data-ttu-id="20e52-135">Get SQL Server Express</span><span class="sxs-lookup"><span data-stu-id="20e52-135">Get SQL Server Express</span></span>

<span data-ttu-id="20e52-136">SQL Server Express는 무료의 초급 수준 버전 SQL server 응용 프로그램과 함께 재배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20e52-136">SQL Server Express is a free, entry-level edition of SQL Server that you can redistribute with applications.</span></span> <span data-ttu-id="20e52-137">다음 페이지에서 SQL Server Express를 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="20e52-137">Download SQL Server Express from the following page:</span></span>
  
[<span data-ttu-id="20e52-138">SQL Server Express Edition</span><span class="sxs-lookup"><span data-stu-id="20e52-138">SQL Server Express Edition</span></span>](https://www.microsoft.com/sql-server/sql-server-editions-express)

<span data-ttu-id="20e52-139">사용 중인 경우 [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017), SQL Server Express LocalDB Professional 이상 버전 뿐만 아니라 Visual Studio의 무료 Community edition에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="20e52-139">If you're using [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017), SQL Server Express LocalDB is included in the free Community edition of Visual Studio, as well as the Professional and higher editions.</span></span>  

## <a name="see-also"></a><span data-ttu-id="20e52-140">참고자료</span><span class="sxs-lookup"><span data-stu-id="20e52-140">See also</span></span>

- [<span data-ttu-id="20e52-141">시작</span><span class="sxs-lookup"><span data-stu-id="20e52-141">Getting Started</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/getting-started.md)
