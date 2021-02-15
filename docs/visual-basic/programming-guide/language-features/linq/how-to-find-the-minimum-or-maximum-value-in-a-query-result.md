---
description: '자세한 정보: 방법: LINQ를 사용 하 여 쿼리 결과의 최소값 또는 최대값 찾기 (Visual Basic)'
title: '방법: LINQ를 사용하여 쿼리 결과의 최솟값 또는 최댓값 찾기'
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
ms.openlocfilehash: e6337b61b01d720bd37390f61e4e285aa150ec3a
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100422807"
---
# <a name="how-to-find-the-minimum-or-maximum-value-in-a-query-result-by-using-linq-visual-basic"></a><span data-ttu-id="ace1c-103">방법: LINQ를 사용하여 쿼리 결과의 최소값 또는 최대값 찾기(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ace1c-103">How to: Find the Minimum or Maximum Value in a Query Result by Using LINQ (Visual Basic)</span></span>

<span data-ttu-id="ace1c-104">LINQ (Language-Integrated Query)를 사용 하면 데이터베이스 정보에 쉽게 액세스 하 고 쿼리를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ace1c-104">Language-Integrated Query (LINQ) makes it easy to access database information and execute queries.</span></span>  
  
 <span data-ttu-id="ace1c-105">다음 예에서는 SQL Server 데이터베이스에 대해 쿼리를 수행 하는 새 응용 프로그램을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ace1c-105">The following example shows how to create a new application that performs queries against a SQL Server database.</span></span> <span data-ttu-id="ace1c-106">이 샘플에서는 and 절을 사용 하 여 결과에 대 한 최소값 및 최대값을 결정 합니다 `Aggregate` `Group By` .</span><span class="sxs-lookup"><span data-stu-id="ace1c-106">The sample determines the minimum and maximum values for the results by using the `Aggregate` and `Group By` clauses.</span></span> <span data-ttu-id="ace1c-107">자세한 내용은 [Aggregate 절](../../../language-reference/queries/aggregate-clause.md) 및 [Group By 절](../../../language-reference/queries/group-by-clause.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ace1c-107">For more information, see [Aggregate Clause](../../../language-reference/queries/aggregate-clause.md) and [Group By Clause](../../../language-reference/queries/group-by-clause.md).</span></span>  
  
 <span data-ttu-id="ace1c-108">이 항목의 예제에서는 Northwind 샘플 데이터베이스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ace1c-108">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="ace1c-109">이 데이터베이스가 개발 컴퓨터에 없는 경우 Microsoft 다운로드 센터에서 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ace1c-109">If you do not have this database on your development computer, you can download it from the Microsoft Download Center.</span></span> <span data-ttu-id="ace1c-110">지침은 [샘플 데이터베이스 다운로드](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ace1c-110">For instructions, see [Downloading Sample Databases](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="create-a-connection-to-a-database"></a><span data-ttu-id="ace1c-111">데이터베이스에 대 한 연결 만들기</span><span class="sxs-lookup"><span data-stu-id="ace1c-111">Create a connection to a database</span></span>  
  
1. <span data-ttu-id="ace1c-112">Visual Studio의  /   / **보기** 메뉴에서 서버 탐색기 **데이터베이스 탐색기** 를 클릭 하 여 서버 탐색기 데이터베이스 탐색기를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="ace1c-112">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2. <span data-ttu-id="ace1c-113">**서버 탐색기** 데이터베이스 탐색기에서 **데이터 연결** 을 마우스 오른쪽 단추로 클릭 한 /  다음 **연결 추가** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ace1c-113">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3. <span data-ttu-id="ace1c-114">Northwind 샘플 데이터베이스에 대 한 올바른 연결을 지정 하십시오.</span><span class="sxs-lookup"><span data-stu-id="ace1c-114">Specify a valid connection to the Northwind sample database.</span></span>  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="ace1c-115">LINQ to SQL 파일을 포함 하는 프로젝트를 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="ace1c-115">To add a project that contains a LINQ to SQL file</span></span>  
  
1. <span data-ttu-id="ace1c-116">Visual Studio의 **파일** 메뉴에서 **새로 만들기** 를 가리킨 다음 **프로젝트** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ace1c-116">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="ace1c-117">Visual Basic **Windows Forms 응용 프로그램** 을 프로젝트 형식으로 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ace1c-117">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2. <span data-ttu-id="ace1c-118">**프로젝트** 메뉴에서 **새 항목 추가** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ace1c-118">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="ace1c-119">**LINQ to SQL 클래스** 항목 템플릿을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ace1c-119">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3. <span data-ttu-id="ace1c-120">파일 이름을 `northwind.dbml`로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ace1c-120">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="ace1c-121">**추가** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ace1c-121">Click **Add**.</span></span> <span data-ttu-id="ace1c-122">Northwind .dbml 파일에 대해 개체 관계형 디자이너 (O/R 디자이너)가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="ace1c-122">The Object Relational Designer (O/R Designer) is opened for the northwind.dbml file.</span></span>  
  
## <a name="add-tables-to-query-to-the-or-designer"></a><span data-ttu-id="ace1c-123">O/R 디자이너에 쿼리할 테이블 추가</span><span class="sxs-lookup"><span data-stu-id="ace1c-123">Add tables to query to the O/R Designer</span></span>  
  
1. <span data-ttu-id="ace1c-124">**서버 탐색기** / **데이터베이스 탐색기** 에서 Northwind 데이터베이스에 대 한 연결을 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="ace1c-124">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="ace1c-125">**테이블** 폴더를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="ace1c-125">Expand the **Tables** folder.</span></span>  
  
     <span data-ttu-id="ace1c-126">O/R 디자이너를 닫은 경우 앞에서 추가한 각각의 .dbml 파일을 두 번 클릭 하 여 다시 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ace1c-126">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2. <span data-ttu-id="ace1c-127">Customers 테이블을 클릭 하 고 디자이너의 왼쪽 창으로 끌어 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="ace1c-127">Click the Customers table and drag it to the left pane of the designer.</span></span> <span data-ttu-id="ace1c-128">Orders 테이블을 클릭 하 고 디자이너의 왼쪽 창으로 끌어 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="ace1c-128">Click the Orders table and drag it to the left pane of the designer.</span></span>  
  
     <span data-ttu-id="ace1c-129">디자이너에서 `Customer` `Order` 프로젝트에 대 한 새 및 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ace1c-129">The designer creates new `Customer` and `Order` objects for your project.</span></span> <span data-ttu-id="ace1c-130">디자이너는 자동으로 테이블 간의 관계를 검색 하 고 관련 개체의 자식 속성을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ace1c-130">Notice that the designer automatically detects relationships between the tables and creates child properties for related objects.</span></span> <span data-ttu-id="ace1c-131">예를 들어 IntelliSense는 `Customer` `Orders` 해당 고객과 관련 된 모든 주문에 대 한 속성을 개체에 포함 하는 것을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ace1c-131">For example, IntelliSense will show that the `Customer` object has an `Orders` property for all orders related to that customer.</span></span>  
  
3. <span data-ttu-id="ace1c-132">변경 내용을 저장 하 고 디자이너를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="ace1c-132">Save your changes and close the designer.</span></span>  
  
4. <span data-ttu-id="ace1c-133">프로젝트를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="ace1c-133">Save your project.</span></span>  
  
## <a name="add-code-to-query-the-database-and-display-the-results"></a><span data-ttu-id="ace1c-134">데이터베이스를 쿼리하고 결과를 표시 하는 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="ace1c-134">Add code to query the database and display the results</span></span>  
  
1. <span data-ttu-id="ace1c-135">**도구 상자** 에서 <xref:System.Windows.Forms.DataGridView> 컨트롤을 프로젝트의 기본 Windows 폼, Form1에 끌어 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="ace1c-135">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2. <span data-ttu-id="ace1c-136">Form1을 두 번 클릭 하 여 폼의 이벤트에 코드를 추가 `Load` 합니다.</span><span class="sxs-lookup"><span data-stu-id="ace1c-136">Double-click Form1 to add code to the `Load` event of the form.</span></span>  
  
3. <span data-ttu-id="ace1c-137">O/R 디자이너에 테이블을 추가 하면 디자이너에서 <xref:System.Data.Linq.DataContext> 프로젝트에 대 한 개체를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="ace1c-137">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object for your project.</span></span> <span data-ttu-id="ace1c-138">이 개체에는 각 테이블에 대 한 개별 개체 및 컬렉션 외에도 해당 테이블에 액세스 하는 데 필요한 코드가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ace1c-138">This object contains the code that you must have to access those tables, in addition to individual objects and collections for each table.</span></span> <span data-ttu-id="ace1c-139"><xref:System.Data.Linq.DataContext>프로젝트에 대 한 개체는 .dbml 파일의 이름을 기반으로 이름이 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ace1c-139">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="ace1c-140">이 프로젝트의 경우 <xref:System.Data.Linq.DataContext> 개체의 이름은 `northwindDataContext` 입니다.</span><span class="sxs-lookup"><span data-stu-id="ace1c-140">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="ace1c-141">코드에서의 인스턴스를 만들고 <xref:System.Data.Linq.DataContext> O/R 디자이너에 지정 된 테이블을 쿼리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ace1c-141">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and query the tables specified by the O/R Designer.</span></span>  
  
     <span data-ttu-id="ace1c-142">이벤트에 다음 코드를 추가 합니다 `Load` .</span><span class="sxs-lookup"><span data-stu-id="ace1c-142">Add the following code to the `Load` event.</span></span> <span data-ttu-id="ace1c-143">이 코드는 데이터 컨텍스트의 속성으로 노출 되는 테이블을 쿼리하고 결과의 최소값과 최대값을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ace1c-143">This code queries the tables that are exposed as properties of your data context and determines the minimum and maximum values for the results.</span></span> <span data-ttu-id="ace1c-144">이 샘플에서는 절을 사용 하 여 단일 결과를 쿼리하고 절을 사용 하 여 `Aggregate` `Group By` 그룹화 된 결과의 평균을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="ace1c-144">The sample uses the `Aggregate` clause to query for a single result, and the `Group By` clause to show an average for grouped results.</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form7.vb#14)]  
  
4. <span data-ttu-id="ace1c-145">**F5** 키를 눌러 프로젝트를 실행 하 고 결과를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ace1c-145">Press **F5** to run your project and view the results.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ace1c-146">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ace1c-146">See also</span></span>

- [<span data-ttu-id="ace1c-147">LINQ</span><span class="sxs-lookup"><span data-stu-id="ace1c-147">LINQ</span></span>](index.md)
- [<span data-ttu-id="ace1c-148">쿼리</span><span class="sxs-lookup"><span data-stu-id="ace1c-148">Queries</span></span>](../../../language-reference/queries/index.md)
- [<span data-ttu-id="ace1c-149">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="ace1c-149">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)
- [<span data-ttu-id="ace1c-150">DataContext 메서드(O/R 디자이너)</span><span class="sxs-lookup"><span data-stu-id="ace1c-150">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)
