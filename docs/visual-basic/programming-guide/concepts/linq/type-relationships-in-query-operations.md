---
title: 쿼리 작업의 형식 관계
ms.date: 07/20/2015
helpviewer_keywords:
- variable relationships [LINQ in Visual Basic]
- type information inferred [LINQ in Visual Basic]
- type relationships [LINQ in Visual Basic]
- queries [LINQ in Visual Basic], type relationships
- data sources [LINQ in Visual Basic], type relationships
- LINQ [Visual Basic], type relationships
- inferring type information [LINQ in Visual Basic]
- relationships [LINQ in Visual Basic]
ms.assetid: b5ff4da5-f3fd-4a8e-aaac-1cbf52fa16f6
ms.openlocfilehash: 73a287541ddf115510bf6ab5c830eafac370cc3a
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84406731"
---
# <a name="type-relationships-in-query-operations-visual-basic"></a><span data-ttu-id="03e6a-102">쿼리 작업의 형식 관계(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="03e6a-102">Type Relationships in Query Operations (Visual Basic)</span></span>

<span data-ttu-id="03e6a-103">LINQ (언어 통합 쿼리) 쿼리 작업에 사용 되는 변수는 강력한 형식 이므로 서로 호환 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="03e6a-103">Variables used in Language-Integrated Query (LINQ) query operations are strongly typed and must be compatible with each other.</span></span> <span data-ttu-id="03e6a-104">강력한 형식 지정은 데이터 소스, 쿼리 자체 및 쿼리 실행에서 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="03e6a-104">Strong typing is used in the data source, in the query itself, and in the query execution.</span></span> <span data-ttu-id="03e6a-105">다음 그림은 LINQ 쿼리를 설명 하는 데 사용 되는 용어를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="03e6a-105">The following illustration identifies terms used to describe a LINQ query.</span></span> <span data-ttu-id="03e6a-106">쿼리 파트에 대 한 자세한 내용은 [기본 쿼리 작업 (Visual Basic)](basic-query-operations.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="03e6a-106">For more information about the parts of a query, see [Basic Query Operations (Visual Basic)](basic-query-operations.md).</span></span>

![요소가 강조 표시 된 의사 코드 쿼리를 보여 주는 스크린샷](./media/type-relationships-in-query-operations/linq-query-description-terms.png)

<span data-ttu-id="03e6a-108">쿼리의 범위 변수 형식은 데이터 소스에 있는 요소의 형식과 호환 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="03e6a-108">The type of the range variable in the query must be compatible with the type of the elements in the data source.</span></span> <span data-ttu-id="03e6a-109">쿼리 변수의 형식은 절에 정의 된 sequence 요소와 호환 되어야 합니다 `Select` .</span><span class="sxs-lookup"><span data-stu-id="03e6a-109">The type of the query variable must be compatible with the sequence element defined in the `Select` clause.</span></span> <span data-ttu-id="03e6a-110">마지막으로 시퀀스 요소의 형식은 `For Each` 쿼리를 실행 하는 문에 사용 되는 루프 제어 변수의 형식과도 호환 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="03e6a-110">Finally, the type of the sequence elements also must be compatible with the type of the loop control variable that is used in the `For Each` statement that executes the query.</span></span> <span data-ttu-id="03e6a-111">이 강력한 형식화는 컴파일 시간에 형식 오류의 식별을 용이 하 게 합니다.</span><span class="sxs-lookup"><span data-stu-id="03e6a-111">This strong typing facilitates identification of type errors at compile time.</span></span>

<span data-ttu-id="03e6a-112">Visual Basic는 *암시적*형식이 라고도 하는 로컬 형식 유추를 구현 하 여 강력한 형식화를 편리 하 게 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="03e6a-112">Visual Basic makes strong typing convenient by implementing local type inference, also known as *implicit typing*.</span></span> <span data-ttu-id="03e6a-113">이전 예제에서이 기능을 사용 하 고 LINQ 샘플 및 설명서 전체에서이 기능을 사용 하는 것을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03e6a-113">That feature is used in the previous example, and you will see it used throughout the LINQ samples and documentation.</span></span> <span data-ttu-id="03e6a-114">Visual Basic에서는 절이 없는 문을 사용 하 여 로컬 형식 유추를 간단히 수행 `Dim` `As` 합니다.</span><span class="sxs-lookup"><span data-stu-id="03e6a-114">In Visual Basic, local type inference is accomplished simply by using a `Dim` statement without an `As` clause.</span></span> <span data-ttu-id="03e6a-115">다음 예제에서 `city` 는 문자열로 강력 하 게 형식화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="03e6a-115">In the following example, `city` is strongly typed as a string.</span></span>

[!code-vb[VbLINQTypeRels#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQTypeRels/VB/Class1.vb#1)]

> [!NOTE]
> <span data-ttu-id="03e6a-116">로컬 형식 유추 `Option Infer` 는가로 설정 된 경우에만 작동 `On` 합니다.</span><span class="sxs-lookup"><span data-stu-id="03e6a-116">Local type inference works only when `Option Infer` is set to `On`.</span></span> <span data-ttu-id="03e6a-117">자세한 내용은 [Option 유추 문](../../../language-reference/statements/option-infer-statement.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="03e6a-117">For more information, see [Option Infer Statement](../../../language-reference/statements/option-infer-statement.md).</span></span>

<span data-ttu-id="03e6a-118">그러나 쿼리에서 로컬 형식 유추를 사용 하는 경우에도 데이터 원본의 변수, 쿼리 변수 및 쿼리 실행 루프 사이에 동일한 형식 관계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03e6a-118">However, even if you use local type inference in a query, the same type relationships are present among the variables in the data source, the query variable, and the query execution loop.</span></span> <span data-ttu-id="03e6a-119">LINQ 쿼리를 작성 하거나 설명서의 샘플 및 코드 예제를 사용 하는 경우 이러한 형식 관계를 기본적으로 이해 하는 것이 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="03e6a-119">It is useful to have a basic understanding of these type relationships when you are writing LINQ queries, or working with the samples and code examples in the documentation.</span></span>

<span data-ttu-id="03e6a-120">데이터 원본에서 반환 되는 형식과 일치 하지 않는 범위 변수에 대 한 명시적 형식을 지정 해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03e6a-120">You may need to specify an explicit type for a range variable that does not match the type returned from the data source.</span></span> <span data-ttu-id="03e6a-121">절을 사용 하 여 범위 변수의 형식을 지정할 수 있습니다 `As` .</span><span class="sxs-lookup"><span data-stu-id="03e6a-121">You can specify the type of the range variable by using an `As` clause.</span></span> <span data-ttu-id="03e6a-122">그러나 변환이 [축소 변환](../../language-features/data-types/widening-and-narrowing-conversions.md) 되 고가로 설정 된 경우이로 인해 오류가 발생 `Option Strict` `On` 합니다.</span><span class="sxs-lookup"><span data-stu-id="03e6a-122">However, this results in an error if the conversion is a [narrowing conversion](../../language-features/data-types/widening-and-narrowing-conversions.md) and `Option Strict` is set to `On`.</span></span> <span data-ttu-id="03e6a-123">따라서 데이터 원본에서 검색 된 값에 대해 변환을 수행 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="03e6a-123">Therefore, we recommend that you perform the conversion on the values retrieved from the data source.</span></span> <span data-ttu-id="03e6a-124">메서드를 사용 하 여 데이터 소스의 값을 명시적 범위 변수 형식으로 변환할 수 있습니다 <xref:System.Linq.Enumerable.Cast%2A> .</span><span class="sxs-lookup"><span data-stu-id="03e6a-124">You can convert the values from the data source to the explicit range variable type by using the <xref:System.Linq.Enumerable.Cast%2A> method.</span></span> <span data-ttu-id="03e6a-125">또한 절에서 선택한 값 `Select` 을 범위 변수의 형식과 다른 명시적 형식으로 캐스팅할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03e6a-125">You can also cast the values selected in the `Select` clause to an explicit type that is different from the type of the range variable.</span></span> <span data-ttu-id="03e6a-126">이러한 요소는 다음 코드에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03e6a-126">These points are illustrated in the following code.</span></span>

[!code-vb[VbLINQTypeRels#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQTypeRels/VB/Class1.vb#4)]

## <a name="queries-that-return-entire-elements-of-the-source-data"></a><span data-ttu-id="03e6a-127">원본 데이터의 전체 요소를 반환 하는 쿼리</span><span class="sxs-lookup"><span data-stu-id="03e6a-127">Queries That Return Entire Elements of the Source Data</span></span>

<span data-ttu-id="03e6a-128">다음 예제에서는 원본 데이터에서 선택한 요소의 시퀀스를 반환 하는 LINQ 쿼리 작업을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="03e6a-128">The following example shows a LINQ query operation that returns a sequence of elements selected from the source data.</span></span> <span data-ttu-id="03e6a-129">원본에는 `names` 문자열 배열이 포함 되 고 쿼리 출력은 문자 M으로 시작 하는 문자열을 포함 하는 시퀀스입니다.</span><span class="sxs-lookup"><span data-stu-id="03e6a-129">The source, `names`, contains an array of strings, and the query output is a sequence containing strings that start with the letter M.</span></span>

[!code-vb[VbLINQTypeRels#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQTypeRels/VB/Class1.vb#2)]

<span data-ttu-id="03e6a-130">이는 다음 코드와 동일 하지만 훨씬 짧고 더 쉽게 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03e6a-130">This is equivalent to the following code, but is much shorter and easier to write.</span></span> <span data-ttu-id="03e6a-131">쿼리에서의 로컬 형식 유추에 의존 하는 것은 Visual Basic에서 선호 되는 스타일입니다.</span><span class="sxs-lookup"><span data-stu-id="03e6a-131">Reliance on local type inference in queries is the preferred style in Visual Basic.</span></span>

[!code-vb[VbLINQTypeRels#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQTypeRels/VB/Class1.vb#3)]

<span data-ttu-id="03e6a-132">형식이 암시적 또는 명시적으로 결정 되는지에 관계 없이 앞의 코드 예제에는 다음 관계가 모두 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03e6a-132">The following relationships exist in both of the previous code examples, whether the types are determined implicitly or explicitly.</span></span>

1. <span data-ttu-id="03e6a-133">데이터 소스에 있는 요소의 형식 ()은 `names` 쿼리에서 범위 변수의 형식입니다 `name` .</span><span class="sxs-lookup"><span data-stu-id="03e6a-133">The type of the elements in the data source, `names`, is the type of the range variable, `name`, in the query.</span></span>

2. <span data-ttu-id="03e6a-134">선택 된 개체의 형식으로, `name` 쿼리 변수의 형식을 결정 `mNames` 합니다.</span><span class="sxs-lookup"><span data-stu-id="03e6a-134">The type of the object that is selected, `name`, determines the type of the query variable, `mNames`.</span></span> <span data-ttu-id="03e6a-135">다음 `name` 은 문자열 이므로 쿼리 변수는 Visual Basic의 IEnumerable (문자열)입니다.</span><span class="sxs-lookup"><span data-stu-id="03e6a-135">Here `name` is a string, so the query variable is IEnumerable(Of String) in Visual Basic.</span></span>

3. <span data-ttu-id="03e6a-136">에서 정의 된 쿼리는 `mNames` 루프에서 실행 됩니다 `For Each` .</span><span class="sxs-lookup"><span data-stu-id="03e6a-136">The query defined in `mNames` is executed in the `For Each` loop.</span></span> <span data-ttu-id="03e6a-137">루프는 쿼리를 실행 한 결과를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="03e6a-137">The loop iterates over the result of executing the query.</span></span> <span data-ttu-id="03e6a-138">`mNames`실행 되는 경우는 문자열 시퀀스를 반환 하 고 루프 반복 변수인 `nm` 도 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="03e6a-138">Because `mNames`, when it is executed, will return a sequence of strings, the loop iteration variable, `nm`, also is a string.</span></span>

## <a name="queries-that-return-one-field-from-selected-elements"></a><span data-ttu-id="03e6a-139">선택한 요소에서 한 필드를 반환 하는 쿼리</span><span class="sxs-lookup"><span data-stu-id="03e6a-139">Queries That Return One Field from Selected Elements</span></span>

<span data-ttu-id="03e6a-140">다음 예에서는 [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] 데이터 소스에서 선택한 각 요소의 한 부분만 포함 된 시퀀스를 반환 하는 쿼리 작업을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="03e6a-140">The following example shows a [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] query operation that returns a sequence containing only one part of each element selected from the data source.</span></span> <span data-ttu-id="03e6a-141">이 쿼리는 개체의 컬렉션을 `Customer` 데이터 원본으로 사용 하 고 `Name` 결과의 속성만 프로젝션 합니다.</span><span class="sxs-lookup"><span data-stu-id="03e6a-141">The query takes a collection of `Customer` objects as its data source and projects only the `Name` property in the result.</span></span> <span data-ttu-id="03e6a-142">고객 이름이 문자열 이기 때문에 쿼리는 문자열 시퀀스를 출력으로 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="03e6a-142">Because the customer name is a string, the query produces a sequence of strings as output.</span></span>

```vb
' Method GetTable returns a table of Customer objects.
Dim customers = db.GetTable(Of Customer)()
Dim custNames = From cust In customers
                Where cust.City = "London"
                Select cust.Name

For Each custName In custNames
    Console.WriteLine(custName)
Next
```

<span data-ttu-id="03e6a-143">변수 간의 관계는 간단한 예제와 유사 합니다.</span><span class="sxs-lookup"><span data-stu-id="03e6a-143">The relationships between variables are like those in the simpler example.</span></span>

1. <span data-ttu-id="03e6a-144">데이터 소스에 있는 요소의 형식 ()은 `customers` 쿼리에서 범위 변수의 형식입니다 `cust` .</span><span class="sxs-lookup"><span data-stu-id="03e6a-144">The type of the elements in the data source, `customers`, is the type of the range variable, `cust`, in the query.</span></span> <span data-ttu-id="03e6a-145">이 예제에서 해당 형식은 `Customer` 입니다.</span><span class="sxs-lookup"><span data-stu-id="03e6a-145">In this example, that type is `Customer`.</span></span>

2. <span data-ttu-id="03e6a-146">`Select`문은 `Name` 전체 개체 대신 각 개체의 속성을 반환 합니다 `Customer` .</span><span class="sxs-lookup"><span data-stu-id="03e6a-146">The `Select` statement returns the `Name` property of each `Customer` object instead of the whole object.</span></span> <span data-ttu-id="03e6a-147">가 문자열 이기 때문에 `Name` 쿼리 변수는가 `custNames` 아닌 IEnumerable (문자열)입니다 `Customer` .</span><span class="sxs-lookup"><span data-stu-id="03e6a-147">Because `Name` is a string, the query variable, `custNames`, will again be IEnumerable(Of String), not of `Customer`.</span></span>

3. <span data-ttu-id="03e6a-148">는 `custNames` 문자열 시퀀스를 나타내므로 `For Each` 루프의 반복 변수는 `custName` 문자열 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="03e6a-148">Because `custNames` represents a sequence of strings, the `For Each` loop's iteration variable, `custName`, must be a string.</span></span>

<span data-ttu-id="03e6a-149">로컬 형식 유추가 없으면 다음 예제와 같이 앞의 예제를 작성 하 고 이해 하기가 더 복잡 합니다.</span><span class="sxs-lookup"><span data-stu-id="03e6a-149">Without local type inference, the previous example would be more cumbersome to write and to understand, as the following example shows.</span></span>

```vb
' Method GetTable returns a table of Customer objects.
 Dim customers As Table(Of Customer) = db.GetTable(Of Customer)()
 Dim custNames As IEnumerable(Of String) =
     From cust As Customer In customers
     Where cust.City = "London"
     Select cust.Name

 For Each custName As String In custNames
     Console.WriteLine(custName)
 Next
```

## <a name="queries-that-require-anonymous-types"></a><span data-ttu-id="03e6a-150">익명 형식이 필요한 쿼리</span><span class="sxs-lookup"><span data-stu-id="03e6a-150">Queries That Require Anonymous Types</span></span>

<span data-ttu-id="03e6a-151">다음 예제에서는 좀 더 복잡 한 상황을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="03e6a-151">The following example shows a more complex situation.</span></span> <span data-ttu-id="03e6a-152">이전 예제에서는 모든 변수에 대해 명시적으로 형식을 지정 하는 것이 불편할 수 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="03e6a-152">In the previous example, it was inconvenient to specify types for all the variables explicitly.</span></span> <span data-ttu-id="03e6a-153">이 예에서는 불가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="03e6a-153">In this example, it is impossible.</span></span> <span data-ttu-id="03e6a-154">`Customer`이 쿼리의 절은 데이터 소스에서 전체 요소를 선택 하는 대신 또는 각 요소의 단일 필드를 선택 하는 대신 `Select` 원래 `Customer` 개체인 및의 두 속성을 `Name` 반환 `City` 합니다.</span><span class="sxs-lookup"><span data-stu-id="03e6a-154">Instead of selecting entire `Customer` elements from the data source, or a single field from each element, the `Select` clause in this query returns two properties of the original `Customer` object: `Name` and `City`.</span></span> <span data-ttu-id="03e6a-155">절에 대 한 응답으로 `Select` 컴파일러는 이러한 두 속성을 포함 하는 익명 형식을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="03e6a-155">In response to the `Select` clause, the compiler defines an anonymous type that contains those two properties.</span></span> <span data-ttu-id="03e6a-156">루프에서를 실행 한 결과는 `nameCityQuery` `For Each` 새 익명 형식의 인스턴스 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="03e6a-156">The result of executing `nameCityQuery` in the `For Each` loop is a collection of instances of the new anonymous type.</span></span> <span data-ttu-id="03e6a-157">익명 형식에는 사용할 수 있는 이름이 없으므로 또는의 형식을 명시적으로 지정할 수 없습니다 `nameCityQuery` `custInfo` .</span><span class="sxs-lookup"><span data-stu-id="03e6a-157">Because the anonymous type has no usable name, you cannot specify the type of `nameCityQuery` or `custInfo` explicitly.</span></span> <span data-ttu-id="03e6a-158">즉, 무명 형식의 경우에서 대신 사용할 형식 이름이 없습니다 `String` `IEnumerable(Of String)` .</span><span class="sxs-lookup"><span data-stu-id="03e6a-158">That is, with an anonymous type, you have no type name to use in place of `String` in `IEnumerable(Of String)`.</span></span> <span data-ttu-id="03e6a-159">자세한 내용은 [무명 형식](../../language-features/objects-and-classes/anonymous-types.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="03e6a-159">For more information, see [Anonymous Types](../../language-features/objects-and-classes/anonymous-types.md).</span></span>

```vb
' Method GetTable returns a table of Customer objects.
Dim customers = db.GetTable(Of Customer)()
Dim nameCityQuery = From cust In customers
                    Where cust.City = "London"
                    Select cust.Name, cust.City

For Each custInfo In nameCityQuery
    Console.WriteLine(custInfo.Name)
Next
```

<span data-ttu-id="03e6a-160">이전 예제의 모든 변수에 대해 형식을 지정할 수는 없지만 관계는 동일 하 게 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="03e6a-160">Although it is not possible to specify types for all the variables in the previous example, the relationships remain the same.</span></span>

1. <span data-ttu-id="03e6a-161">데이터 소스에 있는 요소의 형식이 다시 쿼리의 범위 변수 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="03e6a-161">The type of the elements in the data source is again the type of the range variable in the query.</span></span> <span data-ttu-id="03e6a-162">이 예에서 `cust` 의 인스턴스가 `Customer`합니다.</span><span class="sxs-lookup"><span data-stu-id="03e6a-162">In this example, `cust` is an instance of `Customer`.</span></span>

2. <span data-ttu-id="03e6a-163">이 `Select` 문은 무명 형식을 생성 하므로 쿼리 변수는 `nameCityQuery` 무명 형식으로 암시적으로 형식화 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="03e6a-163">Because the `Select` statement produces an anonymous type, the query variable, `nameCityQuery`, must be implicitly typed as an anonymous type.</span></span> <span data-ttu-id="03e6a-164">익명 형식에는 사용할 수 있는 이름이 없으므로 명시적으로 지정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="03e6a-164">An anonymous type has no usable name, and therefore cannot be specified explicitly.</span></span>

3. <span data-ttu-id="03e6a-165">루프의 반복 변수 형식은 `For Each` 2 단계에서 만든 익명 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="03e6a-165">The type of the iteration variable in the `For Each` loop is the anonymous type created in step 2.</span></span> <span data-ttu-id="03e6a-166">형식에 사용할 수 있는 이름이 없으므로 루프 반복 변수의 형식은 암시적으로 결정 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="03e6a-166">Because the type has no usable name, the type of the loop iteration variable must be determined implicitly.</span></span>

## <a name="see-also"></a><span data-ttu-id="03e6a-167">참고 항목</span><span class="sxs-lookup"><span data-stu-id="03e6a-167">See also</span></span>

- [<span data-ttu-id="03e6a-168">Visual Basic에서 LINQ 시작</span><span class="sxs-lookup"><span data-stu-id="03e6a-168">Getting Started with LINQ in Visual Basic</span></span>](getting-started-with-linq.md)
- [<span data-ttu-id="03e6a-169">익명 형식</span><span class="sxs-lookup"><span data-stu-id="03e6a-169">Anonymous Types</span></span>](../../language-features/objects-and-classes/anonymous-types.md)
- [<span data-ttu-id="03e6a-170">지역 형식 유추</span><span class="sxs-lookup"><span data-stu-id="03e6a-170">Local Type Inference</span></span>](../../language-features/variables/local-type-inference.md)
- [<span data-ttu-id="03e6a-171">Visual Basic의 LINQ 소개</span><span class="sxs-lookup"><span data-stu-id="03e6a-171">Introduction to LINQ in Visual Basic</span></span>](../../language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="03e6a-172">LINQ</span><span class="sxs-lookup"><span data-stu-id="03e6a-172">LINQ</span></span>](../../language-features/linq/index.md)
- [<span data-ttu-id="03e6a-173">쿼리</span><span class="sxs-lookup"><span data-stu-id="03e6a-173">Queries</span></span>](../../../language-reference/queries/index.md)
