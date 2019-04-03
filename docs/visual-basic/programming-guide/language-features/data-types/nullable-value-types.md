---
title: Nullable 값 형식(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Nullable
helpviewer_keywords:
- nullable types [Visual Basic]
- '? [Visual Basic]'
- types [Visual Basic], nullable
- nullable types [Visual Basic]
- data types [Visual Basic], nullable
ms.assetid: 9ac3b602-6f96-4e6d-96f7-cd4e81c468a6
ms.openlocfilehash: 437107bb522e1635dffa4a2de88c5d10d6707592
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58825146"
---
# <a name="nullable-value-types-visual-basic"></a><span data-ttu-id="ac269-102">Nullable 값 형식(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ac269-102">Nullable Value Types (Visual Basic)</span></span>
<span data-ttu-id="ac269-103">경우에 따라 특정 상황에서 정의 된 값이 없는 값 형식을 사용 하 여 작업할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac269-103">Sometimes you work with a value type that does not have a defined value in certain circumstances.</span></span> <span data-ttu-id="ac269-104">예를 들어 데이터베이스의 필드 구분 하기 위해 의미 있는 있는 할당 된 값이 있는 할당된 된 값 없는 한 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac269-104">For example, a field in a database might have to distinguish between having an assigned value that is meaningful and not having an assigned value.</span></span> <span data-ttu-id="ac269-105">값 형식 매개 변수 정상 값 또는 null 값을 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac269-105">Value types can be extended to take either their normal values or a null value.</span></span> <span data-ttu-id="ac269-106">이러한 확장은 호출을 *nullable 형식*합니다.</span><span class="sxs-lookup"><span data-stu-id="ac269-106">Such an extension is called a *nullable type*.</span></span>  
  
 <span data-ttu-id="ac269-107">Nullable 형식에 각 제네릭에서 생성 되 <xref:System.Nullable%601> 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="ac269-107">Each nullable type is constructed from the generic <xref:System.Nullable%601> structure.</span></span> <span data-ttu-id="ac269-108">데이터베이스를 작업 관련 작업을 추적 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ac269-108">Consider a database that tracks work-related activities.</span></span> <span data-ttu-id="ac269-109">다음 예제에서는 null을 허용 생성 `Boolean` 형식과 해당 형식의 변수를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac269-109">The following example constructs a nullable `Boolean` type and declares a variable of that type.</span></span> <span data-ttu-id="ac269-110">세 가지 방법으로 선언을 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac269-110">You can write the declaration in three ways:</span></span>  
  
 [!code-vb[VbVbalrNullableValue#1](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#1)]  
  
 <span data-ttu-id="ac269-111">변수의 `ridesBusToWork` 의 값을 보유할 수 `True`, 값 `False`, 또는 모두에 값이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ac269-111">The variable `ridesBusToWork` can hold a value of `True`, a value of `False`, or no value at all.</span></span> <span data-ttu-id="ac269-112">초기 기본값은 값에는 예에서 것을 의미할 수도이 사용자에 대 한 정보를 아직 획득 하지.</span><span class="sxs-lookup"><span data-stu-id="ac269-112">Its initial default value is no value at all, which in this case could mean that the information has not yet been obtained for this person.</span></span> <span data-ttu-id="ac269-113">반면, `False` 가져온 정보를 사용자 버스로 작동 하지 않는 의미할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac269-113">In contrast, `False` could mean that the information has been obtained and the person does not ride the bus to work.</span></span>  
  
 <span data-ttu-id="ac269-114">Nullable 형식의 변수 및 속성을 선언할 수 있습니다 하 고 nullable 형식의 요소가 있는 배열을 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac269-114">You can declare variables and properties with nullable types, and you can declare an array with elements of a nullable type.</span></span> <span data-ttu-id="ac269-115">프로시저 매개 변수로 null 허용 형식으로 선언할 수 있으며에서 nullable 형식을 반환할 수 있습니다는 `Function` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="ac269-115">You can declare procedures with nullable types as parameters, and you can return a nullable type from a `Function` procedure.</span></span>  
  
 <span data-ttu-id="ac269-116">배열 같은 참조 형식에서 nullable 형식을 생성할 수 없습니다. 한 `String`, 또는 클래스.</span><span class="sxs-lookup"><span data-stu-id="ac269-116">You cannot construct a nullable type on a reference type such as an array, a `String`, or a class.</span></span> <span data-ttu-id="ac269-117">기본 형식이 값 형식 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac269-117">The underlying type must be a value type.</span></span> <span data-ttu-id="ac269-118">자세한 내용은 [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ac269-118">For more information, see [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md).</span></span>  
  
## <a name="using-a-nullable-type-variable"></a><span data-ttu-id="ac269-119">Nullable 형식 변수를 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="ac269-119">Using a Nullable Type Variable</span></span>  
 <span data-ttu-id="ac269-120">Nullable 형식의 가장 중요 한 멤버는 해당 <xref:System.Nullable%601.HasValue%2A> 고 <xref:System.Nullable%601.Value%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="ac269-120">The most important members of a nullable type are its <xref:System.Nullable%601.HasValue%2A> and <xref:System.Nullable%601.Value%2A> properties.</span></span> <span data-ttu-id="ac269-121">Nullable 형식의 변수에 대 한 <xref:System.Nullable%601.HasValue%2A> 변수에 정의 된 값을 포함 하는 여부를 알려 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ac269-121">For a variable of a nullable type, <xref:System.Nullable%601.HasValue%2A> tells you whether the variable contains a defined value.</span></span> <span data-ttu-id="ac269-122">하는 경우 <xref:System.Nullable%601.HasValue%2A> 됩니다 `True`에서 값을 읽을 수 있습니다 <xref:System.Nullable%601.Value%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="ac269-122">If <xref:System.Nullable%601.HasValue%2A> is `True`, you can read the value from <xref:System.Nullable%601.Value%2A>.</span></span> <span data-ttu-id="ac269-123">둘 다 <xref:System.Nullable%601.HasValue%2A> 하 고 <xref:System.Nullable%601.Value%2A> 는 `ReadOnly` 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="ac269-123">Note that both <xref:System.Nullable%601.HasValue%2A> and <xref:System.Nullable%601.Value%2A> are `ReadOnly` properties.</span></span>  
  
### <a name="default-values"></a><span data-ttu-id="ac269-124">기본값</span><span class="sxs-lookup"><span data-stu-id="ac269-124">Default Values</span></span>  
 <span data-ttu-id="ac269-125">Nullable 형식으로 변수를 선언 하는 경우 해당 <xref:System.Nullable%601.HasValue%2A> 속성의 기본값은 `False`합니다.</span><span class="sxs-lookup"><span data-stu-id="ac269-125">When you declare a variable with a nullable type, its <xref:System.Nullable%601.HasValue%2A> property has a default value of `False`.</span></span> <span data-ttu-id="ac269-126">이 기본적으로 변수에 정의 된 값이 없으며 기본 값 형식의 기본값 대신 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac269-126">This means that by default the variable has no defined value, instead of the default value of its underlying value type.</span></span> <span data-ttu-id="ac269-127">다음 예에서 변수 `numberOfChildren` 처음에 정의 된 값이 없으며도의 기본값은 `Integer` 형식은 0입니다.</span><span class="sxs-lookup"><span data-stu-id="ac269-127">In the following example, the variable `numberOfChildren` initially has no defined value, even though the default value of the `Integer` type is 0.</span></span>  
  
 [!code-vb[VbVbalrNullableValue#2](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#2)]  
  
 <span data-ttu-id="ac269-128">Null 값이 정의 되지 않거나 알 수 없는 값을 나타내는 데 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac269-128">A null value is useful to indicate an undefined or unknown value.</span></span> <span data-ttu-id="ac269-129">하는 경우 `numberOfChildren` 로 선언 `Integer`, 정보를 현재 사용할 수 없는 나타낼 수 있는 값이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac269-129">If `numberOfChildren` had been declared as `Integer`, there would be no value that could indicate that the information is not currently available.</span></span>  
  
### <a name="storing-values"></a><span data-ttu-id="ac269-130">값 저장</span><span class="sxs-lookup"><span data-stu-id="ac269-130">Storing Values</span></span>  
 <span data-ttu-id="ac269-131">일반적인 방식으로 변수 또는 nullable 형식의 속성에 값을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac269-131">You store a value in a variable or property of a nullable type in the typical way.</span></span> <span data-ttu-id="ac269-132">다음 예제에서는 값을 변수에 할당 `numberOfChildren` 이전 예제의 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac269-132">The following example assigns a value to the variable `numberOfChildren` declared in the previous example.</span></span>  
  
 [!code-vb[VbVbalrNullableValue#3](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#3)]  
  
 <span data-ttu-id="ac269-133">변수 또는 nullable 형식의 속성에 정의 된 값이 있으면 해당 하지 않는 경우 할당 된 값의 초기 상태로 되돌리려면 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac269-133">If a variable or property of a nullable type contains a defined value, you can cause it to revert to its initial state of not having a value assigned.</span></span> <span data-ttu-id="ac269-134">변수 또는 속성을 설정 하 여이 작업을 수행 `Nothing`다음 예제와 같이 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac269-134">You do this by setting the variable or property to `Nothing`, as the following example shows.</span></span>  
  
 [!code-vb[VbVbalrNullableValue#4](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#4)]  
  
> [!NOTE]
>  <span data-ttu-id="ac269-135">할당할 수 있지만 `Nothing` nullable 형식의 변수에 대해 테스트할 수 없습니다 있습니다 `Nothing` 등호를 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac269-135">Although you can assign `Nothing` to a variable of a nullable type, you cannot test it for `Nothing` by using the equal sign.</span></span> <span data-ttu-id="ac269-136">등호를 사용 하는 비교 `someVar = Nothing`를 항상 평가 `Nothing`합니다.</span><span class="sxs-lookup"><span data-stu-id="ac269-136">Comparison that uses the equal sign, `someVar = Nothing`, always evaluates to `Nothing`.</span></span> <span data-ttu-id="ac269-137">변수를 테스트할 수 있습니다 <xref:System.Nullable%601.HasValue%2A> 속성에 대 한 `False`, 또는 사용 하 여 테스트 합니다 `Is` 또는 `IsNot` 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="ac269-137">You can test the variable's <xref:System.Nullable%601.HasValue%2A> property for `False`, or test by using the `Is` or `IsNot` operator.</span></span>  
  
### <a name="retrieving-values"></a><span data-ttu-id="ac269-138">값 검색</span><span class="sxs-lookup"><span data-stu-id="ac269-138">Retrieving Values</span></span>  
 <span data-ttu-id="ac269-139">Nullable 형식의 변수 값을 검색 하려면 먼저을 테스트 해야 해당 <xref:System.Nullable%601.HasValue%2A> 속성 값이 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac269-139">To retrieve the value of a variable of a nullable type, you should first test its <xref:System.Nullable%601.HasValue%2A> property to confirm that it has a value.</span></span> <span data-ttu-id="ac269-140">값을 읽을 하려고 하면 때 <xref:System.Nullable%601.HasValue%2A> 됩니다 `False`, Visual Basic throw는 <xref:System.InvalidOperationException> 예외입니다.</span><span class="sxs-lookup"><span data-stu-id="ac269-140">If you try to read the value when <xref:System.Nullable%601.HasValue%2A> is `False`, Visual Basic throws an <xref:System.InvalidOperationException> exception.</span></span> <span data-ttu-id="ac269-141">다음 예제에서는 변수를 읽을 수 있는 좋은 `numberOfChildren` 앞의 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="ac269-141">The following example shows the recommended way to read the variable `numberOfChildren` of the previous examples.</span></span>  
  
 [!code-vb[VbVbalrNullableValue#5](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#5)]  
  
## <a name="comparing-nullable-types"></a><span data-ttu-id="ac269-142">Nullable 형식 비교</span><span class="sxs-lookup"><span data-stu-id="ac269-142">Comparing Nullable Types</span></span>  
 <span data-ttu-id="ac269-143">Null을 허용 하는 경우 `Boolean` 변수는 부울 식에 사용 되 고, 표시 될 수 있습니다 `True`하십시오 `False`, 또는 `Nothing`합니다.</span><span class="sxs-lookup"><span data-stu-id="ac269-143">When nullable `Boolean` variables are used in Boolean expressions, the result can be `True`, `False`, or `Nothing`.</span></span> <span data-ttu-id="ac269-144">다음은 한 진리표 `And` 고 `Or`입니다.</span><span class="sxs-lookup"><span data-stu-id="ac269-144">The following is the truth table for `And` and `Or`.</span></span> <span data-ttu-id="ac269-145">때문에 `b1` 및 `b2` 이제 다음 3 가지 가능한 값인 9 조합을 평가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac269-145">Because `b1` and `b2` now have three possible values, there are nine combinations to evaluate.</span></span>  
  
|<span data-ttu-id="ac269-146">b1</span><span class="sxs-lookup"><span data-stu-id="ac269-146">b1</span></span>|<span data-ttu-id="ac269-147">b2</span><span class="sxs-lookup"><span data-stu-id="ac269-147">b2</span></span>|<span data-ttu-id="ac269-148">b1 및 b2</span><span class="sxs-lookup"><span data-stu-id="ac269-148">b1 And b2</span></span>|<span data-ttu-id="ac269-149">b1 또는 b2</span><span class="sxs-lookup"><span data-stu-id="ac269-149">b1 Or b2</span></span>|  
|--------|--------|---------------|--------------|  
|`Nothing`|`Nothing`|`Nothing`|`Nothing`|  
|`Nothing`|`True`|`Nothing`|`True`|  
|`Nothing`|`False`|`False`|`Nothing`|  
|`True`|`Nothing`|`Nothing`|`True`|  
|`True`|`True`|`True`|`True`|  
|`True`|`False`|`False`|`True`|  
|`False`|`Nothing`|`False`|`Nothing`|  
|`False`|`True`|`False`|`True`|  
|`False`|`False`|`False`|`False`|  
  
 <span data-ttu-id="ac269-150">부울 변수 또는 식의 값이 `Nothing`를 둘 다를 것 `true` 도 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="ac269-150">When the value of a Boolean variable or expression is `Nothing`, it is neither `true` nor `false`.</span></span> <span data-ttu-id="ac269-151">다음 예제를 살펴보십시오.</span><span class="sxs-lookup"><span data-stu-id="ac269-151">Consider the following example.</span></span>  
  
 [!code-vb[VbVbalrNullableValue#6](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#6)]  
  
 <span data-ttu-id="ac269-152">이 예에서 `b1 And b2` 로 `Nothing`합니다.</span><span class="sxs-lookup"><span data-stu-id="ac269-152">In this example, `b1 And b2` evaluates to `Nothing`.</span></span> <span data-ttu-id="ac269-153">결과적으로 `Else` 각 절이 실행 `If` 문과 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ac269-153">As a result, the `Else` clause is executed in each `If` statement, and the output is as follows:</span></span>  
  
 `Expression is not true`  
  
 `Expression is not false`  
  
> [!NOTE]
>  <span data-ttu-id="ac269-154">`AndAlso` 및 `OrElse`를 사용 하는 평가 단락 (short-circuit) 계산 되어야 합니다 두 번째 피연산자를 첫 번째 평가 되 면 `Nothing`합니다.</span><span class="sxs-lookup"><span data-stu-id="ac269-154">`AndAlso` and `OrElse`, which use short-circuit evaluation, must evaluate their second operands when the first evaluates to `Nothing`.</span></span>  
  
## <a name="propagation"></a><span data-ttu-id="ac269-155">전파</span><span class="sxs-lookup"><span data-stu-id="ac269-155">Propagation</span></span>  
 <span data-ttu-id="ac269-156">하나 또는 두 피연산자는 산술, 비교, 시프트 또는 형식 작업의 nullable 인 경우 작업의 결과 nullable 이기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac269-156">If one or both of the operands of an arithmetic, comparison, shift, or type operation is nullable, the result of the operation is also nullable.</span></span> <span data-ttu-id="ac269-157">두 피연산자 모두 값이 없는 경우 `Nothing`, 작업을 둘 다 있는 것 처럼 기본 피연산자 값에 수행할는 nullable 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="ac269-157">If both operands have values that are not `Nothing`, the operation is performed on the underlying values of the operands, as if neither were a nullable type.</span></span> <span data-ttu-id="ac269-158">다음 예에서 변수 `compare1` 고 `sum1` 를 암시적으로 형식화 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac269-158">In the following example, variables `compare1` and `sum1` are implicitly typed.</span></span> <span data-ttu-id="ac269-159">위로 마우스 포인터를 놓으면 컴파일러는 둘 다에 대 한 nullable 형식 유추는 표시 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac269-159">If you rest the mouse pointer over them, you will see that the compiler infers nullable types for both of them.</span></span>  
  
 [!code-vb[VbVbalrNullableValue#7](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#7)]  
  
 <span data-ttu-id="ac269-160">하나 또는 두 피연산자의 값이 있어야 하는 경우 `Nothing`에 반환 됩니다 `Nothing`합니다.</span><span class="sxs-lookup"><span data-stu-id="ac269-160">If one or both operands have a value of `Nothing`, the result will be `Nothing`.</span></span>  
  
 [!code-vb[VbVbalrNullableValue#8](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#8)]  
  
## <a name="using-nullable-types-with-data"></a><span data-ttu-id="ac269-161">데이터를 사용 하 여 Nullable 형식 사용</span><span class="sxs-lookup"><span data-stu-id="ac269-161">Using Nullable Types with Data</span></span>  
 <span data-ttu-id="ac269-162">데이터베이스는 null 허용 형식을 사용 하 여 가장 중요 한 위치 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="ac269-162">A database is one of the most important places to use nullable types.</span></span> <span data-ttu-id="ac269-163">일부 데이터베이스 개체에는 현재 nullable 형식 지원 않지만 테이블 디자이너에서 생성 된 어댑터입니다.</span><span class="sxs-lookup"><span data-stu-id="ac269-163">Not all database objects currently support nullable types, but the designer-generated table adapters do.</span></span> <span data-ttu-id="ac269-164">"TableAdapter Nullable 형식 지원"을 참조 하세요 [TableAdapter 개요](/visualstudio/data-tools/tableadapter-overview)합니다.</span><span class="sxs-lookup"><span data-stu-id="ac269-164">See "TableAdapter Support for Nullable Types" in [TableAdapter Overview](/visualstudio/data-tools/tableadapter-overview).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ac269-165">참고자료</span><span class="sxs-lookup"><span data-stu-id="ac269-165">See also</span></span>

- <xref:System.InvalidOperationException>
- <xref:System.Nullable%601.HasValue%2A>
- [<span data-ttu-id="ac269-166">Nullable 형식 사용</span><span class="sxs-lookup"><span data-stu-id="ac269-166">Using Nullable Types</span></span>](../../../../csharp/programming-guide/nullable-types/using-nullable-types.md)
- [<span data-ttu-id="ac269-167">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="ac269-167">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [<span data-ttu-id="ac269-168">Value Types and Reference Types</span><span class="sxs-lookup"><span data-stu-id="ac269-168">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [<span data-ttu-id="ac269-169">데이터 형식 문제 해결</span><span class="sxs-lookup"><span data-stu-id="ac269-169">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [<span data-ttu-id="ac269-170">TableAdapter 개요</span><span class="sxs-lookup"><span data-stu-id="ac269-170">TableAdapter Overview</span></span>](/visualstudio/data-tools/tableadapter-overview)
- [<span data-ttu-id="ac269-171">If 연산자</span><span class="sxs-lookup"><span data-stu-id="ac269-171">If Operator</span></span>](../../../../visual-basic/language-reference/operators/if-operator.md)
- [<span data-ttu-id="ac269-172">지역 형식 유추</span><span class="sxs-lookup"><span data-stu-id="ac269-172">Local Type Inference</span></span>](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="ac269-173">Is 연산자</span><span class="sxs-lookup"><span data-stu-id="ac269-173">Is Operator</span></span>](../../../../visual-basic/language-reference/operators/is-operator.md)
- [<span data-ttu-id="ac269-174">IsNot 연산자</span><span class="sxs-lookup"><span data-stu-id="ac269-174">IsNot Operator</span></span>](../../../../visual-basic/language-reference/operators/isnot-operator.md)
