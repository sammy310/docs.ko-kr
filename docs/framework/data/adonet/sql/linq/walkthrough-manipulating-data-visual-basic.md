---
title: '연습: 데이터 조작(Visual Basic)'
ms.date: 03/30/2017
dev_langs:
- vb
ms.assetid: 1f6a54f6-ec33-452a-a37d-48122207bf14
ms.openlocfilehash: 7acce3f8483fab3c2978de7cbd1b9d875900f1d3
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/07/2019
ms.locfileid: "72003390"
---
# <a name="walkthrough-manipulating-data-visual-basic"></a><span data-ttu-id="a77ef-102">연습: 데이터 조작(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a77ef-102">Walkthrough: Manipulating Data (Visual Basic)</span></span>
<span data-ttu-id="a77ef-103">이 연습에서는 데이터베이스의 데이터를 추가, 수정 및 삭제하기 위한 기본 엔드투엔드 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 시나리오를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a77ef-103">This walkthrough provides a fundamental end-to-end [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] scenario for adding, modifying, and deleting data in a database.</span></span> <span data-ttu-id="a77ef-104">Northwind 샘플 데이터베이스의 복사본을 사용하여 고객을 추가하고, 고객의 이름을 변경하고, 주문을 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="a77ef-104">You will use a copy of the sample Northwind database to add a customer, change the name of a customer, and delete an order.</span></span>  
  
 [!INCLUDE[note_settings_general](../../../../../../includes/note-settings-general-md.md)]  
  
 <span data-ttu-id="a77ef-105">이 연습은 Visual Basic 개발 설정을 사용하여 작성했습니다.</span><span class="sxs-lookup"><span data-stu-id="a77ef-105">This walkthrough was written by using Visual Basic Development Settings.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a77ef-106">사전 요구 사항</span><span class="sxs-lookup"><span data-stu-id="a77ef-106">Prerequisites</span></span>  
 <span data-ttu-id="a77ef-107">이 연습에서는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="a77ef-107">This walkthrough requires the following:</span></span>  
  
- <span data-ttu-id="a77ef-108">이 연습에서는 전용 폴더("c:\linqtest2")를 사용하여 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="a77ef-108">This walkthrough uses a dedicated folder ("c:\linqtest2") to hold files.</span></span> <span data-ttu-id="a77ef-109">연습을 시작하기 전에 먼저 이 폴더를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a77ef-109">Create this folder before you begin the walkthrough.</span></span>  
  
- <span data-ttu-id="a77ef-110">Northwind 샘플 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="a77ef-110">The Northwind sample database.</span></span>  
  
     <span data-ttu-id="a77ef-111">이 데이터베이스가 개발 컴퓨터에 없는 경우 Microsoft 다운로드 사이트에서 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a77ef-111">If you do not have this database on your development computer, you can download it from the Microsoft download site.</span></span> <span data-ttu-id="a77ef-112">지침은 [샘플 데이터베이스 다운로드](downloading-sample-databases.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a77ef-112">For instructions, see [Downloading Sample Databases](downloading-sample-databases.md).</span></span> <span data-ttu-id="a77ef-113">이 데이터베이스를 다운로드한 후 northwnd.mdf 파일을 c:\linqtest2 폴더에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="a77ef-113">After you have downloaded the database, copy the northwnd.mdf file to the c:\linqtest2 folder.</span></span>  
  
- <span data-ttu-id="a77ef-114">Northwind 데이터베이스에서 생성된 Visual Basic 코드 파일</span><span class="sxs-lookup"><span data-stu-id="a77ef-114">A Visual Basic code file generated from the Northwind database.</span></span>  
  
     <span data-ttu-id="a77ef-115">개체 관계형 디자이너 또는 SQLMetal 도구를 사용 하 여이 파일을 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a77ef-115">You can generate this file by using either the Object Relational Designer or the SQLMetal tool.</span></span> <span data-ttu-id="a77ef-116">이 연습은 다음 명령줄을 사용하여 SQLMetal 도구를 통해 작성했습니다.</span><span class="sxs-lookup"><span data-stu-id="a77ef-116">This walkthrough was written by using the SQLMetal tool with the following command line:</span></span>  
  
     <span data-ttu-id="a77ef-117">**sqlmetal /code:"c:\linqtest2\northwind.vb" /language:vb "C:\linqtest2\northwnd.mdf" /pluralize**</span><span class="sxs-lookup"><span data-stu-id="a77ef-117">**sqlmetal /code:"c:\linqtest2\northwind.vb" /language:vb "C:\linqtest2\northwnd.mdf" /pluralize**</span></span>  
  
     <span data-ttu-id="a77ef-118">자세한 내용은 [SqlMetal.exe(코드 생성 도구)](../../../../tools/sqlmetal-exe-code-generation-tool.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a77ef-118">For more information, see [SqlMetal.exe (Code Generation Tool)](../../../../tools/sqlmetal-exe-code-generation-tool.md).</span></span>  
  
## <a name="overview"></a><span data-ttu-id="a77ef-119">개요</span><span class="sxs-lookup"><span data-stu-id="a77ef-119">Overview</span></span>  
 <span data-ttu-id="a77ef-120">이 연습은 다음과 같은 여섯 가지 주요 작업으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="a77ef-120">This walkthrough consists of six main tasks:</span></span>  
  
- <span data-ttu-id="a77ef-121">Visual Studio에서 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 솔루션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a77ef-121">Creating the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] solution in Visual Studio.</span></span>  
  
- <span data-ttu-id="a77ef-122">데이터베이스 코드 파일을 프로젝트에 추가</span><span class="sxs-lookup"><span data-stu-id="a77ef-122">Adding the database code file to the project.</span></span>  
  
- <span data-ttu-id="a77ef-123">새 Customer 개체 만들기</span><span class="sxs-lookup"><span data-stu-id="a77ef-123">Creating a new customer object.</span></span>  
  
- <span data-ttu-id="a77ef-124">고객의 연락처 이름 수정</span><span class="sxs-lookup"><span data-stu-id="a77ef-124">Modifying the contact name of a customer.</span></span>  
  
- <span data-ttu-id="a77ef-125">주문 삭제</span><span class="sxs-lookup"><span data-stu-id="a77ef-125">Deleting an order.</span></span>  
  
- <span data-ttu-id="a77ef-126">이러한 변경 내용을 Northwind 데이터베이스로 전송</span><span class="sxs-lookup"><span data-stu-id="a77ef-126">Submitting these changes to the Northwind database.</span></span>  
  
## <a name="creating-a-linq-to-sql-solution"></a><span data-ttu-id="a77ef-127">LINQ to SQL 솔루션 만들기</span><span class="sxs-lookup"><span data-stu-id="a77ef-127">Creating a LINQ to SQL Solution</span></span>  
 <span data-ttu-id="a77ef-128">이 첫 번째 작업에서는 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 프로젝트를 빌드하고 실행 하는 데 필요한 참조를 포함 하는 Visual Studio 솔루션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a77ef-128">In this first task, you create a Visual Studio solution that contains the necessary references to build and run a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] project.</span></span>  
  
#### <a name="to-create-a-linq-to-sql-solution"></a><span data-ttu-id="a77ef-129">LINQ to SQL 솔루션을 만들려면</span><span class="sxs-lookup"><span data-stu-id="a77ef-129">To create a LINQ to SQL solution</span></span>  
  
1. <span data-ttu-id="a77ef-130">Visual Studio의 **파일** 메뉴에서 **새 프로젝트**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a77ef-130">On the Visual Studio **File** menu, click **New Project**.</span></span>  
  
2. <span data-ttu-id="a77ef-131">**새 프로젝트** 대화 상자의 **프로젝트 형식** 창에서 **Visual Basic**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a77ef-131">In the **Project types** pane in the **New Project** dialog box, click **Visual Basic**.</span></span>  
  
3. <span data-ttu-id="a77ef-132">**템플릿** 창에서 **콘솔 애플리케이션**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a77ef-132">In the **Templates** pane, click **Console Application**.</span></span>  
  
4. <span data-ttu-id="a77ef-133">**이름** 상자에 **linqdatamanipulationapp 입력**을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="a77ef-133">In the **Name** box, type **LinqDataManipulationApp**.</span></span>  
  
5. <span data-ttu-id="a77ef-134">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a77ef-134">Click **OK**.</span></span>  
  
## <a name="adding-linq-references-and-directives"></a><span data-ttu-id="a77ef-135">LINQ 참조 및 지시문 추가</span><span class="sxs-lookup"><span data-stu-id="a77ef-135">Adding LINQ References and Directives</span></span>  
 <span data-ttu-id="a77ef-136">이 연습에서는 프로젝트에 기본적으로 설치되어 있지 않을 수 있는 어셈블리를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a77ef-136">This walkthrough uses assemblies that might not be installed by default in your project.</span></span> <span data-ttu-id="a77ef-137">@No__t-0이 프로젝트에 참조로 나열 되어 있지 않으면 ( **솔루션 탐색기** 의 **모든 파일 표시** 를 클릭 하 고 **참조** 노드를 확장) 다음 단계에 설명 된 대로 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="a77ef-137">If `System.Data.Linq` is not listed as a reference in your project (click **Show All Files** in **Solution Explorer** and expand the **References** node), add it, as explained in the following steps.</span></span>  
  
#### <a name="to-add-systemdatalinq"></a><span data-ttu-id="a77ef-138">System.Data.Linq를 추가하려면</span><span class="sxs-lookup"><span data-stu-id="a77ef-138">To add System.Data.Linq</span></span>  
  
1. <span data-ttu-id="a77ef-139">**솔루션 탐색기**에서 **참조**를 마우스 오른쪽 단추로 클릭 한 다음 **참조 추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a77ef-139">In **Solution Explorer**, right-click **References**, and then click **Add Reference**.</span></span>  
  
2. <span data-ttu-id="a77ef-140">**참조 추가** 대화 상자에서 **.net**을 클릭 하 고 system.xml 어셈블리를 클릭 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a77ef-140">In the **Add Reference** dialog box, click **.NET**, click the System.Data.Linq assembly, and then click **OK**.</span></span>  
  
     <span data-ttu-id="a77ef-141">어셈블리가 프로젝트에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="a77ef-141">The assembly is added to the project.</span></span>  
  
3. <span data-ttu-id="a77ef-142">코드 편집기에서 **Module1**위에 다음 지시문을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="a77ef-142">In the code editor, add the following directives above **Module1**:</span></span>  
  
     [!code-vb[DLinqWalk3VB#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk3VB/vb/Module1.vb#1)]  
  
## <a name="adding-the-northwind-code-file-to-the-project"></a><span data-ttu-id="a77ef-143">Northwind 코드 파일을 프로젝트에 추가</span><span class="sxs-lookup"><span data-stu-id="a77ef-143">Adding the Northwind Code File to the Project</span></span>  
 <span data-ttu-id="a77ef-144">이 단계에서는 SQLMetal 도구를 사용하여 Northwind 샘플 데이터베이스에서 코드 파일을 생성했다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="a77ef-144">These steps assume that you have used the SQLMetal tool to generate a code file from the Northwind sample database.</span></span> <span data-ttu-id="a77ef-145">자세한 내용은 이 연습 앞부분의 사전 요구 사항 단원을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a77ef-145">For more information, see the Prerequisites section earlier in this walkthrough.</span></span>  
  
#### <a name="to-add-the-northwind-code-file-to-the-project"></a><span data-ttu-id="a77ef-146">northwind 코드 파일을 프로젝트에 추가하려면</span><span class="sxs-lookup"><span data-stu-id="a77ef-146">To add the northwind code file to the project</span></span>  
  
1. <span data-ttu-id="a77ef-147">**프로젝트** 메뉴에서 **기존 항목 추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a77ef-147">On the **Project** menu, click **Add Existing Item**.</span></span>  
  
2. <span data-ttu-id="a77ef-148">**기존 항목 추가** 대화 상자에서 c:\linqtest2\northwind.vb으로 이동한 다음 **추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a77ef-148">In the **Add Existing Item** dialog box, navigate to c:\linqtest2\northwind.vb, and then click **Add**.</span></span>  
  
     <span data-ttu-id="a77ef-149">northwind.vb 파일이 프로젝트에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="a77ef-149">The northwind.vb file is added to the project.</span></span>  
  
## <a name="setting-up-the-database-connection"></a><span data-ttu-id="a77ef-150">데이터베이스 연결 설정</span><span class="sxs-lookup"><span data-stu-id="a77ef-150">Setting Up the Database Connection</span></span>  
 <span data-ttu-id="a77ef-151">먼저 데이터베이스에 대한 연결을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="a77ef-151">First, test your connection to the database.</span></span> <span data-ttu-id="a77ef-152">특히 데이터베이스 이름 Northwnd에 i 문자가 없는 것을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a77ef-152">Note especially that the name of the database, Northwnd, has no i character.</span></span> <span data-ttu-id="a77ef-153">다음 단계에서 오류를 생성하는 경우 northwind.vb 파일을 검토하여 Northwind partial 클래스의 맞춤법을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a77ef-153">If you generate errors in the next steps, review the northwind.vb file to determine how the Northwind partial class is spelled.</span></span>  
  
#### <a name="to-set-up-and-test-the-database-connection"></a><span data-ttu-id="a77ef-154">데이터베이스 연결을 설정하고 테스트하려면</span><span class="sxs-lookup"><span data-stu-id="a77ef-154">To set up and test the database connection</span></span>  
  
1. <span data-ttu-id="a77ef-155">`Sub Main`에 다음 코드를 입력하거나 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="a77ef-155">Type or paste the following code into `Sub Main`:</span></span>  
  
     [!code-vb[DLinqWalk3VB#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk3VB/vb/Module1.vb#2)]  
  
2. <span data-ttu-id="a77ef-156">이때 F5 키를 눌러 애플리케이션을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="a77ef-156">Press F5 to test the application at this point.</span></span>  
  
     <span data-ttu-id="a77ef-157">**콘솔** 창이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="a77ef-157">A **Console** window opens.</span></span>  
  
     <span data-ttu-id="a77ef-158">**콘솔** 창에서 enter 키를 누르거나 Visual Studio **디버그** 메뉴에서 **디버깅 중지** 를 클릭 하 여 응용 프로그램을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="a77ef-158">Close the application by pressing Enter in the **Console** window, or by clicking **Stop Debugging** on the Visual Studio **Debug** menu.</span></span>  
  
## <a name="creating-a-new-entity"></a><span data-ttu-id="a77ef-159">새 엔터티 만들기</span><span class="sxs-lookup"><span data-stu-id="a77ef-159">Creating a New Entity</span></span>  
 <span data-ttu-id="a77ef-160">새 엔터티를 만드는 과정은 단순합니다.</span><span class="sxs-lookup"><span data-stu-id="a77ef-160">Creating a new entity is straightforward.</span></span> <span data-ttu-id="a77ef-161">`Customer` 키워드를 사용하여 개체(예: `New`)를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a77ef-161">You can create objects (such as `Customer`) by using the `New` keyword.</span></span>  
  
 <span data-ttu-id="a77ef-162">이 단원과 다음 단원에서는 로컬 캐시만 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="a77ef-162">In this and the following sections, you are making changes only to the local cache.</span></span> <span data-ttu-id="a77ef-163">이 연습의 끝에서 <xref:System.Data.Linq.DataContext.SubmitChanges%2A>를 호출할 때까지 변경 내용이 데이터베이스로 전송되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a77ef-163">No changes are sent to the database until you call <xref:System.Data.Linq.DataContext.SubmitChanges%2A> toward the end of this walkthrough.</span></span>  
  
#### <a name="to-add-a-new-customer-entity-object"></a><span data-ttu-id="a77ef-164">새 Customer 엔터티 개체를 추가하려면</span><span class="sxs-lookup"><span data-stu-id="a77ef-164">To add a new Customer entity object</span></span>  
  
1. <span data-ttu-id="a77ef-165">`Customer`의 `Console.ReadLine` 앞에 다음 코드를 추가하여 새 `Sub Main`를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a77ef-165">Create a new `Customer` by adding the following code before `Console.ReadLine` in `Sub Main`:</span></span>  
  
     [!code-vb[DLinqWalk3VB#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk3VB/vb/Module1.vb#3)]  
  
2. <span data-ttu-id="a77ef-166">F5 키를 눌러 솔루션을 디버깅합니다.</span><span class="sxs-lookup"><span data-stu-id="a77ef-166">Press F5 to debug the solution.</span></span>  
  
     <span data-ttu-id="a77ef-167">콘솔 창에 표시되는 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a77ef-167">The results that are shown in the console window are as follows:</span></span>  
  
     `Customers matching CA before insert:`  
  
     `Customer ID: CACTU`  
  
     `Customer ID: RICAR`  
  
     <span data-ttu-id="a77ef-168">새 행이 결과에 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a77ef-168">Note that the new row does not appear in the results.</span></span> <span data-ttu-id="a77ef-169">새 데이터가 아직 데이터베이스로 전송되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="a77ef-169">The new data has not yet been submitted to the database.</span></span>  
  
3. <span data-ttu-id="a77ef-170">**콘솔** 창에서 enter 키를 눌러 디버깅을 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="a77ef-170">Press Enter in the **Console** window to stop debugging.</span></span>  
  
## <a name="updating-an-entity"></a><span data-ttu-id="a77ef-171">엔터티 업데이트</span><span class="sxs-lookup"><span data-stu-id="a77ef-171">Updating an Entity</span></span>  
 <span data-ttu-id="a77ef-172">다음 단계에서는 `Customer` 개체를 검색하고 해당 속성 중 하나를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="a77ef-172">In the following steps, you will retrieve a `Customer` object and modify one of its properties.</span></span>  
  
#### <a name="to-change-the-name-of-a-customer"></a><span data-ttu-id="a77ef-173">Customer 이름을 변경하려면</span><span class="sxs-lookup"><span data-stu-id="a77ef-173">To change the name of a Customer</span></span>  
  
- <span data-ttu-id="a77ef-174">`Console.ReadLine()` 위에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a77ef-174">Add the following code above `Console.ReadLine()`:</span></span>  
  
     [!code-vb[DLinqWalk3VB#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk3VB/vb/Module1.vb#4)]  
  
## <a name="deleting-an-entity"></a><span data-ttu-id="a77ef-175">엔터티 삭제</span><span class="sxs-lookup"><span data-stu-id="a77ef-175">Deleting an Entity</span></span>  
 <span data-ttu-id="a77ef-176">동일한 Customer 개체를 사용하여 첫 번째 주문을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a77ef-176">Using the same customer object, you can delete the first order.</span></span>  
  
 <span data-ttu-id="a77ef-177">다음 코드에서는 행 간의 관계를 끊는 방법과 데이터베이스에서 행을 삭제하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a77ef-177">The following code demonstrates how to sever relationships between rows, and how to delete a row from the database.</span></span>  
  
#### <a name="to-delete-a-row"></a><span data-ttu-id="a77ef-178">행을 삭제하려면</span><span class="sxs-lookup"><span data-stu-id="a77ef-178">To delete a row</span></span>  
  
- <span data-ttu-id="a77ef-179">`Console.ReadLine()` 바로 위에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a77ef-179">Add the following code just above `Console.ReadLine()`:</span></span>  
  
     [!code-vb[DLinqWalk3VB#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk3VB/vb/Module1.vb#5)]  
  
## <a name="submitting-changes-to-the-database"></a><span data-ttu-id="a77ef-180">변경 내용을 데이터베이스로 전송</span><span class="sxs-lookup"><span data-stu-id="a77ef-180">Submitting Changes to the Database</span></span>  
 <span data-ttu-id="a77ef-181">개체를 만들고 업데이트 및 삭제하는 데 필요한 첫 번째 단계는 실제로 변경 내용을 데이터베이스로 전송하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a77ef-181">The final step required for creating, updating, and deleting objects is to actually submit the changes to the database.</span></span> <span data-ttu-id="a77ef-182">이 단계를 수행하지 않으면 변경 내용은 로컬에만 적용되고 쿼리 결과에 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a77ef-182">Without this step, your changes are only local and will not appear in query results.</span></span>  
  
#### <a name="to-submit-changes-to-the-database"></a><span data-ttu-id="a77ef-183">변경 내용을 데이터베이스로 전송하려면</span><span class="sxs-lookup"><span data-stu-id="a77ef-183">To submit changes to the database</span></span>  
  
1. <span data-ttu-id="a77ef-184">`Console.ReadLine` 바로 위에 다음 코드를 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="a77ef-184">Insert the following code just above `Console.ReadLine`:</span></span>  
  
     [!code-vb[DLinqWalk3VB#6](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk3VB/vb/Module1.vb#6)]  
  
2. <span data-ttu-id="a77ef-185">`SubmitChanges` 뒤에 다음 코드를 삽입하여 변경 내용 전송 전후의 결과를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a77ef-185">Insert the following code (after `SubmitChanges`) to show the before and after effects of submitting the changes:</span></span>  
  
     [!code-vb[DLinqWalk3VB#7](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk3VB/vb/Module1.vb#7)]  
  
3. <span data-ttu-id="a77ef-186">F5 키를 눌러 솔루션을 디버깅합니다.</span><span class="sxs-lookup"><span data-stu-id="a77ef-186">Press F5 to debug the solution.</span></span>  
  
     <span data-ttu-id="a77ef-187">콘솔 창이 다음과 같이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="a77ef-187">The console window appears as follows:</span></span>  
  
    ```console
    Customers matching CA before update:  
    Customer ID: CACTU  
    Customer ID: RICAR  
  
    The Order Detail to be deleted is: OrderID = 10643  
  
    Customers matching CA after update:  
    Customer ID: A3VCA  
    Customer ID: CACTU  
    Customer ID: RICAR  
    ```  
  
4. <span data-ttu-id="a77ef-188">**콘솔** 창에서 enter 키를 눌러 디버깅을 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="a77ef-188">Press Enter in the **Console** window to stop debugging.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a77ef-189">변경 내용을 전송하여 새 고객을 추가한 후에는 동일한 고객을 있는 그대로 다시 추가할 수 없으므로 이 솔루션을 있는 그대로 다시 실행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a77ef-189">After you have added the new customer by submitting the changes, you cannot execute this solution again as is, because you cannot add the same customer again as is.</span></span> <span data-ttu-id="a77ef-190">솔루션을 다시 실행하려면 추가할 고객 ID의 값을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="a77ef-190">To execute the solution again, change the value of the customer ID to be added.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a77ef-191">참조</span><span class="sxs-lookup"><span data-stu-id="a77ef-191">See also</span></span>

- [<span data-ttu-id="a77ef-192">연습으로 학습</span><span class="sxs-lookup"><span data-stu-id="a77ef-192">Learning by Walkthroughs</span></span>](learning-by-walkthroughs.md)
