---
title: '방법: LINQ를 사용하여 저장 프로시저 호출'
ms.date: 07/20/2015
helpviewer_keywords:
- queries [LINQ in Visual Basic], stored procedure calls
- stored procedures sample [Visual Basic]
- stored procedures [LINQ to SQL]
- queries [LINQ in Visual Basic], how-to topics
ms.assetid: 6436d384-d1e0-40aa-8afd-451007477260
ms.openlocfilehash: b451642a16f36c4f7fd19c853fdfd2282f5bede5
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84405032"
---
# <a name="how-to-call-a-stored-procedure-by-using-linq-visual-basic"></a><span data-ttu-id="e886e-102">방법: LINQ를 사용하여 저장 프로시저 호출(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e886e-102">How to: Call a Stored Procedure by Using LINQ (Visual Basic)</span></span>
<span data-ttu-id="e886e-103">LINQ (통합 언어 쿼리)를 사용 하면 저장 프로시저와 같은 데이터베이스 개체를 비롯 한 데이터베이스 정보에 쉽게 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e886e-103">Language-Integrated Query (LINQ) makes it easy to access database information, including database objects such as stored procedures.</span></span>  
  
 <span data-ttu-id="e886e-104">다음 예에서는 SQL Server 데이터베이스의 저장 프로시저를 호출 하는 응용 프로그램을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e886e-104">The following example shows how to create an application that calls a stored procedure in a SQL Server database.</span></span> <span data-ttu-id="e886e-105">이 샘플에서는 데이터베이스의 서로 다른 두 개의 저장 프로시저를 호출 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e886e-105">The sample shows how to call two different stored procedures in the database.</span></span> <span data-ttu-id="e886e-106">각 프로시저는 쿼리 결과를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="e886e-106">Each procedure returns the results of a query.</span></span> <span data-ttu-id="e886e-107">한 프로시저는 입력 매개 변수를 사용 하 고 다른 프로시저는 매개 변수를 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e886e-107">One procedure takes input parameters, and the other procedure does not take parameters.</span></span>  
  
 <span data-ttu-id="e886e-108">이 항목의 예제에서는 Northwind 샘플 데이터베이스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e886e-108">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="e886e-109">이 데이터베이스가 개발 컴퓨터에 없는 경우 Microsoft 다운로드 센터에서 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e886e-109">If you do not have this database on your development computer, you can download it from the Microsoft Download Center.</span></span> <span data-ttu-id="e886e-110">지침은 [샘플 데이터베이스 다운로드](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e886e-110">For instructions, see [Downloading Sample Databases](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="e886e-111">데이터베이스에 대 한 연결을 만들려면</span><span class="sxs-lookup"><span data-stu-id="e886e-111">To create a connection to a database</span></span>  
  
1. <span data-ttu-id="e886e-112">Visual Studio의 **Server Explorer** / **Database Explorer** **Server Explorer** / **보기** 메뉴에서 서버 탐색기**데이터베이스 탐색기** 를 클릭 하 여 서버 탐색기 데이터베이스 탐색기를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="e886e-112">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2. <span data-ttu-id="e886e-113">**서버 탐색기**데이터베이스 탐색기에서 **데이터 연결** 을 마우스 오른쪽 단추로 클릭 한 / **Database Explorer** 다음 **연결 추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e886e-113">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3. <span data-ttu-id="e886e-114">Northwind 샘플 데이터베이스에 대 한 올바른 연결을 지정 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e886e-114">Specify a valid connection to the Northwind sample database.</span></span>  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="e886e-115">LINQ to SQL 파일을 포함 하는 프로젝트를 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="e886e-115">To add a project that contains a LINQ to SQL file</span></span>  
  
1. <span data-ttu-id="e886e-116">Visual Studio의 **파일** 메뉴에서 **새로 만들기** 를 가리킨 다음 **프로젝트**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e886e-116">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="e886e-117">Visual Basic **Windows Forms 응용 프로그램** 을 프로젝트 형식으로 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e886e-117">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2. <span data-ttu-id="e886e-118">**프로젝트** 메뉴에서 **새 항목 추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e886e-118">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="e886e-119">**LINQ to SQL 클래스** 항목 템플릿을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e886e-119">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3. <span data-ttu-id="e886e-120">파일 이름을 `northwind.dbml`로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e886e-120">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="e886e-121">**추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e886e-121">Click **Add**.</span></span> <span data-ttu-id="e886e-122">Northwind .dbml 파일에 대해 개체 관계형 디자이너 (O/R 디자이너)가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="e886e-122">The Object Relational Designer (O/R Designer) is opened for the northwind.dbml file.</span></span>  
  
### <a name="to-add-stored-procedures-to-the-or-designer"></a><span data-ttu-id="e886e-123">O/R 디자이너에 저장 프로시저를 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="e886e-123">To add stored procedures to the O/R Designer</span></span>  
  
1. <span data-ttu-id="e886e-124">**서버 탐색기** / **데이터베이스 탐색기**에서 Northwind 데이터베이스에 대 한 연결을 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="e886e-124">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="e886e-125">**저장 프로시저** 폴더를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="e886e-125">Expand the **Stored Procedures** folder.</span></span>  
  
     <span data-ttu-id="e886e-126">O/R 디자이너를 닫은 경우 앞에서 추가한 각각의 .dbml 파일을 두 번 클릭 하 여 다시 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e886e-126">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2. <span data-ttu-id="e886e-127">**연도별 매출** 저장 프로시저를 클릭 하 고 디자이너의 오른쪽 창으로 끌어 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="e886e-127">Click the **Sales by Year** stored procedure and drag it to the right pane of the designer.</span></span> <span data-ttu-id="e886e-128">**가장 비싼 10 개 제품** 저장 프로시저를 클릭 하 여 디자이너의 오른쪽 창으로 끌어 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="e886e-128">Click the **Ten Most Expensive Products** stored procedure drag it to the right pane of the designer.</span></span>  
  
3. <span data-ttu-id="e886e-129">변경 내용을 저장 하 고 디자이너를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="e886e-129">Save your changes and close the designer.</span></span>  
  
4. <span data-ttu-id="e886e-130">프로젝트를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="e886e-130">Save your project.</span></span>  
  
### <a name="to-add-code-to-display-the-results-of-the-stored-procedures"></a><span data-ttu-id="e886e-131">저장 프로시저의 결과를 표시 하는 코드를 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="e886e-131">To add code to display the results of the stored procedures</span></span>  
  
1. <span data-ttu-id="e886e-132">**도구 상자**에서 <xref:System.Windows.Forms.DataGridView> 컨트롤을 프로젝트의 기본 Windows 폼, Form1에 끌어 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="e886e-132">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2. <span data-ttu-id="e886e-133">Form1을 두 번 클릭 하 여 이벤트에 코드를 추가 `Load` 합니다.</span><span class="sxs-lookup"><span data-stu-id="e886e-133">Double-click Form1 to add code to its `Load` event.</span></span>  
  
3. <span data-ttu-id="e886e-134">O/R 디자이너에 저장 프로시저를 추가 하면 디자이너에서 <xref:System.Data.Linq.DataContext> 프로젝트에 대 한 개체를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="e886e-134">When you added stored procedures to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object for your project.</span></span> <span data-ttu-id="e886e-135">이 개체에는 해당 프로시저에 액세스 하는 데 필요한 코드가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e886e-135">This object contains the code that you must have to access those procedures.</span></span> <span data-ttu-id="e886e-136"><xref:System.Data.Linq.DataContext>프로젝트에 대 한 개체는 .dbml 파일의 이름을 기반으로 이름이 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e886e-136">The <xref:System.Data.Linq.DataContext> object for the project is named based on the name of the .dbml file.</span></span> <span data-ttu-id="e886e-137">이 프로젝트의 경우 <xref:System.Data.Linq.DataContext> 개체의 이름은 `northwindDataContext` 입니다.</span><span class="sxs-lookup"><span data-stu-id="e886e-137">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="e886e-138">코드에서의 인스턴스를 만들고 <xref:System.Data.Linq.DataContext> O/R 디자이너에 지정 된 저장 프로시저 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e886e-138">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and call the stored procedure methods specified by the O/R Designer.</span></span> <span data-ttu-id="e886e-139">개체에 바인딩하려면 <xref:System.Windows.Forms.DataGridView> <xref:System.Linq.Enumerable.ToList%2A> 저장 프로시저의 결과에 대해 메서드를 호출 하 여 쿼리를 즉시 실행 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e886e-139">To bind to the <xref:System.Windows.Forms.DataGridView> object, you may have to force the query to execute immediately by calling the <xref:System.Linq.Enumerable.ToList%2A> method on the results of the stored procedure.</span></span>  
  
     <span data-ttu-id="e886e-140">이벤트에 다음 코드를 추가 `Load` 하 여 데이터 컨텍스트에 대 한 메서드로 노출 되는 저장 프로시저 중 하나를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="e886e-140">Add the following code to the `Load` event to call either of the stored procedures exposed as methods for your data context.</span></span>  
  
     [!code-vb[VbLINQtoSQLHowTos#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form3.vb#1)]  
    [!code-vb[VbLINQtoSQLHowTos#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form3.vb#2)]  
  
4. <span data-ttu-id="e886e-141">F5 키를 눌러 프로젝트를 실행 하 고 결과를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e886e-141">Press F5 to run your project and view the results.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e886e-142">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e886e-142">See also</span></span>

- [<span data-ttu-id="e886e-143">LINQ</span><span class="sxs-lookup"><span data-stu-id="e886e-143">LINQ</span></span>](index.md)
- [<span data-ttu-id="e886e-144">쿼리</span><span class="sxs-lookup"><span data-stu-id="e886e-144">Queries</span></span>](../../../language-reference/queries/index.md)
- [<span data-ttu-id="e886e-145">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="e886e-145">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)
- [<span data-ttu-id="e886e-146">DataContext 메서드 (O/R 디자이너)</span><span class="sxs-lookup"><span data-stu-id="e886e-146">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)
- [<span data-ttu-id="e886e-147">방법: 저장 프로시저를 할당 하 여 업데이트, 삽입 및 삭제 수행 (O/R 디자이너)</span><span class="sxs-lookup"><span data-stu-id="e886e-147">How to: Assign stored procedures to perform updates, inserts, and deletes (O/R Designer)</span></span>](/visualstudio/data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer)
