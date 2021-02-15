---
description: '자세한 정보: 연습: Visual Basic에서 쿼리 작성'
title: 쿼리 작성
ms.date: 07/20/2015
helpviewer_keywords:
- queries [LINQ in Visual Basic], writing
- LINQ [Visual Basic], walkthroughs
- LINQ [Visual Basic], writing queries
- writing LINQ queries [Visual Basic]
ms.assetid: f0045808-b9fe-4d31-88d1-473d9957211e
ms.openlocfilehash: 55a1b3382d587b7982b79448334c4688895fa6e6
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100466811"
---
# <a name="walkthrough-writing-queries-in-visual-basic"></a><span data-ttu-id="2a2e0-103">연습: Visual Basic에서 쿼리 작성</span><span class="sxs-lookup"><span data-stu-id="2a2e0-103">Walkthrough: Writing Queries in Visual Basic</span></span>

<span data-ttu-id="2a2e0-104">이 연습에서는 Visual Basic 언어 기능을 사용 하 여 LINQ (Language-Integrated Query) 쿼리 식을 작성 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2a2e0-104">This walkthrough demonstrates how you can use Visual Basic language features to write Language-Integrated Query (LINQ) query expressions.</span></span> <span data-ttu-id="2a2e0-105">이 연습에서는 학생 개체 목록에 대 한 쿼리를 만드는 방법, 쿼리를 실행 하는 방법 및 수정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2a2e0-105">The walkthrough demonstrates how to create queries on a list of Student objects, how to run the queries, and how to modify them.</span></span> <span data-ttu-id="2a2e0-106">이 쿼리는 개체 이니셜라이저, 로컬 형식 유추 및 익명 형식을 비롯 한 여러 기능을 통합 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a2e0-106">The queries incorporate several features including object initializers, local type inference, and anonymous types.</span></span>

<span data-ttu-id="2a2e0-107">이 연습을 완료 하면 관심 있는 특정 LINQ 공급자에 대 한 샘플 및 설명서로 이동할 준비가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a2e0-107">After completing this walkthrough, you will be ready to move on to the samples and documentation for the specific LINQ provider you are interested in.</span></span> <span data-ttu-id="2a2e0-108">LINQ 공급자는 [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] , LINQ to DataSet 및를 포함 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a2e0-108">LINQ providers include [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)], LINQ to DataSet, and [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span></span>

## <a name="create-a-project"></a><span data-ttu-id="2a2e0-109">프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="2a2e0-109">Create a Project</span></span>

### <a name="to-create-a-console-application-project"></a><span data-ttu-id="2a2e0-110">콘솔 응용 프로그램 프로젝트를 만들려면</span><span class="sxs-lookup"><span data-stu-id="2a2e0-110">To create a console application project</span></span>

1. <span data-ttu-id="2a2e0-111">Visual Studio를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="2a2e0-111">Start Visual Studio.</span></span>

2. <span data-ttu-id="2a2e0-112">**파일** 메뉴에서 **새로 만들기** 를 가리킨 다음 **프로젝트** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2a2e0-112">On the **File** menu, point to **New**, and then click **Project**.</span></span>

3. <span data-ttu-id="2a2e0-113">**설치 된 템플릿** 목록에서 **Visual Basic** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a2e0-113">In the **Installed Templates** list, click **Visual Basic**.</span></span>

4. <span data-ttu-id="2a2e0-114">프로젝트 형식 목록에서 **콘솔 응용 프로그램** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a2e0-114">In the list of project types, click **Console Application**.</span></span> <span data-ttu-id="2a2e0-115">**이름** 상자에 프로젝트의 이름을 입력 하 고 **확인** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a2e0-115">In the **Name** box, type a name for the project, and then click **OK**.</span></span>

    <span data-ttu-id="2a2e0-116">프로젝트가 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a2e0-116">A project is created.</span></span> <span data-ttu-id="2a2e0-117">기본적으로 System.Core.dll에 대 한 참조가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a2e0-117">By default, it contains a reference to System.Core.dll.</span></span> <span data-ttu-id="2a2e0-118">또한 [프로젝트 디자이너 (Visual Basic)의 참조 페이지](/visualstudio/ide/reference/references-page-project-designer-visual-basic) 에서 **가져온 네임 스페이스** 목록에는 <xref:System.Linq?displayProperty=nameWithType> 네임 스페이스가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a2e0-118">Also, the **Imported namespaces** list on the [References Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic) includes the <xref:System.Linq?displayProperty=nameWithType> namespace.</span></span>

5. <span data-ttu-id="2a2e0-119">[컴파일 페이지, 프로젝트 디자이너 (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)에서 **옵션 유추** 가 **On** 으로 설정 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a2e0-119">On the [Compile Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic), ensure that **Option infer** is set to **On**.</span></span>

## <a name="add-an-in-memory-data-source"></a><span data-ttu-id="2a2e0-120">In-Memory 데이터 원본 추가</span><span class="sxs-lookup"><span data-stu-id="2a2e0-120">Add an In-Memory Data Source</span></span>

<span data-ttu-id="2a2e0-121">이 연습의 쿼리에 대 한 데이터 소스는 개체의 목록입니다 `Student` .</span><span class="sxs-lookup"><span data-stu-id="2a2e0-121">The data source for the queries in this walkthrough is a list of `Student` objects.</span></span> <span data-ttu-id="2a2e0-122">각 `Student` 개체에는 학생 본문의 이름, 성, 클래스 연도 및 교육 등급이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a2e0-122">Each `Student` object contains a first name, a last name, a class year, and an academic rank in the student body.</span></span>

### <a name="to-add-the-data-source"></a><span data-ttu-id="2a2e0-123">데이터 소스를 추가하려면</span><span class="sxs-lookup"><span data-stu-id="2a2e0-123">To add the data source</span></span>

- <span data-ttu-id="2a2e0-124">클래스를 정의 `Student` 하 고 클래스의 인스턴스 목록을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2a2e0-124">Define a `Student` class, and create a list of instances of the class.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="2a2e0-125">클래스를 정의 하 `Student` 고 연습 예제에 사용 된 목록을 만드는 데 필요한 코드는 [방법: 항목 목록 만들기](how-to-create-a-list-of-items.md)에서 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a2e0-125">The code needed to define the `Student` class and create the list used in the walkthrough examples is provided in [How to: Create a List of Items](how-to-create-a-list-of-items.md).</span></span> <span data-ttu-id="2a2e0-126">여기에서 복사 하 여 프로젝트에 붙여 넣을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a2e0-126">You can copy it from there and paste it into your project.</span></span> <span data-ttu-id="2a2e0-127">새 코드는 프로젝트를 만들 때 표시 된 코드를 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a2e0-127">The new code replaces the code that appeared when you created the project.</span></span>

### <a name="to-add-a-new-student-to-the-students-list"></a><span data-ttu-id="2a2e0-128">학생 목록에 새 학생을 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="2a2e0-128">To add a new student to the students list</span></span>

- <span data-ttu-id="2a2e0-129">메서드의 패턴에 따라 `getStudents` 클래스의 다른 인스턴스를 `Student` 목록에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a2e0-129">Follow the pattern in the `getStudents` method to add another instance of the `Student` class to the list.</span></span> <span data-ttu-id="2a2e0-130">학생을 추가 하면 개체 이니셜라이저를 소개 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a2e0-130">Adding the student will introduce you to object initializers.</span></span> <span data-ttu-id="2a2e0-131">자세한 내용은 [개체 이니셜라이저: 명명 된 형식과 익명 형식](../../language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2a2e0-131">For more information, see [Object Initializers: Named and Anonymous Types](../../language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md).</span></span>

## <a name="create-a-query"></a><span data-ttu-id="2a2e0-132">쿼리 만들기</span><span class="sxs-lookup"><span data-stu-id="2a2e0-132">Create a Query</span></span>

<span data-ttu-id="2a2e0-133">이 섹션에 추가 된 쿼리는 실행 될 때 교육 등급이 상위 10 개에 배치 하는 학생의 목록을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a2e0-133">When executed, the query added in this section produces a list of the students whose academic rank puts them in the top ten.</span></span> <span data-ttu-id="2a2e0-134">쿼리가 매번 전체 개체를 선택 하기 때문에 `Student` 쿼리 결과의 형식은 `IEnumerable(Of Student)` 입니다.</span><span class="sxs-lookup"><span data-stu-id="2a2e0-134">Because the query selects the complete `Student` object each time, the type of the query result is `IEnumerable(Of Student)`.</span></span> <span data-ttu-id="2a2e0-135">그러나 일반적으로 쿼리 형식은 쿼리 정의에 지정 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2a2e0-135">However, the type of the query typically is not specified in query definitions.</span></span> <span data-ttu-id="2a2e0-136">대신 컴파일러는 로컬 형식 유추를 사용 하 여 형식을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a2e0-136">Instead, the compiler uses local type inference to determine the type.</span></span> <span data-ttu-id="2a2e0-137">자세한 내용은 [지역 형식 유추](../../language-features/variables/local-type-inference.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2a2e0-137">For more information, see [Local Type Inference](../../language-features/variables/local-type-inference.md).</span></span> <span data-ttu-id="2a2e0-138">쿼리의 범위 변수는 `currentStudent` 소스의 각 인스턴스에 대 한 참조로 사용 `Student` `students` 되어에서 각 개체의 속성에 대 한 액세스를 제공 `students` 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a2e0-138">The query's range variable, `currentStudent`, serves as a reference to each `Student` instance in the source, `students`, providing access to the properties of each object in `students`.</span></span>

### <a name="to-create-a-simple-query"></a><span data-ttu-id="2a2e0-139">단순 쿼리를 작성하려면</span><span class="sxs-lookup"><span data-stu-id="2a2e0-139">To create a simple query</span></span>

1. <span data-ttu-id="2a2e0-140">`Main`프로젝트의 메서드에서 다음과 같이 표시 되는 위치를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="2a2e0-140">Find the place in the `Main` method of the project that is marked as follows:</span></span>

    [!code-vb[VbLINQWalkthrough#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQWalkthrough/VB/Class1.vb#1)]

    <span data-ttu-id="2a2e0-141">다음 코드를 복사 하 여에 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="2a2e0-141">Copy the following code and paste it in.</span></span>

    [!code-vb[VbLINQWalkthrough#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQWalkthrough/VB/Class1.vb#2)]

2. <span data-ttu-id="2a2e0-142">코드에서 마우스 포인터를 올려 `studentQuery` 컴파일러 할당 형식이 인지 확인 합니다 `IEnumerable(Of Student)` .</span><span class="sxs-lookup"><span data-stu-id="2a2e0-142">Rest the mouse pointer over `studentQuery` in your code to verify that the compiler-assigned type is `IEnumerable(Of Student)`.</span></span>

## <a name="run-the-query"></a><span data-ttu-id="2a2e0-143">쿼리 실행</span><span class="sxs-lookup"><span data-stu-id="2a2e0-143">Run the Query</span></span>

<span data-ttu-id="2a2e0-144">변수는 쿼리 `studentQuery` 실행 결과가 아닌 쿼리 정의를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a2e0-144">The variable `studentQuery` contains the definition of the query, not the results of running the query.</span></span> <span data-ttu-id="2a2e0-145">쿼리를 실행 하는 일반적인 메커니즘은 `For Each` 루프입니다.</span><span class="sxs-lookup"><span data-stu-id="2a2e0-145">A typical mechanism for running a query is a `For Each` loop.</span></span> <span data-ttu-id="2a2e0-146">반환 된 시퀀스의 각 요소는 루프 반복 변수를 통해 액세스 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a2e0-146">Each element in the returned sequence is accessed through the loop iteration variable.</span></span> <span data-ttu-id="2a2e0-147">쿼리 실행에 대 한 자세한 내용은 [첫 번째 LINQ 쿼리 작성](writing-your-first-linq-query.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2a2e0-147">For more information about query execution, see [Writing Your First LINQ Query](writing-your-first-linq-query.md).</span></span>

### <a name="to-run-the-query"></a><span data-ttu-id="2a2e0-148">쿼리를 실행 하려면</span><span class="sxs-lookup"><span data-stu-id="2a2e0-148">To run the query</span></span>

1. <span data-ttu-id="2a2e0-149">`For Each`프로젝트의 쿼리 아래에 다음 루프를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a2e0-149">Add the following `For Each` loop below the query in your project.</span></span>

    [!code-vb[VbLINQWalkthrough#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQWalkthrough/VB/Class1.vb#3)]

2. <span data-ttu-id="2a2e0-150">루프 제어 변수 위에 마우스 포인터를 놓으면 `studentRecord` 해당 데이터 형식이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a2e0-150">Rest the mouse pointer over the loop control variable `studentRecord` to see its data type.</span></span> <span data-ttu-id="2a2e0-151">의 형식은 `studentRecord` `Student` `studentQuery` 인스턴스 컬렉션을 반환 하기 때문에로 유추 됩니다 `Student` .</span><span class="sxs-lookup"><span data-stu-id="2a2e0-151">The type of `studentRecord` is inferred to be `Student`, because `studentQuery` returns a collection of `Student` instances.</span></span>

3. <span data-ttu-id="2a2e0-152">CTRL + F5 키를 눌러 응용 프로그램을 빌드하고 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a2e0-152">Build and run the application by pressing CTRL+F5.</span></span> <span data-ttu-id="2a2e0-153">콘솔 창에서 결과를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a2e0-153">Note the results in the console window.</span></span>

## <a name="modify-the-query"></a><span data-ttu-id="2a2e0-154">쿼리 수정</span><span class="sxs-lookup"><span data-stu-id="2a2e0-154">Modify the Query</span></span>

<span data-ttu-id="2a2e0-155">쿼리 결과가 지정 된 순서로 검색 되는 것이 더 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="2a2e0-155">It is easier to scan query results if they are in a specified order.</span></span> <span data-ttu-id="2a2e0-156">사용 가능한 필드에 따라 반환 된 시퀀스를 정렬할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a2e0-156">You can sort the returned sequence based on any available field.</span></span>

### <a name="to-order-the-results"></a><span data-ttu-id="2a2e0-157">결과를 정렬하려면</span><span class="sxs-lookup"><span data-stu-id="2a2e0-157">To order the results</span></span>

1. <span data-ttu-id="2a2e0-158">`Order By`문과 쿼리 문 사이에 다음 절을 추가 `Where` `Select` 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a2e0-158">Add the following `Order By` clause between the `Where` statement and the `Select` statement of the query.</span></span> <span data-ttu-id="2a2e0-159">`Order By`절은 각 학생의 성에 따라 사전순으로 결과의 순서를 정렬 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a2e0-159">The `Order By` clause will order the results alphabetically from A to Z, according to the last name of each student.</span></span>

    ```vb
    Order By currentStudent.Last Ascending
    ```

2. <span data-ttu-id="2a2e0-160">성을 기준으로 정렬 한 다음 이름을 기준으로 정렬 하려면 두 필드를 모두 쿼리에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a2e0-160">To order by last name and then first name, add both fields to the query:</span></span>

    ```vb
    Order By currentStudent.Last Ascending, currentStudent.First Ascending
    ```

    <span data-ttu-id="2a2e0-161">또한 `Descending` Z에서 A로 정렬 하도록 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a2e0-161">You can also specify `Descending` to order from Z to A.</span></span>

3. <span data-ttu-id="2a2e0-162">CTRL + F5 키를 눌러 응용 프로그램을 빌드하고 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a2e0-162">Build and run the application by pressing CTRL+F5.</span></span> <span data-ttu-id="2a2e0-163">콘솔 창에서 결과를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a2e0-163">Note the results in the console window.</span></span>

### <a name="to-introduce-a-local-identifier"></a><span data-ttu-id="2a2e0-164">로컬 식별자를 도입 하려면</span><span class="sxs-lookup"><span data-stu-id="2a2e0-164">To introduce a local identifier</span></span>

1. <span data-ttu-id="2a2e0-165">이 섹션의 코드를 추가 하 여 쿼리 식의 로컬 식별자를 소개 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a2e0-165">Add the code in this section to introduce a local identifier in the query expression.</span></span> <span data-ttu-id="2a2e0-166">로컬 식별자에는 중간 결과가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a2e0-166">The local identifier will hold an intermediate result.</span></span> <span data-ttu-id="2a2e0-167">다음 예제에서 `name` 는 학생의 성과 이름에 대 한 연결을 보유 하는 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="2a2e0-167">In the following example, `name` is an identifier that holds a concatenation of the student's first and last names.</span></span> <span data-ttu-id="2a2e0-168">로컬 식별자를 편리 하 게 사용 하거나 여러 번 계산 되는 식의 결과를 저장 하 여 성능을 향상 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a2e0-168">A local identifier can be used for convenience, or it can enhance performance by storing the results of an expression that would otherwise be calculated multiple times.</span></span>

    [!code-vb[VbLINQWalkthrough#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQWalkthrough/VB/Class1.vb#4)]

2. <span data-ttu-id="2a2e0-169">CTRL + F5 키를 눌러 응용 프로그램을 빌드하고 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a2e0-169">Build and run the application by pressing CTRL+F5.</span></span> <span data-ttu-id="2a2e0-170">콘솔 창에서 결과를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a2e0-170">Note the results in the console window.</span></span>

### <a name="to-project-one-field-in-the-select-clause"></a><span data-ttu-id="2a2e0-171">Select 절에서 하나의 필드를 프로젝션 하려면</span><span class="sxs-lookup"><span data-stu-id="2a2e0-171">To project one field in the Select clause</span></span>

1. <span data-ttu-id="2a2e0-172">`For Each`이 섹션에서 쿼리와 루프를 추가 하 여 요소가 소스의 요소와 다른 시퀀스를 생성 하는 쿼리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2a2e0-172">Add the query and `For Each` loop from this section to create a query that produces a sequence whose elements differ from the elements in the source.</span></span> <span data-ttu-id="2a2e0-173">다음 예제에서 원본은 개체의 컬렉션 `Student` 이지만 각 개체의 한 멤버만 반환 됩니다. 성이 가르시아 섬 인 학생의 첫 번째 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="2a2e0-173">In the following example, the source is a collection of `Student` objects, but only one member of each object is returned: the first name of students whose last name is Garcia.</span></span> <span data-ttu-id="2a2e0-174">`currentStudent.First`는 문자열 이므로에서 반환 하는 시퀀스의 데이터 형식은 `studentQuery3` `IEnumerable(Of String)` 문자열의 시퀀스입니다.</span><span class="sxs-lookup"><span data-stu-id="2a2e0-174">Because `currentStudent.First` is a string, the data type of the sequence returned by `studentQuery3` is `IEnumerable(Of String)`, a sequence of strings.</span></span> <span data-ttu-id="2a2e0-175">앞의 예제와 같이에 대 한 데이터 형식의 할당은 `studentQuery3` 컴파일러에서 로컬 형식 유추를 사용 하 여 결정 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a2e0-175">As in earlier examples, the assignment of a data type for `studentQuery3` is left for the compiler to determine by using local type inference.</span></span>

    [!code-vb[VbLINQWalkthrough#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQWalkthrough/VB/Class1.vb#5)]

2. <span data-ttu-id="2a2e0-176">코드의 위에 마우스 포인터를 올려 `studentQuery3` 할당 된 형식이 인지 확인 `IEnumerable(Of String)` 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a2e0-176">Rest the mouse pointer over `studentQuery3` in your code to verify that the assigned type is `IEnumerable(Of String)`.</span></span>

3. <span data-ttu-id="2a2e0-177">CTRL + F5 키를 눌러 응용 프로그램을 빌드하고 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a2e0-177">Build and run the application by pressing CTRL+F5.</span></span> <span data-ttu-id="2a2e0-178">콘솔 창에서 결과를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a2e0-178">Note the results in the console window.</span></span>

### <a name="to-create-an-anonymous-type-in-the-select-clause"></a><span data-ttu-id="2a2e0-179">Select 절에서 익명 형식을 만들려면</span><span class="sxs-lookup"><span data-stu-id="2a2e0-179">To create an anonymous type in the Select clause</span></span>

1. <span data-ttu-id="2a2e0-180">쿼리에서 익명 형식이 사용 되는 방법을 보려면이 섹션의 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a2e0-180">Add the code from this section to see how anonymous types are used in queries.</span></span> <span data-ttu-id="2a2e0-181">이러한 쿼리는 전체 레코드 ( `currentStudent` 이전 예제의 레코드) 또는 단일 필드 (이전 섹션)가 아닌 데이터 원본에서 여러 필드를 반환 하려는 경우 쿼리에서 사용 `First` 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a2e0-181">You use them in queries when you want to return several fields from the data source rather than complete records (`currentStudent` records in previous examples) or single fields (`First` in the preceding section).</span></span> <span data-ttu-id="2a2e0-182">결과에 포함할 필드를 포함 하는 새 명명 된 형식을 정의 하는 대신 절에 필드를 지정 하면 `Select` 컴파일러에서 해당 필드를 속성으로 사용 하 여 익명 형식을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2a2e0-182">Instead of defining a new named type that contains the fields you want to include in the result, you specify the fields in the `Select` clause and the compiler creates an anonymous type with those fields as its properties.</span></span> <span data-ttu-id="2a2e0-183">자세한 내용은 [무명 형식](../../language-features/objects-and-classes/anonymous-types.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2a2e0-183">For more information, see [Anonymous Types](../../language-features/objects-and-classes/anonymous-types.md).</span></span>

    <span data-ttu-id="2a2e0-184">다음 예에서는 교육용 순위를 1에서 10 사이에 있는 seniors의 이름과 순위를 반환 하는 쿼리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2a2e0-184">The following example creates a query that returns the name and rank of seniors whose academic rank is between 1 and 10, in order of academic rank.</span></span> <span data-ttu-id="2a2e0-185">이 예제에서는 `studentQuery4` `Select` 절이 무명 형식의 인스턴스를 반환 하 고 익명 형식에 사용할 수 있는 이름이 없으므로의 형식을 유추 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a2e0-185">In this example, the type of `studentQuery4` must be inferred because the `Select` clause returns an instance of an anonymous type, and an anonymous type has no usable name.</span></span>

    [!code-vb[VbLINQWalkthrough#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQWalkthrough/VB/Class1.vb#6)]

2. <span data-ttu-id="2a2e0-186">CTRL + F5 키를 눌러 응용 프로그램을 빌드하고 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a2e0-186">Build and run the application by pressing CTRL+F5.</span></span> <span data-ttu-id="2a2e0-187">콘솔 창에서 결과를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a2e0-187">Note the results in the console window.</span></span>

## <a name="additional-examples"></a><span data-ttu-id="2a2e0-188">추가 예</span><span class="sxs-lookup"><span data-stu-id="2a2e0-188">Additional Examples</span></span>

<span data-ttu-id="2a2e0-189">기본 사항을 이해 했으므로 다음은 LINQ 쿼리의 유연성과 성능을 보여 주는 추가 예제 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="2a2e0-189">Now that you understand the basics, the following is a list of additional examples to illustrate the flexibility and power of LINQ queries.</span></span> <span data-ttu-id="2a2e0-190">각 예제 앞에는 수행 되는 작업에 대 한 간략 한 설명이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a2e0-190">Each example is preceded by a brief description of what it does.</span></span> <span data-ttu-id="2a2e0-191">각 쿼리에 대 한 쿼리 결과 변수 위로 마우스 포인터를 가져가면 유추 된 형식을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a2e0-191">Rest the mouse pointer over the query result variable for each query to see the inferred type.</span></span> <span data-ttu-id="2a2e0-192">루프를 사용 `For Each` 하 여 결과를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a2e0-192">Use a `For Each` loop to produce the results.</span></span>

[!code-vb[VbLINQWalkthrough#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQWalkthrough/VB/Class1.vb#7)]

## <a name="additional-information"></a><span data-ttu-id="2a2e0-193">추가 정보</span><span class="sxs-lookup"><span data-stu-id="2a2e0-193">Additional Information</span></span>

<span data-ttu-id="2a2e0-194">쿼리 작업의 기본 개념을 잘 알고 있으면 관심 있는 특정 형식의 LINQ 공급자에 대 한 설명서와 샘플을 읽을 준비가 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2a2e0-194">After you are familiar with the basic concepts of working with queries, you are ready to read the documentation and samples for the specific type of LINQ provider that you are interested in:</span></span>

- [<span data-ttu-id="2a2e0-195">LINQ to Objects</span><span class="sxs-lookup"><span data-stu-id="2a2e0-195">LINQ to Objects</span></span>](linq-to-objects.md)

- [<span data-ttu-id="2a2e0-196">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="2a2e0-196">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)

- [<span data-ttu-id="2a2e0-197">LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="2a2e0-197">LINQ to XML</span></span>](../../../../standard/linq/linq-xml-overview.md)

- [<span data-ttu-id="2a2e0-198">LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="2a2e0-198">LINQ to DataSet</span></span>](../../../../framework/data/adonet/linq-to-dataset.md)

## <a name="see-also"></a><span data-ttu-id="2a2e0-199">추가 정보</span><span class="sxs-lookup"><span data-stu-id="2a2e0-199">See also</span></span>

- [<span data-ttu-id="2a2e0-200">LINQ(Language-Integrated Query)(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2a2e0-200">Language-Integrated Query (LINQ) (Visual Basic)</span></span>](index.md)
- [<span data-ttu-id="2a2e0-201">Visual Basic에서 LINQ 시작</span><span class="sxs-lookup"><span data-stu-id="2a2e0-201">Getting Started with LINQ in Visual Basic</span></span>](getting-started-with-linq.md)
- [<span data-ttu-id="2a2e0-202">지역 형식 유추</span><span class="sxs-lookup"><span data-stu-id="2a2e0-202">Local Type Inference</span></span>](../../language-features/variables/local-type-inference.md)
- [<span data-ttu-id="2a2e0-203">개체 이니셜라이저: 명명된 형식 및 무명 형식</span><span class="sxs-lookup"><span data-stu-id="2a2e0-203">Object Initializers: Named and Anonymous Types</span></span>](../../language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [<span data-ttu-id="2a2e0-204">익명 형식</span><span class="sxs-lookup"><span data-stu-id="2a2e0-204">Anonymous Types</span></span>](../../language-features/objects-and-classes/anonymous-types.md)
- [<span data-ttu-id="2a2e0-205">Visual Basic의 LINQ 소개</span><span class="sxs-lookup"><span data-stu-id="2a2e0-205">Introduction to LINQ in Visual Basic</span></span>](../../language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="2a2e0-206">LINQ</span><span class="sxs-lookup"><span data-stu-id="2a2e0-206">LINQ</span></span>](../../language-features/linq/index.md)
- [<span data-ttu-id="2a2e0-207">쿼리</span><span class="sxs-lookup"><span data-stu-id="2a2e0-207">Queries</span></span>](../../../language-reference/queries/index.md)
