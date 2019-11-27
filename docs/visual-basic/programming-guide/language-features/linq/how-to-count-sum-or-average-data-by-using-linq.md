---
title: '방법: LINQ를 사용 하 여 데이터 계산, 합계 또는 평균 계산'
ms.date: 07/20/2015
helpviewer_keywords:
- average operator [LINQ in Visual Basic]
- aggregate operator [LINQ in Visual Basic]
- aggregate queries
- queries [LINQ in Visual Basic], sum results
- Aggregate clause [Visual Basic]
- sum operator [LINQ in Visual Basic]
- queries [LINQ in Visual Basic], aggregate queries
- queries [LINQ in Visual Basic], counting results
- querying databases [LINQ]
- queries [LINQ in Visual Basic], how-to topics
- query samples [Visual Basic]
- count operator [LINQ in Visual Basic]
ms.assetid: 51ca1f59-7770-4884-8b76-113002e54fc0
ms.openlocfilehash: 7e105c75653f979f53567ef49f1f4cdeafaa4d0f
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345019"
---
# <a name="how-to-count-sum-or-average-data-by-using-linq-visual-basic"></a><span data-ttu-id="7da1a-102">방법: LINQ를 사용하여 데이터 개수, 합 또는 평균 계산(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7da1a-102">How to: Count, Sum, or Average Data by Using LINQ (Visual Basic)</span></span>
<span data-ttu-id="7da1a-103">LINQ (통합 언어 쿼리)를 사용 하면 데이터베이스 정보에 쉽게 액세스 하 고 쿼리를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7da1a-103">Language-Integrated Query (LINQ) makes it easy to access database information and execute queries.</span></span>  
  
 <span data-ttu-id="7da1a-104">다음 예에서는 SQL Server 데이터베이스에 대해 쿼리를 수행 하는 새 응용 프로그램을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7da1a-104">The following example shows how to create a new application that performs queries against a SQL Server database.</span></span> <span data-ttu-id="7da1a-105">이 샘플에서는 `Aggregate` 및 `Group By` 절을 사용 하 여 결과의 수, 합계 및 평균을 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="7da1a-105">The sample counts, sums, and averages the results by using the `Aggregate` and `Group By` clauses.</span></span> <span data-ttu-id="7da1a-106">자세한 내용은 [Aggregate 절](../../../../visual-basic/language-reference/queries/aggregate-clause.md) 및 [Group By 절](../../../../visual-basic/language-reference/queries/group-by-clause.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7da1a-106">For more information, see [Aggregate Clause](../../../../visual-basic/language-reference/queries/aggregate-clause.md) and [Group By Clause](../../../../visual-basic/language-reference/queries/group-by-clause.md).</span></span>  
  
 <span data-ttu-id="7da1a-107">이 항목의 예제에서는 Northwind 샘플 데이터베이스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7da1a-107">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="7da1a-108">이 데이터베이스가 개발 컴퓨터에 없는 경우 Microsoft 다운로드 센터에서 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7da1a-108">If you do not have this database on your development computer, you can download it from the Microsoft Download Center.</span></span> <span data-ttu-id="7da1a-109">지침은 [샘플 데이터베이스 다운로드](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7da1a-109">For instructions, see [Downloading Sample Databases](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="7da1a-110">데이터베이스에 대 한 연결을 만들려면</span><span class="sxs-lookup"><span data-stu-id="7da1a-110">To create a connection to a database</span></span>  
  
1. <span data-ttu-id="7da1a-111">Visual Studio의 **보기** 메뉴에서 **서버 탐색기**/**데이터베이스 탐색기** 를 클릭 하 여 **서버 탐색기**/**데이터베이스 탐색기** 를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="7da1a-111">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2. <span data-ttu-id="7da1a-112">**서버 탐색기**/**데이터베이스 탐색기** 에서 **데이터 연결** 을 마우스 오른쪽 단추로 클릭 한 다음 **연결 추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="7da1a-112">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3. <span data-ttu-id="7da1a-113">Northwind 샘플 데이터베이스에 대 한 올바른 연결을 지정 하십시오.</span><span class="sxs-lookup"><span data-stu-id="7da1a-113">Specify a valid connection to the Northwind sample database.</span></span>  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="7da1a-114">LINQ to SQL 파일을 포함 하는 프로젝트를 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="7da1a-114">To add a project that contains a LINQ to SQL file</span></span>  
  
1. <span data-ttu-id="7da1a-115">Visual Studio의 **파일** 메뉴에서 **새로 만들기**를 가리킨 다음 **프로젝트**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7da1a-115">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="7da1a-116">Visual Basic **Windows Forms 응용 프로그램** 을 프로젝트 형식으로 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7da1a-116">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2. <span data-ttu-id="7da1a-117">**프로젝트** 메뉴에서 **새 항목 추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7da1a-117">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="7da1a-118">**LINQ to SQL 클래스** 항목 템플릿을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7da1a-118">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3. <span data-ttu-id="7da1a-119">파일 이름을 `northwind.dbml`로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7da1a-119">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="7da1a-120">**추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7da1a-120">Click **Add**.</span></span> <span data-ttu-id="7da1a-121">Northwind .dbml 파일에 대해 개체 관계형 디자이너 (O/R 디자이너)가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="7da1a-121">The Object Relational Designer (O/R Designer) is opened for the northwind.dbml file.</span></span>  
  
### <a name="to-add-tables-to-query-to-the-or-designer"></a><span data-ttu-id="7da1a-122">O/R 디자이너에 쿼리할 테이블을 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="7da1a-122">To add tables to query to the O/R Designer</span></span>  
  
1. <span data-ttu-id="7da1a-123">**서버 탐색기**/**데이터베이스 탐색기**에서 Northwind 데이터베이스에 대 한 연결을 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="7da1a-123">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="7da1a-124">**Tables** 폴더를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="7da1a-124">Expand the **Tables** folder.</span></span>  
  
     <span data-ttu-id="7da1a-125">O/R 디자이너를 닫은 경우 앞에서 추가한 각각의 .dbml 파일을 두 번 클릭 하 여 다시 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7da1a-125">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2. <span data-ttu-id="7da1a-126">Customers 테이블을 클릭 하 고 디자이너의 왼쪽 창으로 끌어 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="7da1a-126">Click the Customers table and drag it to the left pane of the designer.</span></span> <span data-ttu-id="7da1a-127">Orders 테이블을 클릭 하 고 디자이너의 왼쪽 창으로 끌어 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="7da1a-127">Click the Orders table and drag it to the left pane of the designer.</span></span>  
  
     <span data-ttu-id="7da1a-128">디자이너는 프로젝트에 대 한 새 `Customer` 및 `Order` 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7da1a-128">The designer creates new `Customer` and `Order` objects for your project.</span></span> <span data-ttu-id="7da1a-129">디자이너는 자동으로 테이블 간의 관계를 검색 하 고 관련 개체의 자식 속성을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7da1a-129">Notice that the designer automatically detects relationships between the tables and creates child properties for related objects.</span></span> <span data-ttu-id="7da1a-130">예를 들어 IntelliSense는 `Customer` 개체에 해당 고객과 관련 된 모든 주문에 대 한 `Orders` 속성이 있음을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7da1a-130">For example, IntelliSense will show that the `Customer` object has an `Orders` property for all orders related to that customer.</span></span>  
  
3. <span data-ttu-id="7da1a-131">변경 내용을 저장 하 고 디자이너를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="7da1a-131">Save your changes and close the designer.</span></span>  
  
4. <span data-ttu-id="7da1a-132">프로젝트를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="7da1a-132">Save your project.</span></span>  
  
### <a name="to-add-code-to-query-the-database-and-display-the-results"></a><span data-ttu-id="7da1a-133">데이터베이스를 쿼리하고 결과를 표시 하는 코드를 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="7da1a-133">To add code to query the database and display the results</span></span>  
  
1. <span data-ttu-id="7da1a-134">**도구 상자**에서 <xref:System.Windows.Forms.DataGridView> 컨트롤을 프로젝트의 기본 Windows 폼 (Form1)으로 끌어옵니다.</span><span class="sxs-lookup"><span data-stu-id="7da1a-134">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2. <span data-ttu-id="7da1a-135">Form1을 두 번 클릭 하 여 양식의 `Load` 이벤트에 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="7da1a-135">Double-click Form1 to add code to the `Load` event of the form.</span></span>  
  
3. <span data-ttu-id="7da1a-136">O/R 디자이너에 테이블을 추가 하는 경우 디자이너는 프로젝트에 대 한 <xref:System.Data.Linq.DataContext> 개체를 추가 했습니다.</span><span class="sxs-lookup"><span data-stu-id="7da1a-136">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object for your project.</span></span> <span data-ttu-id="7da1a-137">이 개체에는 해당 테이블에 액세스 하 고 각 테이블에 대 한 개별 개체 및 컬렉션에 액세스 하는 데 필요한 코드가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7da1a-137">This object contains the code that you must have to access those tables, and to access individual objects and collections for each table.</span></span> <span data-ttu-id="7da1a-138">프로젝트에 대 한 <xref:System.Data.Linq.DataContext> 개체는 .dbml 파일의 이름을 기반으로 이름이 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7da1a-138">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="7da1a-139">이 프로젝트의 경우 <xref:System.Data.Linq.DataContext> 개체의 이름은 `northwindDataContext`입니다.</span><span class="sxs-lookup"><span data-stu-id="7da1a-139">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="7da1a-140">코드에서 <xref:System.Data.Linq.DataContext>의 인스턴스를 만들고 O/R 디자이너에 지정 된 테이블을 쿼리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7da1a-140">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and query the tables specified by the O/R Designer.</span></span>  
  
     <span data-ttu-id="7da1a-141">`Load` 이벤트에 다음 코드를 추가 하 여 <xref:System.Data.Linq.DataContext>의 속성으로 표시 되는 테이블을 쿼리하고 결과를 계산, 합계 및 평균을 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="7da1a-141">Add the following code to the `Load` event to query the tables that are exposed as properties of your <xref:System.Data.Linq.DataContext> and count, sum, and average the results.</span></span> <span data-ttu-id="7da1a-142">이 샘플에서는 `Aggregate` 절을 사용 하 여 단일 결과를 쿼리하고 `Group By` 절을 사용 하 여 그룹화 된 결과의 평균을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="7da1a-142">The sample uses the `Aggregate` clause to query for a single result, and the `Group By` clause to show an average for grouped results.</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form6.vb#13)]  
  
4. <span data-ttu-id="7da1a-143">F5 키를 눌러 프로젝트를 실행 하 고 결과를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="7da1a-143">Press F5 to run your project and view the results.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7da1a-144">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7da1a-144">See also</span></span>

- [<span data-ttu-id="7da1a-145">LINQ</span><span class="sxs-lookup"><span data-stu-id="7da1a-145">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [<span data-ttu-id="7da1a-146">쿼리</span><span class="sxs-lookup"><span data-stu-id="7da1a-146">Queries</span></span>](../../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="7da1a-147">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="7da1a-147">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)
- [<span data-ttu-id="7da1a-148">DataContext 메서드(O/R 디자이너)</span><span class="sxs-lookup"><span data-stu-id="7da1a-148">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)
- [<span data-ttu-id="7da1a-149">Aggregate 절</span><span class="sxs-lookup"><span data-stu-id="7da1a-149">Aggregate Clause</span></span>](../../../../visual-basic/language-reference/queries/aggregate-clause.md)
- [<span data-ttu-id="7da1a-150">Group By 절</span><span class="sxs-lookup"><span data-stu-id="7da1a-150">Group By Clause</span></span>](../../../../visual-basic/language-reference/queries/group-by-clause.md)
