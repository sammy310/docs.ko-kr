---
description: '자세한 정보: 연습: 저장 프로시저만 사용 (c #)'
title: '연습: 저장 프로시저만 사용(C#)'
ms.date: 03/30/2017
ms.assetid: ecde4bf2-fa4d-4252-b5e4-96a46b9e097d
ms.openlocfilehash: 89cb6da9ec4e8d144726b6e3575a32c04d6aeec0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99791779"
---
# <a name="walkthrough-using-only-stored-procedures-c"></a><span data-ttu-id="21a8f-103">연습: 저장 프로시저만 사용(C#)</span><span class="sxs-lookup"><span data-stu-id="21a8f-103">Walkthrough: Using Only Stored Procedures (C#)</span></span>

<span data-ttu-id="21a8f-104">이 연습에서는 저장 프로시저만 실행하여 데이터에 액세스하기 위한 기본 엔드투엔드 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 시나리오를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="21a8f-104">This walkthrough provides a basic end-to-end [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] scenario for accessing data by executing stored procedures only.</span></span> <span data-ttu-id="21a8f-105">일반적으로 데이터베이스 관리자는 데이터 저장소에 액세스하는 방법을 제한하기 위해 이 방법을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="21a8f-105">This approach is often used by database administrators to limit how the datastore is accessed.</span></span>

> [!NOTE]
> <span data-ttu-id="21a8f-106">또한 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 애플리케이션에서 저장 프로시저를 사용하여 특히 `Create`, `Update` 및 `Delete` 프로세스의 경우에 기본 동작을 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21a8f-106">You can also use stored procedures in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] applications to override default behavior, especially for `Create`, `Update`, and `Delete` processes.</span></span> <span data-ttu-id="21a8f-107">자세한 내용은 [삽입, 업데이트 및 삭제 작업 사용자 지정](customizing-insert-update-and-delete-operations.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="21a8f-107">For more information, see [Customizing Insert, Update, and Delete Operations](customizing-insert-update-and-delete-operations.md).</span></span>

<span data-ttu-id="21a8f-108">이 연습에서는 Northwind 샘플 데이터베이스인 CustOrdersDetail 및 CustOrderHist의 저장 프로시저에 매핑된 두 개의 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="21a8f-108">For purposes of this walkthrough, you will use two methods that have been mapped to stored procedures in the Northwind sample database: CustOrdersDetail and CustOrderHist.</span></span> <span data-ttu-id="21a8f-109">SqlMetal 명령줄 도구를 실행하여 C# 파일을 생성할 경우 매핑이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="21a8f-109">The mapping occurs when you run the SqlMetal command-line tool to generate a C# file.</span></span> <span data-ttu-id="21a8f-110">자세한 내용은 이 연습 뒷부분의 사전 요구 사항 단원을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="21a8f-110">For more information, see the Prerequisites section later in this walkthrough.</span></span>

<span data-ttu-id="21a8f-111">이 연습에서는 개체 관계형 디자이너을 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="21a8f-111">This walkthrough does not rely on the Object Relational Designer.</span></span> <span data-ttu-id="21a8f-112">Visual Studio를 사용 하는 개발자는 O/R 디자이너를 사용 하 여 저장 프로시저 기능을 구현할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21a8f-112">Developers using Visual Studio can also use the O/R Designer to implement stored procedure functionality.</span></span> <span data-ttu-id="21a8f-113">[Visual Studio의 LINQ to SQL 도구를](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="21a8f-113">See [LINQ to SQL Tools in Visual Studio](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2).</span></span>

[!INCLUDE[note_settings_general](../../../../../../includes/note-settings-general-md.md)]

<span data-ttu-id="21a8f-114">이 연습은 Visual C# 개발 설정을 사용하여 작성했습니다.</span><span class="sxs-lookup"><span data-stu-id="21a8f-114">This walkthrough was written by using Visual C# Development Settings.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="21a8f-115">사전 요구 사항</span><span class="sxs-lookup"><span data-stu-id="21a8f-115">Prerequisites</span></span>

<span data-ttu-id="21a8f-116">이 연습에서는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="21a8f-116">This walkthrough requires the following:</span></span>

- <span data-ttu-id="21a8f-117">이 연습에서는 파일을 보유하기 위해 전용 폴더("c:\linqtest7")가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="21a8f-117">This walkthrough uses a dedicated folder ("c:\linqtest7") to hold files.</span></span> <span data-ttu-id="21a8f-118">연습을 시작하기 전에 먼저 이 폴더를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="21a8f-118">Create this folder before you begin the walkthrough.</span></span>

- <span data-ttu-id="21a8f-119">Northwind 샘플 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="21a8f-119">The Northwind sample database.</span></span>

     <span data-ttu-id="21a8f-120">이 데이터베이스가 개발 컴퓨터에 없는 경우 Microsoft 다운로드 사이트에서 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21a8f-120">If you do not have this database on your development computer, you can download it from the Microsoft download site.</span></span> <span data-ttu-id="21a8f-121">지침은 [샘플 데이터베이스 다운로드](downloading-sample-databases.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="21a8f-121">For instructions, see [Downloading Sample Databases](downloading-sample-databases.md).</span></span> <span data-ttu-id="21a8f-122">이 데이터베이스를 다운로드한 후 northwnd.mdf 파일을 c:\linqtest7 폴더에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="21a8f-122">After you have downloaded the database, copy the northwnd.mdf file to the c:\linqtest7 folder.</span></span>

- <span data-ttu-id="21a8f-123">Northwind 데이터베이스에서 생성된 C# 코드 파일</span><span class="sxs-lookup"><span data-stu-id="21a8f-123">A C# code file generated from the Northwind database.</span></span>

     <span data-ttu-id="21a8f-124">이 연습은 다음 명령줄을 사용하여 SqlMetal 도구를 통해 작성했습니다.</span><span class="sxs-lookup"><span data-stu-id="21a8f-124">This walkthrough was written by using the SqlMetal tool with the following command line:</span></span>

     <span data-ttu-id="21a8f-125">**sqlmetal /code:"c:\linqtest7\northwind.cs" /language:csharp "c:\linqtest7\northwnd.mdf" /sprocs /functions /pluralize**</span><span class="sxs-lookup"><span data-stu-id="21a8f-125">**sqlmetal /code:"c:\linqtest7\northwind.cs" /language:csharp "c:\linqtest7\northwnd.mdf" /sprocs /functions /pluralize**</span></span>

     <span data-ttu-id="21a8f-126">자세한 내용은 [SqlMetal.exe(코드 생성 도구)](../../../../tools/sqlmetal-exe-code-generation-tool.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="21a8f-126">For more information, see [SqlMetal.exe (Code Generation Tool)](../../../../tools/sqlmetal-exe-code-generation-tool.md).</span></span>

## <a name="overview"></a><span data-ttu-id="21a8f-127">개요</span><span class="sxs-lookup"><span data-stu-id="21a8f-127">Overview</span></span>

<span data-ttu-id="21a8f-128">이 연습은 다음과 같은 여섯 가지 주요 작업으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="21a8f-128">This walkthrough consists of six main tasks:</span></span>

- <span data-ttu-id="21a8f-129">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]Visual Studio에서 솔루션 설정</span><span class="sxs-lookup"><span data-stu-id="21a8f-129">Setting up the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] solution in Visual Studio.</span></span>

- <span data-ttu-id="21a8f-130">System.Data.Linq 어셈블리를 프로젝트에 추가</span><span class="sxs-lookup"><span data-stu-id="21a8f-130">Adding the System.Data.Linq assembly to the project.</span></span>

- <span data-ttu-id="21a8f-131">데이터베이스 코드 파일을 프로젝트에 추가</span><span class="sxs-lookup"><span data-stu-id="21a8f-131">Adding the database code file to the project.</span></span>

- <span data-ttu-id="21a8f-132">데이터베이스와 연결 만들기</span><span class="sxs-lookup"><span data-stu-id="21a8f-132">Creating a connection with the database.</span></span>

- <span data-ttu-id="21a8f-133">사용자 인터페이스 설정</span><span class="sxs-lookup"><span data-stu-id="21a8f-133">Setting up the user interface.</span></span>

- <span data-ttu-id="21a8f-134">애플리케이션 실행 및 테스트</span><span class="sxs-lookup"><span data-stu-id="21a8f-134">Running and testing the application.</span></span>

## <a name="creating-a-linq-to-sql-solution"></a><span data-ttu-id="21a8f-135">LINQ to SQL 솔루션 만들기</span><span class="sxs-lookup"><span data-stu-id="21a8f-135">Creating a LINQ to SQL Solution</span></span>

<span data-ttu-id="21a8f-136">이 첫 번째 작업에서는 프로젝트를 빌드하고 실행 하는 데 필요한 참조를 포함 하는 Visual Studio 솔루션을 만듭니다 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="21a8f-136">In this first task, you create a Visual Studio solution that contains the necessary references to build and run a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] project.</span></span>

### <a name="to-create-a-linq-to-sql-solution"></a><span data-ttu-id="21a8f-137">LINQ to SQL 솔루션을 만들려면</span><span class="sxs-lookup"><span data-stu-id="21a8f-137">To create a LINQ to SQL solution</span></span>

1. <span data-ttu-id="21a8f-138">Visual Studio **파일** 메뉴에서 **새로 만들기** 를 가리킨 다음 **프로젝트** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="21a8f-138">On the Visual Studio **File** menu, point to **New**, and then click **Project**.</span></span>

2. <span data-ttu-id="21a8f-139">**새 프로젝트** 대화 상자의 **프로젝트 형식** 창에서 **Visual c #** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="21a8f-139">In the **Project types** pane in the **New Project** dialog box, click **Visual C#**.</span></span>

3. <span data-ttu-id="21a8f-140">**템플릿** 창에서 **Windows Forms 애플리케이션** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="21a8f-140">In the **Templates** pane, click **Windows Forms Application**.</span></span>

4. <span data-ttu-id="21a8f-141">**이름** 상자에 **Sproconlyapp** 을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="21a8f-141">In the **Name** box, type **SprocOnlyApp**.</span></span>

5. <span data-ttu-id="21a8f-142">**위치** 상자에서 프로젝트 파일을 저장할 위치를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="21a8f-142">In the **Location** box, verify where you want to store your project files.</span></span>

6. <span data-ttu-id="21a8f-143">**확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="21a8f-143">Click **OK**.</span></span>

     <span data-ttu-id="21a8f-144">Windows Forms 디자이너가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="21a8f-144">The Windows Forms Designer opens.</span></span>

## <a name="adding-the-linq-to-sql-assembly-reference"></a><span data-ttu-id="21a8f-145">LINQ to SQL 어셈블리 참조 추가</span><span class="sxs-lookup"><span data-stu-id="21a8f-145">Adding the LINQ to SQL Assembly Reference</span></span>

<span data-ttu-id="21a8f-146">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 어셈블리는 표준 Windows Forms 애플리케이션 템플릿에 포함되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="21a8f-146">The [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] assembly is not included in the standard Windows Forms Application template.</span></span> <span data-ttu-id="21a8f-147">다음 단계에 설명된 대로 이 어셈블리를 직접 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="21a8f-147">You will have to add the assembly yourself, as explained in the following steps:</span></span>

### <a name="to-add-systemdatalinqdll"></a><span data-ttu-id="21a8f-148">System.Data.Linq.dll을 추가하려면</span><span class="sxs-lookup"><span data-stu-id="21a8f-148">To add System.Data.Linq.dll</span></span>

1. <span data-ttu-id="21a8f-149">**솔루션 탐색기** 에서 **참조** 를 마우스 오른쪽 단추로 클릭 한 다음 **참조 추가** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="21a8f-149">In **Solution Explorer**, right-click **References**, and then click **Add Reference**.</span></span>

2. <span data-ttu-id="21a8f-150">**참조 추가** 대화 상자에서 **.net** 을 클릭 하 고 system.xml 어셈블리를 클릭 한 다음 **확인** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="21a8f-150">In the **Add Reference** dialog box, click **.NET**, click the System.Data.Linq assembly, and then click **OK**.</span></span>

     <span data-ttu-id="21a8f-151">어셈블리가 프로젝트에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="21a8f-151">The assembly is added to the project.</span></span>

## <a name="adding-the-northwind-code-file-to-the-project"></a><span data-ttu-id="21a8f-152">Northwind 코드 파일을 프로젝트에 추가</span><span class="sxs-lookup"><span data-stu-id="21a8f-152">Adding the Northwind Code File to the Project</span></span>

<span data-ttu-id="21a8f-153">이 단계에서는 SqlMetal 도구를 사용하여 Northwind 샘플 데이터베이스에서 코드 파일을 생성했다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="21a8f-153">This step assumes that you have used the SqlMetal tool to generate a code file from the Northwind sample database.</span></span> <span data-ttu-id="21a8f-154">자세한 내용은 이 연습 앞부분의 사전 요구 사항 단원을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="21a8f-154">For more information, see the Prerequisites section earlier in this walkthrough.</span></span>

### <a name="to-add-the-northwind-code-file-to-the-project"></a><span data-ttu-id="21a8f-155">northwind 코드 파일을 프로젝트에 추가하려면</span><span class="sxs-lookup"><span data-stu-id="21a8f-155">To add the northwind code file to the project</span></span>

1. <span data-ttu-id="21a8f-156">**프로젝트** 메뉴에서 **기존 항목 추가** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="21a8f-156">On the **Project** menu, click **Add Existing Item**.</span></span>

2. <span data-ttu-id="21a8f-157">**기존 항목 추가** 대화 상자에서 c:\linqtest7\ northwind.cs으로 이동한 다음 **추가** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="21a8f-157">In the **Add Existing Item** dialog box, move to c:\linqtest7\northwind.cs, and then click **Add**.</span></span>

     <span data-ttu-id="21a8f-158">northwind.cs 파일이 프로젝트에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="21a8f-158">The northwind.cs file is added to the project.</span></span>

## <a name="creating-a-database-connection"></a><span data-ttu-id="21a8f-159">데이터베이스 연결 만들기</span><span class="sxs-lookup"><span data-stu-id="21a8f-159">Creating a Database Connection</span></span>

<span data-ttu-id="21a8f-160">이 단계에서는 Northwind 샘플 데이터베이스에 대한 연결을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="21a8f-160">In this step, you define the connection to the Northwind sample database.</span></span> <span data-ttu-id="21a8f-161">"c:\linqtest7\northwnd.mdf"가 이 연습에서 경로로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="21a8f-161">This walkthrough uses "c:\linqtest7\northwnd.mdf" as the path.</span></span>

### <a name="to-create-the-database-connection"></a><span data-ttu-id="21a8f-162">데이터베이스 연결을 만들려면</span><span class="sxs-lookup"><span data-stu-id="21a8f-162">To create the database connection</span></span>

1. <span data-ttu-id="21a8f-163">**솔루션 탐색기** 에서 **Form1.cs** 을 마우스 오른쪽 단추로 클릭 한 다음 **코드 보기** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="21a8f-163">In **Solution Explorer**, right-click **Form1.cs**, and then click **View Code**.</span></span>

2. <span data-ttu-id="21a8f-164">다음 코드를 `Form1` 클래스에 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="21a8f-164">Type the following code into the `Form1` class:</span></span>

     [!code-csharp[DLinqWalk4CS#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk4CS/cs/Form1.cs#1)]

## <a name="setting-up-the-user-interface"></a><span data-ttu-id="21a8f-165">사용자 인터페이스 설정</span><span class="sxs-lookup"><span data-stu-id="21a8f-165">Setting up the User Interface</span></span>

<span data-ttu-id="21a8f-166">이 작업에서는 사용자가 저장 프로시저를 실행하여 데이터베이스의 데이터에 액세스할 수 있도록 인터페이스를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="21a8f-166">In this task you set up an interface so that users can execute stored procedures to access data in the database.</span></span> <span data-ttu-id="21a8f-167">이 연습을 사용하여 개발하는 애플리케이션에서 사용자는 애플리케이션에 포함된 저장 프로시저를 통해서만 데이터베이스의 데이터에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21a8f-167">In the applications that you are developing with this walkthrough, users can access data in the database only by using the stored procedures embedded in the application.</span></span>

### <a name="to-set-up-the-user-interface"></a><span data-ttu-id="21a8f-168">사용자 인터페이스를 설정하려면</span><span class="sxs-lookup"><span data-stu-id="21a8f-168">To set up the user interface</span></span>

1. <span data-ttu-id="21a8f-169">Windows Forms 디자이너 (**Form1 [Design]**)로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="21a8f-169">Return to the Windows Forms Designer (**Form1.cs[Design]**).</span></span>

2. <span data-ttu-id="21a8f-170">**보기** 메뉴에서 **도구 상자** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="21a8f-170">On the **View** menu, click **Toolbox**.</span></span>

     <span data-ttu-id="21a8f-171">도구 상자가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="21a8f-171">The toolbox opens.</span></span>

    > [!NOTE]
    > <span data-ttu-id="21a8f-172">자동 **숨기기** 압정 아이콘을 클릭 하 여이 섹션의 나머지 단계를 수행 하는 동안 도구 상자를 열어 둡니다.</span><span class="sxs-lookup"><span data-stu-id="21a8f-172">Click the **AutoHide** pushpin to keep the toolbox open while you perform the remaining steps in this section.</span></span>

3. <span data-ttu-id="21a8f-173">두 개의 단추, 두 개의 텍스트 상자 및 두 개의 레이블을 도구 상자에서 **Form1** 로 끌어 옵니다.</span><span class="sxs-lookup"><span data-stu-id="21a8f-173">Drag two buttons, two text boxes, and two labels from the toolbox onto **Form1**.</span></span>

     <span data-ttu-id="21a8f-174">함께 나와 있는 그림과 같이 컨트롤을 정렬합니다.</span><span class="sxs-lookup"><span data-stu-id="21a8f-174">Arrange the controls as in the accompanying illustration.</span></span> <span data-ttu-id="21a8f-175">컨트롤이 쉽게 들어가도록 **Form1** 을 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="21a8f-175">Expand **Form1** so that the controls fit easily.</span></span>

4. <span data-ttu-id="21a8f-176">**Label1** 을 마우스 오른쪽 단추로 클릭 한 다음 **속성** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="21a8f-176">Right-click **label1**, and then click **Properties**.</span></span>

5. <span data-ttu-id="21a8f-177">**텍스트** 속성을 **Label1** 에서 **Enter OrderID:** 로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="21a8f-177">Change the **Text** property from **label1** to **Enter OrderID:**.</span></span>

6. <span data-ttu-id="21a8f-178">**Label2** 와 동일한 방식으로 **텍스트** 속성을 **label2** 에서 **Enter CustomerID:** 로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="21a8f-178">In the same way for **label2**, change the **Text** property from **label2** to **Enter CustomerID:**.</span></span>

7. <span data-ttu-id="21a8f-179">이와 같은 방법으로 **button1** 의 **텍스트** 속성을 **Order Details** 로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="21a8f-179">In the same way, change the **Text** property for **button1** to **Order Details**.</span></span>

8. <span data-ttu-id="21a8f-180">**Button2** 의 **Text** 속성을 **Order History** 로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="21a8f-180">Change the **Text** property for **button2** to **Order History**.</span></span>

     <span data-ttu-id="21a8f-181">모든 텍스트를 볼 수 있도록 단추 컨트롤을 넓힙니다.</span><span class="sxs-lookup"><span data-stu-id="21a8f-181">Widen the button controls so that all the text is visible.</span></span>

### <a name="to-handle-button-clicks"></a><span data-ttu-id="21a8f-182">단추 클릭을 처리하려면</span><span class="sxs-lookup"><span data-stu-id="21a8f-182">To handle button clicks</span></span>

1. <span data-ttu-id="21a8f-183">**Form1** 에서 **Order Details** 를 두 번 클릭 하 여 코드 편집기에서 button1 이벤트 처리기를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="21a8f-183">Double-click **Order Details** on **Form1** to open the button1 event handler in the code editor.</span></span>

2. <span data-ttu-id="21a8f-184">다음 코드를 `button1` 처리기에 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="21a8f-184">Type the following code into the `button1` handler:</span></span>

     [!code-csharp[DLinqWalk4CS#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk4CS/cs/Form1.cs#2)]

3. <span data-ttu-id="21a8f-185">이제 **Form1** 에서 **button2** 를 두 번 클릭 하 여 처리기를 엽니다. `button2`</span><span class="sxs-lookup"><span data-stu-id="21a8f-185">Now double-click **button2** on **Form1** to open the `button2` handler</span></span>

4. <span data-ttu-id="21a8f-186">다음 코드를 `button2` 처리기에 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="21a8f-186">Type the following code into the `button2` handler:</span></span>

     [!code-csharp[DLinqWalk4CS#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk4CS/cs/Form1.cs#3)]

## <a name="testing-the-application"></a><span data-ttu-id="21a8f-187">애플리케이션 테스트</span><span class="sxs-lookup"><span data-stu-id="21a8f-187">Testing the Application</span></span>

<span data-ttu-id="21a8f-188">이제 애플리케이션을 테스트할 차례입니다.</span><span class="sxs-lookup"><span data-stu-id="21a8f-188">Now it is time to test your application.</span></span> <span data-ttu-id="21a8f-189">데이터 저장소와의 연결은 두 개의 저장 프로시저가 수행할 수 있는 작업으로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="21a8f-189">Note that your contact with the datastore is limited to whatever actions the two stored procedures can take.</span></span> <span data-ttu-id="21a8f-190">이러한 작업은 입력한 orderID에 대한 포함된 제품을 반환하거나 입력한 CustomerID에 대한 주문된 제품의 기록을 반환하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="21a8f-190">Those actions are to return the products included for any orderID you enter, or to return a history of products ordered for any CustomerID you enter.</span></span>

### <a name="to-test-the-application"></a><span data-ttu-id="21a8f-191">애플리케이션을 테스트하려면</span><span class="sxs-lookup"><span data-stu-id="21a8f-191">To test the application</span></span>

1. <span data-ttu-id="21a8f-192">F5 키를 눌러 디버깅을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="21a8f-192">Press F5 to start debugging.</span></span>

     <span data-ttu-id="21a8f-193">Form1이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="21a8f-193">Form1 appears.</span></span>

2. <span data-ttu-id="21a8f-194">**Enter OrderID** 상자에를 입력 하 `10249` 고 **Order Details** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="21a8f-194">In the **Enter OrderID** box, type `10249`, and then click **Order Details**.</span></span>

     <span data-ttu-id="21a8f-195">메시지 상자에는 주문 10249에 포함된 제품이 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="21a8f-195">A message box lists the products included in order 10249.</span></span>

     <span data-ttu-id="21a8f-196">**확인** 을 클릭하여 메시지 상자를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="21a8f-196">Click **OK** to close the message box.</span></span>

3. <span data-ttu-id="21a8f-197">**CustomerID 입력** 상자에를 입력 한 `ALFKI` 다음 **Order History** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="21a8f-197">In the **Enter CustomerID** box, type `ALFKI`, and then click **Order History**.</span></span>

     <span data-ttu-id="21a8f-198">고객 ALFKI에 대한 주문 기록이 나열된 메시지 상자가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="21a8f-198">A message box appears that lists the order history for customer ALFKI.</span></span>

     <span data-ttu-id="21a8f-199">**확인** 을 클릭하여 메시지 상자를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="21a8f-199">Click **OK** to close the message box.</span></span>

4. <span data-ttu-id="21a8f-200">**Enter OrderID** 상자에를 입력 하 `123` 고 **Order Details** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="21a8f-200">In the **Enter OrderID** box, type `123`, and then click **Order Details**.</span></span>

     <span data-ttu-id="21a8f-201">"No results"가 표시된 메시지 상자가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="21a8f-201">A message box appears that displays "No results."</span></span>

     <span data-ttu-id="21a8f-202">**확인** 을 클릭하여 메시지 상자를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="21a8f-202">Click **OK** to close the message box.</span></span>

5. <span data-ttu-id="21a8f-203">**디버그** 메뉴에서 **디버깅 중지** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="21a8f-203">On the **Debug** menu, click **Stop debugging**.</span></span>

     <span data-ttu-id="21a8f-204">디버그 세션이 닫힙니다.</span><span class="sxs-lookup"><span data-stu-id="21a8f-204">The debug session closes.</span></span>

6. <span data-ttu-id="21a8f-205">실험을 완료 한 경우 **파일** 메뉴에서 **프로젝트 닫기** 를 클릭 하 고 메시지가 표시 되 면 프로젝트를 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21a8f-205">If you have finished experimenting, you can click **Close Project** on the **File** menu, and save your project when you are prompted.</span></span>

## <a name="next-steps"></a><span data-ttu-id="21a8f-206">다음 단계</span><span class="sxs-lookup"><span data-stu-id="21a8f-206">Next Steps</span></span>

<span data-ttu-id="21a8f-207">약간의 변경을 통해 이 프로젝트를 향상시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21a8f-207">You can enhance this project by making some changes.</span></span> <span data-ttu-id="21a8f-208">예를 들어 목록 상자에 사용 가능한 저장 프로시저를 나열하고 사용자가 실행할 프로시저를 선택하도록 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21a8f-208">For example, you could list available stored procedures in a list box and have the user select which procedures to execute.</span></span> <span data-ttu-id="21a8f-209">또한 보고서의 출력을 텍스트 파일에 스트리밍할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21a8f-209">You could also stream the output of the reports to a text file.</span></span>

## <a name="see-also"></a><span data-ttu-id="21a8f-210">참고 항목</span><span class="sxs-lookup"><span data-stu-id="21a8f-210">See also</span></span>

- [<span data-ttu-id="21a8f-211">연습으로 학습</span><span class="sxs-lookup"><span data-stu-id="21a8f-211">Learning by Walkthroughs</span></span>](learning-by-walkthroughs.md)
- [<span data-ttu-id="21a8f-212">저장 프로시저</span><span class="sxs-lookup"><span data-stu-id="21a8f-212">Stored Procedures</span></span>](stored-procedures.md)
