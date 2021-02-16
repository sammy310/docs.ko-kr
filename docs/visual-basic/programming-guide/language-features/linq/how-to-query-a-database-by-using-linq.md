---
description: '자세한 정보: 방법: LINQ를 사용 하 여 데이터베이스 쿼리 (Visual Basic)'
title: '방법: LINQ를 사용하여 데이터베이스 쿼리'
ms.date: 07/20/2015
helpviewer_keywords:
- query samples [LINQ]
- database querying [LINQ]
- queries [LINQ in Visual Basic], database querying
- querying databases [LINQ]
- queries [LINQ in Visual Basic], how-to topics
- query samples [Visual Basic]
ms.assetid: bcf5e9c3-a236-4399-9a7f-3991eca7cf56
ms.openlocfilehash: 9a5577b52fc9bb313717386ce921421a34928a4c
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100430601"
---
# <a name="how-to-query-a-database-by-using-linq-visual-basic"></a><span data-ttu-id="bc53e-103">방법: LINQ를 사용하여 데이터베이스 쿼리(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bc53e-103">How to: Query a Database by Using LINQ (Visual Basic)</span></span>

<span data-ttu-id="bc53e-104">LINQ (Language-Integrated Query)를 사용 하면 데이터베이스 정보에 쉽게 액세스 하 고 쿼리를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc53e-104">Language-Integrated Query (LINQ) makes it easy to access database information and execute queries.</span></span>  
  
 <span data-ttu-id="bc53e-105">다음 예에서는 SQL Server 데이터베이스에 대해 쿼리를 수행 하는 새 응용 프로그램을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bc53e-105">The following example shows how to create a new application that performs queries against a SQL Server database.</span></span>  
  
 <span data-ttu-id="bc53e-106">이 항목의 예제에서는 Northwind 샘플 데이터베이스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc53e-106">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="bc53e-107">이 데이터베이스가 개발 컴퓨터에 없는 경우 Microsoft 다운로드 센터에서 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc53e-107">If you do not have this database on your development computer, you can download it from the Microsoft Download Center.</span></span> <span data-ttu-id="bc53e-108">지침은 [샘플 데이터베이스 다운로드](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bc53e-108">For instructions, see [Downloading Sample Databases](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="bc53e-109">데이터베이스에 대 한 연결을 만들려면</span><span class="sxs-lookup"><span data-stu-id="bc53e-109">To create a connection to a database</span></span>  
  
1. <span data-ttu-id="bc53e-110">Visual Studio의  /   / **보기** 메뉴에서 서버 탐색기 **데이터베이스 탐색기** 를 클릭 하 여 서버 탐색기 데이터베이스 탐색기를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="bc53e-110">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2. <span data-ttu-id="bc53e-111">**서버 탐색기** 데이터베이스 탐색기에서 **데이터 연결** 을 마우스 오른쪽 단추로 클릭 한 /  다음 **연결 추가** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc53e-111">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3. <span data-ttu-id="bc53e-112">Northwind 샘플 데이터베이스에 대 한 올바른 연결을 지정 하십시오.</span><span class="sxs-lookup"><span data-stu-id="bc53e-112">Specify a valid connection to the Northwind sample database.</span></span>  
  
## <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="bc53e-113">LINQ to SQL 파일을 포함 하는 프로젝트를 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="bc53e-113">To add a project that contains a LINQ to SQL file</span></span>  
  
1. <span data-ttu-id="bc53e-114">Visual Studio의 **파일** 메뉴에서 **새로 만들기** 를 가리킨 다음 **프로젝트** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="bc53e-114">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="bc53e-115">Visual Basic **Windows Forms 응용 프로그램** 을 프로젝트 형식으로 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc53e-115">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2. <span data-ttu-id="bc53e-116">**프로젝트** 메뉴에서 **새 항목 추가** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="bc53e-116">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="bc53e-117">**LINQ to SQL 클래스** 항목 템플릿을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc53e-117">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3. <span data-ttu-id="bc53e-118">파일 이름을 `northwind.dbml`로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="bc53e-118">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="bc53e-119">**추가** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="bc53e-119">Click **Add**.</span></span> <span data-ttu-id="bc53e-120">Northwind .dbml 파일에 대해 개체 관계형 디자이너 (O/R 디자이너)가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="bc53e-120">The Object Relational Designer (O/R Designer) is opened for the northwind.dbml file.</span></span>  
  
## <a name="to-add-tables-to-query-to-the-or-designer"></a><span data-ttu-id="bc53e-121">O/R 디자이너에 쿼리할 테이블을 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="bc53e-121">To add tables to query to the O/R Designer</span></span>  
  
1. <span data-ttu-id="bc53e-122">**서버 탐색기** / **데이터베이스 탐색기** 에서 Northwind 데이터베이스에 대 한 연결을 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc53e-122">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="bc53e-123">**테이블** 폴더를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="bc53e-123">Expand the **Tables** folder.</span></span>  
  
     <span data-ttu-id="bc53e-124">O/R 디자이너를 닫은 경우 앞에서 추가한 각각의 .dbml 파일을 두 번 클릭 하 여 다시 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc53e-124">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2. <span data-ttu-id="bc53e-125">Customers 테이블을 클릭 하 고 디자이너의 왼쪽 창으로 끌어 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="bc53e-125">Click the Customers table and drag it to the left pane of the designer.</span></span> <span data-ttu-id="bc53e-126">Orders 테이블을 클릭 하 고 디자이너의 왼쪽 창으로 끌어 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="bc53e-126">Click the Orders table and drag it to the left pane of the designer.</span></span>  
  
     <span data-ttu-id="bc53e-127">디자이너에서 `Customer` `Order` 프로젝트에 대 한 새 및 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="bc53e-127">The designer creates new `Customer` and `Order` objects for your project.</span></span> <span data-ttu-id="bc53e-128">디자이너는 자동으로 테이블 간의 관계를 검색 하 고 관련 개체의 자식 속성을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="bc53e-128">Notice that the designer automatically detects relationships between the tables and creates child properties for related objects.</span></span> <span data-ttu-id="bc53e-129">예를 들어 IntelliSense는 `Customer` `Orders` 해당 고객과 관련 된 모든 주문에 대 한 속성을 개체에 포함 하는 것을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bc53e-129">For example, IntelliSense will show that the `Customer` object has an `Orders` property for all orders related to that customer.</span></span>  
  
3. <span data-ttu-id="bc53e-130">변경 내용을 저장 하 고 디자이너를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="bc53e-130">Save your changes and close the designer.</span></span>  
  
4. <span data-ttu-id="bc53e-131">프로젝트를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="bc53e-131">Save your project.</span></span>  
  
## <a name="to-add-code-to-query-the-database-and-display-the-results"></a><span data-ttu-id="bc53e-132">데이터베이스를 쿼리하고 결과를 표시 하는 코드를 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="bc53e-132">To add code to query the database and display the results</span></span>  
  
1. <span data-ttu-id="bc53e-133">**도구 상자** 에서 <xref:System.Windows.Forms.DataGridView> 컨트롤을 프로젝트의 기본 Windows 폼, Form1에 끌어 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="bc53e-133">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2. <span data-ttu-id="bc53e-134">Form1을 두 번 클릭 하 여 폼의 이벤트에 코드를 추가 `Load` 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc53e-134">Double-click Form1 to add code to the `Load` event of the form.</span></span>  
  
3. <span data-ttu-id="bc53e-135">O/R 디자이너에 테이블을 추가 하면 디자이너에서 <xref:System.Data.Linq.DataContext> 프로젝트에 대 한 개체를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc53e-135">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object for your project.</span></span> <span data-ttu-id="bc53e-136">이 개체에는 각 테이블에 대 한 개별 개체 및 컬렉션 외에도 해당 테이블에 액세스 하는 데 필요한 코드가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc53e-136">This object contains the code that you must have to access those tables, in addition to individual objects and collections for each table.</span></span> <span data-ttu-id="bc53e-137"><xref:System.Data.Linq.DataContext>프로젝트에 대 한 개체는 .dbml 파일의 이름을 기반으로 이름이 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc53e-137">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="bc53e-138">이 프로젝트의 경우 <xref:System.Data.Linq.DataContext> 개체의 이름은 `northwindDataContext` 입니다.</span><span class="sxs-lookup"><span data-stu-id="bc53e-138">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="bc53e-139">코드에서의 인스턴스를 만들고 <xref:System.Data.Linq.DataContext> O/R 디자이너에 지정 된 테이블을 쿼리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc53e-139">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and query the tables specified by the O/R Designer.</span></span>  
  
     <span data-ttu-id="bc53e-140">이벤트에 다음 코드를 추가 `Load` 하 여 데이터 컨텍스트의 속성으로 노출 되는 테이블을 쿼리 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc53e-140">Add the following code to the `Load` event to query the tables that are exposed as properties of your data context.</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form2.vb#3)]  
  
4. <span data-ttu-id="bc53e-141">F5 키를 눌러 프로젝트를 실행 하 고 결과를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc53e-141">Press F5 to run your project and view the results.</span></span>  
  
5. <span data-ttu-id="bc53e-142">다음은 시도해 볼 수 있는 몇 가지 추가 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="bc53e-142">Following are some additional queries that you can try:</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form2.vb#4)]  
    [!code-vb[VbLINQToSQLHowTos#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form2.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="bc53e-143">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bc53e-143">See also</span></span>

- [<span data-ttu-id="bc53e-144">LINQ</span><span class="sxs-lookup"><span data-stu-id="bc53e-144">LINQ</span></span>](index.md)
- [<span data-ttu-id="bc53e-145">쿼리</span><span class="sxs-lookup"><span data-stu-id="bc53e-145">Queries</span></span>](../../../language-reference/queries/index.md)
- [<span data-ttu-id="bc53e-146">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="bc53e-146">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)
- [<span data-ttu-id="bc53e-147">DataContext 메서드(O/R 디자이너)</span><span class="sxs-lookup"><span data-stu-id="bc53e-147">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)
