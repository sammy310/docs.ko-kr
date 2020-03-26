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
ms.openlocfilehash: beed8262c50dc68330b8f03aa3d864ed2f8df0d5
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249684"
---
# <a name="nullable-value-types-visual-basic"></a><span data-ttu-id="b4f82-102">Nullable 값 형식(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b4f82-102">Nullable Value Types (Visual Basic)</span></span>

<span data-ttu-id="b4f82-103">경우에 따라 특정 상황에서 정의된 값이 없는 값 형식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4f82-103">Sometimes you work with a value type that does not have a defined value in certain circumstances.</span></span> <span data-ttu-id="b4f82-104">예를 들어 데이터베이스의 필드는 의미 있는 할당된 값을 갖는 것과 할당된 값이 없는 것을 구별해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4f82-104">For example, a field in a database might have to distinguish between having an assigned value that is meaningful and not having an assigned value.</span></span> <span data-ttu-id="b4f82-105">값 형식을 확장하여 일반 값 또는 null 값을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4f82-105">Value types can be extended to take either their normal values or a null value.</span></span> <span data-ttu-id="b4f82-106">이러한 확장을 *null형식이라고*합니다.</span><span class="sxs-lookup"><span data-stu-id="b4f82-106">Such an extension is called a *nullable type*.</span></span>

<span data-ttu-id="b4f82-107">각 nullable 값 형식은 <xref:System.Nullable%601> 제네릭 구조에서 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4f82-107">Each nullable value type is constructed from the generic <xref:System.Nullable%601> structure.</span></span> <span data-ttu-id="b4f82-108">작업 관련 활동을 추적하는 데이터베이스를 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="b4f82-108">Consider a database that tracks work-related activities.</span></span> <span data-ttu-id="b4f82-109">다음 예제는 nullable `Boolean` 형식을 생성 하 고 해당 형식의 변수를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4f82-109">The following example constructs a nullable `Boolean` type and declares a variable of that type.</span></span> <span data-ttu-id="b4f82-110">세 가지 방법으로 선언을 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4f82-110">You can write the declaration in three ways:</span></span>

[!code-vb[VbVbalrNullableValue#1](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#1)]

<span data-ttu-id="b4f82-111">변수는 `ridesBusToWork` `True`의 `False`값을 보유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4f82-111">The variable `ridesBusToWork` can hold a value of `True`, a value of `False`, or no value at all.</span></span> <span data-ttu-id="b4f82-112">초기 기본값은 전혀 값이 아니며, 이 경우 이 사람에 대한 정보가 아직 가져오지 않은 것을 의미할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4f82-112">Its initial default value is no value at all, which in this case could mean that the information has not yet been obtained for this person.</span></span> <span data-ttu-id="b4f82-113">반대로, `False` 정보를 입수하고 사람이 출근하기 위해 버스를 타지 않는다는 것을 의미 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4f82-113">In contrast, `False` could mean that the information has been obtained and the person does not ride the bus to work.</span></span>

<span data-ttu-id="b4f82-114">nullable 값 형식을 사용 하 고 nullable 값 형식의 요소를 사용 하 고 배열을 선언할 수 있습니다 변수 및 속성을 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4f82-114">You can declare variables and properties with nullable value types, and you can declare an array with elements of a nullable value type.</span></span> <span data-ttu-id="b4f82-115">nullable 값 형식을 매개 변수로 프로시저를 선언할 수 있으며 `Function` 프로시저에서 nullable 값 형식을 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4f82-115">You can declare procedures with nullable value types as parameters, and you can return a nullable value type from a `Function` procedure.</span></span>

<span data-ttu-id="b4f82-116">배열, a `String`또는 클래스와 같은 참조 형식에서 nullable 형식을 생성할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b4f82-116">You cannot construct a nullable type on a reference type such as an array, a `String`, or a class.</span></span> <span data-ttu-id="b4f82-117">기본 형식은 값 형식이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4f82-117">The underlying type must be a value type.</span></span> <span data-ttu-id="b4f82-118">자세한 내용은 [값 유형 및 참조 유형을](value-types-and-reference-types.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b4f82-118">For more information, see [Value Types and Reference Types](value-types-and-reference-types.md).</span></span>

## <a name="using-a-nullable-type-variable"></a><span data-ttu-id="b4f82-119">Nullable 형식 변수 사용</span><span class="sxs-lookup"><span data-stu-id="b4f82-119">Using a Nullable Type Variable</span></span>

<span data-ttu-id="b4f82-120">nullable 값 형식의 가장 중요한 <xref:System.Nullable%601.HasValue%2A> 멤버는 해당 멤버와 <xref:System.Nullable%601.Value%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="b4f82-120">The most important members of a nullable value type are its <xref:System.Nullable%601.HasValue%2A> and <xref:System.Nullable%601.Value%2A> properties.</span></span> <span data-ttu-id="b4f82-121">nullable 값 형식의 변수의 <xref:System.Nullable%601.HasValue%2A> 경우 변수에 정의된 값이 포함되어 있는지 여부를 알려줍니다.</span><span class="sxs-lookup"><span data-stu-id="b4f82-121">For a variable of a nullable value type, <xref:System.Nullable%601.HasValue%2A> tells you whether the variable contains a defined value.</span></span> <span data-ttu-id="b4f82-122">의 경우 에서 값을 <xref:System.Nullable%601.Value%2A>읽을 수 있습니다. <xref:System.Nullable%601.HasValue%2A> `True`</span><span class="sxs-lookup"><span data-stu-id="b4f82-122">If <xref:System.Nullable%601.HasValue%2A> is `True`, you can read the value from <xref:System.Nullable%601.Value%2A>.</span></span> <span data-ttu-id="b4f82-123">둘 다 <xref:System.Nullable%601.HasValue%2A> <xref:System.Nullable%601.Value%2A> 속성입니다. `ReadOnly`</span><span class="sxs-lookup"><span data-stu-id="b4f82-123">Note that both <xref:System.Nullable%601.HasValue%2A> and <xref:System.Nullable%601.Value%2A> are `ReadOnly` properties.</span></span>

### <a name="default-values"></a><span data-ttu-id="b4f82-124">기본값</span><span class="sxs-lookup"><span data-stu-id="b4f82-124">Default Values</span></span>

<span data-ttu-id="b4f82-125">nullable 값 형식을 사용 하 고 <xref:System.Nullable%601.HasValue%2A> 변수를 선언 하는 `False`경우 해당 속성의 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="b4f82-125">When you declare a variable with a nullable value type, its <xref:System.Nullable%601.HasValue%2A> property has a default value of `False`.</span></span> <span data-ttu-id="b4f82-126">즉, 기본적으로 변수는 기본 값 형식의 기본값 대신 정의된 값이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b4f82-126">This means that by default the variable has no defined value, instead of the default value of its underlying value type.</span></span> <span data-ttu-id="b4f82-127">다음 예제에서 `numberOfChildren` `Integer` 변수는 처음에는 형식의 기본값이 0이더라도 정의된 값이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b4f82-127">In the following example, the variable `numberOfChildren` initially has no defined value, even though the default value of the `Integer` type is 0.</span></span>

[!code-vb[VbVbalrNullableValue#2](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#2)]

<span data-ttu-id="b4f82-128">null 값은 정의되지 않거나 알 수 없는 값을 나타내는 데 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="b4f82-128">A null value is useful to indicate an undefined or unknown value.</span></span> <span data-ttu-id="b4f82-129">로 선언된 경우 `numberOfChildren` 현재 정보를 사용할 수 없음을 나타낼 수 있는 값이 없습니다. `Integer`</span><span class="sxs-lookup"><span data-stu-id="b4f82-129">If `numberOfChildren` had been declared as `Integer`, there would be no value that could indicate that the information is not currently available.</span></span>

### <a name="storing-values"></a><span data-ttu-id="b4f82-130">값 저장</span><span class="sxs-lookup"><span data-stu-id="b4f82-130">Storing Values</span></span>

<span data-ttu-id="b4f82-131">일반적인 방법으로 nullable 값 형식의 변수 또는 속성에 값을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4f82-131">You store a value in a variable or property of a nullable value type in the typical way.</span></span> <span data-ttu-id="b4f82-132">다음 예제에서는 이전 예제에서 `numberOfChildren` 선언된 변수에 값을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="b4f82-132">The following example assigns a value to the variable `numberOfChildren` declared in the previous example.</span></span>

[!code-vb[VbVbalrNullableValue#3](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#3)]

<span data-ttu-id="b4f82-133">nullable 값 형식의 변수 또는 속성에 정의된 값이 포함된 경우 값이 할당되지 않은 초기 상태로 되돌릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4f82-133">If a variable or property of a nullable value type contains a defined value, you can cause it to revert to its initial state of not having a value assigned.</span></span> <span data-ttu-id="b4f82-134">다음 예제와 같이 변수 또는 `Nothing`속성을 로 설정하여 이 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="b4f82-134">You do this by setting the variable or property to `Nothing`, as the following example shows.</span></span>

[!code-vb[VbVbalrNullableValue#4](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#4)]

> [!NOTE]
> <span data-ttu-id="b4f82-135">nullable 값 `Nothing` 형식의 변수에 할당할 수 있지만 등기호를 `Nothing` 사용하여 테스트할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b4f82-135">Although you can assign `Nothing` to a variable of a nullable value type, you cannot test it for `Nothing` by using the equal sign.</span></span> <span data-ttu-id="b4f82-136">와 같은 기호를 `someVar = Nothing`사용하는 비교는 `Nothing`항상 을 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="b4f82-136">Comparison that uses the equal sign, `someVar = Nothing`, always evaluates to `Nothing`.</span></span> <span data-ttu-id="b4f82-137">에 <xref:System.Nullable%601.HasValue%2A> 대한 `False`변수의 속성을 테스트하거나 `Is` 또는 `IsNot` 연산자를 사용하여 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4f82-137">You can test the variable's <xref:System.Nullable%601.HasValue%2A> property for `False`, or test by using the `Is` or `IsNot` operator.</span></span>

### <a name="retrieving-values"></a><span data-ttu-id="b4f82-138">값 검색</span><span class="sxs-lookup"><span data-stu-id="b4f82-138">Retrieving Values</span></span>

<span data-ttu-id="b4f82-139">nullable 값 형식의 변수 값을 검색하려면 먼저 해당 <xref:System.Nullable%601.HasValue%2A> 속성을 테스트하여 값이 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4f82-139">To retrieve the value of a variable of a nullable value type, you should first test its <xref:System.Nullable%601.HasValue%2A> property to confirm that it has a value.</span></span> <span data-ttu-id="b4f82-140">때 값을 <xref:System.Nullable%601.HasValue%2A> 읽으려고 하면 `False`Visual Basic예외가 <xref:System.InvalidOperationException> 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="b4f82-140">If you try to read the value when <xref:System.Nullable%601.HasValue%2A> is `False`, Visual Basic throws an <xref:System.InvalidOperationException> exception.</span></span> <span data-ttu-id="b4f82-141">다음 예제에서는 이전 예제의 변수를 `numberOfChildren` 읽는 권장된 방법을 보여 주어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4f82-141">The following example shows the recommended way to read the variable `numberOfChildren` of the previous examples.</span></span>

[!code-vb[VbVbalrNullableValue#5](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#5)]

## <a name="comparing-nullable-types"></a><span data-ttu-id="b4f82-142">Null 형식 비교</span><span class="sxs-lookup"><span data-stu-id="b4f82-142">Comparing Nullable Types</span></span>

<span data-ttu-id="b4f82-143">nullable `Boolean` 변수가 부울 식에서 사용되는 경우 결과는 `True` `False`" `Nothing`또는 .</span><span class="sxs-lookup"><span data-stu-id="b4f82-143">When nullable `Boolean` variables are used in Boolean expressions, the result can be `True`, `False`, or `Nothing`.</span></span> <span data-ttu-id="b4f82-144">다음은 에 대한 `And` 진실 `Or`테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="b4f82-144">The following is the truth table for `And` and `Or`.</span></span> <span data-ttu-id="b4f82-145">이제 세 가지 가능한 값이 있기 때문에 `b1` 평가할 9개의 조합이 있습니다. `b2`</span><span class="sxs-lookup"><span data-stu-id="b4f82-145">Because `b1` and `b2` now have three possible values, there are nine combinations to evaluate.</span></span>

|<span data-ttu-id="b4f82-146">b1</span><span class="sxs-lookup"><span data-stu-id="b4f82-146">b1</span></span>|<span data-ttu-id="b4f82-147">B2</span><span class="sxs-lookup"><span data-stu-id="b4f82-147">b2</span></span>|<span data-ttu-id="b4f82-148">b1 및 b2</span><span class="sxs-lookup"><span data-stu-id="b4f82-148">b1 And b2</span></span>|<span data-ttu-id="b4f82-149">b1 또는 b2</span><span class="sxs-lookup"><span data-stu-id="b4f82-149">b1 Or b2</span></span>|
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

<span data-ttu-id="b4f82-150">부울 변수 또는 식의 값이 `Nothing`있는 경우 `true` `false`는</span><span class="sxs-lookup"><span data-stu-id="b4f82-150">When the value of a Boolean variable or expression is `Nothing`, it is neither `true` nor `false`.</span></span> <span data-ttu-id="b4f82-151">아래 예제를 고려해 보세요.</span><span class="sxs-lookup"><span data-stu-id="b4f82-151">Consider the following example.</span></span>

[!code-vb[VbVbalrNullableValue#6](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#6)]

<span data-ttu-id="b4f82-152">이 예제에서는 `b1 And b2` 을 `Nothing`평가합니다.</span><span class="sxs-lookup"><span data-stu-id="b4f82-152">In this example, `b1 And b2` evaluates to `Nothing`.</span></span> <span data-ttu-id="b4f82-153">결과적으로 절은 `Else` 각 `If` 명령문에서 실행되고 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b4f82-153">As a result, the `Else` clause is executed in each `If` statement, and the output is as follows:</span></span>

`Expression is not true`

`Expression is not false`

> [!NOTE]
> <span data-ttu-id="b4f82-154">`AndAlso`단락 `OrElse`평가를 사용하는 경우 첫 번째 로 평가할 때 두 번째 `Nothing`이연산생을 평가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4f82-154">`AndAlso` and `OrElse`, which use short-circuit evaluation, must evaluate their second operands when the first evaluates to `Nothing`.</span></span>

## <a name="propagation"></a><span data-ttu-id="b4f82-155">전파</span><span class="sxs-lookup"><span data-stu-id="b4f82-155">Propagation</span></span>

<span data-ttu-id="b4f82-156">산술, 비교, 시프트 또는 형식 작업의 피연산자 중 하나 또는 둘 다가 nullable 값 형식인 경우 작업의 결과는 nullable 값 형식이기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4f82-156">If one or both of the operands of an arithmetic, comparison, shift, or type operation is a nullable value type, the result of the operation is also a nullable value type.</span></span> <span data-ttu-id="b4f82-157">두 피연산자 모두 값이 `Nothing`없는 경우, 두 피연산자는 모두 nullable 값 형식이 아닌 것처럼 피연산자의 기본 값에서 작업이 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4f82-157">If both operands have values that are not `Nothing`, the operation is performed on the underlying values of the operands, as if neither were a nullable value type.</span></span> <span data-ttu-id="b4f82-158">다음 예제에서는 `compare1` 변수와 `sum1` 암시적으로 입력됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4f82-158">In the following example, variables `compare1` and `sum1` are implicitly typed.</span></span> <span data-ttu-id="b4f82-159">마우스 포인터를 놓으면 컴파일러가 두 포인터 모두에 대해 null able 값 형식을 유추하는 것을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4f82-159">If you rest the mouse pointer over them, you will see that the compiler infers nullable value types for both of them.</span></span>

[!code-vb[VbVbalrNullableValue#7](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#7)]

<span data-ttu-id="b4f82-160">하나 또는 둘 다의 값이 있는 `Nothing`경우 은. `Nothing`</span><span class="sxs-lookup"><span data-stu-id="b4f82-160">If one or both operands have a value of `Nothing`, the result will be `Nothing`.</span></span>

[!code-vb[VbVbalrNullableValue#8](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#8)]

## <a name="using-nullable-types-with-data"></a><span data-ttu-id="b4f82-161">데이터와 함께 Nullable 형식 사용</span><span class="sxs-lookup"><span data-stu-id="b4f82-161">Using Nullable Types with Data</span></span>

<span data-ttu-id="b4f82-162">데이터베이스는 nullable 값 형식을 사용하는 가장 중요한 장소 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="b4f82-162">A database is one of the most important places to use nullable value types.</span></span> <span data-ttu-id="b4f82-163">현재 모든 데이터베이스 개체가 nullable 값 형식을 지원하지는 않지만 디자이너가 생성한 테이블 어댑터는 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4f82-163">Not all database objects currently support nullable value types, but the designer-generated table adapters do.</span></span> <span data-ttu-id="b4f82-164">[nullable 형식에 대한 TableAdapter 지원을](/visualstudio/data-tools/fill-datasets-by-using-tableadapters#tableadapter-support-for-nullable-types)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b4f82-164">See [TableAdapter support for nullable types](/visualstudio/data-tools/fill-datasets-by-using-tableadapters#tableadapter-support-for-nullable-types).</span></span>

## <a name="see-also"></a><span data-ttu-id="b4f82-165">참조</span><span class="sxs-lookup"><span data-stu-id="b4f82-165">See also</span></span>

- <xref:System.InvalidOperationException>
- <xref:System.Nullable%601.HasValue%2A>
- [<span data-ttu-id="b4f82-166">데이터 유형</span><span class="sxs-lookup"><span data-stu-id="b4f82-166">Data Types</span></span>](index.md)
- [<span data-ttu-id="b4f82-167">Value Types and Reference Types</span><span class="sxs-lookup"><span data-stu-id="b4f82-167">Value Types and Reference Types</span></span>](value-types-and-reference-types.md)
- [<span data-ttu-id="b4f82-168">데이터 형식 문제 해결</span><span class="sxs-lookup"><span data-stu-id="b4f82-168">Troubleshooting Data Types</span></span>](troubleshooting-data-types.md)
- [<span data-ttu-id="b4f82-169">TableAdapters를 사용하여 데이터 세트 채우기</span><span class="sxs-lookup"><span data-stu-id="b4f82-169">Fill datasets by using TableAdapters</span></span>](/visualstudio/data-tools/fill-datasets-by-using-tableadapters)
- [<span data-ttu-id="b4f82-170">If 연산자</span><span class="sxs-lookup"><span data-stu-id="b4f82-170">If Operator</span></span>](../../../language-reference/operators/if-operator.md)
- [<span data-ttu-id="b4f82-171">지역 형식 유추</span><span class="sxs-lookup"><span data-stu-id="b4f82-171">Local Type Inference</span></span>](../variables/local-type-inference.md)
- [<span data-ttu-id="b4f82-172">Is 연산자</span><span class="sxs-lookup"><span data-stu-id="b4f82-172">Is Operator</span></span>](../../../language-reference/operators/is-operator.md)
- [<span data-ttu-id="b4f82-173">IsNot 연산자</span><span class="sxs-lookup"><span data-stu-id="b4f82-173">IsNot Operator</span></span>](../../../language-reference/operators/isnot-operator.md)
- [<span data-ttu-id="b4f82-174">무효화 가능한 값 유형(C#)</span><span class="sxs-lookup"><span data-stu-id="b4f82-174">Nullable Value Types (C#)</span></span>](../../../../csharp/language-reference/builtin-types/nullable-value-types.md)
