---
description: '자세한 정보: Nullable 값 형식 (Visual Basic)'
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
ms.openlocfilehash: acc91d98a3ed288a9bf0bcf6abbd3d8a516bd699
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100483887"
---
# <a name="nullable-value-types-visual-basic"></a><span data-ttu-id="a19da-103">Nullable 값 형식(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a19da-103">Nullable Value Types (Visual Basic)</span></span>

<span data-ttu-id="a19da-104">특정 상황에서 정의 된 값이 없는 값 형식을 사용 하는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a19da-104">Sometimes you work with a value type that does not have a defined value in certain circumstances.</span></span> <span data-ttu-id="a19da-105">예를 들어 데이터베이스의 필드는 할당 된 값이 있는 것을 의미 하는 값이 할당 되는 것을 구분 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a19da-105">For example, a field in a database might have to distinguish between having an assigned value that is meaningful and not having an assigned value.</span></span> <span data-ttu-id="a19da-106">값 형식은 일반 값 이나 null 값을 사용 하도록 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a19da-106">Value types can be extended to take either their normal values or a null value.</span></span> <span data-ttu-id="a19da-107">이러한 확장을 *nullable 형식* 이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="a19da-107">Such an extension is called a *nullable type*.</span></span>

<span data-ttu-id="a19da-108">각 nullable 값 형식은 제네릭 구조체에서 생성 됩니다 <xref:System.Nullable%601> .</span><span class="sxs-lookup"><span data-stu-id="a19da-108">Each nullable value type is constructed from the generic <xref:System.Nullable%601> structure.</span></span> <span data-ttu-id="a19da-109">작업 관련 작업을 추적 하는 데이터베이스를 고려 합니다.</span><span class="sxs-lookup"><span data-stu-id="a19da-109">Consider a database that tracks work-related activities.</span></span> <span data-ttu-id="a19da-110">다음 예제에서는 nullable 형식을 생성 하 `Boolean` 고 해당 형식의 변수를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="a19da-110">The following example constructs a nullable `Boolean` type and declares a variable of that type.</span></span> <span data-ttu-id="a19da-111">다음 세 가지 방법으로 선언을 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a19da-111">You can write the declaration in three ways:</span></span>

[!code-vb[VbVbalrNullableValue#1](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#1)]

<span data-ttu-id="a19da-112">변수는 값, 값 또는 값을 `ridesBusToWork` 가질 수 `True` `False` 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a19da-112">The variable `ridesBusToWork` can hold a value of `True`, a value of `False`, or no value at all.</span></span> <span data-ttu-id="a19da-113">초기 기본값은 값이 아닙니다 .이 경우이 사용자에 대 한 정보가 아직 획득 되지 않았음을 의미할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a19da-113">Its initial default value is no value at all, which in this case could mean that the information has not yet been obtained for this person.</span></span> <span data-ttu-id="a19da-114">이와 대조적으로는 `False` 정보를 얻고 사용자가 버스를 사용 하 여 작업을 수행 하지 않았음을 의미할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a19da-114">In contrast, `False` could mean that the information has been obtained and the person does not ride the bus to work.</span></span>

<span data-ttu-id="a19da-115">Nullable 값 형식을 사용 하 여 변수 및 속성을 선언할 수 있으며 nullable 값 형식의 요소가 포함 된 배열을 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a19da-115">You can declare variables and properties with nullable value types, and you can declare an array with elements of a nullable value type.</span></span> <span data-ttu-id="a19da-116">Null을 허용 하는 값 형식을 포함 하는 프로시저를 매개 변수로 선언할 수 있으며 프로시저에서 nullable 값 형식을 반환할 수 있습니다 `Function` .</span><span class="sxs-lookup"><span data-stu-id="a19da-116">You can declare procedures with nullable value types as parameters, and you can return a nullable value type from a `Function` procedure.</span></span>

<span data-ttu-id="a19da-117">배열, 또는 클래스와 같은 참조 형식에서 nullable 형식을 생성할 수 없습니다 `String` .</span><span class="sxs-lookup"><span data-stu-id="a19da-117">You cannot construct a nullable type on a reference type such as an array, a `String`, or a class.</span></span> <span data-ttu-id="a19da-118">내부 형식은 값 형식 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a19da-118">The underlying type must be a value type.</span></span> <span data-ttu-id="a19da-119">자세한 내용은 [값 형식 및 참조 형식](value-types-and-reference-types.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a19da-119">For more information, see [Value Types and Reference Types](value-types-and-reference-types.md).</span></span>

## <a name="using-a-nullable-type-variable"></a><span data-ttu-id="a19da-120">Nullable 형식 변수 사용</span><span class="sxs-lookup"><span data-stu-id="a19da-120">Using a Nullable Type Variable</span></span>

<span data-ttu-id="a19da-121">Nullable 값 형식의 가장 중요 한 멤버는 <xref:System.Nullable%601.HasValue%2A> 및 <xref:System.Nullable%601.Value%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="a19da-121">The most important members of a nullable value type are its <xref:System.Nullable%601.HasValue%2A> and <xref:System.Nullable%601.Value%2A> properties.</span></span> <span data-ttu-id="a19da-122">Nullable 값 형식의 변수에 대해는 <xref:System.Nullable%601.HasValue%2A> 변수에 정의 된 값이 포함 되어 있는지 여부를 알려 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a19da-122">For a variable of a nullable value type, <xref:System.Nullable%601.HasValue%2A> tells you whether the variable contains a defined value.</span></span> <span data-ttu-id="a19da-123"><xref:System.Nullable%601.HasValue%2A>가 이면 `True` 에서 값을 읽을 수 있습니다 <xref:System.Nullable%601.Value%2A> .</span><span class="sxs-lookup"><span data-stu-id="a19da-123">If <xref:System.Nullable%601.HasValue%2A> is `True`, you can read the value from <xref:System.Nullable%601.Value%2A>.</span></span> <span data-ttu-id="a19da-124">및는 모두 <xref:System.Nullable%601.HasValue%2A> <xref:System.Nullable%601.Value%2A> `ReadOnly` 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="a19da-124">Note that both <xref:System.Nullable%601.HasValue%2A> and <xref:System.Nullable%601.Value%2A> are `ReadOnly` properties.</span></span>

### <a name="default-values"></a><span data-ttu-id="a19da-125">기본값</span><span class="sxs-lookup"><span data-stu-id="a19da-125">Default Values</span></span>

<span data-ttu-id="a19da-126">Nullable 값 형식으로 변수를 선언 하는 경우 해당 <xref:System.Nullable%601.HasValue%2A> 속성의 기본값은 `False` 입니다.</span><span class="sxs-lookup"><span data-stu-id="a19da-126">When you declare a variable with a nullable value type, its <xref:System.Nullable%601.HasValue%2A> property has a default value of `False`.</span></span> <span data-ttu-id="a19da-127">즉, 기본적으로 변수에는 기본 값 형식의 기본 값 대신 정의 된 값이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a19da-127">This means that by default the variable has no defined value, instead of the default value of its underlying value type.</span></span> <span data-ttu-id="a19da-128">다음 예제에서 변수의 `numberOfChildren` 기본값은 0 이지만 원래 값에는 정의 된 값이 없습니다 `Integer` .</span><span class="sxs-lookup"><span data-stu-id="a19da-128">In the following example, the variable `numberOfChildren` initially has no defined value, even though the default value of the `Integer` type is 0.</span></span>

[!code-vb[VbVbalrNullableValue#2](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#2)]

<span data-ttu-id="a19da-129">Null 값은 정의 되지 않거나 알 수 없는 값을 나타내는 데 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a19da-129">A null value is useful to indicate an undefined or unknown value.</span></span> <span data-ttu-id="a19da-130">가 `numberOfChildren` 로 선언 된 경우 `Integer` 정보를 현재 사용할 수 없음을 나타낼 수 있는 값이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a19da-130">If `numberOfChildren` had been declared as `Integer`, there would be no value that could indicate that the information is not currently available.</span></span>

### <a name="storing-values"></a><span data-ttu-id="a19da-131">값 저장</span><span class="sxs-lookup"><span data-stu-id="a19da-131">Storing Values</span></span>

<span data-ttu-id="a19da-132">일반적으로 nullable 값 형식의 변수 또는 속성에 값을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="a19da-132">You store a value in a variable or property of a nullable value type in the typical way.</span></span> <span data-ttu-id="a19da-133">다음 예제에서는 `numberOfChildren` 이전 예제에서 선언 된 변수에 값을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="a19da-133">The following example assigns a value to the variable `numberOfChildren` declared in the previous example.</span></span>

[!code-vb[VbVbalrNullableValue#3](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#3)]

<span data-ttu-id="a19da-134">Nullable 값 형식의 변수 또는 속성이 정의 된 값을 포함 하는 경우 해당 값이 할당 되지 않은 초기 상태로 되돌아갈 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a19da-134">If a variable or property of a nullable value type contains a defined value, you can cause it to revert to its initial state of not having a value assigned.</span></span> <span data-ttu-id="a19da-135">다음 예제와 같이 변수 또는 속성을로 설정 하 여이 작업을 수행 `Nothing` 합니다.</span><span class="sxs-lookup"><span data-stu-id="a19da-135">You do this by setting the variable or property to `Nothing`, as the following example shows.</span></span>

[!code-vb[VbVbalrNullableValue#4](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#4)]

> [!NOTE]
> <span data-ttu-id="a19da-136">`Nothing`Nullable 값 형식의 변수에 할당할 수 있지만 등호를 사용 하 여에 대해 테스트할 수는 없습니다 `Nothing` .</span><span class="sxs-lookup"><span data-stu-id="a19da-136">Although you can assign `Nothing` to a variable of a nullable value type, you cannot test it for `Nothing` by using the equal sign.</span></span> <span data-ttu-id="a19da-137">등호를 사용 하는 비교는 `someVar = Nothing` 항상로 평가 `Nothing` 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a19da-137">Comparison that uses the equal sign, `someVar = Nothing`, always evaluates to `Nothing`.</span></span> <span data-ttu-id="a19da-138"><xref:System.Nullable%601.HasValue%2A> `False` 또는 연산자를 사용 하 여에 대해 변수의 속성을 테스트 하거나 테스트할 수 있습니다 `Is` `IsNot` .</span><span class="sxs-lookup"><span data-stu-id="a19da-138">You can test the variable's <xref:System.Nullable%601.HasValue%2A> property for `False`, or test by using the `Is` or `IsNot` operator.</span></span>

### <a name="retrieving-values"></a><span data-ttu-id="a19da-139">값 검색</span><span class="sxs-lookup"><span data-stu-id="a19da-139">Retrieving Values</span></span>

<span data-ttu-id="a19da-140">Nullable 값 형식의 변수 값을 검색 하려면 먼저 해당 속성을 테스트 <xref:System.Nullable%601.HasValue%2A> 하 여 값이 있는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a19da-140">To retrieve the value of a variable of a nullable value type, you should first test its <xref:System.Nullable%601.HasValue%2A> property to confirm that it has a value.</span></span> <span data-ttu-id="a19da-141">가 일 때 값을 읽으려고 하는 <xref:System.Nullable%601.HasValue%2A> 경우 `False` Visual Basic 예외를 throw <xref:System.InvalidOperationException> 합니다.</span><span class="sxs-lookup"><span data-stu-id="a19da-141">If you try to read the value when <xref:System.Nullable%601.HasValue%2A> is `False`, Visual Basic throws an <xref:System.InvalidOperationException> exception.</span></span> <span data-ttu-id="a19da-142">다음 예제에서는 이전 예제의 변수를 읽는 데 권장 되는 방법을 보여 줍니다 `numberOfChildren` .</span><span class="sxs-lookup"><span data-stu-id="a19da-142">The following example shows the recommended way to read the variable `numberOfChildren` of the previous examples.</span></span>

[!code-vb[VbVbalrNullableValue#5](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#5)]

## <a name="comparing-nullable-types"></a><span data-ttu-id="a19da-143">Nullable 형식 비교</span><span class="sxs-lookup"><span data-stu-id="a19da-143">Comparing Nullable Types</span></span>

<span data-ttu-id="a19da-144">Nullable `Boolean` 변수가 부울 식에 사용 되는 경우 결과는, 또는가 될 수 있습니다 `True` `False` `Nothing` .</span><span class="sxs-lookup"><span data-stu-id="a19da-144">When nullable `Boolean` variables are used in Boolean expressions, the result can be `True`, `False`, or `Nothing`.</span></span> <span data-ttu-id="a19da-145">다음은 및에 대 한 진위 테이블입니다 `And` `Or` .</span><span class="sxs-lookup"><span data-stu-id="a19da-145">The following is the truth table for `And` and `Or`.</span></span> <span data-ttu-id="a19da-146">`b1`및는 `b2` 세 가지 가능한 값을 가지 므로 평가할 조합 수는 9 개입니다.</span><span class="sxs-lookup"><span data-stu-id="a19da-146">Because `b1` and `b2` now have three possible values, there are nine combinations to evaluate.</span></span>

|<span data-ttu-id="a19da-147">b1</span><span class="sxs-lookup"><span data-stu-id="a19da-147">b1</span></span>|<span data-ttu-id="a19da-148">b2</span><span class="sxs-lookup"><span data-stu-id="a19da-148">b2</span></span>|<span data-ttu-id="a19da-149">b1 및 b2</span><span class="sxs-lookup"><span data-stu-id="a19da-149">b1 And b2</span></span>|<span data-ttu-id="a19da-150">b1 또는 b2</span><span class="sxs-lookup"><span data-stu-id="a19da-150">b1 Or b2</span></span>|
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

<span data-ttu-id="a19da-151">부울 변수나 식의 값이 이면이 고 `Nothing` , 그렇지 않으면 `true` `false` 입니다.</span><span class="sxs-lookup"><span data-stu-id="a19da-151">When the value of a Boolean variable or expression is `Nothing`, it is neither `true` nor `false`.</span></span> <span data-ttu-id="a19da-152">다음 예제를 살펴보십시오.</span><span class="sxs-lookup"><span data-stu-id="a19da-152">Consider the following example.</span></span>

[!code-vb[VbVbalrNullableValue#6](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#6)]

<span data-ttu-id="a19da-153">이 예에서는가 `b1 And b2` 로 평가 `Nothing` 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a19da-153">In this example, `b1 And b2` evaluates to `Nothing`.</span></span> <span data-ttu-id="a19da-154">따라서 `Else` 절은 각 문에서 실행 되며 출력은 다음과 같습니다 `If` .</span><span class="sxs-lookup"><span data-stu-id="a19da-154">As a result, the `Else` clause is executed in each `If` statement, and the output is as follows:</span></span>

`Expression is not true`

`Expression is not false`

> [!NOTE]
> <span data-ttu-id="a19da-155">`AndAlso``OrElse`단락 평가를 사용 하는 및는 첫 번째 피연산자가로 평가 될 때 두 번째 피연산자를 계산 해야 합니다 `Nothing` .</span><span class="sxs-lookup"><span data-stu-id="a19da-155">`AndAlso` and `OrElse`, which use short-circuit evaluation, must evaluate their second operands when the first evaluates to `Nothing`.</span></span>

## <a name="propagation"></a><span data-ttu-id="a19da-156">전파</span><span class="sxs-lookup"><span data-stu-id="a19da-156">Propagation</span></span>

<span data-ttu-id="a19da-157">산술 연산자, 비교 연산자 또는 형식 작업의 피연산자 중 하나 또는 둘 다가 nullable 값 형식인 경우 연산의 결과도 nullable 값 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="a19da-157">If one or both of the operands of an arithmetic, comparison, shift, or type operation is a nullable value type, the result of the operation is also a nullable value type.</span></span> <span data-ttu-id="a19da-158">두 피연산자의 값이 모두 null이 아닌 경우 null을 허용 하는 값 `Nothing` 형식인 것 처럼 연산이 피연산자의 내부 값에 대해 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a19da-158">If both operands have values that are not `Nothing`, the operation is performed on the underlying values of the operands, as if neither were a nullable value type.</span></span> <span data-ttu-id="a19da-159">다음 예제에서는 및 변수를 `compare1` `sum1` 암시적으로 형식화 합니다.</span><span class="sxs-lookup"><span data-stu-id="a19da-159">In the following example, variables `compare1` and `sum1` are implicitly typed.</span></span> <span data-ttu-id="a19da-160">마우스 포인터를 올려 놓으면 컴파일러가 둘 모두에 대해 nullable 값 형식을 유추 하는 것을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a19da-160">If you rest the mouse pointer over them, you will see that the compiler infers nullable value types for both of them.</span></span>

[!code-vb[VbVbalrNullableValue#7](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#7)]

<span data-ttu-id="a19da-161">피연산자 중 하나 또는 둘 다의 값이 이면 `Nothing` 결과는가 됩니다 `Nothing` .</span><span class="sxs-lookup"><span data-stu-id="a19da-161">If one or both operands have a value of `Nothing`, the result will be `Nothing`.</span></span>

[!code-vb[VbVbalrNullableValue#8](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#8)]

## <a name="using-nullable-types-with-data"></a><span data-ttu-id="a19da-162">데이터에 Nullable 형식 사용</span><span class="sxs-lookup"><span data-stu-id="a19da-162">Using Nullable Types with Data</span></span>

<span data-ttu-id="a19da-163">데이터베이스는 nullable 값 형식을 사용 하는 가장 중요 한 위치 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="a19da-163">A database is one of the most important places to use nullable value types.</span></span> <span data-ttu-id="a19da-164">일부 데이터베이스 개체는 현재 nullable 값 형식을 지원 하지만 디자이너에서 생성 된 테이블 어댑터는 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a19da-164">Not all database objects currently support nullable value types, but the designer-generated table adapters do.</span></span> <span data-ttu-id="a19da-165">[Nullable 형식에 대 한 TableAdapter 지원을](/visualstudio/data-tools/fill-datasets-by-using-tableadapters#tableadapter-support-for-nullable-types)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a19da-165">See [TableAdapter support for nullable types](/visualstudio/data-tools/fill-datasets-by-using-tableadapters#tableadapter-support-for-nullable-types).</span></span>

## <a name="see-also"></a><span data-ttu-id="a19da-166">추가 정보</span><span class="sxs-lookup"><span data-stu-id="a19da-166">See also</span></span>

- <xref:System.InvalidOperationException>
- <xref:System.Nullable%601.HasValue%2A>
- [<span data-ttu-id="a19da-167">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="a19da-167">Data Types</span></span>](index.md)
- [<span data-ttu-id="a19da-168">Value Types and Reference Types</span><span class="sxs-lookup"><span data-stu-id="a19da-168">Value Types and Reference Types</span></span>](value-types-and-reference-types.md)
- [<span data-ttu-id="a19da-169">데이터 형식 문제 해결</span><span class="sxs-lookup"><span data-stu-id="a19da-169">Troubleshooting Data Types</span></span>](troubleshooting-data-types.md)
- [<span data-ttu-id="a19da-170">TableAdapters를 사용하여 데이터 세트 채우기</span><span class="sxs-lookup"><span data-stu-id="a19da-170">Fill datasets by using TableAdapters</span></span>](/visualstudio/data-tools/fill-datasets-by-using-tableadapters)
- [<span data-ttu-id="a19da-171">If 연산자</span><span class="sxs-lookup"><span data-stu-id="a19da-171">If Operator</span></span>](../../../language-reference/operators/if-operator.md)
- [<span data-ttu-id="a19da-172">지역 형식 유추</span><span class="sxs-lookup"><span data-stu-id="a19da-172">Local Type Inference</span></span>](../variables/local-type-inference.md)
- [<span data-ttu-id="a19da-173">Is 연산자</span><span class="sxs-lookup"><span data-stu-id="a19da-173">Is Operator</span></span>](../../../language-reference/operators/is-operator.md)
- [<span data-ttu-id="a19da-174">IsNot 연산자</span><span class="sxs-lookup"><span data-stu-id="a19da-174">IsNot Operator</span></span>](../../../language-reference/operators/isnot-operator.md)
- [<span data-ttu-id="a19da-175">Nullable 값 형식 (c #)</span><span class="sxs-lookup"><span data-stu-id="a19da-175">Nullable Value Types (C#)</span></span>](../../../../csharp/language-reference/builtin-types/nullable-value-types.md)
