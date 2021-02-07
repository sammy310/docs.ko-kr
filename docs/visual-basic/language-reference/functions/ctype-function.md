---
description: '자세한 정보: CType 함수 (Visual Basic)'
title: CType Function
ms.date: 07/20/2015
f1_keywords:
- vb.CType
helpviewer_keywords:
- expression conversion results
- explicit data type conversions [Visual Basic]
- CType function
- conversions [Visual Basic], expression
ms.assetid: dd4b29e7-6fa1-428c-877e-69955420bb72
ms.openlocfilehash: 9732f52b40e5f762769ba5dc340c000e7e1ba17a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99701263"
---
# <a name="ctype-function-visual-basic"></a><span data-ttu-id="b8085-103">CType 함수(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b8085-103">CType Function (Visual Basic)</span></span>

<span data-ttu-id="b8085-104">식을 지정한 데이터 형식, 개체, 구조체, 클래스 또는 인터페이스로 명시적으로 변환한 결과를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8085-104">Returns the result of explicitly converting an expression to a specified data type, object, structure, class, or interface.</span></span>

## <a name="syntax"></a><span data-ttu-id="b8085-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="b8085-105">Syntax</span></span>

```vb
CType(expression, typename)
```

## <a name="parts"></a><span data-ttu-id="b8085-106">부분</span><span class="sxs-lookup"><span data-stu-id="b8085-106">Parts</span></span>

<span data-ttu-id="b8085-107">`expression` 모든 유효한 식입니다.</span><span class="sxs-lookup"><span data-stu-id="b8085-107">`expression` Any valid expression.</span></span> <span data-ttu-id="b8085-108">의 값 `expression` 이에서 허용 하는 범위를 벗어나면 `typename` Visual Basic 예외를 throw 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8085-108">If the value of `expression` is outside the range allowed by `typename`, Visual Basic throws an exception.</span></span>

<span data-ttu-id="b8085-109">`typename``As`문의 절, `Dim` 즉 데이터 형식, 개체, 구조체, 클래스 또는 인터페이스의 이름에 적합 한 식입니다.</span><span class="sxs-lookup"><span data-stu-id="b8085-109">`typename` Any expression that is legal within an `As` clause in a `Dim` statement, that is, the name of any data type, object, structure, class, or interface.</span></span>

## <a name="remarks"></a><span data-ttu-id="b8085-110">설명</span><span class="sxs-lookup"><span data-stu-id="b8085-110">Remarks</span></span>

> [!TIP]
> <span data-ttu-id="b8085-111">다음 함수를 사용 하 여 형식 변환을 수행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8085-111">You can also use the following functions to perform a type conversion:</span></span>
>
> - <span data-ttu-id="b8085-112">`CByte` `CDbl` `CInt` 특정 데이터 형식으로 변환을 수행 하는,, 등의 형식 변환 함수</span><span class="sxs-lookup"><span data-stu-id="b8085-112">Type conversion functions such as `CByte`, `CDbl`, and `CInt` that perform a conversion to a specific data type.</span></span> <span data-ttu-id="b8085-113">자세한 내용은 [형식 변환 함수](type-conversion-functions.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b8085-113">For more information, see [Type Conversion Functions](type-conversion-functions.md).</span></span>
> - <span data-ttu-id="b8085-114">[DirectCast operator](../operators/directcast-operator.md) 또는 [TryCast operator](../operators/trycast-operator.md).</span><span class="sxs-lookup"><span data-stu-id="b8085-114">[DirectCast Operator](../operators/directcast-operator.md) or [TryCast Operator](../operators/trycast-operator.md).</span></span> <span data-ttu-id="b8085-115">이러한 연산자를 적용 하려면 한 형식이 다른 형식에서 상속 하거나 다른 형식을 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8085-115">These operators require that one type inherit from or implement the other type.</span></span> <span data-ttu-id="b8085-116">`CType`데이터 형식으로 변환 하는 경우 보다 약간 더 나은 성능을 제공할 수 있습니다 `Object` .</span><span class="sxs-lookup"><span data-stu-id="b8085-116">They can provide somewhat better performance than `CType` when converting to and from the `Object` data type.</span></span>

<span data-ttu-id="b8085-117">`CType` 는 인라인으로 컴파일 되므로 변환 코드는 식을 계산 하는 코드의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="b8085-117">`CType` is compiled inline, which means that the conversion code is part of the code that evaluates the expression.</span></span> <span data-ttu-id="b8085-118">변환을 수행 하기 위해 프로시저가 호출 되지 않기 때문에 코드가 더 빨리 실행 되는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8085-118">In some cases, the code runs faster because no procedures are called to perform the conversion.</span></span>

<span data-ttu-id="b8085-119">에서로의 변환이 정의 되지 않은 경우 `expression` `typename` (예:에서 `Integer` 로 `Date` ) Visual Basic 컴파일 시간 오류 메시지를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8085-119">If no conversion is defined from `expression` to `typename` (for example, from `Integer` to `Date`), Visual Basic displays a compile-time error message.</span></span>

<span data-ttu-id="b8085-120">런타임에 변환이 실패 하면 적절 한 예외가 throw 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8085-120">If a conversion fails at run time, the appropriate exception is thrown.</span></span> <span data-ttu-id="b8085-121">축소 변환에 실패 하는 경우 <xref:System.OverflowException> 가 가장 일반적인 결과입니다.</span><span class="sxs-lookup"><span data-stu-id="b8085-121">If a narrowing conversion fails, an <xref:System.OverflowException> is the most common result.</span></span> <span data-ttu-id="b8085-122">변환이 정의 되지 않은 경우이 <xref:System.InvalidCastException> throw 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8085-122">If the conversion is undefined, an <xref:System.InvalidCastException> in thrown.</span></span> <span data-ttu-id="b8085-123">예를 들어 `expression` 가 형식이 `Object` 고 해당 런타임 형식이로 변환 되지 않은 경우이 문제가 발생할 수 있습니다 `typename` .</span><span class="sxs-lookup"><span data-stu-id="b8085-123">For example, this can happen  if `expression` is of type `Object` and its run-time type has no conversion to `typename`.</span></span>

<span data-ttu-id="b8085-124">또는의 데이터 형식이 `expression` `typename` 정의한 클래스 또는 구조체 인 경우 `CType` 해당 클래스 또는 구조체를 변환 연산자로 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8085-124">If the data type of `expression` or `typename` is a class or structure you've defined, you can define `CType` on that class or structure as a conversion operator.</span></span> <span data-ttu-id="b8085-125">이렇게 하면 `CType` *오버 로드 된 연산자* 역할을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8085-125">This makes `CType` act as an *overloaded operator*.</span></span> <span data-ttu-id="b8085-126">이 작업을 수행 하는 경우 throw 할 수 있는 예외를 포함 하 여 클래스 또는 구조체에서 변환의 동작을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8085-126">If you do this, you can control the behavior of conversions to and from your class or structure, including the exceptions that can be thrown.</span></span>

## <a name="overloading"></a><span data-ttu-id="b8085-127">오버로딩</span><span class="sxs-lookup"><span data-stu-id="b8085-127">Overloading</span></span>

<span data-ttu-id="b8085-128">`CType`코드 외부에서 정의 된 클래스 또는 구조체에서 연산자를 오버 로드할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8085-128">The `CType` operator can also be overloaded on a class or structure defined outside your code.</span></span> <span data-ttu-id="b8085-129">코드가 이러한 클래스나 구조체 간에 변환 되는 경우 해당 연산자의 동작을 이해 하 고 있어야 합니다 `CType` .</span><span class="sxs-lookup"><span data-stu-id="b8085-129">If your code converts to or from such a class or structure, be sure you understand the behavior of its `CType` operator.</span></span> <span data-ttu-id="b8085-130">자세한 내용은 [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b8085-130">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>

## <a name="converting-dynamic-objects"></a><span data-ttu-id="b8085-131">동적 개체 변환</span><span class="sxs-lookup"><span data-stu-id="b8085-131">Converting Dynamic Objects</span></span>

<span data-ttu-id="b8085-132">동적 개체의 형식 변환은 또는 메서드를 사용 하는 사용자 정의 동적 변환에 의해 수행 됩니다 <xref:System.Dynamic.DynamicObject.TryConvert%2A> <xref:System.Dynamic.DynamicMetaObject.BindConvert%2A> .</span><span class="sxs-lookup"><span data-stu-id="b8085-132">Type conversions of dynamic objects are performed by user-defined dynamic conversions that use the <xref:System.Dynamic.DynamicObject.TryConvert%2A> or <xref:System.Dynamic.DynamicMetaObject.BindConvert%2A> methods.</span></span> <span data-ttu-id="b8085-133">동적 개체로 작업 하는 경우 메서드를 사용 <xref:Microsoft.VisualBasic.Conversion.CTypeDynamic%2A> 하 여 동적 개체를 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8085-133">If you're working with dynamic objects, use the <xref:Microsoft.VisualBasic.Conversion.CTypeDynamic%2A> method to convert the dynamic object.</span></span>

## <a name="example"></a><span data-ttu-id="b8085-134">예제</span><span class="sxs-lookup"><span data-stu-id="b8085-134">Example</span></span>

<span data-ttu-id="b8085-135">다음 예에서는 함수를 사용 하 여 `CType` 식을 데이터 형식으로 변환 합니다 `Single` .</span><span class="sxs-lookup"><span data-stu-id="b8085-135">The following example uses the `CType` function to convert an expression to the `Single` data type.</span></span>

[!code-vb[VbVbalrFunctions#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#24)]

<span data-ttu-id="b8085-136">추가 예제는 [암시적 변환과 명시적 변환](../../programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b8085-136">For additional examples, see [Implicit and Explicit Conversions](../../programming-guide/language-features/data-types/implicit-and-explicit-conversions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b8085-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b8085-137">See also</span></span>

- <xref:System.OverflowException>
- <xref:System.InvalidCastException>
- [<span data-ttu-id="b8085-138">형식 변환 함수</span><span class="sxs-lookup"><span data-stu-id="b8085-138">Type Conversion Functions</span></span>](type-conversion-functions.md)
- [<span data-ttu-id="b8085-139">변환 함수</span><span class="sxs-lookup"><span data-stu-id="b8085-139">Conversion Functions</span></span>](conversion-functions.md)
- [<span data-ttu-id="b8085-140">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="b8085-140">Operator Statement</span></span>](../statements/operator-statement.md)
- [<span data-ttu-id="b8085-141">방법: 변환 연산자 정의</span><span class="sxs-lookup"><span data-stu-id="b8085-141">How to: Define a Conversion Operator</span></span>](../../programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
- [<span data-ttu-id="b8085-142">.NET Framework의 형식 변환</span><span class="sxs-lookup"><span data-stu-id="b8085-142">Type Conversion in the .NET Framework</span></span>](../../../standard/base-types/type-conversion.md)
