---
title: '방법: LINQ를 사용하여 쿼리 결과의 최소값 또는 최대값 찾기'
ms.date: 07/20/2015
helpviewer_keywords:
- max operator [LINQ in Visual Basic]
- aggregate operator [LINQ in Visual Basic]
- aggregate queries
- minimum values [LINQ in Visual Basic]
- min operator [LINQ in Visual Basic]
- queries [LINQ in Visual Basic], minimum and maximum values
- Max property
- maximum values [LINQ in Visual Basic]
- Aggregate clause [Visual Basic]
- queries [LINQ in Visual Basic], aggregate queries
- queries [LINQ in Visual Basic], how-to topics
ms.assetid: 238b763b-7dcd-4b14-8050-b65500a4f71c
ms.openlocfilehash: ef5f218cdcc7275f616486110825ad0b9df11cc3
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112364"
---
# <a name="how-to-find-the-minimum-or-maximum-value-in-a-query-result-by-using-linq-visual-basic"></a><span data-ttu-id="7b189-102">방법: LINQ를 사용하여 쿼리 결과의 최소값 또는 최대값 찾기(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7b189-102">How to: Find the Minimum or Maximum Value in a Query Result by Using LINQ (Visual Basic)</span></span>
<span data-ttu-id="7b189-103">LINQ(언어 통합 쿼리)를 사용하면 데이터베이스 정보에 쉽게 액세스하고 쿼리를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b189-103">Language-Integrated Query (LINQ) makes it easy to access database information and execute queries.</span></span>  
  
 <span data-ttu-id="7b189-104">다음 예제에서는 SQL Server 데이터베이스에 대해 쿼리를 수행하는 새 응용 프로그램을 만드는 방법을 보여 주습니다.</span><span class="sxs-lookup"><span data-stu-id="7b189-104">The following example shows how to create a new application that performs queries against a SQL Server database.</span></span> <span data-ttu-id="7b189-105">샘플은 `Aggregate` 및 `Group By` 절을 사용하여 결과에 대한 최소값과 최대값을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="7b189-105">The sample determines the minimum and maximum values for the results by using the `Aggregate` and `Group By` clauses.</span></span> <span data-ttu-id="7b189-106">자세한 내용은 집계 절 및 [그룹별](../../../../visual-basic/language-reference/queries/group-by-clause.md) [절을](../../../../visual-basic/language-reference/queries/aggregate-clause.md) 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="7b189-106">For more information, see [Aggregate Clause](../../../../visual-basic/language-reference/queries/aggregate-clause.md) and [Group By Clause](../../../../visual-basic/language-reference/queries/group-by-clause.md).</span></span>  
  
 <span data-ttu-id="7b189-107">이 항목의 예제에서는 Northwind 샘플 데이터베이스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7b189-107">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="7b189-108">이 데이터베이스가 개발 컴퓨터에 없는 경우 Microsoft 다운로드 센터에서 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b189-108">If you do not have this database on your development computer, you can download it from the Microsoft Download Center.</span></span> <span data-ttu-id="7b189-109">지침은 샘플 [데이터베이스 다운로드를](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="7b189-109">For instructions, see [Downloading Sample Databases](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="create-a-connection-to-a-database"></a><span data-ttu-id="7b189-110">데이터베이스에 대한 연결 만들기</span><span class="sxs-lookup"><span data-stu-id="7b189-110">Create a connection to a database</span></span>  
  
1. <span data-ttu-id="7b189-111">Visual Studio에서 **보기** 메뉴에서 **서버 탐색기**/데이터베이스 탐색기를 클릭하여 **서버 탐색기**/**데이터베이스 탐색기를** 엽니다.**Database Explorer**</span><span class="sxs-lookup"><span data-stu-id="7b189-111">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2. <span data-ttu-id="7b189-112">**서버 탐색기**/**데이터베이스 탐색기에서** **데이터 연결을** 마우스 오른쪽 단추로 클릭한 다음 연결 **추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7b189-112">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3. <span data-ttu-id="7b189-113">Northwind 샘플 데이터베이스에 대한 유효한 연결을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7b189-113">Specify a valid connection to the Northwind sample database.</span></span>  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="7b189-114">SQL 파일에 LINQ가 포함된 프로젝트를 추가하려면</span><span class="sxs-lookup"><span data-stu-id="7b189-114">To add a project that contains a LINQ to SQL file</span></span>  
  
1. <span data-ttu-id="7b189-115">비주얼 스튜디오에서 **파일** 메뉴에서 **새로** 를 가리킨 다음 **프로젝트를**클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7b189-115">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="7b189-116">시각적 기본 **Windows 양식 응용 프로그램을** 프로젝트 유형으로 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7b189-116">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2. <span data-ttu-id="7b189-117">**프로젝트** 메뉴에서 **새 항목 추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7b189-117">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="7b189-118">LINQ에서 SQL 클래스 항목 항목 **템플릿을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="7b189-118">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3. <span data-ttu-id="7b189-119">파일 이름을 `northwind.dbml`로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7b189-119">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="7b189-120">**추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7b189-120">Click **Add**.</span></span> <span data-ttu-id="7b189-121">northwind.dbml 파일에 대해 개체 관계형 디자이너(O/R 디자이너)가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="7b189-121">The Object Relational Designer (O/R Designer) is opened for the northwind.dbml file.</span></span>  
  
## <a name="add-tables-to-query-to-the-or-designer"></a><span data-ttu-id="7b189-122">O/R 디자이너에 쿼리할 테이블 추가</span><span class="sxs-lookup"><span data-stu-id="7b189-122">Add tables to query to the O/R Designer</span></span>  
  
1. <span data-ttu-id="7b189-123">**서버 탐색기**/**데이터베이스 탐색기에서**Northwind 데이터베이스에 대한 연결을 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="7b189-123">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="7b189-124">**테이블** 폴더를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="7b189-124">Expand the **Tables** folder.</span></span>  
  
     <span data-ttu-id="7b189-125">O/R 디자이너를 닫은 경우 이전에 추가한 northwind.dbml 파일을 두 번 클릭하여 다시 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b189-125">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2. <span data-ttu-id="7b189-126">Customers 테이블을 클릭하고 디자이너의 왼쪽 창으로 드래그합니다.</span><span class="sxs-lookup"><span data-stu-id="7b189-126">Click the Customers table and drag it to the left pane of the designer.</span></span> <span data-ttu-id="7b189-127">Orders 테이블을 클릭하고 디자이너의 왼쪽 창으로 드래그합니다.</span><span class="sxs-lookup"><span data-stu-id="7b189-127">Click the Orders table and drag it to the left pane of the designer.</span></span>  
  
     <span data-ttu-id="7b189-128">디자이너는 프로젝트에 `Customer` `Order` 대한 새 개체와 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7b189-128">The designer creates new `Customer` and `Order` objects for your project.</span></span> <span data-ttu-id="7b189-129">디자이너는 테이블 간의 관계를 자동으로 감지하고 관련 개체에 대한 자식 속성을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7b189-129">Notice that the designer automatically detects relationships between the tables and creates child properties for related objects.</span></span> <span data-ttu-id="7b189-130">예를 들어 IntelliSense는 개체에 `Customer` 해당 `Orders` 고객과 관련된 모든 주문에 대한 속성이 있음을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="7b189-130">For example, IntelliSense will show that the `Customer` object has an `Orders` property for all orders related to that customer.</span></span>  
  
3. <span data-ttu-id="7b189-131">변경 내용을 저장하고 디자이너를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="7b189-131">Save your changes and close the designer.</span></span>  
  
4. <span data-ttu-id="7b189-132">프로젝트를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="7b189-132">Save your project.</span></span>  
  
## <a name="add-code-to-query-the-database-and-display-the-results"></a><span data-ttu-id="7b189-133">데이터베이스를 쿼리하고 결과를 표시하는 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7b189-133">Add code to query the database and display the results</span></span>  
  
1. <span data-ttu-id="7b189-134">도구 **상자에서**컨트롤을 <xref:System.Windows.Forms.DataGridView> 프로젝트의 기본 Windows 양식인 Form1로 드래그합니다.</span><span class="sxs-lookup"><span data-stu-id="7b189-134">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2. <span data-ttu-id="7b189-135">양식 1을 두 번 클릭하여 `Load` 양식의 이벤트에 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7b189-135">Double-click Form1 to add code to the `Load` event of the form.</span></span>  
  
3. <span data-ttu-id="7b189-136">O/R 디자이너에 테이블을 추가하면 디자이너가 <xref:System.Data.Linq.DataContext> 프로젝트에 대한 개체를 추가했습니다.</span><span class="sxs-lookup"><span data-stu-id="7b189-136">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object for your project.</span></span> <span data-ttu-id="7b189-137">이 개체에는 각 테이블에 대한 개별 개체 및 컬렉션 외에 해당 테이블에 액세스해야 하는 코드가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b189-137">This object contains the code that you must have to access those tables, in addition to individual objects and collections for each table.</span></span> <span data-ttu-id="7b189-138">프로젝트의 <xref:System.Data.Linq.DataContext> 개체는 .dbml 파일의 이름을 기반으로 이름이 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b189-138">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="7b189-139">이 프로젝트의 경우 <xref:System.Data.Linq.DataContext> 개체 `northwindDataContext`이름이 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b189-139">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="7b189-140">코드의 <xref:System.Data.Linq.DataContext> 인스턴스를 만들고 O/R 디자이너가 지정한 테이블을 쿼리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b189-140">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and query the tables specified by the O/R Designer.</span></span>  
  
     <span data-ttu-id="7b189-141">이벤트에 다음 코드를 `Load` 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7b189-141">Add the following code to the `Load` event.</span></span> <span data-ttu-id="7b189-142">이 코드는 데이터 컨텍스트의 속성으로 노출되는 테이블을 쿼리하고 결과에 대한 최소값과 최대값을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="7b189-142">This code queries the tables that are exposed as properties of your data context and determines the minimum and maximum values for the results.</span></span> <span data-ttu-id="7b189-143">샘플에서는 절을 `Aggregate` 사용하여 단일 결과를 쿼리하고 `Group By` 절은 그룹화된 결과에 대한 평균을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="7b189-143">The sample uses the `Aggregate` clause to query for a single result, and the `Group By` clause to show an average for grouped results.</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form7.vb#14)]  
  
4. <span data-ttu-id="7b189-144">**F5를** 눌러 프로젝트를 실행하고 결과를 봅니다.</span><span class="sxs-lookup"><span data-stu-id="7b189-144">Press **F5** to run your project and view the results.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b189-145">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7b189-145">See also</span></span>

- [<span data-ttu-id="7b189-146">LINQ</span><span class="sxs-lookup"><span data-stu-id="7b189-146">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [<span data-ttu-id="7b189-147">쿼리</span><span class="sxs-lookup"><span data-stu-id="7b189-147">Queries</span></span>](../../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="7b189-148">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="7b189-148">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)
- [<span data-ttu-id="7b189-149">데이터 컨텍스트 메서드(O/R 디자이너)</span><span class="sxs-lookup"><span data-stu-id="7b189-149">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)
