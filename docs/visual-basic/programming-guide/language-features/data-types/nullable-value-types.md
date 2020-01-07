---
title: Nullable 값 형식
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
ms.openlocfilehash: 0d259e11a969f4eb7e64626a4adf498db06ece06
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/25/2019
ms.locfileid: "75347833"
---
# <a name="nullable-value-types-visual-basic"></a><span data-ttu-id="fc041-102">Nullable 값 형식(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fc041-102">Nullable Value Types (Visual Basic)</span></span>

<span data-ttu-id="fc041-103">특정 상황에서 정의 된 값이 없는 값 형식을 사용 하는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc041-103">Sometimes you work with a value type that does not have a defined value in certain circumstances.</span></span> <span data-ttu-id="fc041-104">예를 들어 데이터베이스의 필드는 할당 된 값이 있는 것을 의미 하는 값이 할당 되는 것을 구분 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc041-104">For example, a field in a database might have to distinguish between having an assigned value that is meaningful and not having an assigned value.</span></span> <span data-ttu-id="fc041-105">값 형식은 일반 값 이나 null 값을 사용 하도록 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc041-105">Value types can be extended to take either their normal values or a null value.</span></span> <span data-ttu-id="fc041-106">이러한 확장을 *nullable 형식*이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc041-106">Such an extension is called a *nullable type*.</span></span>

<span data-ttu-id="fc041-107">각 nullable 형식은 제네릭 <xref:System.Nullable%601> 구조체에서 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc041-107">Each nullable type is constructed from the generic <xref:System.Nullable%601> structure.</span></span> <span data-ttu-id="fc041-108">작업 관련 작업을 추적 하는 데이터베이스를 고려 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc041-108">Consider a database that tracks work-related activities.</span></span> <span data-ttu-id="fc041-109">다음 예제에서는 nullable `Boolean` 형식을 생성 하 고 해당 형식의 변수를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc041-109">The following example constructs a nullable `Boolean` type and declares a variable of that type.</span></span> <span data-ttu-id="fc041-110">다음 세 가지 방법으로 선언을 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc041-110">You can write the declaration in three ways:</span></span>

[!code-vb[VbVbalrNullableValue#1](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#1)]

<span data-ttu-id="fc041-111">변수 `ridesBusToWork` `True`값, `False`값 또는 값 없음을 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc041-111">The variable `ridesBusToWork` can hold a value of `True`, a value of `False`, or no value at all.</span></span> <span data-ttu-id="fc041-112">초기 기본값은 값이 아닙니다 .이 경우이 사용자에 대 한 정보가 아직 획득 되지 않았음을 의미할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc041-112">Its initial default value is no value at all, which in this case could mean that the information has not yet been obtained for this person.</span></span> <span data-ttu-id="fc041-113">이와 달리 `False`은 정보를 얻고 사용자는 버스를 사용 하 여 작동 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc041-113">In contrast, `False` could mean that the information has been obtained and the person does not ride the bus to work.</span></span>

<span data-ttu-id="fc041-114">Nullable 형식을 사용 하 여 변수 및 속성을 선언할 수 있으며 nullable 형식의 요소가 포함 된 배열을 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc041-114">You can declare variables and properties with nullable types, and you can declare an array with elements of a nullable type.</span></span> <span data-ttu-id="fc041-115">Nullable 형식을 매개 변수로 사용 하 여 프로시저를 선언 하 고 `Function` 프로시저에서 nullable 형식을 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc041-115">You can declare procedures with nullable types as parameters, and you can return a nullable type from a `Function` procedure.</span></span>

<span data-ttu-id="fc041-116">배열, `String`또는 클래스와 같은 참조 형식에서 nullable 형식을 생성할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fc041-116">You cannot construct a nullable type on a reference type such as an array, a `String`, or a class.</span></span> <span data-ttu-id="fc041-117">내부 형식은 값 형식 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc041-117">The underlying type must be a value type.</span></span> <span data-ttu-id="fc041-118">자세한 내용은 [Value Types and Reference Types](value-types-and-reference-types.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fc041-118">For more information, see [Value Types and Reference Types](value-types-and-reference-types.md).</span></span>

## <a name="using-a-nullable-type-variable"></a><span data-ttu-id="fc041-119">Nullable 형식 변수 사용</span><span class="sxs-lookup"><span data-stu-id="fc041-119">Using a Nullable Type Variable</span></span>

<span data-ttu-id="fc041-120">Nullable 형식의 가장 중요 한 멤버는 <xref:System.Nullable%601.HasValue%2A> 및 <xref:System.Nullable%601.Value%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="fc041-120">The most important members of a nullable type are its <xref:System.Nullable%601.HasValue%2A> and <xref:System.Nullable%601.Value%2A> properties.</span></span> <span data-ttu-id="fc041-121">Nullable 형식의 변수에 대해 <xref:System.Nullable%601.HasValue%2A>는 변수에 정의 된 값이 포함 되어 있는지 여부를 알려 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fc041-121">For a variable of a nullable type, <xref:System.Nullable%601.HasValue%2A> tells you whether the variable contains a defined value.</span></span> <span data-ttu-id="fc041-122"><xref:System.Nullable%601.HasValue%2A> `True`경우 <xref:System.Nullable%601.Value%2A>에서 값을 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc041-122">If <xref:System.Nullable%601.HasValue%2A> is `True`, you can read the value from <xref:System.Nullable%601.Value%2A>.</span></span> <span data-ttu-id="fc041-123"><xref:System.Nullable%601.HasValue%2A> 및 <xref:System.Nullable%601.Value%2A>는 모두 `ReadOnly` 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="fc041-123">Note that both <xref:System.Nullable%601.HasValue%2A> and <xref:System.Nullable%601.Value%2A> are `ReadOnly` properties.</span></span>

### <a name="default-values"></a><span data-ttu-id="fc041-124">기본값</span><span class="sxs-lookup"><span data-stu-id="fc041-124">Default Values</span></span>

<span data-ttu-id="fc041-125">Nullable 형식을 사용 하 여 변수를 선언 하는 경우 해당 <xref:System.Nullable%601.HasValue%2A> 속성의 기본값은 `False`입니다.</span><span class="sxs-lookup"><span data-stu-id="fc041-125">When you declare a variable with a nullable type, its <xref:System.Nullable%601.HasValue%2A> property has a default value of `False`.</span></span> <span data-ttu-id="fc041-126">즉, 기본적으로 변수에는 기본 값 형식의 기본 값 대신 정의 된 값이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fc041-126">This means that by default the variable has no defined value, instead of the default value of its underlying value type.</span></span> <span data-ttu-id="fc041-127">다음 예에서는 `Integer` 형식의 기본값이 0 이더라도 변수 `numberOfChildren` 처음에는 정의 된 값이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fc041-127">In the following example, the variable `numberOfChildren` initially has no defined value, even though the default value of the `Integer` type is 0.</span></span>

[!code-vb[VbVbalrNullableValue#2](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#2)]

<span data-ttu-id="fc041-128">Null 값은 정의 되지 않거나 알 수 없는 값을 나타내는 데 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc041-128">A null value is useful to indicate an undefined or unknown value.</span></span> <span data-ttu-id="fc041-129">`numberOfChildren` `Integer`으로 선언 된 경우 정보를 현재 사용할 수 없음을 나타낼 수 있는 값이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fc041-129">If `numberOfChildren` had been declared as `Integer`, there would be no value that could indicate that the information is not currently available.</span></span>

### <a name="storing-values"></a><span data-ttu-id="fc041-130">값 저장</span><span class="sxs-lookup"><span data-stu-id="fc041-130">Storing Values</span></span>

<span data-ttu-id="fc041-131">일반적으로 nullable 형식의 변수 또는 속성에 값을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc041-131">You store a value in a variable or property of a nullable type in the typical way.</span></span> <span data-ttu-id="fc041-132">다음 예제에서는 이전 예제에서 선언 `numberOfChildren` 변수에 값을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc041-132">The following example assigns a value to the variable `numberOfChildren` declared in the previous example.</span></span>

[!code-vb[VbVbalrNullableValue#3](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#3)]

<span data-ttu-id="fc041-133">Nullable 형식의 변수 또는 속성이 정의 된 값을 포함 하는 경우 해당 값이 할당 되지 않은 초기 상태로 되돌아갈 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc041-133">If a variable or property of a nullable type contains a defined value, you can cause it to revert to its initial state of not having a value assigned.</span></span> <span data-ttu-id="fc041-134">이렇게 하려면 다음 예제와 같이 변수나 속성을 `Nothing`로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc041-134">You do this by setting the variable or property to `Nothing`, as the following example shows.</span></span>

[!code-vb[VbVbalrNullableValue#4](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#4)]

> [!NOTE]
> <span data-ttu-id="fc041-135">Nullable 형식의 변수에 `Nothing`를 할당할 수 있지만 등호를 사용 하 여 `Nothing`에 대해 테스트할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fc041-135">Although you can assign `Nothing` to a variable of a nullable type, you cannot test it for `Nothing` by using the equal sign.</span></span> <span data-ttu-id="fc041-136">등호 (`someVar = Nothing`)를 사용 하는 비교는 항상 `Nothing`으로 평가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc041-136">Comparison that uses the equal sign, `someVar = Nothing`, always evaluates to `Nothing`.</span></span> <span data-ttu-id="fc041-137">`Is` 또는 `IsNot` 연산자를 사용 하 여 `False`에 대해 변수의 <xref:System.Nullable%601.HasValue%2A> 속성을 테스트 하거나 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc041-137">You can test the variable's <xref:System.Nullable%601.HasValue%2A> property for `False`, or test by using the `Is` or `IsNot` operator.</span></span>

### <a name="retrieving-values"></a><span data-ttu-id="fc041-138">값 검색</span><span class="sxs-lookup"><span data-stu-id="fc041-138">Retrieving Values</span></span>

<span data-ttu-id="fc041-139">Nullable 형식의 변수 값을 검색 하려면 먼저 해당 <xref:System.Nullable%601.HasValue%2A> 속성을 테스트 하 여 값이 있는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc041-139">To retrieve the value of a variable of a nullable type, you should first test its <xref:System.Nullable%601.HasValue%2A> property to confirm that it has a value.</span></span> <span data-ttu-id="fc041-140"><xref:System.Nullable%601.HasValue%2A> `False`될 때 값을 읽으려고 하는 경우 Visual Basic <xref:System.InvalidOperationException> 예외를 throw 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc041-140">If you try to read the value when <xref:System.Nullable%601.HasValue%2A> is `False`, Visual Basic throws an <xref:System.InvalidOperationException> exception.</span></span> <span data-ttu-id="fc041-141">다음 예에서는 이전 예제의 `numberOfChildren` 변수를 읽는 권장 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fc041-141">The following example shows the recommended way to read the variable `numberOfChildren` of the previous examples.</span></span>

[!code-vb[VbVbalrNullableValue#5](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#5)]

## <a name="comparing-nullable-types"></a><span data-ttu-id="fc041-142">Nullable 형식 비교</span><span class="sxs-lookup"><span data-stu-id="fc041-142">Comparing Nullable Types</span></span>

<span data-ttu-id="fc041-143">Nullable `Boolean` 변수가 부울 식에 사용 되는 경우 결과는 `True`, `False`또는 `Nothing`수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc041-143">When nullable `Boolean` variables are used in Boolean expressions, the result can be `True`, `False`, or `Nothing`.</span></span> <span data-ttu-id="fc041-144">다음은 `And` 및 `Or`에 대 한 진위 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="fc041-144">The following is the truth table for `And` and `Or`.</span></span> <span data-ttu-id="fc041-145">`b1` 및 `b2`에는 세 가지 가능한 값이 있기 때문에 평가할 조합 수는 9 개입니다.</span><span class="sxs-lookup"><span data-stu-id="fc041-145">Because `b1` and `b2` now have three possible values, there are nine combinations to evaluate.</span></span>

|<span data-ttu-id="fc041-146">b1</span><span class="sxs-lookup"><span data-stu-id="fc041-146">b1</span></span>|<span data-ttu-id="fc041-147">b2</span><span class="sxs-lookup"><span data-stu-id="fc041-147">b2</span></span>|<span data-ttu-id="fc041-148">b1 및 b2</span><span class="sxs-lookup"><span data-stu-id="fc041-148">b1 And b2</span></span>|<span data-ttu-id="fc041-149">b1 또는 b2</span><span class="sxs-lookup"><span data-stu-id="fc041-149">b1 Or b2</span></span>|
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

<span data-ttu-id="fc041-150">부울 변수 또는 식의 값이 `Nothing`경우에는 `true` 나 `false`되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fc041-150">When the value of a Boolean variable or expression is `Nothing`, it is neither `true` nor `false`.</span></span> <span data-ttu-id="fc041-151">다음 예제를 살펴보십시오.</span><span class="sxs-lookup"><span data-stu-id="fc041-151">Consider the following example.</span></span>

[!code-vb[VbVbalrNullableValue#6](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#6)]

<span data-ttu-id="fc041-152">이 예제에서 `b1 And b2`은 `Nothing`으로 평가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc041-152">In this example, `b1 And b2` evaluates to `Nothing`.</span></span> <span data-ttu-id="fc041-153">따라서 `Else` 절은 각 `If` 문에서 실행 되며 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fc041-153">As a result, the `Else` clause is executed in each `If` statement, and the output is as follows:</span></span>

`Expression is not true`

`Expression is not false`

> [!NOTE]
> <span data-ttu-id="fc041-154">단락 평가를 사용 하는 `AndAlso` 및 `OrElse`는 첫 번째 피연산자가 `Nothing`될 때 두 번째 피연산자를 계산 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc041-154">`AndAlso` and `OrElse`, which use short-circuit evaluation, must evaluate their second operands when the first evaluates to `Nothing`.</span></span>

## <a name="propagation"></a><span data-ttu-id="fc041-155">전파</span><span class="sxs-lookup"><span data-stu-id="fc041-155">Propagation</span></span>

<span data-ttu-id="fc041-156">산술 연산자, 비교 연산자 또는 형식 작업의 피연산자 중 하나 또는 둘 다가 null을 허용 하면 작업 결과도 nullable입니다.</span><span class="sxs-lookup"><span data-stu-id="fc041-156">If one or both of the operands of an arithmetic, comparison, shift, or type operation is nullable, the result of the operation is also nullable.</span></span> <span data-ttu-id="fc041-157">두 피연산자의 값이 모두 `Nothing`되지 않은 경우 nullable 형식이 아닌 것 처럼 피연산자의 기본 값에 대해 연산이 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc041-157">If both operands have values that are not `Nothing`, the operation is performed on the underlying values of the operands, as if neither were a nullable type.</span></span> <span data-ttu-id="fc041-158">다음 예제에서는 `compare1` 및 `sum1` 변수를 암시적으로 형식화 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc041-158">In the following example, variables `compare1` and `sum1` are implicitly typed.</span></span> <span data-ttu-id="fc041-159">마우스 포인터를 올려 놓으면 컴파일러가 두 항목 모두에 대해 nullable 형식을 유추 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc041-159">If you rest the mouse pointer over them, you will see that the compiler infers nullable types for both of them.</span></span>

[!code-vb[VbVbalrNullableValue#7](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#7)]

<span data-ttu-id="fc041-160">피연산자 중 하나 또는 둘 다에 `Nothing`값이 있으면 결과가 `Nothing`됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc041-160">If one or both operands have a value of `Nothing`, the result will be `Nothing`.</span></span>

[!code-vb[VbVbalrNullableValue#8](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#8)]

## <a name="using-nullable-types-with-data"></a><span data-ttu-id="fc041-161">데이터에 Nullable 형식 사용</span><span class="sxs-lookup"><span data-stu-id="fc041-161">Using Nullable Types with Data</span></span>

<span data-ttu-id="fc041-162">데이터베이스는 nullable 형식을 사용 하는 가장 중요 한 위치 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="fc041-162">A database is one of the most important places to use nullable types.</span></span> <span data-ttu-id="fc041-163">일부 데이터베이스 개체는 현재 nullable 형식을 지원 하지만 디자이너에서 생성 한 테이블 어댑터는 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fc041-163">Not all database objects currently support nullable types, but the designer-generated table adapters do.</span></span> <span data-ttu-id="fc041-164">[Nullable 형식에 대 한 TableAdapter 지원을](/visualstudio/data-tools/fill-datasets-by-using-tableadapters#tableadapter-support-for-nullable-types)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fc041-164">See [TableAdapter support for nullable types](/visualstudio/data-tools/fill-datasets-by-using-tableadapters#tableadapter-support-for-nullable-types).</span></span>

## <a name="see-also"></a><span data-ttu-id="fc041-165">참조</span><span class="sxs-lookup"><span data-stu-id="fc041-165">See also</span></span>

- <xref:System.InvalidOperationException>
- <xref:System.Nullable%601.HasValue%2A>
- [<span data-ttu-id="fc041-166">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="fc041-166">Data Types</span></span>](index.md)
- [<span data-ttu-id="fc041-167">값 형식과 참조 형식</span><span class="sxs-lookup"><span data-stu-id="fc041-167">Value Types and Reference Types</span></span>](value-types-and-reference-types.md)
- [<span data-ttu-id="fc041-168">데이터 형식 문제 해결</span><span class="sxs-lookup"><span data-stu-id="fc041-168">Troubleshooting Data Types</span></span>](troubleshooting-data-types.md)
- [<span data-ttu-id="fc041-169">TableAdapter를 사용하여 데이터 세트 채우기</span><span class="sxs-lookup"><span data-stu-id="fc041-169">Fill datasets by using TableAdapters</span></span>](/visualstudio/data-tools/fill-datasets-by-using-tableadapters)
- [<span data-ttu-id="fc041-170">If 연산자</span><span class="sxs-lookup"><span data-stu-id="fc041-170">If Operator</span></span>](../../../language-reference/operators/if-operator.md)
- [<span data-ttu-id="fc041-171">지역 형식 유추</span><span class="sxs-lookup"><span data-stu-id="fc041-171">Local Type Inference</span></span>](../variables/local-type-inference.md)
- [<span data-ttu-id="fc041-172">Is 연산자</span><span class="sxs-lookup"><span data-stu-id="fc041-172">Is Operator</span></span>](../../../language-reference/operators/is-operator.md)
- [<span data-ttu-id="fc041-173">IsNot 연산자</span><span class="sxs-lookup"><span data-stu-id="fc041-173">IsNot Operator</span></span>](../../../language-reference/operators/isnot-operator.md)
- [<span data-ttu-id="fc041-174">Nullable 값 형식 (C#)</span><span class="sxs-lookup"><span data-stu-id="fc041-174">Nullable Value Types (C#)</span></span>](../../../../csharp/language-reference/builtin-types/nullable-value-types.md)
