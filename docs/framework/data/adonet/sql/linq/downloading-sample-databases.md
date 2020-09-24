---
title: ADO.NET 코드 샘플에 대 한 샘플 SQL Server 데이터베이스 가져오기
description: ADO.NET 설명서의 코드 샘플에 사용 된 샘플 SQL Server 데이터베이스와 SQL Server 및 관리 도구를 다운로드 합니다.
ms.date: 01/11/2019
ms.assetid: ef9d69a1-9461-43fe-94bb-7c836754bcb5
ms.openlocfilehash: f7c0d1eb0089a6bfabc92e1deecf563c3e59cc6a
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91156058"
---
# <a name="get-the-sample-databases-for-adonet-code-samples"></a><span data-ttu-id="8df70-103">ADO.NET 코드 샘플에 대 한 샘플 데이터베이스 가져오기</span><span class="sxs-lookup"><span data-stu-id="8df70-103">Get the sample databases for ADO.NET code samples</span></span>

<span data-ttu-id="8df70-104">설명서의 여러 예제 및 연습에서는 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 예제 SQL Server 데이터베이스 및 SQL Server Express를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8df70-104">A number of examples and walkthroughs in the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] documentation use sample SQL Server databases and SQL Server Express.</span></span> <span data-ttu-id="8df70-105">이러한 제품은 Microsoft에서 무료로 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8df70-105">You can download these products free of charge from Microsoft.</span></span>

## <a name="get-the-northwind-sample-database-for-sql-server"></a><span data-ttu-id="8df70-106">SQL Server에 대 한 Northwind 샘플 데이터베이스 가져오기</span><span class="sxs-lookup"><span data-stu-id="8df70-106">Get the Northwind sample database for SQL Server</span></span>

<span data-ttu-id="8df70-107">`instnwnd.sql`다음 GitHub 리포지토리에서 스크립트를 다운로드 하 여 SQL Server에 대 한 Northwind 샘플 데이터베이스를 만들고 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="8df70-107">Download the script `instnwnd.sql` from the following GitHub repository to create and load the Northwind sample database for SQL Server:</span></span>

[<span data-ttu-id="8df70-108">Microsoft SQL Server에 대 한 Northwind 및 pubs 예제 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="8df70-108">Northwind and pubs sample databases for Microsoft SQL Server</span></span>](https://github.com/Microsoft/sql-server-samples/tree/master/samples/databases/northwind-pubs)

<span data-ttu-id="8df70-109">Northwind 데이터베이스를 사용 하려면 먼저 다운로드 한 스크립트 파일을 실행 하 여 `instnwnd.sql` [SQL Server Management Studio](#get_ssms) 또는 유사한 도구를 사용 하 여 SQL Server 인스턴스에 데이터베이스를 다시 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8df70-109">Before you can use the Northwind database, you have to run the downloaded `instnwnd.sql` script file to recreate the database on an instance of SQL Server by using [SQL Server Management Studio](#get_ssms) or a similar tool.</span></span> <span data-ttu-id="8df70-110">리포지토리의 추가 정보 파일에 있는 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="8df70-110">Follow the instructions in the Readme file in the repository.</span></span>

> [!TIP]
> <span data-ttu-id="8df70-111">Microsoft Access 용 Northwind 데이터베이스를 찾고 있는 경우 [Microsoft access 용 northwind 샘플 데이터베이스 설치](#northwind_access)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8df70-111">If you're looking for the Northwind database for Microsoft Access, see [Install the Northwind sample database for Microsoft Access](#northwind_access).</span></span>

## <a name="get-the-northwind-sample-database-for-microsoft-access"></a><a name="northwind_access"></a> <span data-ttu-id="8df70-112">Microsoft Access 용 Northwind 샘플 데이터베이스 가져오기</span><span class="sxs-lookup"><span data-stu-id="8df70-112">Get the Northwind sample database for Microsoft Access</span></span>

<span data-ttu-id="8df70-113">Microsoft Access 용 Northwind 샘플 데이터베이스는 Microsoft 다운로드 센터에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8df70-113">The Northwind sample database for Microsoft Access is not available on the Microsoft Download Center.</span></span> <span data-ttu-id="8df70-114">액세스 내에서 직접 Northwind를 설치 하려면 다음 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="8df70-114">To install Northwind directly from within Access, do the following things:</span></span>

1. <span data-ttu-id="8df70-115">액세스를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="8df70-115">Open Access.</span></span>

1. <span data-ttu-id="8df70-116">**온라인 템플릿 검색** 상자에 **Northwind** 를 입력 한 다음 **enter 키**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8df70-116">Enter **Northwind** in the **Search for Online Templates** box, and then select **Enter**.</span></span>

1. <span data-ttu-id="8df70-117">결과 화면에서 **Northwind**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8df70-117">On the results screen, select **Northwind**.</span></span> <span data-ttu-id="8df70-118">Northwind 데이터베이스에 대 한 설명이 포함 된 새 창이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="8df70-118">A new window opens with a description of the Northwind database.</span></span>

1. <span data-ttu-id="8df70-119">새 창의 **파일 이름** 텍스트 상자에 Northwind 데이터베이스의 복사본에 대 한 파일 이름을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="8df70-119">In the new window, in the **File Name** text box, provide a filename for your copy of the Northwind database.</span></span>

1. <span data-ttu-id="8df70-120">**만들기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8df70-120">Select **Create**.</span></span> <span data-ttu-id="8df70-121">Access는 Northwind 데이터베이스를 다운로드 하 고 파일을 준비 합니다.</span><span class="sxs-lookup"><span data-stu-id="8df70-121">Access downloads the Northwind database and prepares the file.</span></span>

1. <span data-ttu-id="8df70-122">이 프로세스가 완료 되 면 시작 화면이 포함 된 데이터베이스가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="8df70-122">When this process is complete, the database opens with a Welcome screen.</span></span>

## <a name="get-the-adventureworks-sample-database-for-sql-server"></a><span data-ttu-id="8df70-123">SQL Server에 대 한 AdventureWorks 예제 데이터베이스 가져오기</span><span class="sxs-lookup"><span data-stu-id="8df70-123">Get the AdventureWorks sample database for SQL Server</span></span>

<span data-ttu-id="8df70-124">다음 GitHub 리포지토리에서 SQL Server 용 AdventureWorks 샘플 데이터베이스를 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="8df70-124">Download the AdventureWorks sample database for SQL Server from the following GitHub repository:</span></span>

[<span data-ttu-id="8df70-125">AdventureWorks 예제 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="8df70-125">AdventureWorks sample databases</span></span>](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks)

<span data-ttu-id="8df70-126">데이터베이스 백업 파일 (.bak) 중 하나를 다운로드 한 후 \* SQL Server Management Studio (SSMS)를 사용 하 여 SQL Server 인스턴스에 백업을 복원 합니다.</span><span class="sxs-lookup"><span data-stu-id="8df70-126">After you download one of the database backup (\*.bak) files, restore the backup to an instance of SQL Server by using SQL Server Management Studio (SSMS).</span></span> <span data-ttu-id="8df70-127">[Get SQL Server Management Studio](#get_ssms)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8df70-127">See [Get SQL Server Management Studio](#get_ssms).</span></span>

## <a name="get-sql-server-management-studio"></a><a name="get_ssms"></a> <span data-ttu-id="8df70-128">SQL Server Management Studio 가져오기</span><span class="sxs-lookup"><span data-stu-id="8df70-128">Get SQL Server Management Studio</span></span>

<span data-ttu-id="8df70-129">다운로드 한 데이터베이스를 보거나 수정 하려는 경우 SSMS (SQL Server Management Studio)를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8df70-129">If you want to view or modify a database that you've downloaded, you can use SQL Server Management Studio (SSMS).</span></span> <span data-ttu-id="8df70-130">다음 페이지에서 SSMS를 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="8df70-130">Download SSMS from the following page:</span></span>

[<span data-ttu-id="8df70-131">SSMS(SQL Server Management Studio) 다운로드</span><span class="sxs-lookup"><span data-stu-id="8df70-131">Download SQL Server Management Studio (SSMS)</span></span>](/sql/ssms/download-sql-server-management-studio-ssms)

<span data-ttu-id="8df70-132">Visual Studio IDE (통합 개발 환경)에서 데이터베이스를 보고 관리할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8df70-132">You can also view and manage databases in the Visual Studio integrated development environment (IDE).</span></span> <span data-ttu-id="8df70-133">[Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019)에서 **SQL Server 개체 탐색기**의 데이터베이스에 연결 하거나 **서버 탐색기**데이터베이스에 대 한 데이터 연결을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8df70-133">In [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019), connect to the database from **SQL Server Object Explorer**, or create a Data Connection to the database in **Server Explorer**.</span></span> <span data-ttu-id="8df70-134">**보기** 메뉴에서 다음 탐색기 창을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="8df70-134">Open these explorer panes from the **View** menu.</span></span>

## <a name="get-sql-server-express"></a><a name="get_sql"></a> <span data-ttu-id="8df70-135">SQL Server Express 가져오기</span><span class="sxs-lookup"><span data-stu-id="8df70-135">Get SQL Server Express</span></span>

<span data-ttu-id="8df70-136">SQL Server Express는 응용 프로그램을 사용 하 여 재배포할 수 있는 SQL Server의 초급 수준의 무료로 제공 되는 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="8df70-136">SQL Server Express is a free, entry-level edition of SQL Server that you can redistribute with applications.</span></span> <span data-ttu-id="8df70-137">다음 페이지에서 SQL Server Express를 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="8df70-137">Download SQL Server Express from the following page:</span></span>
  
[<span data-ttu-id="8df70-138">SQL Server Express Edition</span><span class="sxs-lookup"><span data-stu-id="8df70-138">SQL Server Express Edition</span></span>](https://www.microsoft.com/sql-server/sql-server-editions-express)

<span data-ttu-id="8df70-139">[Visual studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019)를 사용 하는 경우 SQL Server Express LocalDB는 visual studio의 무료 Community edition 뿐만 아니라 Professional 이상 버전에 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8df70-139">If you're using [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019), SQL Server Express LocalDB is included in the free Community edition of Visual Studio, as well as the Professional and higher editions.</span></span>  

## <a name="see-also"></a><span data-ttu-id="8df70-140">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8df70-140">See also</span></span>

- [<span data-ttu-id="8df70-141">시작</span><span class="sxs-lookup"><span data-stu-id="8df70-141">Getting Started</span></span>](getting-started.md)
