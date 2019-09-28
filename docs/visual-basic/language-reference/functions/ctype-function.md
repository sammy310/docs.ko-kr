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
ms.openlocfilehash: 4a0391b0a5d76f36803b433369d4832c02b05e09
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/28/2019
ms.locfileid: "71592105"
---
# <a name="ctype-function-visual-basic"></a><span data-ttu-id="42ca8-102">CType 함수(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="42ca8-102">CType Function (Visual Basic)</span></span>

<span data-ttu-id="42ca8-103">식을 지정한 데이터 형식, 개체, 구조체, 클래스 또는 인터페이스로 명시적으로 변환한 결과를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="42ca8-103">Returns the result of explicitly converting an expression to a specified data type, object, structure, class, or interface.</span></span>

## <a name="syntax"></a><span data-ttu-id="42ca8-104">구문</span><span class="sxs-lookup"><span data-stu-id="42ca8-104">Syntax</span></span>

```vb
CType(expression, typename)
```

## <a name="parts"></a><span data-ttu-id="42ca8-105">요소</span><span class="sxs-lookup"><span data-stu-id="42ca8-105">Parts</span></span>

<span data-ttu-id="42ca8-106">`expression` 모든 유효한 식입니다.</span><span class="sxs-lookup"><span data-stu-id="42ca8-106">`expression` Any valid expression.</span></span> <span data-ttu-id="42ca8-107">@No__t-0의 값이 `typename`에서 허용 하는 범위를 벗어나면 Visual Basic에서 예외를 throw 합니다.</span><span class="sxs-lookup"><span data-stu-id="42ca8-107">If the value of `expression` is outside the range allowed by `typename`, Visual Basic throws an exception.</span></span>

<span data-ttu-id="42ca8-108">`typename` `Dim` 문의 `As` 절, 즉 모든 데이터 형식, 개체, 구조체, 클래스 또는 인터페이스의 이름에 적합 한 식입니다.</span><span class="sxs-lookup"><span data-stu-id="42ca8-108">`typename` Any expression that is legal within an `As` clause in a `Dim` statement, that is, the name of any data type, object, structure, class, or interface.</span></span>

## <a name="remarks"></a><span data-ttu-id="42ca8-109">설명</span><span class="sxs-lookup"><span data-stu-id="42ca8-109">Remarks</span></span>

> [!TIP]
> <span data-ttu-id="42ca8-110">다음 함수를 사용 하 여 형식 변환을 수행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42ca8-110">You can also use the following functions to perform a type conversion:</span></span>
>
> - <span data-ttu-id="42ca8-111">특정 데이터 형식으로 변환을 수행 하는 `CByte`, `CDbl`, `CInt`와 같은 형식 변환 함수</span><span class="sxs-lookup"><span data-stu-id="42ca8-111">Type conversion functions such as `CByte`, `CDbl`, and `CInt` that perform a conversion to a specific data type.</span></span> <span data-ttu-id="42ca8-112">자세한 내용은 [형식 변환 함수](../../../visual-basic/language-reference/functions/type-conversion-functions.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="42ca8-112">For more information, see [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md).</span></span>
> - <span data-ttu-id="42ca8-113">[DirectCast operator](../../../visual-basic/language-reference/operators/directcast-operator.md) 또는 [TryCast operator](../../../visual-basic/language-reference/operators/trycast-operator.md).</span><span class="sxs-lookup"><span data-stu-id="42ca8-113">[DirectCast Operator](../../../visual-basic/language-reference/operators/directcast-operator.md) or [TryCast Operator](../../../visual-basic/language-reference/operators/trycast-operator.md).</span></span> <span data-ttu-id="42ca8-114">이러한 연산자를 적용 하려면 한 형식이 다른 형식에서 상속 하거나 다른 형식을 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="42ca8-114">These operators require that one type inherit from or implement the other type.</span></span> <span data-ttu-id="42ca8-115">@No__t-1 데이터 형식으로 변환할 때 `CType` 보다 약간 더 나은 성능을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42ca8-115">They can provide somewhat better performance than `CType` when converting to and from the `Object` data type.</span></span>

<span data-ttu-id="42ca8-116">`CType`은 인라인으로 컴파일되어 있습니다. 즉, 변환 코드는 식을 계산 하는 코드의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="42ca8-116">`CType` is compiled inline, which means that the conversion code is part of the code that evaluates the expression.</span></span> <span data-ttu-id="42ca8-117">변환을 수행 하기 위해 프로시저가 호출 되지 않기 때문에 코드가 더 빨리 실행 되는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42ca8-117">In some cases, the code runs faster because no procedures are called to perform the conversion.</span></span>

<span data-ttu-id="42ca8-118">@No__t-0에서-1 @no__t로의 변환이 정의 되지 않은 경우 (예: `Integer`에서 `Date`) Visual Basic 컴파일 타임 오류 메시지를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="42ca8-118">If no conversion is defined from `expression` to `typename` (for example, from `Integer` to `Date`), Visual Basic displays a compile-time error message.</span></span>

<span data-ttu-id="42ca8-119">런타임에 변환이 실패 하면 적절 한 예외가 throw 됩니다.</span><span class="sxs-lookup"><span data-stu-id="42ca8-119">If a conversion fails at run time, the appropriate exception is thrown.</span></span> <span data-ttu-id="42ca8-120">축소 변환에 실패 하는 경우 <xref:System.OverflowException>이 가장 일반적인 결과입니다.</span><span class="sxs-lookup"><span data-stu-id="42ca8-120">If a narrowing conversion fails, an <xref:System.OverflowException> is the most common result.</span></span> <span data-ttu-id="42ca8-121">변환이 정의 되어 있지 않으면 <xref:System.InvalidCastException>이 throw 됩니다.</span><span class="sxs-lookup"><span data-stu-id="42ca8-121">If the conversion is undefined, an <xref:System.InvalidCastException> in thrown.</span></span> <span data-ttu-id="42ca8-122">예를 들어 `expression`이 `Object` 형식이 고 런타임 형식이 `typename`로 변환 되지 않은 경우이 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42ca8-122">For example, this can happen  if `expression` is of type `Object` and its run-time type has no conversion to `typename`.</span></span>

<span data-ttu-id="42ca8-123">@No__t-0 또는 `typename`의 데이터 형식이 정의한 클래스 또는 구조체 인 경우 해당 클래스 또는 구조체에 대 한 `CType`를 변환 연산자로 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42ca8-123">If the data type of `expression` or `typename` is a class or structure you've defined, you can define `CType` on that class or structure as a conversion operator.</span></span> <span data-ttu-id="42ca8-124">이렇게 하면 `CType`이 *오버 로드 된 연산자*역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="42ca8-124">This makes `CType` act as an *overloaded operator*.</span></span> <span data-ttu-id="42ca8-125">이 작업을 수행 하는 경우 throw 할 수 있는 예외를 포함 하 여 클래스 또는 구조체에서 변환의 동작을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42ca8-125">If you do this, you can control the behavior of conversions to and from your class or structure, including the exceptions that can be thrown.</span></span>

## <a name="overloading"></a><span data-ttu-id="42ca8-126">오버로딩</span><span class="sxs-lookup"><span data-stu-id="42ca8-126">Overloading</span></span>

<span data-ttu-id="42ca8-127">@No__t-0 연산자는 코드 외부에서 정의 된 클래스 또는 구조체에서 오버 로드 될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42ca8-127">The `CType` operator can also be overloaded on a class or structure defined outside your code.</span></span> <span data-ttu-id="42ca8-128">코드가 이러한 클래스나 구조체 간에 변환 되는 경우 `CType` 연산자의 동작을 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="42ca8-128">If your code converts to or from such a class or structure, be sure you understand the behavior of its `CType` operator.</span></span> <span data-ttu-id="42ca8-129">자세한 내용은 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="42ca8-129">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>

## <a name="converting-dynamic-objects"></a><span data-ttu-id="42ca8-130">동적 개체 변환</span><span class="sxs-lookup"><span data-stu-id="42ca8-130">Converting Dynamic Objects</span></span>

<span data-ttu-id="42ca8-131">동적 개체의 형식 변환은 <xref:System.Dynamic.DynamicObject.TryConvert%2A> 또는 <xref:System.Dynamic.DynamicMetaObject.BindConvert%2A> 메서드를 사용 하는 사용자 정의 동적 변환에 의해 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="42ca8-131">Type conversions of dynamic objects are performed by user-defined dynamic conversions that use the <xref:System.Dynamic.DynamicObject.TryConvert%2A> or <xref:System.Dynamic.DynamicMetaObject.BindConvert%2A> methods.</span></span> <span data-ttu-id="42ca8-132">동적 개체로 작업 하는 경우 <xref:Microsoft.VisualBasic.Conversion.CTypeDynamic%2A> 메서드를 사용 하 여 동적 개체를 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="42ca8-132">If you're working with dynamic objects, use the <xref:Microsoft.VisualBasic.Conversion.CTypeDynamic%2A> method to convert the dynamic object.</span></span>

## <a name="example"></a><span data-ttu-id="42ca8-133">예제</span><span class="sxs-lookup"><span data-stu-id="42ca8-133">Example</span></span>

<span data-ttu-id="42ca8-134">다음 예에서는 `CType` 함수를 사용 하 여 식을 `Single` 데이터 형식으로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="42ca8-134">The following example uses the `CType` function to convert an expression to the `Single` data type.</span></span>

[!code-vb[VbVbalrFunctions#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#24)]

<span data-ttu-id="42ca8-135">추가 예제는 [암시적 변환과 명시적 변환](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="42ca8-135">For additional examples, see [Implicit and Explicit Conversions](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="42ca8-136">참조</span><span class="sxs-lookup"><span data-stu-id="42ca8-136">See also</span></span>

- <xref:System.OverflowException>
- <xref:System.InvalidCastException>
- [<span data-ttu-id="42ca8-137">형식 변환 함수</span><span class="sxs-lookup"><span data-stu-id="42ca8-137">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="42ca8-138">변환 함수</span><span class="sxs-lookup"><span data-stu-id="42ca8-138">Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/conversion-functions.md)
- [<span data-ttu-id="42ca8-139">Operator 문</span><span class="sxs-lookup"><span data-stu-id="42ca8-139">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)
- <span data-ttu-id="42ca8-140">[방법: 변환 연산자 정의 @ no__t-0</span><span class="sxs-lookup"><span data-stu-id="42ca8-140">[How to: Define a Conversion Operator](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)</span></span>
- [<span data-ttu-id="42ca8-141">.NET Framework의 형식 변환</span><span class="sxs-lookup"><span data-stu-id="42ca8-141">Type Conversion in the .NET Framework</span></span>](../../../standard/base-types/type-conversion.md)
