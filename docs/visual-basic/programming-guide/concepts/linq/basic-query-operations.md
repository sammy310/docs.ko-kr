---
title: 기본 쿼리 작업
ms.date: 07/20/2015
helpviewer_keywords:
- data sources [LINQ in Visual Basic]
- Join clause [LINQ in Visual Basic]
- ordering data [LINQ in Visual Basic]
- projections [LINQ in Visual Basic]
- LINQ [Visual Basic], query operations
- Order By clause [LINQ in Visual Basic]
- joining data [LINQ in Visual Basic]
- queries [LINQ in Visual Basic], basic operations
- selecting data [LINQ in Visual Basic]
- Group By clause [LINQ in Visual Basic]
- grouping data [LINQ in Visual Basic]
- Select clause [LINQ in Visual Basic]
ms.assetid: 1146f6d0-fcb8-4f4d-8223-c9db52620d21
ms.openlocfilehash: efae72c65ad67b4a1b157b67dcc4d4d65f31f77b
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2020
ms.locfileid: "78266380"
---
# <a name="basic-query-operations-visual-basic"></a><span data-ttu-id="345b4-102">기본 쿼리 작업(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="345b4-102">Basic Query Operations (Visual Basic)</span></span>
<span data-ttu-id="345b4-103">이 항목에서는 Visual Basic의 LINQ(언어 통합 쿼리) 식및 쿼리에서 수행하는 일반적인 작업 의 일부에 대해 간략하게 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="345b4-103">This topic provides a brief introduction to Language-Integrated Query (LINQ) expressions in Visual Basic, and to some of the typical kinds of operations that you perform in a query.</span></span> <span data-ttu-id="345b4-104">자세한 내용은 아래 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="345b4-104">For more information, see the following topics:</span></span>  
  
 [<span data-ttu-id="345b4-105">Visual Basic의 LINQ 소개</span><span class="sxs-lookup"><span data-stu-id="345b4-105">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
  
 [<span data-ttu-id="345b4-106">쿼리</span><span class="sxs-lookup"><span data-stu-id="345b4-106">Queries</span></span>](../../../../visual-basic/language-reference/queries/index.md)  
  
 [<span data-ttu-id="345b4-107">연습: Visual Basic에서 쿼리 작성</span><span class="sxs-lookup"><span data-stu-id="345b4-107">Walkthrough: Writing Queries in Visual Basic</span></span>](../../../../visual-basic/programming-guide/concepts/linq/walkthrough-writing-queries.md)  
  
## <a name="specifying-the-data-source-from"></a><span data-ttu-id="345b4-108">데이터 원본 지정(에서)</span><span class="sxs-lookup"><span data-stu-id="345b4-108">Specifying the Data Source (From)</span></span>  
 <span data-ttu-id="345b4-109">LINQ 쿼리에서 첫 번째 단계는 쿼리할 데이터 원본을 지정하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="345b4-109">In a LINQ query, the first step is to specify the data source that you want to query.</span></span> <span data-ttu-id="345b4-110">따라서 쿼리의 절이 `From` 항상 먼저 옵니다.</span><span class="sxs-lookup"><span data-stu-id="345b4-110">Therefore, the `From` clause in a query always comes first.</span></span> <span data-ttu-id="345b4-111">쿼리 연산자는 소스 유형에 따라 결과를 선택하고 셰이핑합니다.</span><span class="sxs-lookup"><span data-stu-id="345b4-111">Query operators select and shape the result based on the type of the source.</span></span>  
  
 [!code-vb[VbLINQBasicOps#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#1)]  
  
 <span data-ttu-id="345b4-112">절은 `From` 데이터 원본 `customers`및 범위 *변수를* `cust`지정합니다.</span><span class="sxs-lookup"><span data-stu-id="345b4-112">The `From` clause specifies the data source, `customers`, and a *range variable*, `cust`.</span></span> <span data-ttu-id="345b4-113">range 변수는 쿼리 식에서 실제 반복이 발생하지 않는다는 점을 제외하면 루프 반복 변수와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="345b4-113">The range variable is like a loop iteration variable, except that in a query expression, no actual iteration occurs.</span></span> <span data-ttu-id="345b4-114">루프를 사용하여 `For Each` 쿼리가 실행되는 경우 range 변수는 에서 각 연속 요소에 `customers`대한 참조 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="345b4-114">When the query is executed, often by using a `For Each` loop, the range variable serves as a reference to each successive element in `customers`.</span></span> <span data-ttu-id="345b4-115">컴파일러에서 `cust` 형식을 유추할 수 있으므로 명시적으로 지정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="345b4-115">Because the compiler can infer the type of `cust`, you do not have to specify it explicitly.</span></span> <span data-ttu-id="345b4-116">명시적 입력 없이 작성된 쿼리의 예는 [쿼리 작업(Visual Basic)에서 관계 유형 참조를](../../../../visual-basic/programming-guide/concepts/linq/type-relationships-in-query-operations.md)참조합니다.</span><span class="sxs-lookup"><span data-stu-id="345b4-116">For examples of queries written with and without explicit typing, see [Type Relationships in Query Operations (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/type-relationships-in-query-operations.md).</span></span>  
  
 <span data-ttu-id="345b4-117">시각적 기본에서 절을 `From` 사용하는 방법에 대한 자세한 내용은 From [절을](../../../../visual-basic/language-reference/queries/from-clause.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="345b4-117">For more information about how to use the `From` clause in Visual Basic, see [From Clause](../../../../visual-basic/language-reference/queries/from-clause.md).</span></span>  
  
## <a name="filtering-data-where"></a><span data-ttu-id="345b4-118">데이터 필터링(위치)</span><span class="sxs-lookup"><span data-stu-id="345b4-118">Filtering Data (Where)</span></span>  
 <span data-ttu-id="345b4-119">가장 일반적인 쿼리 작업은 부울 식의 형태로 필터를 적용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="345b4-119">Probably the most common query operation is applying a filter in the form of a Boolean expression.</span></span> <span data-ttu-id="345b4-120">그런 다음 쿼리는 식이 true인 요소만 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="345b4-120">The query then returns only those elements for which the expression is true.</span></span> <span data-ttu-id="345b4-121">절은 `Where` 필터링을 수행하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="345b4-121">A `Where` clause is used to perform the filtering.</span></span> <span data-ttu-id="345b4-122">필터는 데이터 원본의 요소들이 결과 시퀀스에 포함하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="345b4-122">The filter specifies which elements in the data source to include in the resulting sequence.</span></span> <span data-ttu-id="345b4-123">다음 예제에서는 런던에 주소가 있는 고객만 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="345b4-123">In the following example, only those customers who have an address in London are included.</span></span>  
  
 [!code-vb[VbLINQBasicOps#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#2)]  
  
 <span data-ttu-id="345b4-124">논리 연산자(예: `And` `Or` 및 필터 식을 `Where` 절)에 결합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="345b4-124">You can use logical operators such as `And` and `Or` to combine filter expressions in a `Where` clause.</span></span> <span data-ttu-id="345b4-125">예를 들어 런던 출신이고 이름이 Devon인 고객만 반환하려면 다음 코드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="345b4-125">For example, to return only those customers who are from London and whose name is Devon, use the following code:</span></span>  
  
```vb  
Where cust.City = "London" And cust.Name = "Devon"
```  
  
 <span data-ttu-id="345b4-126">런던 또는 파리에서 반품하는 고객을 반품하려면 다음 코드를 사용하십시오.</span><span class="sxs-lookup"><span data-stu-id="345b4-126">To return customers from London or Paris, use the following code:</span></span>  
  
```vb  
Where cust.City = "London" Or cust.City = "Paris"
```  
  
 <span data-ttu-id="345b4-127">시각적 기본에서 절을 `Where` 사용하는 방법에 대한 자세한 내용은 Where [절을](../../../../visual-basic/language-reference/queries/where-clause.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="345b4-127">For more information about how to use the `Where` clause in Visual Basic, see [Where Clause](../../../../visual-basic/language-reference/queries/where-clause.md).</span></span>  
  
## <a name="ordering-data-order-by"></a><span data-ttu-id="345b4-128">데이터 주문(주문별)</span><span class="sxs-lookup"><span data-stu-id="345b4-128">Ordering Data (Order By)</span></span>  
 <span data-ttu-id="345b4-129">반환된 데이터를 특정 순서로 정렬하는 것이 편리한 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="345b4-129">It often is convenient to sort returned data into a particular order.</span></span> <span data-ttu-id="345b4-130">이 `Order By` 절은 반환된 시퀀스의 요소를 지정된 필드 또는 필드에서 정렬하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="345b4-130">The `Order By` clause will cause the elements in the returned sequence to be sorted on a specified field or fields.</span></span> <span data-ttu-id="345b4-131">예를 들어 다음 쿼리는 속성을 기반으로 `Name` 결과를 정렬합니다.</span><span class="sxs-lookup"><span data-stu-id="345b4-131">For example, the following query sorts the results based on the `Name` property.</span></span> <span data-ttu-id="345b4-132">문자열이기 때문에 `Name` 반환된 데이터는 A에서 Z로 알파벳 순으로 정렬됩니다.</span><span class="sxs-lookup"><span data-stu-id="345b4-132">Because `Name` is a string, the returned data will be sorted alphabetically, from A to Z.</span></span>  
  
 [!code-vb[VbLINQBasicOps#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#3)]  
  
 <span data-ttu-id="345b4-133">결과를 역순으로 정렬하려면 `Order By...Descending` 절을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="345b4-133">To order the results in reverse order, from Z to A, use the `Order By...Descending` clause.</span></span> <span data-ttu-id="345b4-134">기본값은 `Ascending` 둘 `Ascending` `Descending` 중 어느 쪽도 지정되지 않은 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="345b4-134">The default is `Ascending` when neither `Ascending` nor `Descending` is specified.</span></span>  
  
 <span data-ttu-id="345b4-135">시각적 기본에서 `Order By` 절을 사용하는 방법에 대한 자세한 내용은 [절별 순서를](../../../../visual-basic/language-reference/queries/order-by-clause.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="345b4-135">For more information about how to use the `Order By` clause in Visual Basic, see [Order By Clause](../../../../visual-basic/language-reference/queries/order-by-clause.md).</span></span>  
  
## <a name="selecting-data-select"></a><span data-ttu-id="345b4-136">데이터 선택(선택)</span><span class="sxs-lookup"><span data-stu-id="345b4-136">Selecting Data (Select)</span></span>  
 <span data-ttu-id="345b4-137">이 `Select` 절은 반환된 요소의 양식과 내용을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="345b4-137">The `Select` clause specifies the form and content of returned elements.</span></span> <span data-ttu-id="345b4-138">예를 들어 결과가 전체 `Customer` 개체, 하나의 `Customer` 속성, 속성 하위 집합, 다양한 데이터 원본의 속성 조합 또는 계산에 기반한 새 결과 유형으로 구성되는지 여부를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="345b4-138">For example, you can specify whether your results will consist of complete `Customer` objects, just one `Customer` property, a subset of properties, a combination of properties from various data sources, or some new result type based on a computation.</span></span> <span data-ttu-id="345b4-139">`Select` 절이 소스 요소의 복사본이 아닌 다른 항목을 생성하는 경우 이 작업을 *프로젝션*이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="345b4-139">When the `Select` clause produces something other than a copy of the source element, the operation is called a *projection*.</span></span>  
  
 <span data-ttu-id="345b4-140">전체 `Customer` 개체로 구성된 컬렉션을 검색하려면 range 변수 자체를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="345b4-140">To retrieve a collection that consists of complete `Customer` objects, select the range variable itself:</span></span>  
  
 [!code-vb[VbLINQBasicOps#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#4)]  
  
 <span data-ttu-id="345b4-141">`Customer` 인스턴스에 필드가 많은 큰 개체이고 검색하려는 모든 개체가 이름인 경우 `cust.Name`다음 예제와 같이 을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="345b4-141">If a `Customer` instance is a large object that has many fields, and all that you want to retrieve is the name, you can select `cust.Name`, as shown in the following example.</span></span> <span data-ttu-id="345b4-142">로컬 형식 추론은 이로 인해 결과 형식이 `Customer` 개체 컬렉션에서 문자열 컬렉션으로 변경된다는 것을 인식합니다.</span><span class="sxs-lookup"><span data-stu-id="345b4-142">Local type inference recognizes that this changes the result type from a collection of `Customer` objects to a collection of strings.</span></span>  
  
 [!code-vb[VbLINQBasicOps#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#5)]  
  
 <span data-ttu-id="345b4-143">데이터 원본에서 여러 필드를 선택하려면 다음 두 가지 를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="345b4-143">To select multiple fields from the data source, you have two choices:</span></span>  
  
- <span data-ttu-id="345b4-144">절에서 `Select` 결과에 포함할 필드를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="345b4-144">In the `Select` clause, specify the fields you want to include in the result.</span></span> <span data-ttu-id="345b4-145">컴파일러는 해당 필드가 있는 익명 형식을 속성으로 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="345b4-145">The compiler will define an anonymous type that has those fields as its properties.</span></span> <span data-ttu-id="345b4-146">자세한 내용은 [무명 형식](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="345b4-146">For more information, see [Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span></span>  
  
     <span data-ttu-id="345b4-147">다음 예제에서 반환된 요소는 익명 형식의 인스턴스이므로 코드의 다른 위치에 있는 이름으로 형식을 참조할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="345b4-147">Because the returned elements in the following example are instances of an anonymous type, you cannot refer to the type by name elsewhere in your code.</span></span> <span data-ttu-id="345b4-148">형식에 대한 컴파일러 지정 이름에는 일반 Visual Basic 코드에서 유효하지 않은 문자가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="345b4-148">The compiler-designated name for the type contains characters that are not valid in normal Visual Basic code.</span></span> <span data-ttu-id="345b4-149">다음 예제에서 쿼리에서 `londonCusts4` 반환되는 컬렉션의 요소는 익명 형식의 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="345b4-149">In the following example, the elements in the collection that is returned by the query in `londonCusts4` are instances of an anonymous type</span></span>  
  
     [!code-vb[VbLINQBasicOps#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#6)]  
  
     <span data-ttu-id="345b4-150">또는</span><span class="sxs-lookup"><span data-stu-id="345b4-150">-or-</span></span>  
  
- <span data-ttu-id="345b4-151">결과에 포함할 특정 필드를 포함하는 명명된 형식을 정의하고 `Select` 절에서 형식의 인스턴스를 만들고 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="345b4-151">Define a named type that contains the particular fields that you want to include in the result, and create and initialize instances of the type in the `Select` clause.</span></span> <span data-ttu-id="345b4-152">반환되는 컬렉션 외부에서 개별 결과를 사용해야 하거나 메서드 호출에서 매개 변수로 전달해야 하는 경우에만 이 옵션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="345b4-152">Use this option only if you have to use individual results outside the collection in which they are returned, or if you have to pass them as parameters in method calls.</span></span> <span data-ttu-id="345b4-153">다음 예제의 `londonCusts5` 유형은 IEnumerable(네임폰)입니다.</span><span class="sxs-lookup"><span data-stu-id="345b4-153">The type of `londonCusts5` in the following example is IEnumerable(Of NamePhone).</span></span>  
  
     [!code-vb[VbLINQBasicOps#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#7)]  
  
     [!code-vb[VbLINQBasicOps#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#8)]  
  
 <span data-ttu-id="345b4-154">시각적 기본에서 절을 `Select` 사용하는 방법에 대한 자세한 내용은 절 [선택](../../../../visual-basic/language-reference/queries/select-clause.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="345b4-154">For more information about how to use the `Select` clause in Visual Basic, see [Select Clause](../../../../visual-basic/language-reference/queries/select-clause.md).</span></span>  
  
## <a name="joining-data-join-and-group-join"></a><span data-ttu-id="345b4-155">조인 데이터(조인 및 그룹 조인)</span><span class="sxs-lookup"><span data-stu-id="345b4-155">Joining Data (Join and Group Join)</span></span>  
 <span data-ttu-id="345b4-156">여러 가지 방법으로 절에 두 `From` 개 이상의 데이터 원본을 결합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="345b4-156">You can combine more than one data source in the `From` clause in several ways.</span></span> <span data-ttu-id="345b4-157">예를 들어 다음 코드는 두 데이터 원본을 사용하고 결과에서 두 데이터 소스의 속성을 암시적으로 결합합니다.</span><span class="sxs-lookup"><span data-stu-id="345b4-157">For example, the following code uses two data sources and implicitly combines properties from both of them in the result.</span></span> <span data-ttu-id="345b4-158">쿼리는 이름이 모음으로 시작하는 학생을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="345b4-158">The query selects students whose last names start with a vowel.</span></span>  
  
 [!code-vb[VbLINQBasicOps#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#9)]  
  
> [!NOTE]
> <span data-ttu-id="345b4-159">항목 목록 [만들기 방법:](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md)에서 만든 학생 목록과 함께 이 코드를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="345b4-159">You can run this code with the list of students created in [How to: Create a List of Items](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md).</span></span>  
  
 <span data-ttu-id="345b4-160">키워드는 `Join` SQL에서와 `INNER JOIN` 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="345b4-160">The `Join` keyword is equivalent to an `INNER JOIN` in SQL.</span></span> <span data-ttu-id="345b4-161">두 컬렉션의 요소 간에 일치하는 키 값을 기반으로 두 컬렉션을 결합합니다.</span><span class="sxs-lookup"><span data-stu-id="345b4-161">It combines two collections based on matching key values between elements in the two collections.</span></span> <span data-ttu-id="345b4-162">쿼리는 일치하는 키 값이 있는 컬렉션 요소의 전체 또는 일부를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="345b4-162">The query returns all or part of the collection elements that have matching key values.</span></span> <span data-ttu-id="345b4-163">예를 들어 다음 코드는 이전 암시적 조인의 작업을 복제합니다.</span><span class="sxs-lookup"><span data-stu-id="345b4-163">For example, the following code duplicates the action of the previous implicit join.</span></span>  
  
 [!code-vb[VbLINQBasicOps#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#10)]  
  
 <span data-ttu-id="345b4-164">`Group Join`SQL에서와 마찬가지로 컬렉션을 단일 계층 적 컬렉션으로 `LEFT JOIN` 결합합니다.</span><span class="sxs-lookup"><span data-stu-id="345b4-164">`Group Join` combines collections into a single hierarchical collection, just like a `LEFT JOIN` in SQL.</span></span> <span data-ttu-id="345b4-165">자세한 내용은 [조인 절](../../../../visual-basic/language-reference/queries/join-clause.md) 및 [그룹 조인 절을](../../../../visual-basic/language-reference/queries/group-join-clause.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="345b4-165">For more information, see [Join Clause](../../../../visual-basic/language-reference/queries/join-clause.md) and [Group Join Clause](../../../../visual-basic/language-reference/queries/group-join-clause.md).</span></span>  
  
## <a name="grouping-data-group-by"></a><span data-ttu-id="345b4-166">데이터 그룹화(그룹별)</span><span class="sxs-lookup"><span data-stu-id="345b4-166">Grouping Data (Group By)</span></span>  
 <span data-ttu-id="345b4-167">`Group By` 요소의 하나 이상의 필드에 따라 쿼리 결과의 요소를 그룹화하는 절을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="345b4-167">You can add a `Group By` clause to group the elements in a query result according to one or more fields of the elements.</span></span> <span data-ttu-id="345b4-168">예를 들어 다음 코드는 학생학생을 수업 연도별로 그룹합니다.</span><span class="sxs-lookup"><span data-stu-id="345b4-168">For example, the following code groups students by class year.</span></span>  
  
 [!code-vb[VbLINQBasicOps#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#11)]  
  
 <span data-ttu-id="345b4-169">[방법: 항목 목록 만들기에서](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md)만든 학생 목록을 사용하여 이 코드를 실행하는 경우 `For Each` 명령문의 출력은 다음과 같은 것입니다.</span><span class="sxs-lookup"><span data-stu-id="345b4-169">If you run this code using the list of students created in [How to: Create a List of Items](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md), the output from the `For Each` statement is:</span></span>  
  
 <span data-ttu-id="345b4-170">연도: 주니어</span><span class="sxs-lookup"><span data-stu-id="345b4-170">Year: Junior</span></span>  
  
 <span data-ttu-id="345b4-171">터커, 마이클</span><span class="sxs-lookup"><span data-stu-id="345b4-171">Tucker, Michael</span></span>  
  
 <span data-ttu-id="345b4-172">가르시아, 휴고</span><span class="sxs-lookup"><span data-stu-id="345b4-172">Garcia, Hugo</span></span>  
  
 <span data-ttu-id="345b4-173">가르시아, 데브라</span><span class="sxs-lookup"><span data-stu-id="345b4-173">Garcia, Debra</span></span>  
  
 <span data-ttu-id="345b4-174">터커, 랜스</span><span class="sxs-lookup"><span data-stu-id="345b4-174">Tucker, Lance</span></span>  
  
 <span data-ttu-id="345b4-175">연도: 시니어</span><span class="sxs-lookup"><span data-stu-id="345b4-175">Year: Senior</span></span>  
  
 <span data-ttu-id="345b4-176">오멜첸코, 스베틀라나</span><span class="sxs-lookup"><span data-stu-id="345b4-176">Omelchenko, Svetlana</span></span>  
  
 <span data-ttu-id="345b4-177">오사다 시</span><span class="sxs-lookup"><span data-stu-id="345b4-177">Osada, Michiko</span></span>  
  
 <span data-ttu-id="345b4-178">파쿠리, 파디</span><span class="sxs-lookup"><span data-stu-id="345b4-178">Fakhouri, Fadi</span></span>  
  
 <span data-ttu-id="345b4-179">펑, 하잉</span><span class="sxs-lookup"><span data-stu-id="345b4-179">Feng, Hanying</span></span>  
  
 <span data-ttu-id="345b4-180">애덤스, 테리</span><span class="sxs-lookup"><span data-stu-id="345b4-180">Adams, Terry</span></span>  
  
 <span data-ttu-id="345b4-181">연도: 신입생</span><span class="sxs-lookup"><span data-stu-id="345b4-181">Year: Freshman</span></span>  
  
 <span data-ttu-id="345b4-182">모텐슨, 스벤</span><span class="sxs-lookup"><span data-stu-id="345b4-182">Mortensen, Sven</span></span>  
  
 <span data-ttu-id="345b4-183">가르시아, 세자르</span><span class="sxs-lookup"><span data-stu-id="345b4-183">Garcia, Cesar</span></span>  
  
 <span data-ttu-id="345b4-184">다음 코드에 표시된 변형은 수업 연도를 정렬한 다음 매년 학생에게 성으로 주문합니다.</span><span class="sxs-lookup"><span data-stu-id="345b4-184">The variation shown in the following code orders the class years, and then orders the students within each year by last name.</span></span>  
  
 [!code-vb[VbLINQBasicOps#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#12)]  
  
 <span data-ttu-id="345b4-185">자세한 `Group By`내용은 [그룹별 절을](../../../../visual-basic/language-reference/queries/group-by-clause.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="345b4-185">For more information about `Group By`, see [Group By Clause](../../../../visual-basic/language-reference/queries/group-by-clause.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="345b4-186">참고 항목</span><span class="sxs-lookup"><span data-stu-id="345b4-186">See also</span></span>

- <xref:System.Collections.Generic.IEnumerable%601>
- [<span data-ttu-id="345b4-187">Visual Basic에서 LINQ 시작</span><span class="sxs-lookup"><span data-stu-id="345b4-187">Getting Started with LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)
- [<span data-ttu-id="345b4-188">쿼리</span><span class="sxs-lookup"><span data-stu-id="345b4-188">Queries</span></span>](../../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="345b4-189">표준 쿼리 연산자 개요(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="345b4-189">Standard Query Operators Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="345b4-190">LINQ</span><span class="sxs-lookup"><span data-stu-id="345b4-190">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)
