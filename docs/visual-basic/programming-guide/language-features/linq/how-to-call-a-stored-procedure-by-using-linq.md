---
title: 'How to: Call a Stored Procedure by Using LINQ'
ms.date: 07/20/2015
helpviewer_keywords:
- queries [LINQ in Visual Basic], stored procedure calls
- stored procedures sample [Visual Basic]
- stored procedures [LINQ to SQL]
- queries [LINQ in Visual Basic], how-to topics
ms.assetid: 6436d384-d1e0-40aa-8afd-451007477260
ms.openlocfilehash: f91ccda1842887b3785ce304fd41bdd020a55479
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345031"
---
# <a name="how-to-call-a-stored-procedure-by-using-linq-visual-basic"></a><span data-ttu-id="0084a-102">방법: LINQ를 사용하여 저장 프로시저 호출(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0084a-102">How to: Call a Stored Procedure by Using LINQ (Visual Basic)</span></span>
<span data-ttu-id="0084a-103">Language-Integrated Query (LINQ) makes it easy to access database information, including database objects such as stored procedures.</span><span class="sxs-lookup"><span data-stu-id="0084a-103">Language-Integrated Query (LINQ) makes it easy to access database information, including database objects such as stored procedures.</span></span>  
  
 <span data-ttu-id="0084a-104">The following example shows how to create an application that calls a stored procedure in a SQL Server database.</span><span class="sxs-lookup"><span data-stu-id="0084a-104">The following example shows how to create an application that calls a stored procedure in a SQL Server database.</span></span> <span data-ttu-id="0084a-105">The sample shows how to call two different stored procedures in the database.</span><span class="sxs-lookup"><span data-stu-id="0084a-105">The sample shows how to call two different stored procedures in the database.</span></span> <span data-ttu-id="0084a-106">Each procedure returns the results of a query.</span><span class="sxs-lookup"><span data-stu-id="0084a-106">Each procedure returns the results of a query.</span></span> <span data-ttu-id="0084a-107">One procedure takes input parameters, and the other procedure does not take parameters.</span><span class="sxs-lookup"><span data-stu-id="0084a-107">One procedure takes input parameters, and the other procedure does not take parameters.</span></span>  
  
 <span data-ttu-id="0084a-108">The examples in this topic use the Northwind sample database.</span><span class="sxs-lookup"><span data-stu-id="0084a-108">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="0084a-109">If you do not have this database on your development computer, you can download it from the Microsoft Download Center.</span><span class="sxs-lookup"><span data-stu-id="0084a-109">If you do not have this database on your development computer, you can download it from the Microsoft Download Center.</span></span> <span data-ttu-id="0084a-110">For instructions, see [Downloading Sample Databases](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="0084a-110">For instructions, see [Downloading Sample Databases](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="0084a-111">To create a connection to a database</span><span class="sxs-lookup"><span data-stu-id="0084a-111">To create a connection to a database</span></span>  
  
1. <span data-ttu-id="0084a-112">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span><span class="sxs-lookup"><span data-stu-id="0084a-112">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2. <span data-ttu-id="0084a-113">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span><span class="sxs-lookup"><span data-stu-id="0084a-113">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3. <span data-ttu-id="0084a-114">Specify a valid connection to the Northwind sample database.</span><span class="sxs-lookup"><span data-stu-id="0084a-114">Specify a valid connection to the Northwind sample database.</span></span>  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="0084a-115">To add a project that contains a LINQ to SQL file</span><span class="sxs-lookup"><span data-stu-id="0084a-115">To add a project that contains a LINQ to SQL file</span></span>  
  
1. <span data-ttu-id="0084a-116">Visual Studio의 **파일** 메뉴에서 **새로 만들기**를 가리킨 다음 **프로젝트**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0084a-116">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="0084a-117">Select Visual Basic **Windows Forms Application** as the project type.</span><span class="sxs-lookup"><span data-stu-id="0084a-117">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2. <span data-ttu-id="0084a-118">**프로젝트** 메뉴에서 **새 항목 추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0084a-118">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="0084a-119">Select the **LINQ to SQL Classes** item template.</span><span class="sxs-lookup"><span data-stu-id="0084a-119">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3. <span data-ttu-id="0084a-120">파일 이름을 `northwind.dbml`로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0084a-120">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="0084a-121">**추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0084a-121">Click **Add**.</span></span> <span data-ttu-id="0084a-122">The Object Relational Designer (O/R Designer) is opened for the northwind.dbml file.</span><span class="sxs-lookup"><span data-stu-id="0084a-122">The Object Relational Designer (O/R Designer) is opened for the northwind.dbml file.</span></span>  
  
### <a name="to-add-stored-procedures-to-the-or-designer"></a><span data-ttu-id="0084a-123">To add stored procedures to the O/R Designer</span><span class="sxs-lookup"><span data-stu-id="0084a-123">To add stored procedures to the O/R Designer</span></span>  
  
1. <span data-ttu-id="0084a-124">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span><span class="sxs-lookup"><span data-stu-id="0084a-124">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="0084a-125">Expand the **Stored Procedures** folder.</span><span class="sxs-lookup"><span data-stu-id="0084a-125">Expand the **Stored Procedures** folder.</span></span>  
  
     <span data-ttu-id="0084a-126">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span><span class="sxs-lookup"><span data-stu-id="0084a-126">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2. <span data-ttu-id="0084a-127">Click the **Sales by Year** stored procedure and drag it to the right pane of the designer.</span><span class="sxs-lookup"><span data-stu-id="0084a-127">Click the **Sales by Year** stored procedure and drag it to the right pane of the designer.</span></span> <span data-ttu-id="0084a-128">Click the **Ten Most Expensive Products** stored procedure drag it to the right pane of the designer.</span><span class="sxs-lookup"><span data-stu-id="0084a-128">Click the **Ten Most Expensive Products** stored procedure drag it to the right pane of the designer.</span></span>  
  
3. <span data-ttu-id="0084a-129">Save your changes and close the designer.</span><span class="sxs-lookup"><span data-stu-id="0084a-129">Save your changes and close the designer.</span></span>  
  
4. <span data-ttu-id="0084a-130">프로젝트를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="0084a-130">Save your project.</span></span>  
  
### <a name="to-add-code-to-display-the-results-of-the-stored-procedures"></a><span data-ttu-id="0084a-131">To add code to display the results of the stored procedures</span><span class="sxs-lookup"><span data-stu-id="0084a-131">To add code to display the results of the stored procedures</span></span>  
  
1. <span data-ttu-id="0084a-132">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span><span class="sxs-lookup"><span data-stu-id="0084a-132">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2. <span data-ttu-id="0084a-133">Double-click Form1 to add code to its `Load` event.</span><span class="sxs-lookup"><span data-stu-id="0084a-133">Double-click Form1 to add code to its `Load` event.</span></span>  
  
3. <span data-ttu-id="0084a-134">When you added stored procedures to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object for your project.</span><span class="sxs-lookup"><span data-stu-id="0084a-134">When you added stored procedures to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object for your project.</span></span> <span data-ttu-id="0084a-135">This object contains the code that you must have to access those procedures.</span><span class="sxs-lookup"><span data-stu-id="0084a-135">This object contains the code that you must have to access those procedures.</span></span> <span data-ttu-id="0084a-136">The <xref:System.Data.Linq.DataContext> object for the project is named based on the name of the .dbml file.</span><span class="sxs-lookup"><span data-stu-id="0084a-136">The <xref:System.Data.Linq.DataContext> object for the project is named based on the name of the .dbml file.</span></span> <span data-ttu-id="0084a-137">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span><span class="sxs-lookup"><span data-stu-id="0084a-137">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="0084a-138">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and call the stored procedure methods specified by the O/R Designer.</span><span class="sxs-lookup"><span data-stu-id="0084a-138">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and call the stored procedure methods specified by the O/R Designer.</span></span> <span data-ttu-id="0084a-139">To bind to the <xref:System.Windows.Forms.DataGridView> object, you may have to force the query to execute immediately by calling the <xref:System.Linq.Enumerable.ToList%2A> method on the results of the stored procedure.</span><span class="sxs-lookup"><span data-stu-id="0084a-139">To bind to the <xref:System.Windows.Forms.DataGridView> object, you may have to force the query to execute immediately by calling the <xref:System.Linq.Enumerable.ToList%2A> method on the results of the stored procedure.</span></span>  
  
     <span data-ttu-id="0084a-140">Add the following code to the `Load` event to call either of the stored procedures exposed as methods for your data context.</span><span class="sxs-lookup"><span data-stu-id="0084a-140">Add the following code to the `Load` event to call either of the stored procedures exposed as methods for your data context.</span></span>  
  
     [!code-vb[VbLINQtoSQLHowTos#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form3.vb#1)]  
    [!code-vb[VbLINQtoSQLHowTos#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form3.vb#2)]  
  
4. <span data-ttu-id="0084a-141">Press F5 to run your project and view the results.</span><span class="sxs-lookup"><span data-stu-id="0084a-141">Press F5 to run your project and view the results.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0084a-142">참조</span><span class="sxs-lookup"><span data-stu-id="0084a-142">See also</span></span>

- [<span data-ttu-id="0084a-143">LINQ</span><span class="sxs-lookup"><span data-stu-id="0084a-143">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [<span data-ttu-id="0084a-144">쿼리</span><span class="sxs-lookup"><span data-stu-id="0084a-144">Queries</span></span>](../../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="0084a-145">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="0084a-145">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)
- [<span data-ttu-id="0084a-146">DataContext 메서드(O/R 디자이너)</span><span class="sxs-lookup"><span data-stu-id="0084a-146">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)
- [<span data-ttu-id="0084a-147">방법: 저장 프로시저를 할당하여 업데이트, 삽입 및 삭제 수행(O/R 디자이너)</span><span class="sxs-lookup"><span data-stu-id="0084a-147">How to: Assign stored procedures to perform updates, inserts, and deletes (O/R Designer)</span></span>](/visualstudio/data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer)
