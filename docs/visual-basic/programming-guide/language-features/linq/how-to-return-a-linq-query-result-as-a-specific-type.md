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
ms.openlocfilehash: 1084743b0c50d381375b76a3116ed7c9e6f9d769
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74354209"
---
# <a name="how-to-return-a-linq-query-result-as-a-specific-type-visual-basic"></a><span data-ttu-id="7eb7a-102">방법: LINQ 쿼리 결과를 특정 형식으로 반환(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7eb7a-102">How to: Return a LINQ Query Result as a Specific Type (Visual Basic)</span></span>
<span data-ttu-id="7eb7a-103">Language-Integrated Query (LINQ) makes it easy to access database information and execute queries.</span><span class="sxs-lookup"><span data-stu-id="7eb7a-103">Language-Integrated Query (LINQ) makes it easy to access database information and execute queries.</span></span> <span data-ttu-id="7eb7a-104">By default, LINQ queries return a list of objects as an anonymous type.</span><span class="sxs-lookup"><span data-stu-id="7eb7a-104">By default, LINQ queries return a list of objects as an anonymous type.</span></span> <span data-ttu-id="7eb7a-105">You can also specify that a query return a list of a specific type by using the `Select` clause.</span><span class="sxs-lookup"><span data-stu-id="7eb7a-105">You can also specify that a query return a list of a specific type by using the `Select` clause.</span></span>  
  
 <span data-ttu-id="7eb7a-106">The following example shows how to create a new application that performs queries against a SQL Server database and projects the results as a specific named type.</span><span class="sxs-lookup"><span data-stu-id="7eb7a-106">The following example shows how to create a new application that performs queries against a SQL Server database and projects the results as a specific named type.</span></span> <span data-ttu-id="7eb7a-107">For more information, see [Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md) and [Select Clause](../../../../visual-basic/language-reference/queries/select-clause.md).</span><span class="sxs-lookup"><span data-stu-id="7eb7a-107">For more information, see [Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md) and [Select Clause](../../../../visual-basic/language-reference/queries/select-clause.md).</span></span>  
  
 <span data-ttu-id="7eb7a-108">The examples in this topic use the Northwind sample database.</span><span class="sxs-lookup"><span data-stu-id="7eb7a-108">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="7eb7a-109">If you do not have this database on your development computer, you can download it from the Microsoft Download Center.</span><span class="sxs-lookup"><span data-stu-id="7eb7a-109">If you do not have this database on your development computer, you can download it from the Microsoft Download Center.</span></span> <span data-ttu-id="7eb7a-110">For instructions, see [Downloading Sample Databases](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="7eb7a-110">For instructions, see [Downloading Sample Databases](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="7eb7a-111">To create a connection to a database</span><span class="sxs-lookup"><span data-stu-id="7eb7a-111">To create a connection to a database</span></span>  
  
1. <span data-ttu-id="7eb7a-112">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span><span class="sxs-lookup"><span data-stu-id="7eb7a-112">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2. <span data-ttu-id="7eb7a-113">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span><span class="sxs-lookup"><span data-stu-id="7eb7a-113">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3. <span data-ttu-id="7eb7a-114">Specify a valid connection to the Northwind sample database.</span><span class="sxs-lookup"><span data-stu-id="7eb7a-114">Specify a valid connection to the Northwind sample database.</span></span>  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="7eb7a-115">To add a project that contains a LINQ to SQL file</span><span class="sxs-lookup"><span data-stu-id="7eb7a-115">To add a project that contains a LINQ to SQL file</span></span>  
  
1. <span data-ttu-id="7eb7a-116">Visual Studio의 **파일** 메뉴에서 **새로 만들기**를 가리킨 다음 **프로젝트**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7eb7a-116">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="7eb7a-117">Select Visual Basic **Windows Forms Application** as the project type.</span><span class="sxs-lookup"><span data-stu-id="7eb7a-117">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2. <span data-ttu-id="7eb7a-118">**프로젝트** 메뉴에서 **새 항목 추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7eb7a-118">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="7eb7a-119">Select the **LINQ to SQL Classes** item template.</span><span class="sxs-lookup"><span data-stu-id="7eb7a-119">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3. <span data-ttu-id="7eb7a-120">파일 이름을 `northwind.dbml`로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7eb7a-120">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="7eb7a-121">**추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7eb7a-121">Click **Add**.</span></span> <span data-ttu-id="7eb7a-122">The Object Relational Designer (O/R Designer) is opened for the northwind.dbml file.</span><span class="sxs-lookup"><span data-stu-id="7eb7a-122">The Object Relational Designer (O/R Designer) is opened for the northwind.dbml file.</span></span>  
  
### <a name="to-add-tables-to-query-to-the-or-designer"></a><span data-ttu-id="7eb7a-123">To add tables to query to the O/R Designer</span><span class="sxs-lookup"><span data-stu-id="7eb7a-123">To add tables to query to the O/R Designer</span></span>  
  
1. <span data-ttu-id="7eb7a-124">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span><span class="sxs-lookup"><span data-stu-id="7eb7a-124">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="7eb7a-125">Expand the **Tables** folder.</span><span class="sxs-lookup"><span data-stu-id="7eb7a-125">Expand the **Tables** folder.</span></span>  
  
     <span data-ttu-id="7eb7a-126">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span><span class="sxs-lookup"><span data-stu-id="7eb7a-126">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2. <span data-ttu-id="7eb7a-127">Click the Customers table and drag it to the left pane of the designer.</span><span class="sxs-lookup"><span data-stu-id="7eb7a-127">Click the Customers table and drag it to the left pane of the designer.</span></span>  
  
     <span data-ttu-id="7eb7a-128">The designer creates a new `Customer` object for your project.</span><span class="sxs-lookup"><span data-stu-id="7eb7a-128">The designer creates a new `Customer` object for your project.</span></span> <span data-ttu-id="7eb7a-129">You can project a query result as the `Customer` type or as a type that you create.</span><span class="sxs-lookup"><span data-stu-id="7eb7a-129">You can project a query result as the `Customer` type or as a type that you create.</span></span> <span data-ttu-id="7eb7a-130">This sample will create a new type in a later procedure and project a query result as that type.</span><span class="sxs-lookup"><span data-stu-id="7eb7a-130">This sample will create a new type in a later procedure and project a query result as that type.</span></span>  
  
3. <span data-ttu-id="7eb7a-131">Save your changes and close the designer.</span><span class="sxs-lookup"><span data-stu-id="7eb7a-131">Save your changes and close the designer.</span></span>  
  
4. <span data-ttu-id="7eb7a-132">프로젝트를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="7eb7a-132">Save your project.</span></span>  
  
### <a name="to-add-code-to-query-the-database-and-display-the-results"></a><span data-ttu-id="7eb7a-133">To add code to query the database and display the results</span><span class="sxs-lookup"><span data-stu-id="7eb7a-133">To add code to query the database and display the results</span></span>  
  
1. <span data-ttu-id="7eb7a-134">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span><span class="sxs-lookup"><span data-stu-id="7eb7a-134">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2. <span data-ttu-id="7eb7a-135">Double-click Form1 to modify the Form1 class.</span><span class="sxs-lookup"><span data-stu-id="7eb7a-135">Double-click Form1 to modify the Form1 class.</span></span>  
  
3. <span data-ttu-id="7eb7a-136">After the `End Class` statement of the Form1 class, add the following code to create a `CustomerInfo` type to hold the query results for this sample.</span><span class="sxs-lookup"><span data-stu-id="7eb7a-136">After the `End Class` statement of the Form1 class, add the following code to create a `CustomerInfo` type to hold the query results for this sample.</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form8.vb#16)]  
  
4. <span data-ttu-id="7eb7a-137">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object to your project.</span><span class="sxs-lookup"><span data-stu-id="7eb7a-137">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object to your project.</span></span> <span data-ttu-id="7eb7a-138">This object contains the code that you must have to access those tables, and to access individual objects and collections for each table.</span><span class="sxs-lookup"><span data-stu-id="7eb7a-138">This object contains the code that you must have to access those tables, and to access individual objects and collections for each table.</span></span> <span data-ttu-id="7eb7a-139">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span><span class="sxs-lookup"><span data-stu-id="7eb7a-139">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="7eb7a-140">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span><span class="sxs-lookup"><span data-stu-id="7eb7a-140">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="7eb7a-141">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and query the tables specified by the O/R Designer.</span><span class="sxs-lookup"><span data-stu-id="7eb7a-141">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and query the tables specified by the O/R Designer.</span></span>  
  
     <span data-ttu-id="7eb7a-142">In the `Load` event of the Form1 class, add the following code to query the tables that are exposed as properties of your data context.</span><span class="sxs-lookup"><span data-stu-id="7eb7a-142">In the `Load` event of the Form1 class, add the following code to query the tables that are exposed as properties of your data context.</span></span> <span data-ttu-id="7eb7a-143">The `Select` clause of the query will create a new `CustomerInfo` type instead of an anonymous type for each item of the query result.</span><span class="sxs-lookup"><span data-stu-id="7eb7a-143">The `Select` clause of the query will create a new `CustomerInfo` type instead of an anonymous type for each item of the query result.</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form8.vb#15)]  
  
5. <span data-ttu-id="7eb7a-144">Press F5 to run your project and view the results.</span><span class="sxs-lookup"><span data-stu-id="7eb7a-144">Press F5 to run your project and view the results.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7eb7a-145">참조</span><span class="sxs-lookup"><span data-stu-id="7eb7a-145">See also</span></span>

- [<span data-ttu-id="7eb7a-146">LINQ</span><span class="sxs-lookup"><span data-stu-id="7eb7a-146">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [<span data-ttu-id="7eb7a-147">쿼리</span><span class="sxs-lookup"><span data-stu-id="7eb7a-147">Queries</span></span>](../../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="7eb7a-148">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="7eb7a-148">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)
- [<span data-ttu-id="7eb7a-149">DataContext 메서드(O/R 디자이너)</span><span class="sxs-lookup"><span data-stu-id="7eb7a-149">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)
