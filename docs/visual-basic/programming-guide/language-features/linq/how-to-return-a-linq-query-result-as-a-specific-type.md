---
title: '방법: LINQ 쿼리 결과를 특정 형식으로 반환'
ms.date: 07/20/2015
helpviewer_keywords:
- queries [LINQ in Visual Basic], specific type returned
- projection [LINQ in Visual Basic]
- anonymous types [Visual Basic]
- querying databases [LINQ]
- queries [LINQ in Visual Basic], how-to topics
- query samples [Visual Basic]
ms.assetid: 621bb10a-e5d7-44fb-a025-317964b19d92
ms.openlocfilehash: 249c3eebaeec3d09a297fead07ab056caff1b618
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "91071809"
---
# <a name="how-to-return-a-linq-query-result-as-a-specific-type-visual-basic"></a><span data-ttu-id="fd946-102">방법: LINQ 쿼리 결과를 특정 형식으로 반환(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fd946-102">How to: Return a LINQ Query Result as a Specific Type (Visual Basic)</span></span>

<span data-ttu-id="fd946-103">LINQ (통합 언어 쿼리)를 사용 하면 데이터베이스 정보에 쉽게 액세스 하 고 쿼리를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd946-103">Language-Integrated Query (LINQ) makes it easy to access database information and execute queries.</span></span> <span data-ttu-id="fd946-104">기본적으로 LINQ 쿼리는 개체 목록을 익명 형식으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd946-104">By default, LINQ queries return a list of objects as an anonymous type.</span></span> <span data-ttu-id="fd946-105">또한 절을 사용 하 여 쿼리가 특정 형식의 목록을 반환 하도록 지정할 수 있습니다 `Select` .</span><span class="sxs-lookup"><span data-stu-id="fd946-105">You can also specify that a query return a list of a specific type by using the `Select` clause.</span></span>  
  
 <span data-ttu-id="fd946-106">다음 예에서는 SQL Server 데이터베이스에 대해 쿼리를 수행 하 고 결과를 특정 명명 된 형식으로 프로젝션 하는 새 응용 프로그램을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fd946-106">The following example shows how to create a new application that performs queries against a SQL Server database and projects the results as a specific named type.</span></span> <span data-ttu-id="fd946-107">자세한 내용은 [익명 형식](../objects-and-classes/anonymous-types.md) 및 [Select 절](../../../language-reference/queries/select-clause.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fd946-107">For more information, see [Anonymous Types](../objects-and-classes/anonymous-types.md) and [Select Clause](../../../language-reference/queries/select-clause.md).</span></span>  
  
 <span data-ttu-id="fd946-108">이 항목의 예제에서는 Northwind 샘플 데이터베이스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd946-108">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="fd946-109">이 데이터베이스가 개발 컴퓨터에 없는 경우 Microsoft 다운로드 센터에서 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd946-109">If you do not have this database on your development computer, you can download it from the Microsoft Download Center.</span></span> <span data-ttu-id="fd946-110">지침은 [샘플 데이터베이스 다운로드](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fd946-110">For instructions, see [Downloading Sample Databases](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="fd946-111">데이터베이스에 대 한 연결을 만들려면</span><span class="sxs-lookup"><span data-stu-id="fd946-111">To create a connection to a database</span></span>  
  
1. <span data-ttu-id="fd946-112">Visual Studio의 **Server Explorer** / **Database Explorer** **Server Explorer** / **보기** 메뉴에서 서버 탐색기**데이터베이스 탐색기** 를 클릭 하 여 서버 탐색기 데이터베이스 탐색기를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="fd946-112">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2. <span data-ttu-id="fd946-113">**서버 탐색기**데이터베이스 탐색기에서 **데이터 연결** 을 마우스 오른쪽 단추로 클릭 한 / **Database Explorer** 다음 **연결 추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd946-113">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3. <span data-ttu-id="fd946-114">Northwind 샘플 데이터베이스에 대 한 올바른 연결을 지정 하십시오.</span><span class="sxs-lookup"><span data-stu-id="fd946-114">Specify a valid connection to the Northwind sample database.</span></span>  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="fd946-115">LINQ to SQL 파일을 포함 하는 프로젝트를 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="fd946-115">To add a project that contains a LINQ to SQL file</span></span>  
  
1. <span data-ttu-id="fd946-116">Visual Studio의 **파일** 메뉴에서 **새로 만들기**를 가리킨 다음 **프로젝트**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fd946-116">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="fd946-117">Visual Basic **Windows Forms 응용 프로그램** 을 프로젝트 형식으로 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd946-117">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2. <span data-ttu-id="fd946-118">**프로젝트** 메뉴에서 **새 항목 추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fd946-118">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="fd946-119">**LINQ to SQL 클래스** 항목 템플릿을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd946-119">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3. <span data-ttu-id="fd946-120">파일 이름을 `northwind.dbml`로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fd946-120">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="fd946-121">**추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fd946-121">Click **Add**.</span></span> <span data-ttu-id="fd946-122">Northwind .dbml 파일에 대해 개체 관계형 디자이너 (O/R 디자이너)가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="fd946-122">The Object Relational Designer (O/R Designer) is opened for the northwind.dbml file.</span></span>  
  
### <a name="to-add-tables-to-query-to-the-or-designer"></a><span data-ttu-id="fd946-123">O/R 디자이너에 쿼리할 테이블을 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="fd946-123">To add tables to query to the O/R Designer</span></span>  
  
1. <span data-ttu-id="fd946-124">**서버 탐색기** / **데이터베이스 탐색기**에서 Northwind 데이터베이스에 대 한 연결을 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd946-124">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="fd946-125">**테이블** 폴더를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="fd946-125">Expand the **Tables** folder.</span></span>  
  
     <span data-ttu-id="fd946-126">O/R 디자이너를 닫은 경우 앞에서 추가한 각각의 .dbml 파일을 두 번 클릭 하 여 다시 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd946-126">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2. <span data-ttu-id="fd946-127">Customers 테이블을 클릭 하 고 디자이너의 왼쪽 창으로 끌어 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="fd946-127">Click the Customers table and drag it to the left pane of the designer.</span></span>  
  
     <span data-ttu-id="fd946-128">디자이너에서 `Customer` 프로젝트에 대 한 새 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fd946-128">The designer creates a new `Customer` object for your project.</span></span> <span data-ttu-id="fd946-129">쿼리 결과를 `Customer` 형식 또는 사용자가 만든 형식으로 프로젝션 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd946-129">You can project a query result as the `Customer` type or as a type that you create.</span></span> <span data-ttu-id="fd946-130">이 샘플에서는 이후 절차에서 새 형식을 만들고 쿼리 결과를 해당 형식으로 프로젝션 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd946-130">This sample will create a new type in a later procedure and project a query result as that type.</span></span>  
  
3. <span data-ttu-id="fd946-131">변경 내용을 저장 하 고 디자이너를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="fd946-131">Save your changes and close the designer.</span></span>  
  
4. <span data-ttu-id="fd946-132">프로젝트를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="fd946-132">Save your project.</span></span>  
  
### <a name="to-add-code-to-query-the-database-and-display-the-results"></a><span data-ttu-id="fd946-133">데이터베이스를 쿼리하고 결과를 표시 하는 코드를 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="fd946-133">To add code to query the database and display the results</span></span>  
  
1. <span data-ttu-id="fd946-134">**도구 상자**에서 <xref:System.Windows.Forms.DataGridView> 컨트롤을 프로젝트의 기본 Windows 폼, Form1에 끌어 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="fd946-134">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2. <span data-ttu-id="fd946-135">Form1 클래스를 수정 하려면 Form1을 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd946-135">Double-click Form1 to modify the Form1 class.</span></span>  
  
3. <span data-ttu-id="fd946-136">`End Class`Form1 클래스의 문 뒤에 다음 코드를 추가 하 여 `CustomerInfo` 이 샘플에 대 한 쿼리 결과를 저장 하는 형식을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fd946-136">After the `End Class` statement of the Form1 class, add the following code to create a `CustomerInfo` type to hold the query results for this sample.</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form8.vb#16)]  
  
4. <span data-ttu-id="fd946-137">O/R 디자이너에 테이블을 추가 하면 디자이너에서 <xref:System.Data.Linq.DataContext> 개체를 프로젝트에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd946-137">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object to your project.</span></span> <span data-ttu-id="fd946-138">이 개체에는 해당 테이블에 액세스 하 고 각 테이블에 대 한 개별 개체 및 컬렉션에 액세스 하는 데 필요한 코드가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd946-138">This object contains the code that you must have to access those tables, and to access individual objects and collections for each table.</span></span> <span data-ttu-id="fd946-139"><xref:System.Data.Linq.DataContext>프로젝트에 대 한 개체는 .dbml 파일의 이름을 기반으로 이름이 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd946-139">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="fd946-140">이 프로젝트의 경우 <xref:System.Data.Linq.DataContext> 개체의 이름은 `northwindDataContext` 입니다.</span><span class="sxs-lookup"><span data-stu-id="fd946-140">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="fd946-141">코드에서의 인스턴스를 만들고 <xref:System.Data.Linq.DataContext> O/R 디자이너에 지정 된 테이블을 쿼리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd946-141">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and query the tables specified by the O/R Designer.</span></span>  
  
     <span data-ttu-id="fd946-142">`Load`Form1 클래스의 경우 다음 코드를 추가 하 여 데이터 컨텍스트의 속성으로 노출 되는 테이블을 쿼리 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd946-142">In the `Load` event of the Form1 class, add the following code to query the tables that are exposed as properties of your data context.</span></span> <span data-ttu-id="fd946-143">쿼리의 `Select` 절은 `CustomerInfo` 쿼리 결과의 각 항목에 대해 익명 형식 대신 새 형식을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fd946-143">The `Select` clause of the query will create a new `CustomerInfo` type instead of an anonymous type for each item of the query result.</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form8.vb#15)]  
  
5. <span data-ttu-id="fd946-144">F5 키를 눌러 프로젝트를 실행 하 고 결과를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd946-144">Press F5 to run your project and view the results.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd946-145">참조</span><span class="sxs-lookup"><span data-stu-id="fd946-145">See also</span></span>

- [<span data-ttu-id="fd946-146">LINQ</span><span class="sxs-lookup"><span data-stu-id="fd946-146">LINQ</span></span>](index.md)
- [<span data-ttu-id="fd946-147">쿼리</span><span class="sxs-lookup"><span data-stu-id="fd946-147">Queries</span></span>](../../../language-reference/queries/index.md)
- [<span data-ttu-id="fd946-148">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="fd946-148">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)
- [<span data-ttu-id="fd946-149">DataContext 메서드(O/R 디자이너)</span><span class="sxs-lookup"><span data-stu-id="fd946-149">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)
