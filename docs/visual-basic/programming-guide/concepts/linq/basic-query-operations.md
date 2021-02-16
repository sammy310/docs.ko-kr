---
description: '자세한 정보: 기본 쿼리 작업 (Visual Basic)'
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
ms.openlocfilehash: 1f8fbda83c21fe9032415d96ff2d7e184083a839
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100428690"
---
# <a name="basic-query-operations-visual-basic"></a><span data-ttu-id="07808-103">기본 쿼리 작업(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="07808-103">Basic Query Operations (Visual Basic)</span></span>

<span data-ttu-id="07808-104">이 항목에서는 Visual Basic의 LINQ (Language-Integrated Query) 식 및 쿼리에서 수행 하는 몇 가지 일반적인 작업 종류에 대해 간략하게 소개 합니다.</span><span class="sxs-lookup"><span data-stu-id="07808-104">This topic provides a brief introduction to Language-Integrated Query (LINQ) expressions in Visual Basic, and to some of the typical kinds of operations that you perform in a query.</span></span> <span data-ttu-id="07808-105">자세한 내용은 다음 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="07808-105">For more information, see the following topics:</span></span>  
  
 [<span data-ttu-id="07808-106">Visual Basic의 LINQ 소개</span><span class="sxs-lookup"><span data-stu-id="07808-106">Introduction to LINQ in Visual Basic</span></span>](../../language-features/linq/introduction-to-linq.md)  
  
 [<span data-ttu-id="07808-107">쿼리</span><span class="sxs-lookup"><span data-stu-id="07808-107">Queries</span></span>](../../../language-reference/queries/index.md)  
  
 [<span data-ttu-id="07808-108">연습: Visual Basic에서 쿼리 작성</span><span class="sxs-lookup"><span data-stu-id="07808-108">Walkthrough: Writing Queries in Visual Basic</span></span>](walkthrough-writing-queries.md)  
  
## <a name="specifying-the-data-source-from"></a><span data-ttu-id="07808-109">데이터 원본 지정 (원본)</span><span class="sxs-lookup"><span data-stu-id="07808-109">Specifying the Data Source (From)</span></span>  

 <span data-ttu-id="07808-110">LINQ 쿼리에서 첫 번째 단계는 쿼리 하려는 데이터 원본을 지정 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="07808-110">In a LINQ query, the first step is to specify the data source that you want to query.</span></span> <span data-ttu-id="07808-111">따라서 `From` 쿼리의 절은 항상 먼저 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="07808-111">Therefore, the `From` clause in a query always comes first.</span></span> <span data-ttu-id="07808-112">쿼리 연산자 원본 유형에 따라 결과를 선택 하 고 모양을 합니다.</span><span class="sxs-lookup"><span data-stu-id="07808-112">Query operators select and shape the result based on the type of the source.</span></span>  
  
 [!code-vb[VbLINQBasicOps#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#1)]  
  
 <span data-ttu-id="07808-113">`From`절은 데이터 소스, `customers` 및 *범위 변수* 를 지정 합니다 `cust` .</span><span class="sxs-lookup"><span data-stu-id="07808-113">The `From` clause specifies the data source, `customers`, and a *range variable*, `cust`.</span></span> <span data-ttu-id="07808-114">범위 변수는 쿼리 식에서 실제 반복이 발생 하지 않는다는 점을 제외 하 고 루프 반복 변수와 유사 합니다.</span><span class="sxs-lookup"><span data-stu-id="07808-114">The range variable is like a loop iteration variable, except that in a query expression, no actual iteration occurs.</span></span> <span data-ttu-id="07808-115">루프를 사용 하 여 쿼리를 실행할 때 `For Each` 범위 변수는의 각 연속 요소에 대 한 참조로 사용 됩니다 `customers` .</span><span class="sxs-lookup"><span data-stu-id="07808-115">When the query is executed, often by using a `For Each` loop, the range variable serves as a reference to each successive element in `customers`.</span></span> <span data-ttu-id="07808-116">컴파일러에서 `cust` 형식을 유추할 수 있으므로 명시적으로 지정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="07808-116">Because the compiler can infer the type of `cust`, you do not have to specify it explicitly.</span></span> <span data-ttu-id="07808-117">명시적 형식 지정을 사용 하거나 사용 하지 않고 작성 된 쿼리의 예는 [쿼리 작업의 형식 관계 (Visual Basic)](type-relationships-in-query-operations.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="07808-117">For examples of queries written with and without explicit typing, see [Type Relationships in Query Operations (Visual Basic)](type-relationships-in-query-operations.md).</span></span>  
  
 <span data-ttu-id="07808-118">Visual Basic에서 절을 사용 하는 방법에 대 한 자세한 내용은 `From` [from 절](../../../language-reference/queries/from-clause.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="07808-118">For more information about how to use the `From` clause in Visual Basic, see [From Clause](../../../language-reference/queries/from-clause.md).</span></span>  
  
## <a name="filtering-data-where"></a><span data-ttu-id="07808-119">데이터 필터링 (Where)</span><span class="sxs-lookup"><span data-stu-id="07808-119">Filtering Data (Where)</span></span>  

 <span data-ttu-id="07808-120">가장 일반적인 쿼리 작업은 부울 식의 형태로 필터를 적용 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="07808-120">Probably the most common query operation is applying a filter in the form of a Boolean expression.</span></span> <span data-ttu-id="07808-121">그런 다음이 쿼리는 식이 true 인 요소만 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="07808-121">The query then returns only those elements for which the expression is true.</span></span> <span data-ttu-id="07808-122">`Where`필터링을 수행 하는 데 절이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="07808-122">A `Where` clause is used to perform the filtering.</span></span> <span data-ttu-id="07808-123">필터는 결과 시퀀스에 포함할 데이터 소스의 요소를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="07808-123">The filter specifies which elements in the data source to include in the resulting sequence.</span></span> <span data-ttu-id="07808-124">다음 예에서는 런던에 주소가 있는 고객만 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07808-124">In the following example, only those customers who have an address in London are included.</span></span>  
  
 [!code-vb[VbLINQBasicOps#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#2)]  
  
 <span data-ttu-id="07808-125">And와 같은 논리 연산자를 사용 `And` `Or` 하 여 절에서 필터 식을 결합할 수 있습니다 `Where` .</span><span class="sxs-lookup"><span data-stu-id="07808-125">You can use logical operators such as `And` and `Or` to combine filter expressions in a `Where` clause.</span></span> <span data-ttu-id="07808-126">예를 들어 London에서 이름이 Devon 인 고객만 반환 하려면 다음 코드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="07808-126">For example, to return only those customers who are from London and whose name is Devon, use the following code:</span></span>  
  
```vb  
Where cust.City = "London" And cust.Name = "Devon"
```  
  
 <span data-ttu-id="07808-127">런던 또는 파리에서 고객을 반환 하려면 다음 코드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="07808-127">To return customers from London or Paris, use the following code:</span></span>  
  
```vb  
Where cust.City = "London" Or cust.City = "Paris"
```  
  
 <span data-ttu-id="07808-128">Visual Basic에서 절을 사용 하는 방법에 대 한 자세한 내용은 `Where` [where 절](../../../language-reference/queries/where-clause.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="07808-128">For more information about how to use the `Where` clause in Visual Basic, see [Where Clause](../../../language-reference/queries/where-clause.md).</span></span>  
  
## <a name="ordering-data-order-by"></a><span data-ttu-id="07808-129">데이터 순서 지정 (Order By)</span><span class="sxs-lookup"><span data-stu-id="07808-129">Ordering Data (Order By)</span></span>  

 <span data-ttu-id="07808-130">반환 된 데이터를 특정 순서로 정렬 하는 것이 편리한 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="07808-130">It often is convenient to sort returned data into a particular order.</span></span> <span data-ttu-id="07808-131">`Order By`절을 지정 하면 반환 된 시퀀스의 요소가 지정 된 필드를 기준으로 정렬 됩니다.</span><span class="sxs-lookup"><span data-stu-id="07808-131">The `Order By` clause will cause the elements in the returned sequence to be sorted on a specified field or fields.</span></span> <span data-ttu-id="07808-132">예를 들어 다음 쿼리는 속성을 기반으로 결과를 정렬 합니다 `Name` .</span><span class="sxs-lookup"><span data-stu-id="07808-132">For example, the following query sorts the results based on the `Name` property.</span></span> <span data-ttu-id="07808-133">`Name`는 문자열 이므로 반환 된 데이터는 a에서 Z로 사전순으로 정렬 됩니다.</span><span class="sxs-lookup"><span data-stu-id="07808-133">Because `Name` is a string, the returned data will be sorted alphabetically, from A to Z.</span></span>  
  
 [!code-vb[VbLINQBasicOps#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#3)]  
  
 <span data-ttu-id="07808-134">결과를 역순으로 정렬하려면 `Order By...Descending` 절을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="07808-134">To order the results in reverse order, from Z to A, use the `Order By...Descending` clause.</span></span> <span data-ttu-id="07808-135">`Ascending`및를 모두 지정 하지 않을 경우 기본값은입니다 `Ascending` `Descending` .</span><span class="sxs-lookup"><span data-stu-id="07808-135">The default is `Ascending` when neither `Ascending` nor `Descending` is specified.</span></span>  
  
 <span data-ttu-id="07808-136">Visual Basic에서 절을 사용 하는 방법에 대 한 자세한 내용은 `Order By` [Order by 절](../../../language-reference/queries/order-by-clause.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="07808-136">For more information about how to use the `Order By` clause in Visual Basic, see [Order By Clause](../../../language-reference/queries/order-by-clause.md).</span></span>  
  
## <a name="selecting-data-select"></a><span data-ttu-id="07808-137">데이터 선택 (Select)</span><span class="sxs-lookup"><span data-stu-id="07808-137">Selecting Data (Select)</span></span>  

 <span data-ttu-id="07808-138">`Select`절은 반환 된 요소의 형식 및 내용을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="07808-138">The `Select` clause specifies the form and content of returned elements.</span></span> <span data-ttu-id="07808-139">예를 들어 결과가 전체 `Customer` 개체, 하나의 `Customer` 속성, 속성의 하위 집합, 다양 한 데이터 원본의 속성 조합 또는 계산을 기반으로 하는 몇 가지 새로운 결과 형식으로 구성 될 지 여부를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07808-139">For example, you can specify whether your results will consist of complete `Customer` objects, just one `Customer` property, a subset of properties, a combination of properties from various data sources, or some new result type based on a computation.</span></span> <span data-ttu-id="07808-140">`Select` 절이 소스 요소의 복사본이 아닌 다른 항목을 생성하는 경우 이 작업을 *프로젝션* 이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="07808-140">When the `Select` clause produces something other than a copy of the source element, the operation is called a *projection*.</span></span>  
  
 <span data-ttu-id="07808-141">전체 개체로 구성 된 컬렉션을 검색 하려면 `Customer` 범위 변수 자체를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="07808-141">To retrieve a collection that consists of complete `Customer` objects, select the range variable itself:</span></span>  
  
 [!code-vb[VbLINQBasicOps#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#4)]  
  
 <span data-ttu-id="07808-142">`Customer`인스턴스가 많은 필드가 포함 된 많은 개체이 고 검색 하려는 모든가 이름인 경우 `cust.Name` 다음 예제와 같이를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07808-142">If a `Customer` instance is a large object that has many fields, and all that you want to retrieve is the name, you can select `cust.Name`, as shown in the following example.</span></span> <span data-ttu-id="07808-143">지역 형식 유추는이가 결과 형식을 개체 컬렉션에서 문자열 컬렉션으로 변경 하는 것을 인식 합니다 `Customer` .</span><span class="sxs-lookup"><span data-stu-id="07808-143">Local type inference recognizes that this changes the result type from a collection of `Customer` objects to a collection of strings.</span></span>  
  
 [!code-vb[VbLINQBasicOps#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#5)]  
  
 <span data-ttu-id="07808-144">데이터 원본에서 여러 필드를 선택 하기 위해 다음 두 가지 옵션을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07808-144">To select multiple fields from the data source, you have two choices:</span></span>  
  
- <span data-ttu-id="07808-145">절에서 `Select` 결과에 포함할 필드를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="07808-145">In the `Select` clause, specify the fields you want to include in the result.</span></span> <span data-ttu-id="07808-146">컴파일러는 해당 필드를 속성으로 포함 하는 익명 형식을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="07808-146">The compiler will define an anonymous type that has those fields as its properties.</span></span> <span data-ttu-id="07808-147">자세한 내용은 [무명 형식](../../language-features/objects-and-classes/anonymous-types.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="07808-147">For more information, see [Anonymous Types](../../language-features/objects-and-classes/anonymous-types.md).</span></span>  
  
     <span data-ttu-id="07808-148">다음 예제의 반환 된 요소는 무명 형식의 인스턴스 이므로 코드의 다른 위치에서 이름을 기준으로 형식을 참조할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="07808-148">Because the returned elements in the following example are instances of an anonymous type, you cannot refer to the type by name elsewhere in your code.</span></span> <span data-ttu-id="07808-149">형식에 대 한 컴파일러 지정 이름에 일반 Visual Basic 코드에서 유효 하지 않은 문자가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07808-149">The compiler-designated name for the type contains characters that are not valid in normal Visual Basic code.</span></span> <span data-ttu-id="07808-150">다음 예제에서 쿼리에서 반환 되는 컬렉션의 요소는 `londonCusts4` 무명 형식의 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="07808-150">In the following example, the elements in the collection that is returned by the query in `londonCusts4` are instances of an anonymous type</span></span>  
  
     [!code-vb[VbLINQBasicOps#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#6)]  
  
     <span data-ttu-id="07808-151">또는</span><span class="sxs-lookup"><span data-stu-id="07808-151">-or-</span></span>  
  
- <span data-ttu-id="07808-152">결과에 포함 하려는 특정 필드를 포함 하는 명명 된 형식을 정의 하 고 절에서 형식의 인스턴스를 만들고 초기화 `Select` 합니다.</span><span class="sxs-lookup"><span data-stu-id="07808-152">Define a named type that contains the particular fields that you want to include in the result, and create and initialize instances of the type in the `Select` clause.</span></span> <span data-ttu-id="07808-153">반환 된 컬렉션 외부에서 개별 결과를 사용 해야 하는 경우 또는 메서드 호출에서 매개 변수로 전달 해야 하는 경우에만이 옵션을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="07808-153">Use this option only if you have to use individual results outside the collection in which they are returned, or if you have to pass them as parameters in method calls.</span></span> <span data-ttu-id="07808-154">`londonCusts5`다음 예제에서의 형식은 IEnumerable (Of NamePhone)입니다.</span><span class="sxs-lookup"><span data-stu-id="07808-154">The type of `londonCusts5` in the following example is IEnumerable(Of NamePhone).</span></span>  
  
     [!code-vb[VbLINQBasicOps#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#7)]  
  
     [!code-vb[VbLINQBasicOps#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#8)]  
  
 <span data-ttu-id="07808-155">Visual Basic 절을 사용 하는 방법에 대 한 자세한 내용은 `Select` [select 절](../../../language-reference/queries/select-clause.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="07808-155">For more information about how to use the `Select` clause in Visual Basic, see [Select Clause](../../../language-reference/queries/select-clause.md).</span></span>  
  
## <a name="joining-data-join-and-group-join"></a><span data-ttu-id="07808-156">데이터 조인 (조인 및 그룹 조인)</span><span class="sxs-lookup"><span data-stu-id="07808-156">Joining Data (Join and Group Join)</span></span>  

 <span data-ttu-id="07808-157">여러 가지 방법으로 절에서 둘 이상의 데이터 소스를 결합할 수 있습니다 `From` .</span><span class="sxs-lookup"><span data-stu-id="07808-157">You can combine more than one data source in the `From` clause in several ways.</span></span> <span data-ttu-id="07808-158">예를 들어, 다음 코드는 두 개의 데이터 원본을 사용 하 고 결과에서 둘 다의 속성을 암시적으로 결합 합니다.</span><span class="sxs-lookup"><span data-stu-id="07808-158">For example, the following code uses two data sources and implicitly combines properties from both of them in the result.</span></span> <span data-ttu-id="07808-159">이 쿼리는 성이 모음으로 시작 하는 학생을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="07808-159">The query selects students whose last names start with a vowel.</span></span>  
  
 [!code-vb[VbLINQBasicOps#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#9)]  
  
> [!NOTE]
> <span data-ttu-id="07808-160">[방법: 항목 목록 만들기](how-to-create-a-list-of-items.md)에서 만든 학생의 목록을 사용 하 여이 코드를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07808-160">You can run this code with the list of students created in [How to: Create a List of Items](how-to-create-a-list-of-items.md).</span></span>  
  
 <span data-ttu-id="07808-161">`Join`키워드는 SQL의와 동일 `INNER JOIN` 합니다.</span><span class="sxs-lookup"><span data-stu-id="07808-161">The `Join` keyword is equivalent to an `INNER JOIN` in SQL.</span></span> <span data-ttu-id="07808-162">두 컬렉션의 요소 사이에 일치 하는 키 값을 기준으로 두 컬렉션을 결합 합니다.</span><span class="sxs-lookup"><span data-stu-id="07808-162">It combines two collections based on matching key values between elements in the two collections.</span></span> <span data-ttu-id="07808-163">쿼리에서 일치 하는 키 값이 있는 컬렉션 요소의 전체 또는 일부를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="07808-163">The query returns all or part of the collection elements that have matching key values.</span></span> <span data-ttu-id="07808-164">예를 들어 다음 코드는 이전 암시적 조인의 작업을 복제 합니다.</span><span class="sxs-lookup"><span data-stu-id="07808-164">For example, the following code duplicates the action of the previous implicit join.</span></span>  
  
 [!code-vb[VbLINQBasicOps#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#10)]  
  
 <span data-ttu-id="07808-165">`Group Join` SQL의와 마찬가지로 컬렉션을 단일 계층 구조 컬렉션으로 결합 `LEFT JOIN` 합니다.</span><span class="sxs-lookup"><span data-stu-id="07808-165">`Group Join` combines collections into a single hierarchical collection, just like a `LEFT JOIN` in SQL.</span></span> <span data-ttu-id="07808-166">자세한 내용은 [Join 절](../../../language-reference/queries/join-clause.md) 및 [Group join 절](../../../language-reference/queries/group-join-clause.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="07808-166">For more information, see [Join Clause](../../../language-reference/queries/join-clause.md) and [Group Join Clause](../../../language-reference/queries/group-join-clause.md).</span></span>  
  
## <a name="grouping-data-group-by"></a><span data-ttu-id="07808-167">데이터 그룹화 (Group By)</span><span class="sxs-lookup"><span data-stu-id="07808-167">Grouping Data (Group By)</span></span>  

 <span data-ttu-id="07808-168">요소에 있는 `Group By` 하나 이상의 필드에 따라 쿼리 결과의 요소를 그룹화 하는 절을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07808-168">You can add a `Group By` clause to group the elements in a query result according to one or more fields of the elements.</span></span> <span data-ttu-id="07808-169">예를 들어, 다음 코드는 year를 기준으로 학생을 그룹화 합니다.</span><span class="sxs-lookup"><span data-stu-id="07808-169">For example, the following code groups students by class year.</span></span>  
  
 [!code-vb[VbLINQBasicOps#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#11)]  
  
 <span data-ttu-id="07808-170">[방법: 항목 목록 만들기](how-to-create-a-list-of-items.md)에서 만든 학생 목록을 사용 하 여이 코드를 실행 하는 경우 `For Each` 문의 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="07808-170">If you run this code using the list of students created in [How to: Create a List of Items](how-to-create-a-list-of-items.md), the output from the `For Each` statement is:</span></span>  
  
 <span data-ttu-id="07808-171">연도: Junior</span><span class="sxs-lookup"><span data-stu-id="07808-171">Year: Junior</span></span>  
  
 <span data-ttu-id="07808-172">Tucker, Michael</span><span class="sxs-lookup"><span data-stu-id="07808-172">Tucker, Michael</span></span>  
  
 <span data-ttu-id="07808-173">가르시아 섬, Hugo</span><span class="sxs-lookup"><span data-stu-id="07808-173">Garcia, Hugo</span></span>  
  
 <span data-ttu-id="07808-174">가르시아 섬, Debra</span><span class="sxs-lookup"><span data-stu-id="07808-174">Garcia, Debra</span></span>  
  
 <span data-ttu-id="07808-175">Tucker, Lance</span><span class="sxs-lookup"><span data-stu-id="07808-175">Tucker, Lance</span></span>  
  
 <span data-ttu-id="07808-176">연도: 선임</span><span class="sxs-lookup"><span data-stu-id="07808-176">Year: Senior</span></span>  
  
 <span data-ttu-id="07808-177">Omelchenko, Svetlana</span><span class="sxs-lookup"><span data-stu-id="07808-177">Omelchenko, Svetlana</span></span>  
  
 <span data-ttu-id="07808-178">Osada, Michiko</span><span class="sxs-lookup"><span data-stu-id="07808-178">Osada, Michiko</span></span>  
  
 <span data-ttu-id="07808-179">Fakhouri, Fadi</span><span class="sxs-lookup"><span data-stu-id="07808-179">Fakhouri, Fadi</span></span>  
  
 <span data-ttu-id="07808-180">Feng, 인 hanying</span><span class="sxs-lookup"><span data-stu-id="07808-180">Feng, Hanying</span></span>  
  
 <span data-ttu-id="07808-181">Adams, Terry</span><span class="sxs-lookup"><span data-stu-id="07808-181">Adams, Terry</span></span>  
  
 <span data-ttu-id="07808-182">연도: Freshman</span><span class="sxs-lookup"><span data-stu-id="07808-182">Year: Freshman</span></span>  
  
 <span data-ttu-id="07808-183">Mortensen, Sven</span><span class="sxs-lookup"><span data-stu-id="07808-183">Mortensen, Sven</span></span>  
  
 <span data-ttu-id="07808-184">가르시아 섬, Cesar</span><span class="sxs-lookup"><span data-stu-id="07808-184">Garcia, Cesar</span></span>  
  
 <span data-ttu-id="07808-185">다음 코드에 표시 된 변형은 클래스 연도를 정렬 한 다음 각 연도 내에서 성을 기준으로 학생을 주문 합니다.</span><span class="sxs-lookup"><span data-stu-id="07808-185">The variation shown in the following code orders the class years, and then orders the students within each year by last name.</span></span>  
  
 [!code-vb[VbLINQBasicOps#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#12)]  
  
 <span data-ttu-id="07808-186">에 대 한 자세한 내용은 `Group By` [Group by 절](../../../language-reference/queries/group-by-clause.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="07808-186">For more information about `Group By`, see [Group By Clause](../../../language-reference/queries/group-by-clause.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07808-187">추가 정보</span><span class="sxs-lookup"><span data-stu-id="07808-187">See also</span></span>

- <xref:System.Collections.Generic.IEnumerable%601>
- [<span data-ttu-id="07808-188">Visual Basic에서 LINQ 시작</span><span class="sxs-lookup"><span data-stu-id="07808-188">Getting Started with LINQ in Visual Basic</span></span>](getting-started-with-linq.md)
- [<span data-ttu-id="07808-189">쿼리</span><span class="sxs-lookup"><span data-stu-id="07808-189">Queries</span></span>](../../../language-reference/queries/index.md)
- [<span data-ttu-id="07808-190">표준 쿼리 연산자 개요(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="07808-190">Standard Query Operators Overview (Visual Basic)</span></span>](standard-query-operators-overview.md)
- [<span data-ttu-id="07808-191">LINQ</span><span class="sxs-lookup"><span data-stu-id="07808-191">LINQ</span></span>](../../language-features/linq/index.md)
