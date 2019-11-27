---
title: '방법: LINQ를 사용 하 여 쿼리 결과 필터링'
ms.date: 07/20/2015
helpviewer_keywords:
- filtering [Visual Basic]
- filtering data [LINQ in Visual Basic]
- filtering [LINQ in Visual Basic]
- queries [LINQ in Visual Basic], filtering results
- querying databases [LINQ]
- queries [LINQ in Visual Basic], how-to topics
- query samples [Visual Basic]
- filtering data [Visual Basic]
ms.assetid: ef103092-9bed-4134-97f4-2db696e83c12
ms.openlocfilehash: 2ea8a852a2f012ddb25ec1198c66e09df880ff47
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344983"
---
# <a name="how-to-filter-query-results-by-using-linq-visual-basic"></a><span data-ttu-id="bd7b7-102">방법: LINQ를 사용하여 쿼리 결과 필터링(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bd7b7-102">How to: Filter Query Results by Using LINQ (Visual Basic)</span></span>

<span data-ttu-id="bd7b7-103">LINQ (통합 언어 쿼리)를 사용 하면 데이터베이스 정보에 쉽게 액세스 하 고 쿼리를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd7b7-103">Language-Integrated Query (LINQ) makes it easy to access database information and execute queries.</span></span>

<span data-ttu-id="bd7b7-104">다음 예에서는 SQL Server 데이터베이스에 대해 쿼리를 수행 하 고 `Where` 절을 사용 하 여 특정 값을 기준으로 결과를 필터링 하는 새 응용 프로그램을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bd7b7-104">The following example shows how to create a new application that performs queries against a SQL Server database and filters the results by a particular value by using the `Where` clause.</span></span> <span data-ttu-id="bd7b7-105">자세한 내용은 [Where 절](../../../../visual-basic/language-reference/queries/where-clause.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bd7b7-105">For more information, see [Where Clause](../../../../visual-basic/language-reference/queries/where-clause.md).</span></span>

<span data-ttu-id="bd7b7-106">이 항목의 예제에서는 Northwind 샘플 데이터베이스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd7b7-106">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="bd7b7-107">이 데이터베이스가 개발 컴퓨터에 없는 경우 Microsoft 다운로드 센터에서 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd7b7-107">If you do not have this database on your development computer, you can download it from the Microsoft Download Center.</span></span> <span data-ttu-id="bd7b7-108">지침은 [샘플 데이터베이스 다운로드](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bd7b7-108">For instructions, see [Downloading Sample Databases](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

## <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="bd7b7-109">데이터베이스에 대 한 연결을 만들려면</span><span class="sxs-lookup"><span data-stu-id="bd7b7-109">To create a connection to a database</span></span>

1. <span data-ttu-id="bd7b7-110">Visual Studio의 **보기** 메뉴에서 **서버 탐색기**/**데이터베이스 탐색기** 를 클릭 하 여 **서버 탐색기**/**데이터베이스 탐색기** 를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="bd7b7-110">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>

2. <span data-ttu-id="bd7b7-111">**서버 탐색기**/**데이터베이스 탐색기** 에서 **데이터 연결** 을 마우스 오른쪽 단추로 클릭 한 다음 **연결 추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd7b7-111">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>

3. <span data-ttu-id="bd7b7-112">Northwind 샘플 데이터베이스에 대 한 올바른 연결을 지정 하십시오.</span><span class="sxs-lookup"><span data-stu-id="bd7b7-112">Specify a valid connection to the Northwind sample database.</span></span>

## <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="bd7b7-113">LINQ to SQL 파일을 포함 하는 프로젝트를 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="bd7b7-113">To add a project that contains a LINQ to SQL file</span></span>

1. <span data-ttu-id="bd7b7-114">Visual Studio의 **파일** 메뉴에서 **새로 만들기**를 가리킨 다음 **프로젝트**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="bd7b7-114">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="bd7b7-115">Visual Basic **Windows Forms 응용 프로그램** 을 프로젝트 형식으로 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd7b7-115">Select Visual Basic **Windows Forms Application** as the project type.</span></span>

2. <span data-ttu-id="bd7b7-116">**프로젝트** 메뉴에서 **새 항목 추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="bd7b7-116">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="bd7b7-117">**LINQ to SQL 클래스** 항목 템플릿을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd7b7-117">Select the **LINQ to SQL Classes** item template.</span></span>

3. <span data-ttu-id="bd7b7-118">파일 이름을 `northwind.dbml`로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="bd7b7-118">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="bd7b7-119">**추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="bd7b7-119">Click **Add**.</span></span> <span data-ttu-id="bd7b7-120">Northwind .dbml 파일에 대 한 개체 관계형 디자이너 (O/R 디자이너)이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="bd7b7-120">The Object Relational Designer (O/R Designer) opens for the northwind.dbml file.</span></span>

## <a name="to-add-tables-to-query-to-the-or-designer"></a><span data-ttu-id="bd7b7-121">O/R 디자이너에 쿼리할 테이블을 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="bd7b7-121">To add tables to query to the O/R Designer</span></span>

1. <span data-ttu-id="bd7b7-122">**서버 탐색기**/**데이터베이스 탐색기**에서 Northwind 데이터베이스에 대 한 연결을 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd7b7-122">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="bd7b7-123">**Tables** 폴더를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd7b7-123">Expand the **Tables** folder.</span></span>

     <span data-ttu-id="bd7b7-124">O/R 디자이너를 닫은 경우 앞에서 추가한 각각의 .dbml 파일을 두 번 클릭 하 여 다시 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd7b7-124">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>

2. <span data-ttu-id="bd7b7-125">Customers 테이블을 클릭 하 고 디자이너의 왼쪽 창으로 끌어 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="bd7b7-125">Click the Customers table and drag it to the left pane of the designer.</span></span> <span data-ttu-id="bd7b7-126">Orders 테이블을 클릭 하 고 디자이너의 왼쪽 창으로 끌어 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="bd7b7-126">Click the Orders table and drag it to the left pane of the designer.</span></span>

     <span data-ttu-id="bd7b7-127">디자이너는 프로젝트에 대 한 새 `Customer` 및 `Order` 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="bd7b7-127">The designer creates new `Customer` and `Order` objects for your project.</span></span> <span data-ttu-id="bd7b7-128">디자이너는 자동으로 테이블 간의 관계를 검색 하 고 관련 개체의 자식 속성을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="bd7b7-128">Notice that the designer automatically detects relationships between the tables and creates child properties for related objects.</span></span> <span data-ttu-id="bd7b7-129">예를 들어 IntelliSense는 `Customer` 개체에 해당 고객과 관련 된 모든 주문에 대 한 `Orders` 속성이 있음을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bd7b7-129">For example, IntelliSense will show that the `Customer` object has an `Orders` property for all orders related to that customer.</span></span>

3. <span data-ttu-id="bd7b7-130">변경 내용을 저장 하 고 디자이너를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="bd7b7-130">Save your changes and close the designer.</span></span>

4. <span data-ttu-id="bd7b7-131">프로젝트를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="bd7b7-131">Save your project.</span></span>

## <a name="to-add-code-to-query-the-database-and-display-the-results"></a><span data-ttu-id="bd7b7-132">데이터베이스를 쿼리하고 결과를 표시 하는 코드를 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="bd7b7-132">To add code to query the database and display the results</span></span>

1. <span data-ttu-id="bd7b7-133">**도구 상자**에서 <xref:System.Windows.Forms.DataGridView> 컨트롤을 프로젝트의 기본 Windows 폼 (Form1)으로 끌어옵니다.</span><span class="sxs-lookup"><span data-stu-id="bd7b7-133">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>

2. <span data-ttu-id="bd7b7-134">Form1을 두 번 클릭 하 여 양식의 `Load` 이벤트에 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd7b7-134">Double-click Form1 to add code to the `Load` event of the form.</span></span>

3. <span data-ttu-id="bd7b7-135">O/R 디자이너에 테이블을 추가 하는 경우 디자이너는 프로젝트에 대 한 <xref:System.Data.Linq.DataContext> 개체를 추가 했습니다.</span><span class="sxs-lookup"><span data-stu-id="bd7b7-135">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object for your project.</span></span> <span data-ttu-id="bd7b7-136">이 개체에는 각 테이블에 대 한 개별 개체 및 컬렉션 외에도 해당 테이블에 액세스 하는 데 필요한 코드가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd7b7-136">This object contains the code that you must have to access those tables, in addition to individual objects and collections for each table.</span></span> <span data-ttu-id="bd7b7-137">프로젝트에 대 한 <xref:System.Data.Linq.DataContext> 개체는 .dbml 파일의 이름을 기반으로 이름이 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bd7b7-137">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="bd7b7-138">이 프로젝트의 경우 <xref:System.Data.Linq.DataContext> 개체의 이름은 `northwindDataContext`입니다.</span><span class="sxs-lookup"><span data-stu-id="bd7b7-138">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>

    <span data-ttu-id="bd7b7-139">코드에서 <xref:System.Data.Linq.DataContext>의 인스턴스를 만들고 O/R 디자이너에 지정 된 테이블을 쿼리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd7b7-139">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and query the tables specified by the O/R Designer.</span></span>

    <span data-ttu-id="bd7b7-140">`Load` 이벤트에 다음 코드를 추가 하 여 데이터 컨텍스트의 속성으로 노출 되는 테이블을 쿼리 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd7b7-140">Add the following code to the `Load` event to query the tables that are exposed as properties of your data context.</span></span> <span data-ttu-id="bd7b7-141">쿼리가 결과를 필터링 하 고 `London`에 있는 고객만 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd7b7-141">The query filters the results and returns only customers that are located in `London`.</span></span>

    [!code-vb[VbLINQToSQLHowTos#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form5.vb#11)]

4. <span data-ttu-id="bd7b7-142">F5 키를 눌러 프로젝트를 실행 하 고 결과를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd7b7-142">Press F5 to run your project and view the results.</span></span>

5. <span data-ttu-id="bd7b7-143">다음은 시도해 볼 수 있는 몇 가지 다른 필터입니다.</span><span class="sxs-lookup"><span data-stu-id="bd7b7-143">Following are some other filters that you can try.</span></span>

    [!code-vb[VbLINQToSQLHowTos#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form5.vb#12)]

## <a name="see-also"></a><span data-ttu-id="bd7b7-144">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bd7b7-144">See also</span></span>

- [<span data-ttu-id="bd7b7-145">LINQ</span><span class="sxs-lookup"><span data-stu-id="bd7b7-145">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [<span data-ttu-id="bd7b7-146">쿼리</span><span class="sxs-lookup"><span data-stu-id="bd7b7-146">Queries</span></span>](../../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="bd7b7-147">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="bd7b7-147">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)
- [<span data-ttu-id="bd7b7-148">DataContext 메서드(O/R 디자이너)</span><span class="sxs-lookup"><span data-stu-id="bd7b7-148">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)
