---
description: '자세한 정보: 방법: LINQ를 사용 하 여 쿼리 결과 필터링 (Visual Basic)'
title: '방법: LINQ를 사용하여 쿼리 결과 필터링'
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
ms.openlocfilehash: b3f861d9a7fb7b601606f190ad3bfbeef054cad7
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100422800"
---
# <a name="how-to-filter-query-results-by-using-linq-visual-basic"></a><span data-ttu-id="96ef8-103">방법: LINQ를 사용하여 쿼리 결과 필터링(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="96ef8-103">How to: Filter Query Results by Using LINQ (Visual Basic)</span></span>

<span data-ttu-id="96ef8-104">LINQ (Language-Integrated Query)를 사용 하면 데이터베이스 정보에 쉽게 액세스 하 고 쿼리를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96ef8-104">Language-Integrated Query (LINQ) makes it easy to access database information and execute queries.</span></span>

<span data-ttu-id="96ef8-105">다음 예에서는 SQL Server 데이터베이스에 대해 쿼리를 수행 하 고 절을 사용 하 여 특정 값을 기준으로 결과를 필터링 하는 새 응용 프로그램을 만드는 방법을 보여 줍니다 `Where` .</span><span class="sxs-lookup"><span data-stu-id="96ef8-105">The following example shows how to create a new application that performs queries against a SQL Server database and filters the results by a particular value by using the `Where` clause.</span></span> <span data-ttu-id="96ef8-106">자세한 내용은 [Where 절](../../../language-reference/queries/where-clause.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="96ef8-106">For more information, see [Where Clause](../../../language-reference/queries/where-clause.md).</span></span>

<span data-ttu-id="96ef8-107">이 항목의 예제에서는 Northwind 샘플 데이터베이스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="96ef8-107">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="96ef8-108">이 데이터베이스가 개발 컴퓨터에 없는 경우 Microsoft 다운로드 센터에서 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96ef8-108">If you do not have this database on your development computer, you can download it from the Microsoft Download Center.</span></span> <span data-ttu-id="96ef8-109">지침은 [샘플 데이터베이스 다운로드](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="96ef8-109">For instructions, see [Downloading Sample Databases](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

## <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="96ef8-110">데이터베이스에 대 한 연결을 만들려면</span><span class="sxs-lookup"><span data-stu-id="96ef8-110">To create a connection to a database</span></span>

1. <span data-ttu-id="96ef8-111">Visual Studio의  /   / **보기** 메뉴에서 서버 탐색기 **데이터베이스 탐색기** 를 클릭 하 여 서버 탐색기 데이터베이스 탐색기를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="96ef8-111">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>

2. <span data-ttu-id="96ef8-112">**서버 탐색기** 데이터베이스 탐색기에서 **데이터 연결** 을 마우스 오른쪽 단추로 클릭 한 /  다음 **연결 추가** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="96ef8-112">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>

3. <span data-ttu-id="96ef8-113">Northwind 샘플 데이터베이스에 대 한 올바른 연결을 지정 하십시오.</span><span class="sxs-lookup"><span data-stu-id="96ef8-113">Specify a valid connection to the Northwind sample database.</span></span>

## <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="96ef8-114">LINQ to SQL 파일을 포함 하는 프로젝트를 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="96ef8-114">To add a project that contains a LINQ to SQL file</span></span>

1. <span data-ttu-id="96ef8-115">Visual Studio의 **파일** 메뉴에서 **새로 만들기** 를 가리킨 다음 **프로젝트** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="96ef8-115">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="96ef8-116">Visual Basic **Windows Forms 응용 프로그램** 을 프로젝트 형식으로 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="96ef8-116">Select Visual Basic **Windows Forms Application** as the project type.</span></span>

2. <span data-ttu-id="96ef8-117">**프로젝트** 메뉴에서 **새 항목 추가** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="96ef8-117">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="96ef8-118">**LINQ to SQL 클래스** 항목 템플릿을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="96ef8-118">Select the **LINQ to SQL Classes** item template.</span></span>

3. <span data-ttu-id="96ef8-119">파일 이름을 `northwind.dbml`로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="96ef8-119">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="96ef8-120">**추가** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="96ef8-120">Click **Add**.</span></span> <span data-ttu-id="96ef8-121">Northwind .dbml 파일에 대 한 개체 관계형 디자이너 (O/R 디자이너)이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="96ef8-121">The Object Relational Designer (O/R Designer) opens for the northwind.dbml file.</span></span>

## <a name="to-add-tables-to-query-to-the-or-designer"></a><span data-ttu-id="96ef8-122">O/R 디자이너에 쿼리할 테이블을 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="96ef8-122">To add tables to query to the O/R Designer</span></span>

1. <span data-ttu-id="96ef8-123">**서버 탐색기** / **데이터베이스 탐색기** 에서 Northwind 데이터베이스에 대 한 연결을 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="96ef8-123">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="96ef8-124">**테이블** 폴더를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="96ef8-124">Expand the **Tables** folder.</span></span>

     <span data-ttu-id="96ef8-125">O/R 디자이너를 닫은 경우 앞에서 추가한 각각의 .dbml 파일을 두 번 클릭 하 여 다시 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96ef8-125">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>

2. <span data-ttu-id="96ef8-126">Customers 테이블을 클릭 하 고 디자이너의 왼쪽 창으로 끌어 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="96ef8-126">Click the Customers table and drag it to the left pane of the designer.</span></span> <span data-ttu-id="96ef8-127">Orders 테이블을 클릭 하 고 디자이너의 왼쪽 창으로 끌어 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="96ef8-127">Click the Orders table and drag it to the left pane of the designer.</span></span>

     <span data-ttu-id="96ef8-128">디자이너에서 `Customer` `Order` 프로젝트에 대 한 새 및 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="96ef8-128">The designer creates new `Customer` and `Order` objects for your project.</span></span> <span data-ttu-id="96ef8-129">디자이너는 자동으로 테이블 간의 관계를 검색 하 고 관련 개체의 자식 속성을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="96ef8-129">Notice that the designer automatically detects relationships between the tables and creates child properties for related objects.</span></span> <span data-ttu-id="96ef8-130">예를 들어 IntelliSense는 `Customer` `Orders` 해당 고객과 관련 된 모든 주문에 대 한 속성을 개체에 포함 하는 것을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="96ef8-130">For example, IntelliSense will show that the `Customer` object has an `Orders` property for all orders related to that customer.</span></span>

3. <span data-ttu-id="96ef8-131">변경 내용을 저장 하 고 디자이너를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="96ef8-131">Save your changes and close the designer.</span></span>

4. <span data-ttu-id="96ef8-132">프로젝트를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="96ef8-132">Save your project.</span></span>

## <a name="to-add-code-to-query-the-database-and-display-the-results"></a><span data-ttu-id="96ef8-133">데이터베이스를 쿼리하고 결과를 표시 하는 코드를 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="96ef8-133">To add code to query the database and display the results</span></span>

1. <span data-ttu-id="96ef8-134">**도구 상자** 에서 <xref:System.Windows.Forms.DataGridView> 컨트롤을 프로젝트의 기본 Windows 폼, Form1에 끌어 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="96ef8-134">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>

2. <span data-ttu-id="96ef8-135">Form1을 두 번 클릭 하 여 폼의 이벤트에 코드를 추가 `Load` 합니다.</span><span class="sxs-lookup"><span data-stu-id="96ef8-135">Double-click Form1 to add code to the `Load` event of the form.</span></span>

3. <span data-ttu-id="96ef8-136">O/R 디자이너에 테이블을 추가 하면 디자이너에서 <xref:System.Data.Linq.DataContext> 프로젝트에 대 한 개체를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="96ef8-136">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object for your project.</span></span> <span data-ttu-id="96ef8-137">이 개체에는 각 테이블에 대 한 개별 개체 및 컬렉션 외에도 해당 테이블에 액세스 하는 데 필요한 코드가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96ef8-137">This object contains the code that you must have to access those tables, in addition to individual objects and collections for each table.</span></span> <span data-ttu-id="96ef8-138"><xref:System.Data.Linq.DataContext>프로젝트에 대 한 개체는 .dbml 파일의 이름을 기반으로 이름이 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96ef8-138">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="96ef8-139">이 프로젝트의 경우 <xref:System.Data.Linq.DataContext> 개체의 이름은 `northwindDataContext` 입니다.</span><span class="sxs-lookup"><span data-stu-id="96ef8-139">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>

    <span data-ttu-id="96ef8-140">코드에서의 인스턴스를 만들고 <xref:System.Data.Linq.DataContext> O/R 디자이너에 지정 된 테이블을 쿼리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96ef8-140">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and query the tables specified by the O/R Designer.</span></span>

    <span data-ttu-id="96ef8-141">이벤트에 다음 코드를 추가 `Load` 하 여 데이터 컨텍스트의 속성으로 노출 되는 테이블을 쿼리 합니다.</span><span class="sxs-lookup"><span data-stu-id="96ef8-141">Add the following code to the `Load` event to query the tables that are exposed as properties of your data context.</span></span> <span data-ttu-id="96ef8-142">쿼리가 결과를 필터링 하 고에 있는 고객만 반환 합니다 `London` .</span><span class="sxs-lookup"><span data-stu-id="96ef8-142">The query filters the results and returns only customers that are located in `London`.</span></span>

    [!code-vb[VbLINQToSQLHowTos#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form5.vb#11)]

4. <span data-ttu-id="96ef8-143">F5 키를 눌러 프로젝트를 실행 하 고 결과를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="96ef8-143">Press F5 to run your project and view the results.</span></span>

5. <span data-ttu-id="96ef8-144">다음은 시도해 볼 수 있는 몇 가지 다른 필터입니다.</span><span class="sxs-lookup"><span data-stu-id="96ef8-144">Following are some other filters that you can try.</span></span>

    [!code-vb[VbLINQToSQLHowTos#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form5.vb#12)]

## <a name="see-also"></a><span data-ttu-id="96ef8-145">참고 항목</span><span class="sxs-lookup"><span data-stu-id="96ef8-145">See also</span></span>

- [<span data-ttu-id="96ef8-146">LINQ</span><span class="sxs-lookup"><span data-stu-id="96ef8-146">LINQ</span></span>](index.md)
- [<span data-ttu-id="96ef8-147">쿼리</span><span class="sxs-lookup"><span data-stu-id="96ef8-147">Queries</span></span>](../../../language-reference/queries/index.md)
- [<span data-ttu-id="96ef8-148">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="96ef8-148">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)
- [<span data-ttu-id="96ef8-149">DataContext 메서드(O/R 디자이너)</span><span class="sxs-lookup"><span data-stu-id="96ef8-149">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)
