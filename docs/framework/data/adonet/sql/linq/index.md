---
title: LINQ to SQL
description: LINQ to SQL은 관계형 데이터를 개체로 관리 하기 위한 런타임 인프라를 제공 하는 .NET Framework 구성 요소입니다.
ms.date: 03/30/2017
ms.assetid: 73d13345-eece-471a-af40-4cc7a2f11655
ms.openlocfilehash: 13502bfee3ee24764d190dace1512bc958343973
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286315"
---
# <a name="linq-to-sql"></a><span data-ttu-id="e9575-103">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="e9575-103">LINQ to SQL</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="e9575-104">는 관계형 데이터를 개체로 관리 하는 데 필요한 런타임 인프라를 제공 하는 .NET Framework 버전 3.5의 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="e9575-104">is a component of .NET Framework version 3.5 that provides a run-time infrastructure for managing relational data as objects.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e9575-105">관계형 데이터는 테이블 간에 서로 관계된 공통 열이 있는 이차원 테이블(*관계* 또는 *플랫 파일*)의 컬렉션으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e9575-105">Relational data appears as a collection of two-dimensional tables (*relations* or *flat files*), where common columns relate tables to each other.</span></span> <span data-ttu-id="e9575-106">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]을 효율적으로 사용하려면 관계형 데이터베이스의 기본 원리에 대해 조금은 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9575-106">To use [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] effectively, you must have some familiarity with the underlying principles of relational databases.</span></span>  
  
 <span data-ttu-id="e9575-107">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서 관계형 데이터베이스의 데이터 모델은 개발자의 프로그래밍 언어로 표현되는 개체 모델에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="e9575-107">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], the data model of a relational database is mapped to an object model expressed in the programming language of the developer.</span></span> <span data-ttu-id="e9575-108">애플리케이션을 실행하면 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서는 개체 모델의 SQL 언어 통합 쿼리를 변환하여 실행을 위해 데이터베이스로 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="e9575-108">When the application runs, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] translates into SQL the language-integrated queries in the object model and sends them to the database for execution.</span></span> <span data-ttu-id="e9575-109">데이터베이스에서 결과를 반환하면 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서는 해당 결과를 사용자의 프로그래밍 언어로 작업할 수 있는 개체로 다시 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="e9575-109">When the database returns the results, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] translates them back to objects that you can work with in your own programming language.</span></span>  
  
 <span data-ttu-id="e9575-110">Visual Studio를 사용 하는 개발자는 일반적으로의 많은 기능을 구현 하기 위한 사용자 인터페이스를 제공 하는 개체 관계형 디자이너을 사용 합니다 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e9575-110">Developers using Visual Studio typically use the Object Relational Designer, which provides a user interface for implementing many of the features of [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
 <span data-ttu-id="e9575-111">이 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 릴리스에 포함된 설명서에서는 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 애플리케이션을 빌드하는 데 필요한 기본 빌드 블록, 프로세스 및 기술에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e9575-111">The documentation that is included with this release of [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] describes the basic building blocks, processes, and techniques you need for building [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] applications.</span></span> <span data-ttu-id="e9575-112">또한 특정 문제에 대 한 Microsoft Docs 검색할 수 있으며, 전문가와 함께 보다 복잡 한 항목을 자세히 논의할 수 있는 [LINQ 포럼](https://social.msdn.microsoft.com/forums/home?forum=linqtosql)에 참여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9575-112">You can also search Microsoft Docs for specific issues, and you can participate in the [LINQ Forum](https://social.msdn.microsoft.com/forums/home?forum=linqtosql), where you can discuss more complex topics in detail with experts.</span></span> <span data-ttu-id="e9575-113">마지막으로 [LINQ to SQL: 관계형 데이터에 대 한 .Net 언어 통합 쿼리](https://docs.microsoft.com/previous-versions/dotnet/articles/bb425822(v=msdn.10)) 백서 정보 기술에 대 한 자세한 내용은 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Visual Basic 및 c # 코드 예제를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e9575-113">Finally, the [LINQ to SQL: .NET Language-Integrated Query for Relational Data](https://docs.microsoft.com/previous-versions/dotnet/articles/bb425822(v=msdn.10)) white paper details [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] technology, complete with Visual Basic and C# code examples.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e9575-114">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="e9575-114">In This Section</span></span>  
 [<span data-ttu-id="e9575-115">시작</span><span class="sxs-lookup"><span data-stu-id="e9575-115">Getting Started</span></span>](getting-started.md)  
 <span data-ttu-id="e9575-116">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]을 사용하는 방법에 대한 정보와 함께 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에 대한 간략한 개요를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e9575-116">Provides a condensed overview of [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] along with information about how to get started using [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
 [<span data-ttu-id="e9575-117">프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="e9575-117">Programming Guide</span></span>](programming-guide.md)  
 <span data-ttu-id="e9575-118">매핑, 쿼리, 업데이트, 디버깅 및 유사한 작업에 대한 단계를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e9575-118">Provides steps for mapping, querying, updating, debugging, and similar tasks.</span></span>  
  
 [<span data-ttu-id="e9575-119">참조</span><span class="sxs-lookup"><span data-stu-id="e9575-119">Reference</span></span>](reference.md)  
 <span data-ttu-id="e9575-120">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]의 일부 측면에 대한 참조 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e9575-120">Provides reference information about several aspects of [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span> <span data-ttu-id="e9575-121">항목에는 SQL-CLR 형식 매핑, 표준 쿼리 연산자 변환 등이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="e9575-121">Topics include SQL-CLR Type Mapping, Standard Query Operator Translation, and more.</span></span>  
  
 [<span data-ttu-id="e9575-122">샘플</span><span class="sxs-lookup"><span data-stu-id="e9575-122">Samples</span></span>](samples.md)  
 <span data-ttu-id="e9575-123">Visual Basic 및 c # 샘플에 대 한 링크를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9575-123">Provides links to Visual Basic and C# samples.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="e9575-124">관련 단원</span><span class="sxs-lookup"><span data-stu-id="e9575-124">Related Sections</span></span>  
 <span data-ttu-id="e9575-125">[LINQ (통합 언어 쿼리)-C #](../../../../../csharp/programming-guide/concepts/linq/index.md)</span><span class="sxs-lookup"><span data-stu-id="e9575-125">[Language-Integrated Query (LINQ) - C#](../../../../../csharp/programming-guide/concepts/linq/index.md)</span></span>\
 <span data-ttu-id="e9575-126">C #의 LINQ 기술에 대 한 개요를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9575-126">Provides overviews of LINQ technologies in C#.</span></span>

 [<span data-ttu-id="e9575-127">LINQ(Language-Integrated Query) - Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e9575-127">Language-Integrated Query (LINQ) - Visual Basic</span></span>](../../../../../visual-basic/programming-guide/concepts/linq/index.md)  
 <span data-ttu-id="e9575-128">Visual Basic의 LINQ 기술에 대 한 개요를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9575-128">Provides overviews of LINQ technologies in Visual Basic.</span></span>
  
 [<span data-ttu-id="e9575-129">LINQ</span><span class="sxs-lookup"><span data-stu-id="e9575-129">LINQ</span></span>](../../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 <span data-ttu-id="e9575-130">Visual Basic 사용자를 위한 LINQ 기술에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9575-130">Describes LINQ technologies for Visual Basic users.</span></span>  
  
 [<span data-ttu-id="e9575-131">LINQ 및 ADO.NET</span><span class="sxs-lookup"><span data-stu-id="e9575-131">LINQ and ADO.NET</span></span>](../../linq-and-ado-net.md)  
 <span data-ttu-id="e9575-132">ADO.NET 포털에 대 한 링크입니다.</span><span class="sxs-lookup"><span data-stu-id="e9575-132">Links to the ADO.NET portal.</span></span>  
  
 <span data-ttu-id="e9575-133">[LINQ to SQL 연습](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/bb386295(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="e9575-133">[LINQ to SQL Walkthroughs](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/bb386295(v=vs.90))</span></span>  
 <span data-ttu-id="e9575-134">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에 대한 연습을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e9575-134">Lists walkthroughs available for [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
 [<span data-ttu-id="e9575-135">샘플 데이터베이스 다운로드</span><span class="sxs-lookup"><span data-stu-id="e9575-135">Downloading Sample Databases</span></span>](downloading-sample-databases.md)  
 <span data-ttu-id="e9575-136">설명서에 사용되는 샘플 데이터베이스를 다운로드하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e9575-136">Describes how to download sample databases used in the documentation.</span></span>  
  
 <span data-ttu-id="e9575-137">[LinqDataSource 웹 서버 컨트롤 개요](https://docs.microsoft.com/previous-versions/aspnet/bb547113(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="e9575-137">[LinqDataSource Web Server Control Overview](https://docs.microsoft.com/previous-versions/aspnet/bb547113(v=vs.100))</span></span>  
 <span data-ttu-id="e9575-138"><xref:System.Web.UI.WebControls.LinqDataSource>컨트롤이 ASP.NET 데이터 소스 제어 아키텍처를 통해 웹 개발자에 게 LINQ (통합 언어 쿼리)를 노출 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9575-138">Describes how the <xref:System.Web.UI.WebControls.LinqDataSource> control exposes Language-Integrated Query (LINQ) to Web developers through the ASP.NET data-source control architecture.</span></span>
