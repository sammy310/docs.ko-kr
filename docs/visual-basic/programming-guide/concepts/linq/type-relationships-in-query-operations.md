---
title: 쿼리 작업의 형식 관계(Visual Basic)
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
ms.openlocfilehash: 4dc5497f2e9bacac3062fde6e7dc48270697f1df
ms.sourcegitcommit: 7156c0b9e4ce4ce5ecf48ce3d925403b638b680c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/26/2019
ms.locfileid: "58465219"
---
# <a name="type-relationships-in-query-operations-visual-basic"></a><span data-ttu-id="36684-102">쿼리 작업의 형식 관계(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="36684-102">Type Relationships in Query Operations (Visual Basic)</span></span>
<span data-ttu-id="36684-103">사용 되는 변수 [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] 쿼리 작업은 강력한 형식 이어야 하며 서로 호환 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="36684-103">Variables used in [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] query operations are strongly typed and must be compatible with each other.</span></span> <span data-ttu-id="36684-104">강력한 형식 지정 데이터 원본, 쿼리 자체 및 쿼리 실행에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="36684-104">Strong typing is used in the data source, in the query itself, and in the query execution.</span></span> <span data-ttu-id="36684-105">다음 그림에서는 설명 하는 용어를 식별 하는 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 쿼리 합니다.</span><span class="sxs-lookup"><span data-stu-id="36684-105">The following illustration identifies terms used to describe a [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query.</span></span> <span data-ttu-id="36684-106">쿼리 부분에 대 한 자세한 내용은 참조 하세요. [기본 쿼리 작업 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/basic-query-operations.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="36684-106">For more information about the parts of a query, see [Basic Query Operations (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/basic-query-operations.md).</span></span>  
  
 ![요소가 강조 표시 된 의사 코드 쿼리를 보여주는 스크린샷.](./media/type-relationships-in-query-operations/linq-query-description-terms.png)  
  
 <span data-ttu-id="36684-108">쿼리에서 범위 변수의 형식을 데이터 소스에 있는 요소의 형식과 호환 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="36684-108">The type of the range variable in the query must be compatible with the type of the elements in the data source.</span></span> <span data-ttu-id="36684-109">쿼리 변수의 형식에 정의 된 시퀀스 요소와 호환 되어야 합니다는 `Select` 절.</span><span class="sxs-lookup"><span data-stu-id="36684-109">The type of the query variable must be compatible with the sequence element defined in the `Select` clause.</span></span> <span data-ttu-id="36684-110">마지막으로 시퀀스 요소의 형식입니다도 호환 되어야에 사용 되는 루프 제어 변수의 형식을 사용 하 여는 `For Each` 쿼리를 실행 하는 문입니다.</span><span class="sxs-lookup"><span data-stu-id="36684-110">Finally, the type of the sequence elements also must be compatible with the type of the loop control variable that is used in the `For Each` statement that executes the query.</span></span> <span data-ttu-id="36684-111">이 강력한 형식화 컴파일 타임 형식 오류 식별을 용이 하 게 합니다.</span><span class="sxs-lookup"><span data-stu-id="36684-111">This strong typing facilitates identification of type errors at compile time.</span></span>  
  
 <span data-ttu-id="36684-112">Visual Basic 편리 강력한 형식 지정 라고도 지역 형식 유추를 구현 하 여 *암시적 형식 지정*합니다.</span><span class="sxs-lookup"><span data-stu-id="36684-112">Visual Basic makes strong typing convenient by implementing local type inference, also known as *implicit typing*.</span></span> <span data-ttu-id="36684-113">기능은 이전 예제에서 사용 됩니다 하 고 표시 될 전체에서 사용 되는 것은 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 샘플 및 설명서입니다.</span><span class="sxs-lookup"><span data-stu-id="36684-113">That feature is used in the previous example, and you will see it used throughout the [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] samples and documentation.</span></span> <span data-ttu-id="36684-114">Visual basic에서 지역 형식 유추를 사용 하 여 수행 됩니다는 `Dim` 문 없이 `As` 절.</span><span class="sxs-lookup"><span data-stu-id="36684-114">In Visual Basic, local type inference is accomplished simply by using a `Dim` statement without an `As` clause.</span></span> <span data-ttu-id="36684-115">다음 예에서 `city` 문자열로 강력 하 게 형식화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="36684-115">In the following example, `city` is strongly typed as a string.</span></span>  
  
 [!code-vb[VbLINQTypeRels#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQTypeRels/VB/Class1.vb#1)]  
  
> [!NOTE]
>  <span data-ttu-id="36684-116">경우에만 작동 하는 지역 형식 유추 `Option Infer` 로 설정 된 `On`합니다.</span><span class="sxs-lookup"><span data-stu-id="36684-116">Local type inference works only when `Option Infer` is set to `On`.</span></span> <span data-ttu-id="36684-117">자세한 내용은 [Option Infer 문](../../../../visual-basic/language-reference/statements/option-infer-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="36684-117">For more information, see [Option Infer Statement](../../../../visual-basic/language-reference/statements/option-infer-statement.md).</span></span>  
  
 <span data-ttu-id="36684-118">그러나 쿼리에서 로컬 형식 유추를 사용 하는 경우에 동일한 형식 관계는 데이터 원본에서 변수, 쿼리 변수 및 쿼리 실행 루프 중입니다.</span><span class="sxs-lookup"><span data-stu-id="36684-118">However, even if you use local type inference in a query, the same type relationships are present among the variables in the data source, the query variable, and the query execution loop.</span></span> <span data-ttu-id="36684-119">작성 하는 경우 이러한 형식 관계에 대 한 기본 이해 하는 것이 유용 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 쿼리 또는 샘플 및 설명서의 코드 예제를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="36684-119">It is useful to have a basic understanding of these type relationships when you are writing [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] queries, or working with the samples and code examples in the documentation.</span></span>  
  
 <span data-ttu-id="36684-120">데이터 원본에서 반환 되는 형식과 일치 하지 않는 범위 변수에 명시적 형식을 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="36684-120">You may need to specify an explicit type for a range variable that does not match the type returned from the data source.</span></span> <span data-ttu-id="36684-121">사용 하 여 범위 변수의 형식을 지정할 수 있습니다는 `As` 절.</span><span class="sxs-lookup"><span data-stu-id="36684-121">You can specify the type of the range variable by using an `As` clause.</span></span> <span data-ttu-id="36684-122">그러나이 인해 오류로 변환 되는 경우는 [축소 변환을](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) 및 `Option Strict` 로 설정 되어 `On`합니다.</span><span class="sxs-lookup"><span data-stu-id="36684-122">However, this results in an error if the conversion is a [narrowing conversion](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) and `Option Strict` is set to `On`.</span></span> <span data-ttu-id="36684-123">따라서 데이터 원본에서 검색 된 값에서 변환을 수행 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="36684-123">Therefore, we recommend that you perform the conversion on the values retrieved from the data source.</span></span> <span data-ttu-id="36684-124">사용 하 여 명시적 범위 변수 형식으로 값을 데이터 원본에서 변환할 수는 <xref:System.Linq.Enumerable.Cast%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="36684-124">You can convert the values from the data source to the explicit range variable type by using the <xref:System.Linq.Enumerable.Cast%2A> method.</span></span> <span data-ttu-id="36684-125">선택한 값을 캐스트할 수도 있습니다는 `Select` 명시적 형식 범위 변수 형식에서 다른 절.</span><span class="sxs-lookup"><span data-stu-id="36684-125">You can also cast the values selected in the `Select` clause to an explicit type that is different from the type of the range variable.</span></span> <span data-ttu-id="36684-126">이러한 요소는 다음 코드에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36684-126">These points are illustrated in the following code.</span></span>  
  
 [!code-vb[VbLINQTypeRels#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQTypeRels/VB/Class1.vb#4)]  
  
## <a name="queries-that-return-entire-elements-of-the-source-data"></a><span data-ttu-id="36684-127">원본 데이터의 전체 요소를 반환 하는 쿼리</span><span class="sxs-lookup"><span data-stu-id="36684-127">Queries That Return Entire Elements of the Source Data</span></span>  
 <span data-ttu-id="36684-128">다음 예제와 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 원본 데이터에서 선택한 요소의 시퀀스를 반환 하는 작업을 쿼리 합니다.</span><span class="sxs-lookup"><span data-stu-id="36684-128">The following example shows a [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query operation that returns a sequence of elements selected from the source data.</span></span> <span data-ttu-id="36684-129">원본 `names`, 문자열의 배열을 포함 쿼리 출력은 M으로 시작 하는 문자열을 포함 하는 시퀀스입니다.</span><span class="sxs-lookup"><span data-stu-id="36684-129">The source, `names`, contains an array of strings, and the query output is a sequence containing strings that start with the letter M.</span></span>  
  
 [!code-vb[VbLINQTypeRels#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQTypeRels/VB/Class1.vb#2)]  
  
 <span data-ttu-id="36684-130">이 다음 코드와 동일 하지만 훨씬 더 간결 하 고 더 쉽게 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36684-130">This is equivalent to the following code, but is much shorter and easier to write.</span></span> <span data-ttu-id="36684-131">쿼리에서 지역 형식 유추를 사용 하는 것은 Visual Basic의 기본 스타일입니다.</span><span class="sxs-lookup"><span data-stu-id="36684-131">Reliance on local type inference in queries is the preferred style in Visual Basic.</span></span>  
  
 [!code-vb[VbLINQTypeRels#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQTypeRels/VB/Class1.vb#3)]  
  
 <span data-ttu-id="36684-132">유형은 암시적 또는 명시적으로 결정 됩니다 없이 모두 이전 코드 예제에서는 다음 관계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36684-132">The following relationships exist in both of the previous code examples, whether the types are determined implicitly or explicitly.</span></span>  
  
1.  <span data-ttu-id="36684-133">데이터 원본에 있는 요소의 형식 `names`, 범위 변수의 형식이 `name`, 쿼리에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="36684-133">The type of the elements in the data source, `names`, is the type of the range variable, `name`, in the query.</span></span>  
  
2.  <span data-ttu-id="36684-134">현재 선택 된 개체의 형식을 `name`, 쿼리 변수 형식을 결정 `mNames`합니다.</span><span class="sxs-lookup"><span data-stu-id="36684-134">The type of the object that is selected, `name`, determines the type of the query variable, `mNames`.</span></span> <span data-ttu-id="36684-135">여기 `name` 문자열 이므로 쿼리 변수는 Visual Basic에서 IEnumerable (Of String).</span><span class="sxs-lookup"><span data-stu-id="36684-135">Here `name` is a string, so the query variable is IEnumerable(Of String) in Visual Basic.</span></span>  
  
3.  <span data-ttu-id="36684-136">에 정의 된 쿼리 `mNames` 에서 실행 되는 `For Each` 루프입니다.</span><span class="sxs-lookup"><span data-stu-id="36684-136">The query defined in `mNames` is executed in the `For Each` loop.</span></span> <span data-ttu-id="36684-137">루프는 쿼리를 실행 한 결과 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="36684-137">The loop iterates over the result of executing the query.</span></span> <span data-ttu-id="36684-138">때문에 `mNames`실행 되는 경우 루프 반복 변수, 문자열의 시퀀스를 반환 하는 `nm`, 문자열 이기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="36684-138">Because `mNames`, when it is executed, will return a sequence of strings, the loop iteration variable, `nm`, also is a string.</span></span>  
  
## <a name="queries-that-return-one-field-from-selected-elements"></a><span data-ttu-id="36684-139">선택한 요소에서 하나의 필드를 반환 하는 쿼리</span><span class="sxs-lookup"><span data-stu-id="36684-139">Queries That Return One Field from Selected Elements</span></span>  
 <span data-ttu-id="36684-140">다음 예제와 [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] 데이터 원본에서 선택한 각 요소의 부분만 포함 된 시퀀스를 반환 하는 작업을 쿼리 합니다.</span><span class="sxs-lookup"><span data-stu-id="36684-140">The following example shows a [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] query operation that returns a sequence containing only one part of each element selected from the data source.</span></span> <span data-ttu-id="36684-141">쿼리는 컬렉션 `Customer` 데이터 원본으로 개체를 프로젝트에 해당 합니다 `Name` 결과의 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="36684-141">The query takes a collection of `Customer` objects as its data source and projects only the `Name` property in the result.</span></span> <span data-ttu-id="36684-142">고객 이름을 문자열 이기 때문에 쿼리 출력으로 문자열 시퀀스를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="36684-142">Because the customer name is a string, the query produces a sequence of strings as output.</span></span>  
  
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
  
 <span data-ttu-id="36684-143">변수 간의 관계는 간단한 예제의 경우와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="36684-143">The relationships between variables are like those in the simpler example.</span></span>  
  
1.  <span data-ttu-id="36684-144">데이터 원본에 있는 요소의 형식 `customers`, 범위 변수의 형식이 `cust`, 쿼리에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="36684-144">The type of the elements in the data source, `customers`, is the type of the range variable, `cust`, in the query.</span></span> <span data-ttu-id="36684-145">이 예에서 유형이 `Customer`합니다.</span><span class="sxs-lookup"><span data-stu-id="36684-145">In this example, that type is `Customer`.</span></span>  
  
2.  <span data-ttu-id="36684-146">`Select` 문 반환 합니다 `Name` 의 각 속성 `Customer` 개체 전체가 아니라 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="36684-146">The `Select` statement returns the `Name` property of each `Customer` object instead of the whole object.</span></span> <span data-ttu-id="36684-147">때문에 `Name` 쿼리 변수를 문자열 `custNames`, 다시 되지 IEnumerable (Of String)의 `Customer`합니다.</span><span class="sxs-lookup"><span data-stu-id="36684-147">Because `Name` is a string, the query variable, `custNames`, will again be IEnumerable(Of String), not of `Customer`.</span></span>  
  
3.  <span data-ttu-id="36684-148">때문에 `custNames` 문자열의 시퀀스를 나타냅니다는 `For Each` 루프의 반복 변수도 `custName`, 문자열 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="36684-148">Because `custNames` represents a sequence of strings, the `For Each` loop's iteration variable, `custName`, must be a string.</span></span>  
  
 <span data-ttu-id="36684-149">지역 형식 유추를 하지 않고 앞의 예제를 쓰고 다음 예제와 같이 이해 하기에 다소 복잡 해질 것입니다.</span><span class="sxs-lookup"><span data-stu-id="36684-149">Without local type inference, the previous example would be more cumbersome to write and to understand, as the following example shows.</span></span>  
  
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
  
## <a name="queries-that-require-anonymous-types"></a><span data-ttu-id="36684-150">익명 형식이 필요로 하는 쿼리</span><span class="sxs-lookup"><span data-stu-id="36684-150">Queries That Require Anonymous Types</span></span>  
 <span data-ttu-id="36684-151">다음 예제에서는 보다 복잡 한 상황을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="36684-151">The following example shows a more complex situation.</span></span> <span data-ttu-id="36684-152">이전 예제에서는 모든 변수 형식을 명시적으로 지정 하기에 편리한 없었습니다.</span><span class="sxs-lookup"><span data-stu-id="36684-152">In the previous example, it was inconvenient to specify types for all the variables explicitly.</span></span> <span data-ttu-id="36684-153">이 예제에서는 불가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="36684-153">In this example, it is impossible.</span></span> <span data-ttu-id="36684-154">전체를 선택 하는 대신 `Customer` 데이터 원본 또는 각 요소에서 단일 필드에서 요소를 `Select` 원래의 두 속성을 반환 하는 절이 쿼리에 `Customer` 개체: `Name` 및 `City`합니다.</span><span class="sxs-lookup"><span data-stu-id="36684-154">Instead of selecting entire `Customer` elements from the data source, or a single field from each element, the `Select` clause in this query returns two properties of the original `Customer` object: `Name` and `City`.</span></span> <span data-ttu-id="36684-155">에 대 한 응답을 `Select` 절 컴파일러가 해당 두 가지 속성을 포함 하는 익명 형식을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="36684-155">In response to the `Select` clause, the compiler defines an anonymous type that contains those two properties.</span></span> <span data-ttu-id="36684-156">실행 결과 `nameCityQuery` 에 `For Each` 루프는 새 익명 형식의 인스턴스 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="36684-156">The result of executing `nameCityQuery` in the `For Each` loop is a collection of instances of the new anonymous type.</span></span> <span data-ttu-id="36684-157">익명 형식에 사용 가능한 이름이 없으므로, 유형을 지정할 수 없습니다 `nameCityQuery` 또는 `custInfo` 명시적으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="36684-157">Because the anonymous type has no usable name, you cannot specify the type of `nameCityQuery` or `custInfo` explicitly.</span></span> <span data-ttu-id="36684-158">즉, 익명 형식, 이름이 없는 형식 대신 사용 하 `String` 에서 `IEnumerable(Of String)`합니다.</span><span class="sxs-lookup"><span data-stu-id="36684-158">That is, with an anonymous type, you have no type name to use in place of `String` in `IEnumerable(Of String)`.</span></span> <span data-ttu-id="36684-159">자세한 내용은 [무명 형식](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="36684-159">For more information, see [Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span></span>  
  
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
  
 <span data-ttu-id="36684-160">이전 예제에서 모든 변수에 대 한 형식을 지정 하려면 가능한 경우에 관계 ֿ ´.</span><span class="sxs-lookup"><span data-stu-id="36684-160">Although it is not possible to specify types for all the variables in the previous example, the relationships remain the same.</span></span>  
  
1.  <span data-ttu-id="36684-161">데이터 원본에 있는 요소의 형식은 쿼리에서 범위 변수의 형식을 다시 합니다.</span><span class="sxs-lookup"><span data-stu-id="36684-161">The type of the elements in the data source is again the type of the range variable in the query.</span></span> <span data-ttu-id="36684-162">이 예에서 `cust` 의 인스턴스가 `Customer`합니다.</span><span class="sxs-lookup"><span data-stu-id="36684-162">In this example, `cust` is an instance of `Customer`.</span></span>  
  
2.  <span data-ttu-id="36684-163">때문에 합니다 `Select` 문에서 쿼리 변수를 무명 형식이 생성 `nameCityQuery`, 익명 형식으로 암시적으로 형식화 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="36684-163">Because the `Select` statement produces an anonymous type, the query variable, `nameCityQuery`, must be implicitly typed as an anonymous type.</span></span> <span data-ttu-id="36684-164">익명 형식을 사용 가능한 이름이 없으므로 있으며 따라서 명시적으로 지정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="36684-164">An anonymous type has no usable name, and therefore cannot be specified explicitly.</span></span>  
  
3.  <span data-ttu-id="36684-165">반복 변수 형식의 `For Each` 루프에는 2 단계에서 만든 익명 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="36684-165">The type of the iteration variable in the `For Each` loop is the anonymous type created in step 2.</span></span> <span data-ttu-id="36684-166">형식에 사용 가능한 이름이 없으므로, 루프 반복 변수의 형식이 암시적으로 결정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="36684-166">Because the type has no usable name, the type of the loop iteration variable must be determined implicitly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36684-167">참고자료</span><span class="sxs-lookup"><span data-stu-id="36684-167">See also</span></span>
- [<span data-ttu-id="36684-168">Visual Basic에서 LINQ 시작</span><span class="sxs-lookup"><span data-stu-id="36684-168">Getting Started with LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)
- [<span data-ttu-id="36684-169">익명 형식</span><span class="sxs-lookup"><span data-stu-id="36684-169">Anonymous Types</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
- [<span data-ttu-id="36684-170">지역 형식 유추</span><span class="sxs-lookup"><span data-stu-id="36684-170">Local Type Inference</span></span>](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="36684-171">Visual Basic의 LINQ 소개</span><span class="sxs-lookup"><span data-stu-id="36684-171">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="36684-172">LINQ</span><span class="sxs-lookup"><span data-stu-id="36684-172">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [<span data-ttu-id="36684-173">쿼리</span><span class="sxs-lookup"><span data-stu-id="36684-173">Queries</span></span>](../../../../visual-basic/language-reference/queries/index.md)
