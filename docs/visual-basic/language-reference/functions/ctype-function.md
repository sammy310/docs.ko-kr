---
title: CType 함수(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.CType
helpviewer_keywords:
- expression conversion results
- explicit data type conversions [Visual Basic]
- CType function
- conversions [Visual Basic], expression
ms.assetid: dd4b29e7-6fa1-428c-877e-69955420bb72
ms.openlocfilehash: dbf01263723a9e2890dab57d5ffc3d467ed250fc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61801681"
---
# <a name="ctype-function-visual-basic"></a><span data-ttu-id="09761-102">CType 함수(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="09761-102">CType Function (Visual Basic)</span></span>

<span data-ttu-id="09761-103">식을 지정한 데이터 형식, 개체, 구조체, 클래스 또는 인터페이스 명시적으로 변환한 결과 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="09761-103">Returns the result of explicitly converting an expression to a specified data type, object, structure, class, or interface.</span></span>

## <a name="syntax"></a><span data-ttu-id="09761-104">구문</span><span class="sxs-lookup"><span data-stu-id="09761-104">Syntax</span></span>

```
CType(expression, typename)
```

## <a name="parts"></a><span data-ttu-id="09761-105">요소</span><span class="sxs-lookup"><span data-stu-id="09761-105">Parts</span></span>

<span data-ttu-id="09761-106">`expression` 모든 유효한 식입니다.</span><span class="sxs-lookup"><span data-stu-id="09761-106">`expression` Any valid expression.</span></span> <span data-ttu-id="09761-107">경우 값 `expression` 에서 허용 범위를 벗어난 `typename`, Visual Basic 예외를 throw 합니다.</span><span class="sxs-lookup"><span data-stu-id="09761-107">If the value of `expression` is outside the range allowed by `typename`, Visual Basic throws an exception.</span></span>

<span data-ttu-id="09761-108">`typename` 유효한 식일을 `As` 절을 `Dim` 문, 즉, 모든 데이터 형식, 개체, 구조체, 클래스 또는 인터페이스의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="09761-108">`typename` Any expression that is legal within an `As` clause in a `Dim` statement, that is, the name of any data type, object, structure, class, or interface.</span></span>

## <a name="remarks"></a><span data-ttu-id="09761-109">설명</span><span class="sxs-lookup"><span data-stu-id="09761-109">Remarks</span></span>

> [!TIP]
> <span data-ttu-id="09761-110">또한 형식 변환을 수행 하려면 다음 함수를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09761-110">You can also use the following functions to perform a type conversion:</span></span>
>
> - <span data-ttu-id="09761-111">같은 변환 함수를 입력 `CByte`, `CDbl`, 및 `CInt` 특정 데이터 형식 변환을 수행 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="09761-111">Type conversion functions such as `CByte`, `CDbl`, and `CInt` that perform a conversion to a specific data type.</span></span> <span data-ttu-id="09761-112">자세한 내용은 [형식 변환 함수](../../../visual-basic/language-reference/functions/type-conversion-functions.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="09761-112">For more information, see [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md).</span></span>
> - <span data-ttu-id="09761-113">[DirectCast 연산자](../../../visual-basic/language-reference/operators/directcast-operator.md) 나 [TryCast 연산자](../../../visual-basic/language-reference/operators/trycast-operator.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="09761-113">[DirectCast Operator](../../../visual-basic/language-reference/operators/directcast-operator.md) or [TryCast Operator](../../../visual-basic/language-reference/operators/trycast-operator.md).</span></span> <span data-ttu-id="09761-114">이러한 연산자는 하나의 형식에서 상속 되거나 다른 형식을 구현에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="09761-114">These operators require that one type inherit from or implement the other type.</span></span> <span data-ttu-id="09761-115">보다 약간 더 나은 성능을 제공할 수 있습니다 `CType` 사이에서 변환할 때의 `Object` 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="09761-115">They can provide somewhat better performance than `CType` when converting to and from the `Object` data type.</span></span>

<span data-ttu-id="09761-116">`CType` 인라인으로 컴파일됩니다., 변환 코드가 식을 계산 하는 코드의 일부임을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="09761-116">`CType` is compiled inline, which means that the conversion code is part of the code that evaluates the expression.</span></span> <span data-ttu-id="09761-117">일부 경우 코드를 한 절차가 없습니다 변환을 수행 하려면 호출 되므로 빠르게를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="09761-117">In some cases, the code runs faster because no procedures are called to perform the conversion.</span></span>

<span data-ttu-id="09761-118">정의 된 변환이 없는 경우 `expression` 하 `typename` (예를 들어 `Integer` 에 `Date`), Visual Basic 컴파일 시간 오류 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="09761-118">If no conversion is defined from `expression` to `typename` (for example, from `Integer` to `Date`), Visual Basic displays a compile-time error message.</span></span>

<span data-ttu-id="09761-119">런타임에 변환에 실패 하면 해당 예외가 throw 됩니다.</span><span class="sxs-lookup"><span data-stu-id="09761-119">If a conversion fails at run time, the appropriate exception is thrown.</span></span> <span data-ttu-id="09761-120">축소 변환에 실패 하면는 <xref:System.OverflowException> 가장 일반적인 결과입니다.</span><span class="sxs-lookup"><span data-stu-id="09761-120">If a narrowing conversion fails, an <xref:System.OverflowException> is the most common result.</span></span> <span data-ttu-id="09761-121">변환이 정의 하는 경우는 <xref:System.InvalidCastException> throw 합니다.</span><span class="sxs-lookup"><span data-stu-id="09761-121">If the conversion is undefined, an <xref:System.InvalidCastException> in thrown.</span></span> <span data-ttu-id="09761-122">예를 들어이 발생할 수 있습니다 `expression` 유형임 `Object` 해당 런타임 형식이 변환 되지 않습니다 및 `typename`합니다.</span><span class="sxs-lookup"><span data-stu-id="09761-122">For example, this can happen  if `expression` is of type `Object` and its run-time type has no conversion to `typename`.</span></span>

<span data-ttu-id="09761-123">데이터 형식이 `expression` 나 `typename` 클래스 또는 구조를 정의한 정의할 수 있습니다 `CType` 해당 클래스 또는 구조로 변환 연산자에서.</span><span class="sxs-lookup"><span data-stu-id="09761-123">If the data type of `expression` or `typename` is a class or structure you've defined, you can define `CType` on that class or structure as a conversion operator.</span></span> <span data-ttu-id="09761-124">따라서 `CType` 역할을 *오버 로드 된 연산자*합니다.</span><span class="sxs-lookup"><span data-stu-id="09761-124">This makes `CType` act as an *overloaded operator*.</span></span> <span data-ttu-id="09761-125">이 작업을 수행 하는 경우에 클래스 또는 구조를 throw 할 수 있는 예외를 포함 하 여 변환 하 고 동작을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09761-125">If you do this, you can control the behavior of conversions to and from your class or structure, including the exceptions that can be thrown.</span></span>

## <a name="overloading"></a><span data-ttu-id="09761-126">오버로딩</span><span class="sxs-lookup"><span data-stu-id="09761-126">Overloading</span></span>

<span data-ttu-id="09761-127">`CType` 연산자 클래스 또는 구조체 외부 코드에 정의 된도 오버 로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09761-127">The `CType` operator can also be overloaded on a class or structure defined outside your code.</span></span> <span data-ttu-id="09761-128">코드와 같은 클래스 또는 구조체에서 변환, 하는 경우 사용할의 동작을 알고 있어야 해당 `CType` 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="09761-128">If your code converts to or from such a class or structure, be sure you understand the behavior of its `CType` operator.</span></span> <span data-ttu-id="09761-129">자세한 내용은 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="09761-129">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>

## <a name="converting-dynamic-objects"></a><span data-ttu-id="09761-130">동적 개체 변환</span><span class="sxs-lookup"><span data-stu-id="09761-130">Converting Dynamic Objects</span></span>

<span data-ttu-id="09761-131">동적 개체의 형식 변환을 사용 하는 사용자 정의 동적 변환을 수행한 합니다 <xref:System.Dynamic.DynamicObject.TryConvert%2A> 또는 <xref:System.Dynamic.DynamicMetaObject.BindConvert%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="09761-131">Type conversions of dynamic objects are performed by user-defined dynamic conversions that use the <xref:System.Dynamic.DynamicObject.TryConvert%2A> or <xref:System.Dynamic.DynamicMetaObject.BindConvert%2A> methods.</span></span> <span data-ttu-id="09761-132">동적 개체를 사용 하는 경우 사용 된 <xref:Microsoft.VisualBasic.Conversion.CTypeDynamic%2A> 동적 개체를 변환 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="09761-132">If you're working with dynamic objects, use the <xref:Microsoft.VisualBasic.Conversion.CTypeDynamic%2A> method to convert the dynamic object.</span></span>

## <a name="example"></a><span data-ttu-id="09761-133">예제</span><span class="sxs-lookup"><span data-stu-id="09761-133">Example</span></span>

<span data-ttu-id="09761-134">다음 예제에서는 합니다 `CType` 식을 변환 하는 함수는 `Single` 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="09761-134">The following example uses the `CType` function to convert an expression to the `Single` data type.</span></span>

[!code-vb[VbVbalrFunctions#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#24)]

<span data-ttu-id="09761-135">추가 예제를 보려면 [암시적 변환과 명시적 변환](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="09761-135">For additional examples, see [Implicit and Explicit Conversions](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="09761-136">참고자료</span><span class="sxs-lookup"><span data-stu-id="09761-136">See also</span></span>

- <xref:System.OverflowException>
- <xref:System.InvalidCastException>
- [<span data-ttu-id="09761-137">형식 변환 함수</span><span class="sxs-lookup"><span data-stu-id="09761-137">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="09761-138">변환 함수</span><span class="sxs-lookup"><span data-stu-id="09761-138">Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/conversion-functions.md)
- [<span data-ttu-id="09761-139">Operator 문</span><span class="sxs-lookup"><span data-stu-id="09761-139">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)
- [<span data-ttu-id="09761-140">방법: 변환 연산자를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="09761-140">How to: Define a Conversion Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
- [<span data-ttu-id="09761-141">.NET Framework의 형식 변환</span><span class="sxs-lookup"><span data-stu-id="09761-141">Type Conversion in the .NET Framework</span></span>](../../../standard/base-types/type-conversion.md)
