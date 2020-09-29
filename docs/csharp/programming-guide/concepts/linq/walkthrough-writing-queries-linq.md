---
title: '연습: C#에서 쿼리 작성(LINQ)'
description: 이 연습에서는 LINQ 쿼리 식에서 C# 언어 기능을 사용하는 방법을 보여 줍니다. 이 문서에서는 Visual Studio를 개발 환경으로 사용합니다.
ms.date: 07/20/2015
helpviewer_keywords:
- LINQ [C#], walkthroughs
- LINQ [C#], writing queries
- queries [LINQ in C#], writing
- writing LINQ queries
ms.assetid: 2962a610-419a-4276-9ec8-4b7f2af0c081
ms.openlocfilehash: bdf91f6f52a68309cfcd276b222083c8cb67a0cc
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91176242"
---
# <a name="walkthrough-writing-queries-in-c-linq"></a><span data-ttu-id="a4830-104">연습: C#에서 쿼리 작성(LINQ)</span><span class="sxs-lookup"><span data-stu-id="a4830-104">Walkthrough: Writing Queries in C# (LINQ)</span></span>

<span data-ttu-id="a4830-105">이 연습에서는 LINQ 쿼리 식을 작성하는 데 사용되는 C # 언어 기능을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a4830-105">This walkthrough demonstrates the C# language features that are used to write LINQ query expressions.</span></span>  
  
## <a name="create-a-c-project"></a><span data-ttu-id="a4830-106">C# 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="a4830-106">Create a C# Project</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a4830-107">다음 지침은 Visual Studio용입니다.</span><span class="sxs-lookup"><span data-stu-id="a4830-107">The following instructions are for Visual Studio.</span></span> <span data-ttu-id="a4830-108">다른 개발 환경을 사용하는 경우 System.Core.dll에 대한 참조와 <xref:System.Linq?displayProperty=nameWithType> 네임스페이스에 대한 `using` 지시문을 사용하여 콘솔 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a4830-108">If you are using a different development environment, create a console project with a reference to System.Core.dll and a `using` directive for the <xref:System.Linq?displayProperty=nameWithType> namespace.</span></span>  
  
#### <a name="to-create-a-project-in-visual-studio"></a><span data-ttu-id="a4830-109">Visual Studio에서 프로젝트를 만들려면</span><span class="sxs-lookup"><span data-stu-id="a4830-109">To create a project in Visual Studio</span></span>  
  
1. <span data-ttu-id="a4830-110">Visual Studio를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="a4830-110">Start Visual Studio.</span></span>  
  
2. <span data-ttu-id="a4830-111">메뉴 모음에서 **파일**, **새로 만들기**, **프로젝트**를 차례로 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a4830-111">On the menu bar, choose **File**, **New**, **Project**.</span></span>  
  
     <span data-ttu-id="a4830-112">**새 프로젝트** 대화 상자가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="a4830-112">The **New Project** dialog box opens.</span></span>  
  
3. <span data-ttu-id="a4830-113">**설치됨**, **템플릿**, **Visual C#** 을 차례로 확장하고 **콘솔 애플리케이션**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a4830-113">Expand **Installed**, expand **Templates**, expand **Visual C#**, and then choose **Console Application**.</span></span>  
  
4. <span data-ttu-id="a4830-114">**이름** 텍스트 상자에 다른 이름을 입력하거나 기본 이름을 선택한 다음 **확인** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a4830-114">In the **Name** text box, enter a different name or accept the default name, and then choose the **OK** button.</span></span>  
  
     <span data-ttu-id="a4830-115">**솔루션 탐색기**에 새 프로젝트가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4830-115">The new project appears in **Solution Explorer**.</span></span>  
  
5. <span data-ttu-id="a4830-116">프로젝트에 System.Core.dll에 대한 참조 및 <xref:System.Linq?displayProperty=nameWithType> 네임스페이스에 대한 `using` 지시문이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4830-116">Notice that your project has a reference to System.Core.dll and a `using` directive for the <xref:System.Linq?displayProperty=nameWithType> namespace.</span></span>  
  
## <a name="create-an-in-memory-data-source"></a><span data-ttu-id="a4830-117">메모리 내 데이터 소스 만들기</span><span class="sxs-lookup"><span data-stu-id="a4830-117">Create an in-Memory Data Source</span></span>  

 <span data-ttu-id="a4830-118">쿼리의 데이터 소스는 간단한 `Student` 개체 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="a4830-118">The data source for the queries is a simple list of `Student` objects.</span></span> <span data-ttu-id="a4830-119">각 `Student` 레코드에는 이름, 성 및 클래스의 테스트 점수를 나타내는 정수 배열이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4830-119">Each `Student` record has a first name, last name, and an array of integers that represents their test scores in the class.</span></span> <span data-ttu-id="a4830-120">프로젝트에 이 코드를 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="a4830-120">Copy this code into your project.</span></span> <span data-ttu-id="a4830-121">다음 특성에 주의합니다.</span><span class="sxs-lookup"><span data-stu-id="a4830-121">Note the following characteristics:</span></span>  
  
- <span data-ttu-id="a4830-122">`Student` 클래스는 자동으로 구현된 속성으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4830-122">The `Student` class consists of auto-implemented properties.</span></span>  
  
- <span data-ttu-id="a4830-123">목록의 각 학생은 개체 이니셜라이저로 초기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4830-123">Each student in the list is initialized with an object initializer.</span></span>  
  
- <span data-ttu-id="a4830-124">목록 자체는 컬렉션 이니셜라이저로 초기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4830-124">The list itself is initialized with a collection initializer.</span></span>  
  
 <span data-ttu-id="a4830-125">이 전체 데이터 구조는 생성자 또는 명시적 멤버 액세스에 대한 명시적 호출 없이 초기화되고 인스턴스화됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4830-125">This whole data structure will be initialized and instantiated without explicit calls to any constructor or explicit member access.</span></span> <span data-ttu-id="a4830-126">이러한 새로운 기능에 대한 자세한 내용은 [자동으로 구현된 속성](../../classes-and-structs/auto-implemented-properties.md) 및 [개체 및 컬렉션 이니셜라이저](../../classes-and-structs/object-and-collection-initializers.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a4830-126">For more information about these new features, see [Auto-Implemented Properties](../../classes-and-structs/auto-implemented-properties.md) and [Object and Collection Initializers](../../classes-and-structs/object-and-collection-initializers.md).</span></span>  
  
#### <a name="to-add-the-data-source"></a><span data-ttu-id="a4830-127">데이터 소스를 추가하려면</span><span class="sxs-lookup"><span data-stu-id="a4830-127">To add the data source</span></span>  
  
- <span data-ttu-id="a4830-128">`Student` 클래스 및 초기화된 학생 목록을 프로젝트의 `Program` 클래스에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a4830-128">Add the `Student` class and the initialized list of students to the `Program` class in your project.</span></span>  
  
     [!code-csharp[CsLinqGettingStarted#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#11)]  
  
#### <a name="to-add-a-new-student-to-the-students-list"></a><span data-ttu-id="a4830-129">학생 목록에 새 학생을 추가하려면</span><span class="sxs-lookup"><span data-stu-id="a4830-129">To add a new Student to the Students list</span></span>  
  
1. <span data-ttu-id="a4830-130">새 `Student`를 `Students` 목록에 추가하고 원하는 이름 및 시험 점수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a4830-130">Add a new `Student` to the `Students` list and use a name and test scores of your choice.</span></span> <span data-ttu-id="a4830-131">개체 이니셜라이저의 구문을 더 잘 알 수 있도록 새로운 학생 정보를 모두 입력해 보세요.</span><span class="sxs-lookup"><span data-stu-id="a4830-131">Try typing all the new student information in order to better learn the syntax for the object initializer.</span></span>  
  
## <a name="create-the-query"></a><span data-ttu-id="a4830-132">쿼리 만들기</span><span class="sxs-lookup"><span data-stu-id="a4830-132">Create the Query</span></span>  
  
#### <a name="to-create-a-simple-query"></a><span data-ttu-id="a4830-133">단순 쿼리를 작성하려면</span><span class="sxs-lookup"><span data-stu-id="a4830-133">To create a simple query</span></span>  
  
- <span data-ttu-id="a4830-134">애플리케이션의 `Main` 메서드에서, 실행 시 첫 번째 테스트의 점수가 90보다 큰 모든 학생의 목록을 생성하는 간단한 쿼리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a4830-134">In the application's `Main` method, create a simple query that, when it is executed, will produce a list of all students whose score on the first test was greater than 90.</span></span> <span data-ttu-id="a4830-135">전체 `Student` 개체가 선택되므로 쿼리의 형식은 `IEnumerable<Student>`입니다.</span><span class="sxs-lookup"><span data-stu-id="a4830-135">Note that because the whole `Student` object is selected, the type of the query is `IEnumerable<Student>`.</span></span> <span data-ttu-id="a4830-136">[var](../../../language-reference/keywords/var.md) 키워드를 사용하여 코드에서 암시적 형식을 사용할 수도 있지만, 결과를 명확하게 설명하기 위해 명시적 형식이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4830-136">Although the code could also use implicit typing by using the [var](../../../language-reference/keywords/var.md) keyword, explicit typing is used to clearly illustrate results.</span></span> <span data-ttu-id="a4830-137">`var`에 대한 자세한 내용은 [암시적으로 형식화된 지역 변수](../../classes-and-structs/implicitly-typed-local-variables.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a4830-137">(For more information about `var`, see [Implicitly Typed Local Variables](../../classes-and-structs/implicitly-typed-local-variables.md).)</span></span>  
  
     <span data-ttu-id="a4830-138">또한 쿼리의 범위 변수 `student`는 소스의 각 `Student`에 대한 참조로 사용되며, 각 개체에 대한 멤버 액세스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a4830-138">Note also that the query's range variable, `student`, serves as a reference to each `Student` in the source, providing member access for each object.</span></span>  
  
 [!code-csharp[CsLINQGettingStarted#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#12)]  
  
## <a name="execute-the-query"></a><span data-ttu-id="a4830-139">쿼리 실행</span><span class="sxs-lookup"><span data-stu-id="a4830-139">Execute the Query</span></span>  
  
#### <a name="to-execute-the-query"></a><span data-ttu-id="a4830-140">쿼리를 실행하려면</span><span class="sxs-lookup"><span data-stu-id="a4830-140">To execute the query</span></span>  
  
1. <span data-ttu-id="a4830-141">이제 쿼리를 실행하도록 할 `foreach` 루프를 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="a4830-141">Now write the `foreach` loop that will cause the query to execute.</span></span> <span data-ttu-id="a4830-142">다음은 코드에 대한 유의 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="a4830-142">Note the following about the code:</span></span>  
  
    - <span data-ttu-id="a4830-143">반환된 시퀀스의 각 요소는 `foreach` 루프의 반복 변수를 통해 액세스됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4830-143">Each element in the returned sequence is accessed through the iteration variable in the `foreach` loop.</span></span>  
  
    - <span data-ttu-id="a4830-144">이 변수의 형식은 `Student`이며, 쿼리 변수 형식은 `IEnumerable<Student>`과 호환됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4830-144">The type of this variable is `Student`, and the type of the query variable is compatible, `IEnumerable<Student>`.</span></span>  
  
2. <span data-ttu-id="a4830-145">이 코드를 추가한 후 애플리케이션을 빌드하고 실행하고 **콘솔** 창에서 결과를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="a4830-145">After you have added this code, build and run the application to see the results in the **Console** window.</span></span>  
  
 [!code-csharp[CsLINQGettingStarted#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#13)]  
  
#### <a name="to-add-another-filter-condition"></a><span data-ttu-id="a4830-146">다른 필터 조건을 추가하려면</span><span class="sxs-lookup"><span data-stu-id="a4830-146">To add another filter condition</span></span>  
  
1. <span data-ttu-id="a4830-147">쿼리를 구체화하기 위해 `where` 절에서 여러 부울 조건을 결합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4830-147">You can combine multiple Boolean conditions in the `where` clause in order to further refine a query.</span></span> <span data-ttu-id="a4830-148">다음 코드는 쿼리를 실행하여 첫 번째 점수가 90을 초과하고 마지막 점수가 80 미만인 학생들을 반환하도록 하는 조건을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a4830-148">The following code adds a condition so that the query returns those students whose first score was over 90 and whose last score was less than 80.</span></span> <span data-ttu-id="a4830-149">`where` 절은 다음 코드와 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="a4830-149">The `where` clause should resemble the following code.</span></span>  
  
    ```csharp
    where student.Scores[0] > 90 && student.Scores[3] < 80  
    ```  
  
     <span data-ttu-id="a4830-150">자세한 내용은 [where 절](../../../language-reference/keywords/where-clause.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a4830-150">For more information, see [where clause](../../../language-reference/keywords/where-clause.md).</span></span>  
  
## <a name="modify-the-query"></a><span data-ttu-id="a4830-151">쿼리 수정</span><span class="sxs-lookup"><span data-stu-id="a4830-151">Modify the Query</span></span>  
  
#### <a name="to-order-the-results"></a><span data-ttu-id="a4830-152">결과를 정렬하려면</span><span class="sxs-lookup"><span data-stu-id="a4830-152">To order the results</span></span>  
  
1. <span data-ttu-id="a4830-153">특정 순서로 되어 있는 경우 결과를 더 쉽게 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4830-153">It will be easier to scan the results if they are in some kind of order.</span></span> <span data-ttu-id="a4830-154">반환된 시퀀스를 소스 요소에서 액세스 가능한 필드 기준으로 정렬할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4830-154">You can order the returned sequence by any accessible field in the source elements.</span></span> <span data-ttu-id="a4830-155">예를 들어, 다음 `orderby` 절은 각 학생의 성에 따라 결과를 사전순으로 정렬합니다.</span><span class="sxs-lookup"><span data-stu-id="a4830-155">For example, the following `orderby` clause orders the results in alphabetical order from A to Z according to the last name of each student.</span></span> <span data-ttu-id="a4830-156">`where` 문 바로 다음과 `select` 문 앞에서 다음 `orderby` 절을 쿼리에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a4830-156">Add the following `orderby` clause to your query, right after the `where` statement and before the `select` statement:</span></span>  
  
    ```csharp
    orderby student.Last ascending  
    ```  
  
2. <span data-ttu-id="a4830-157">이제 가장 높은 점수에서 가장 낮은 점수까지 첫 번째 테스트의 점수에 따라 역순으로 결과를 정렬하도록 `orderby` 절을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="a4830-157">Now change the `orderby` clause so that it orders the results in reverse order according to the score on the first test, from the highest score to the lowest score.</span></span>  
  
    ```csharp
    orderby student.Scores[0] descending  
    ```  
  
3. <span data-ttu-id="a4830-158">점수를 볼 수 있도록 `WriteLine` 형식 문자열을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="a4830-158">Change the `WriteLine` format string so that you can see the scores:</span></span>  
  
    ```csharp
    Console.WriteLine("{0}, {1} {2}", student.Last, student.First, student.Scores[0]);  
    ```  
  
     <span data-ttu-id="a4830-159">자세한 내용은 [orderby 절](../../../language-reference/keywords/orderby-clause.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a4830-159">For more information, see [orderby clause](../../../language-reference/keywords/orderby-clause.md).</span></span>  
  
#### <a name="to-group-the-results"></a><span data-ttu-id="a4830-160">결과를 그룹화하려면</span><span class="sxs-lookup"><span data-stu-id="a4830-160">To group the results</span></span>  
  
1. <span data-ttu-id="a4830-161">그룹화는 쿼리 식의 강력한 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="a4830-161">Grouping is a powerful capability in query expressions.</span></span> <span data-ttu-id="a4830-162">그룹 절이 있는 쿼리는 그룹 시퀀스를 생성하며, 각 그룹 자체는 `Key` 및 해당 그룹의 모든 멤버로 구성된 시퀀스를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="a4830-162">A query with a group clause produces a sequence of groups, and each group itself contains a `Key` and a sequence that consists of all the members of that group.</span></span> <span data-ttu-id="a4830-163">다음과 같은 새 쿼리는 학생 성의 첫 글자를 키로 사용하여 학생들을 그룹화합니다.</span><span class="sxs-lookup"><span data-stu-id="a4830-163">The following new query groups the students by using the first letter of their last name as the key.</span></span>  
  
     [!code-csharp[CsLINQGettingStarted#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#14)]  
  
2. <span data-ttu-id="a4830-164">이제 쿼리 형식이 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a4830-164">Note that the type of the query has now changed.</span></span> <span data-ttu-id="a4830-165">이제 쿼리를 실행하면 `char` 형식을 키로 가지고 있고 `Student` 개체의 시퀀스를 가지고 있는 그룹의 시퀀스가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4830-165">It now produces a sequence of groups that have a `char` type as a key, and a sequence of `Student` objects.</span></span> <span data-ttu-id="a4830-166">쿼리 형식이 변경되었으므로 다음 코드는 `foreach` 실행 루프도 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="a4830-166">Because the type of the query has changed, the following code changes the `foreach` execution loop also:</span></span>  
  
     [!code-csharp[CsLINQGettingStarted#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#15)]  
  
3. <span data-ttu-id="a4830-167">애플리케이션을 실행하고 **콘솔** 창에서 결과를 봅니다.</span><span class="sxs-lookup"><span data-stu-id="a4830-167">Run the application and view the results in the **Console** window.</span></span>  
  
     <span data-ttu-id="a4830-168">자세한 내용은 [group 절](../../../language-reference/keywords/group-clause.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a4830-168">For more information, see [group clause](../../../language-reference/keywords/group-clause.md).</span></span>  
  
#### <a name="to-make-the-variables-implicitly-typed"></a><span data-ttu-id="a4830-169">변수를 암시적으로 형식화하려면</span><span class="sxs-lookup"><span data-stu-id="a4830-169">To make the variables implicitly typed</span></span>  
  
1. <span data-ttu-id="a4830-170">`IGroupings`의 `IEnumerables`를 명시적으로 코딩하는 작업은 지루할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4830-170">Explicitly coding `IEnumerables` of `IGroupings` can quickly become tedious.</span></span> <span data-ttu-id="a4830-171">`var`을 사용하여 동일한 쿼리 및 `foreach` 루프를 훨씬 더 편리하게 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4830-171">You can write the same query and `foreach` loop much more conveniently by using `var`.</span></span> <span data-ttu-id="a4830-172">`var` 키워드는 개체 형식을 변경하지 않고, 형식을 추론하도록 컴파일러에 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="a4830-172">The `var` keyword does not change the types of your objects; it just instructs the compiler to infer the types.</span></span> <span data-ttu-id="a4830-173">`studentQuery`의 형식 및 `group` 반복 변수를 `var`로 변경하고 쿼리를 다시 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a4830-173">Change the type of `studentQuery` and the iteration variable `group` to `var` and rerun the query.</span></span> <span data-ttu-id="a4830-174">내부 `foreach` 루프에서 반복 변수의 형식은 여전히 `Student`로 지정되며 쿼리는 이전과 마찬가지로 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="a4830-174">Note that in the inner `foreach` loop, the iteration variable is still typed as `Student`, and the query works just as before.</span></span> <span data-ttu-id="a4830-175">`s` 반복 변수를 `var`로 변경하고 쿼리를 다시 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a4830-175">Change the `s` iteration variable to `var` and run the query again.</span></span> <span data-ttu-id="a4830-176">정확히 동일한 결과가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4830-176">You see that you get exactly the same results.</span></span>  
  
     [!code-csharp[CsLINQGettingStarted#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#16)]  
  
     <span data-ttu-id="a4830-177">[var](../../../language-reference/keywords/var.md)에 대한 자세한 내용은 [암시적으로 형식화된 지역 변수](../../classes-and-structs/implicitly-typed-local-variables.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a4830-177">For more information about [var](../../../language-reference/keywords/var.md), see [Implicitly Typed Local Variables](../../classes-and-structs/implicitly-typed-local-variables.md).</span></span>  
  
#### <a name="to-order-the-groups-by-their-key-value"></a><span data-ttu-id="a4830-178">키 값을 기준으로 그룹을 정렬하려면</span><span class="sxs-lookup"><span data-stu-id="a4830-178">To order the groups by their key value</span></span>  
  
1. <span data-ttu-id="a4830-179">이전 쿼리를 실행하면 그룹이 사전순으로 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a4830-179">When you run the previous query, you notice that the groups are not in alphabetical order.</span></span> <span data-ttu-id="a4830-180">이를 변경하려면 `group` 절 뒤에 `orderby` 절을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4830-180">To change this, you must provide an `orderby` clause after the `group` clause.</span></span> <span data-ttu-id="a4830-181">그러나 `orderby` 절을 사용하려면 우선 `group` 절로 만든 그룹에 대한 참조 역할을 하는 식별자가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="a4830-181">But to use an `orderby` clause, you first need an identifier that serves as a reference to the groups created by the `group` clause.</span></span> <span data-ttu-id="a4830-182">다음과 같이 `into` 키워드를 사용하여 식별자를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a4830-182">You provide the identifier by using the `into` keyword, as follows:</span></span>  
  
     [!code-csharp[csLINQGettingStarted#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#17)]  
  
     <span data-ttu-id="a4830-183">이 쿼리를 실행하면 이제 그룹이 사전순으로 정렬되는 것을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4830-183">When you run this query, you will see the groups are now sorted in alphabetical order.</span></span>  
  
#### <a name="to-introduce-an-identifier-by-using-let"></a><span data-ttu-id="a4830-184">let을 사용하여 식별자를 소개하려면</span><span class="sxs-lookup"><span data-stu-id="a4830-184">To introduce an identifier by using let</span></span>  
  
1. <span data-ttu-id="a4830-185">`let` 키워드를 사용하여 쿼리 식의 식 결과에 대한 식별자를 소개할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4830-185">You can use the `let` keyword to introduce an identifier for any expression result in the query expression.</span></span> <span data-ttu-id="a4830-186">이 식별자는 다음 예제에서처럼 편리하게 사용할 수도 있고, 여러 번 계산할 필요가 없도록 표현식의 결과를 저장하여 성능을 향상시킬 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4830-186">This identifier can be a convenience, as in the following example, or it can enhance performance by storing the results of an expression so that it does not have to be calculated multiple times.</span></span>  
  
     [!code-csharp[csLINQGettingStarted#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#18)]  
  
     <span data-ttu-id="a4830-187">자세한 내용은 [let 절](../../../language-reference/keywords/let-clause.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a4830-187">For more information, see [let clause](../../../language-reference/keywords/let-clause.md).</span></span>  
  
#### <a name="to-use-method-syntax-in-a-query-expression"></a><span data-ttu-id="a4830-188">쿼리 식에서 메서드 구문을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="a4830-188">To use method syntax in a query expression</span></span>  
  
1. <span data-ttu-id="a4830-189">[LINQ의 쿼리 구문 및 메서드 구문](./query-syntax-and-method-syntax-in-linq.md)에 설명된 대로 일부 쿼리 작업은 메서드 구문을 사용해야만 표현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4830-189">As described in [Query Syntax and Method Syntax in LINQ](./query-syntax-and-method-syntax-in-linq.md), some query operations can only be expressed by using method syntax.</span></span> <span data-ttu-id="a4830-190">다음 코드는 소스 시퀀스의 각 `Student`에 대한 총 점수를 계산한 다음, 해당 쿼리의 결과에 대해 `Average()` 메서드를 호출하여 클래스의 평균 점수를 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="a4830-190">The following code calculates the total score for each `Student` in the source sequence, and then calls the `Average()` method on the results of that query to calculate the average score of the class.</span></span>
  
     [!code-csharp[csLINQGettingStarted#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#19)]  
  
#### <a name="to-transform-or-project-in-the-select-clause"></a><span data-ttu-id="a4830-191">select 절에서 변환 또는 프로젝션하려면</span><span class="sxs-lookup"><span data-stu-id="a4830-191">To transform or project in the select clause</span></span>  
  
1. <span data-ttu-id="a4830-192">쿼리가 소스 시퀀스의 요소와 다른 요소를 갖는 시퀀스를 생성하는 것은 매우 일반적입니다.</span><span class="sxs-lookup"><span data-stu-id="a4830-192">It is very common for a query to produce a sequence whose elements differ from the elements in the source sequences.</span></span> <span data-ttu-id="a4830-193">이전 쿼리 및 실행 루프를 삭제하거나 주석으로 처리하고 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="a4830-193">Delete or comment out your previous query and execution loop, and replace it with the following code.</span></span> <span data-ttu-id="a4830-194">쿼리는 문자열 시퀀스(`Students` 아님)를 반환하며 이 사실은 `foreach` 루프에 반영됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4830-194">Note that the query returns a sequence of strings (not `Students`), and this fact is reflected in the `foreach` loop.</span></span>  
  
     [!code-csharp[csLINQGettingStarted#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#20)]  
  
2. <span data-ttu-id="a4830-195">이 연습의 앞부분에 있는 코드는 평균 클래스 점수가 약 334임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a4830-195">Code earlier in this walkthrough indicated that the average class score is approximately 334.</span></span> <span data-ttu-id="a4830-196">총점이 클래스 평균보다 큰 `Students`의 시퀀스를 `Student ID`와 함께 생성하려면 `select` 문에서 무명 형식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4830-196">To produce a sequence of `Students` whose total score is greater than the class average, together with their `Student ID`, you can use an anonymous type in the `select` statement:</span></span>  
  
     [!code-csharp[csLINQGettingStarted#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#21)]  
  
## <a name="next-steps"></a><span data-ttu-id="a4830-197">다음 단계</span><span class="sxs-lookup"><span data-stu-id="a4830-197">Next Steps</span></span>  

 <span data-ttu-id="a4830-198">C#에서 쿼리 작업의 기본 사항에 익숙해지면 관심이 있는 특정 LINQ 공급자 형식에 대한 설명서와 샘플을 읽을 준비가 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a4830-198">After you are familiar with the basic aspects of working with queries in C#, you are ready to read the documentation and samples for the specific type of LINQ provider you are interested in:</span></span>  
  
 [<span data-ttu-id="a4830-199">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="a4830-199">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)  
  
 [<span data-ttu-id="a4830-200">LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="a4830-200">LINQ to DataSet</span></span>](../../../../framework/data/adonet/linq-to-dataset.md)  
  
 [<span data-ttu-id="a4830-201">LINQ to XML(C#)</span><span class="sxs-lookup"><span data-stu-id="a4830-201">LINQ to XML (C#)</span></span>](../../../../standard/linq/linq-xml-overview.md)  
  
 [<span data-ttu-id="a4830-202">LINQ to Objects(C#)</span><span class="sxs-lookup"><span data-stu-id="a4830-202">LINQ to Objects (C#)</span></span>](./linq-to-objects.md)  
  
## <a name="see-also"></a><span data-ttu-id="a4830-203">참조</span><span class="sxs-lookup"><span data-stu-id="a4830-203">See also</span></span>

- [<span data-ttu-id="a4830-204">LINQ(Language-Integrated Query)(C#)</span><span class="sxs-lookup"><span data-stu-id="a4830-204">Language-Integrated Query (LINQ) (C#)</span></span>](./index.md)
- [<span data-ttu-id="a4830-205">LINQ 쿼리 식</span><span class="sxs-lookup"><span data-stu-id="a4830-205">LINQ Query Expressions</span></span>](../../../linq/index.md)
