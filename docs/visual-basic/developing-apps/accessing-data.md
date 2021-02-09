---
description: '자세한 정보: Visual Basic 애플리케이션에서 데이터에 액세스'
title: Visual Basic 애플리케이션에서 데이터에 액세스
ms.date: 07/20/2015
helpviewer_keywords:
- data [Visual Basic]
- Visual Basic, data access
ms.assetid: 3086ab38-3be5-4b22-9385-7d0e16b04f6a
ms.openlocfilehash: 751705a1375782fae1f7ed3aa8590c377ac93d9c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99641592"
---
# <a name="accessing-data-in-visual-basic-applications"></a><span data-ttu-id="dc5e6-103">Visual Basic 애플리케이션에서 데이터에 액세스</span><span class="sxs-lookup"><span data-stu-id="dc5e6-103">Accessing data in Visual Basic applications</span></span>

<span data-ttu-id="dc5e6-104">Visual Basic에는 데이터에 액세스하는 애플리케이션 개발을 지원하기 위한 여러 가지 새로운 기능이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc5e6-104">Visual Basic includes several new features to assist in developing applications that access data.</span></span> <span data-ttu-id="dc5e6-105">[데이터 소스 창](/visualstudio/data-tools/add-new-data-sources)에서 양식으로 항목을 끌어 Windows 애플리케이션에 대한 데이터 바인딩된 양식을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="dc5e6-105">Data-bound forms for Windows applications are created by dragging items from the [Data Sources Window](/visualstudio/data-tools/add-new-data-sources) onto the form.</span></span> <span data-ttu-id="dc5e6-106">**데이터 소스 창** 에서 기존 컨트롤로 항목을 끌어 컨트롤을 데이터에 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="dc5e6-106">You bind controls to data by dragging items from the **Data Sources Window** onto existing controls.</span></span>

## <a name="related-sections"></a><span data-ttu-id="dc5e6-107">관련 단원</span><span class="sxs-lookup"><span data-stu-id="dc5e6-107">Related sections</span></span>

[<span data-ttu-id="dc5e6-108">Visual Studio에서 데이터 액세스</span><span class="sxs-lookup"><span data-stu-id="dc5e6-108">Accessing Data in Visual Studio</span></span>](/visualstudio/data-tools/)  
<span data-ttu-id="dc5e6-109">애플리케이션에 데이터 액세스 기능을 통합하는 방법을 설명하는 페이지의 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="dc5e6-109">Provides links to pages that discuss incorporating data access functionality into your applications.</span></span>

[<span data-ttu-id="dc5e6-110">.NET용 Visual Studio 데이터 도구</span><span class="sxs-lookup"><span data-stu-id="dc5e6-110">Visual Studio data tools for .NET</span></span>](/visualstudio/data-tools/visual-studio-data-tools-for-dotnet)  
<span data-ttu-id="dc5e6-111">Visual Studio를 통해 데이터를 사용하는 애플리케이션을 만드는 방법에 대한 페이지의 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="dc5e6-111">Provides links to pages on creating applications that work with data, using Visual Studio.</span></span>

[<span data-ttu-id="dc5e6-112">LINQ</span><span class="sxs-lookup"><span data-stu-id="dc5e6-112">LINQ</span></span>](../programming-guide/language-features/linq/index.md)  
<span data-ttu-id="dc5e6-113">Visual Basic에서 LINQ를 사용하는 방법을 설명하는 항목의 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="dc5e6-113">Provides links to topics that describe how to use LINQ with Visual Basic.</span></span>

[<span data-ttu-id="dc5e6-114">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="dc5e6-114">LINQ to SQL</span></span>](../../framework/data/adonet/sql/linq/index.md)  
<span data-ttu-id="dc5e6-115">[!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)]에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="dc5e6-115">Provides information about [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)].</span></span> <span data-ttu-id="dc5e6-116">프로그래밍 예제를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="dc5e6-116">Includes programming examples.</span></span>  

<span data-ttu-id="dc5e6-117">[LINQ to SQL Tools in Visual Studio](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2)(Visual Studio의 LINQ to SQL 도구)</span><span class="sxs-lookup"><span data-stu-id="dc5e6-117">[LINQ to SQL Tools in Visual Studio](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2)</span></span>  
<span data-ttu-id="dc5e6-118">애플리케이션에서 [LINQ to SQL](../../framework/data/adonet/sql/linq/index.md) 개체 모델을 만드는 방법에 대한 항목의 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="dc5e6-118">Provides links to topics about how to create a [LINQ to SQL](../../framework/data/adonet/sql/linq/index.md) object model in applications.</span></span>

[<span data-ttu-id="dc5e6-119">n 계층 애플리케이션에서 데이터 세트 작업</span><span class="sxs-lookup"><span data-stu-id="dc5e6-119">Work with datasets in n-tier applications</span></span>](/visualstudio/data-tools/work-with-datasets-in-n-tier-applications)  
<span data-ttu-id="dc5e6-120">다중 계층 데이터 애플리케이션을 만드는 방법에 대한 항목의 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="dc5e6-120">Provides links to topics about how to create multitiered data applications.</span></span>

[<span data-ttu-id="dc5e6-121">새 연결 추가</span><span class="sxs-lookup"><span data-stu-id="dc5e6-121">Add new connections</span></span>](/visualstudio/data-tools/add-new-connections)  
<span data-ttu-id="dc5e6-122">Visual Studio를 사용하여 디자인 타임 도구 및 ADO.NET 연결 개체를 통해 애플리케이션을 데이터에 연결하는 방법에 대한 페이지의 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="dc5e6-122">Provides links to pages on connecting your application to data with design-time tools and ADO.NET connection objects, using Visual Studio.</span></span>

[<span data-ttu-id="dc5e6-123">Visual Studio의 데이터 세트 도구</span><span class="sxs-lookup"><span data-stu-id="dc5e6-123">Dataset Tools in Visual Studio</span></span>](/visualstudio/data-tools/dataset-tools-in-visual-studio)  
<span data-ttu-id="dc5e6-124">데이터를 데이터 세트에 로드하는 방법 및 SQL 문과 저장 프로시저를 실행하는 방법을 설명하는 페이지의 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="dc5e6-124">Provides links to pages describing how to load data into datasets and how to execute SQL statements and stored procedures.</span></span>  

[<span data-ttu-id="dc5e6-125">Visual Studio에서 데이터에 컨트롤 바인딩</span><span class="sxs-lookup"><span data-stu-id="dc5e6-125">Bind controls to data in Visual Studio</span></span>](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio)  
<span data-ttu-id="dc5e6-126">데이터 바인딩된 컨트롤을 통해 Windows Forms에 데이터를 표시하는 방법을 설명하는 페이지의 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="dc5e6-126">Provides links to pages that explain how to display data on Windows Forms through data-bound controls.</span></span>

[<span data-ttu-id="dc5e6-127">데이터 세트의 데이터 편집</span><span class="sxs-lookup"><span data-stu-id="dc5e6-127">Edit Data in Datasets</span></span>](/visualstudio/data-tools/edit-data-in-datasets)  
<span data-ttu-id="dc5e6-128">데이터 세트의 데이터 테이블에서 데이터를 조작하는 방법을 설명하는 페이지의 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="dc5e6-128">Provides links to pages describing how to manipulate the data in the data tables of a dataset.</span></span>  

[<span data-ttu-id="dc5e6-129">데이터 세트의 데이터 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="dc5e6-129">Validate data in datasets</span></span>](/visualstudio/data-tools/validate-data-in-datasets)  
<span data-ttu-id="dc5e6-130">열 및 행 변경 중에 데이터 세트에 유효성 검사를 추가하는 방법을 설명하는 페이지의 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="dc5e6-130">Provides links to pages describing how to add validation to a dataset during column and row changes.</span></span>

[<span data-ttu-id="dc5e6-131">데이터를 다시 데이터베이스에 저장</span><span class="sxs-lookup"><span data-stu-id="dc5e6-131">Save data back to the database</span></span>](/visualstudio/data-tools/save-data-back-to-the-database)  
<span data-ttu-id="dc5e6-132">애플리케이션에서 데이터베이스로 업데이트된 데이터를 보내는 방법을 설명하는 페이지의 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="dc5e6-132">Provides links to pages explaining how to send updated data from an application to the database.</span></span>

[<span data-ttu-id="dc5e6-133">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="dc5e6-133">ADO.NET</span></span>](../../framework/data/adonet/index.md)  
<span data-ttu-id="dc5e6-134">.NET Framework 프로그래머에게 데이터 액세스 서비스를 표시하는 ADO.NET 클래스에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="dc5e6-134">Describes the ADO.NET classes, which expose data-access services to the .NET Framework programmer.</span></span>

[<span data-ttu-id="dc5e6-135">Office 솔루션의 데이터</span><span class="sxs-lookup"><span data-stu-id="dc5e6-135">Data in Office Solutions</span></span>](/visualstudio/vsto/data-in-office-solutions)  
<span data-ttu-id="dc5e6-136">스키마 지향 프로그래밍, 데이터 캐싱 및 서버 쪽 데이터 액세스에 대한 정보를 비롯하여 Office 솔루션에서 데이터가 작동하는 방법을 설명하는 페이지의 링크가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc5e6-136">Contains links to pages that explain how data works in Office solutions, including information about schema-oriented programming, data caching, and server-side data access.</span></span>
