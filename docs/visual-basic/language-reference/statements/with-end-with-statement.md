---
description: 다음에 대해 자세히 알아보세요. End With 문 (Visual Basic)
title: With...End With 문
ms.date: 07/20/2015
f1_keywords:
- vb.With
helpviewer_keywords:
- With keyword [Visual Basic]
- loop structures [Visual Basic], and With...End With statements
- execution [Visual Basic], on object
- instructions, repeating
- With...End With statements [Visual Basic]
- With statement [Visual Basic]
- With statement [Visual Basic], nesting
- objects [Visual Basic], accessing
- With block
- End keyword [Visual Basic], With...End With statements
ms.assetid: 340d5fbb-4f43-48ec-a024-80843c137817
ms.openlocfilehash: 86393d5dee7a03b2b8396b34b31326d1b0ea3c28
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99787567"
---
# <a name="withend-with-statement-visual-basic"></a><span data-ttu-id="0f0e4-103">With...End With 문(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0f0e4-103">With...End With Statement (Visual Basic)</span></span>

<span data-ttu-id="0f0e4-104">개체 또는 구문의 멤버에 액세스할 때 문에서 단순화된 구문을 사용할 수 있도록 단일 개체를 반복적으로 참조하는 일련의 문을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0f0e4-104">Executes a series of statements that repeatedly refer to a single object or structure so that the statements can use a simplified syntax when accessing members of the object or structure.</span></span>  <span data-ttu-id="0f0e4-105">구조체를 사용하면 멤버 또는 호출 메서드의 값을 읽을 수만 있으며, `With...End With` 문에서 사용된 구조체의 멤버에 값을 할당하도록 시도하는 경우 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="0f0e4-105">When using a structure, you can only read the values of members or invoke methods, and you get an error if you try to assign values to members of a structure used in a `With...End With` statement.</span></span>

## <a name="syntax"></a><span data-ttu-id="0f0e4-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="0f0e4-106">Syntax</span></span>

```vb
With objectExpression
    [ statements ]
End With
```

## <a name="parts"></a><span data-ttu-id="0f0e4-107">부분</span><span class="sxs-lookup"><span data-stu-id="0f0e4-107">Parts</span></span>

|<span data-ttu-id="0f0e4-108">용어</span><span class="sxs-lookup"><span data-stu-id="0f0e4-108">Term</span></span>|<span data-ttu-id="0f0e4-109">정의</span><span class="sxs-lookup"><span data-stu-id="0f0e4-109">Definition</span></span>|
|---|---|
|`objectExpression`|<span data-ttu-id="0f0e4-110">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="0f0e4-110">Required.</span></span> <span data-ttu-id="0f0e4-111">개체를 평가하는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="0f0e4-111">An expression that evaluates to an object.</span></span> <span data-ttu-id="0f0e4-112">식은 임의적으로 복잡할 수 있으며, 한 번만 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f0e4-112">The expression may be arbitrarily complex and is evaluated only once.</span></span> <span data-ttu-id="0f0e4-113">식이 기본 형식을 포함하여 모든 데이터 형식으로 계산될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f0e4-113">The expression can evaluate to any data type, including elementary types.</span></span>|
|`statements`|<span data-ttu-id="0f0e4-114">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="0f0e4-114">Optional.</span></span> <span data-ttu-id="0f0e4-115">`With`의 평가를 통해 생성된 개체의 멤버를 참조할 수 있는 `End With`와 `objectExpression` 사이의 하나 이상의 문입니다.</span><span class="sxs-lookup"><span data-stu-id="0f0e4-115">One or more statements between `With` and `End With` that may refer to members of an object that's produced by the evaluation of `objectExpression`.</span></span>|
|`End With`|<span data-ttu-id="0f0e4-116">필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="0f0e4-116">Required.</span></span> <span data-ttu-id="0f0e4-117">`With` 블록의 정의를 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="0f0e4-117">Terminates the definition of the `With` block.</span></span>|

## <a name="remarks"></a><span data-ttu-id="0f0e4-118">설명</span><span class="sxs-lookup"><span data-stu-id="0f0e4-118">Remarks</span></span>

<span data-ttu-id="0f0e4-119">`With...End With`를 사용하여 개체의 이름을 여러 번 지정하지 않고 지정된 개체에 일련의 문을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f0e4-119">By using `With...End With`, you can perform a series of statements on a specified object without specifying the name of the object multiple times.</span></span> <span data-ttu-id="0f0e4-120">`With` 문 블록 내에서 `With` 문 개체가 앞에 오는 것처럼 기간으로 시작하는 개체의 멤버를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f0e4-120">Within a `With` statement block, you can specify a member of the object starting with a period, as if the `With` statement object preceded it.</span></span>

<span data-ttu-id="0f0e4-121">예를 들어, 하나의 개체에 있는 여러 속성을 변경하려면 속성을 할당할 때마다 한 번이 아닌 해당 개체를 한 번만 참조하여 `With...End With` 블록 내에 속성 할당 문을 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="0f0e4-121">For example, to change multiple properties on a single object, place the property assignment statements inside the `With...End With` block, referring to the object only once instead of once for each property assignment.</span></span>

<span data-ttu-id="0f0e4-122">코드가 여러 문에서 동일한 개체에 액세스하는 경우 `With` 문을 사용하여 다음과 같은 이점을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f0e4-122">If your code accesses the same object in multiple statements, you gain the following benefits by using the `With` statement:</span></span>

- <span data-ttu-id="0f0e4-123">복합 식을 여러 번 평가하거나 멤버를 여러 번 참조하기 위해 결과를 임시 변수에 할당할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0f0e4-123">You don't need to evaluate a complex expression multiple times or assign the result to a temporary variable to refer to its members multiple times.</span></span>

- <span data-ttu-id="0f0e4-124">반복적인 정규화 식을 제거하여 코드를 더욱 쉽게 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f0e4-124">You make your code more readable by eliminating repetitive qualifying expressions.</span></span>

<span data-ttu-id="0f0e4-125">`objectExpression`의 데이터 형식은 모든 클래스 또는 구조체 형식이거나 `Integer`와 같은 Visual Basic 기본 형식일 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f0e4-125">The data type of `objectExpression` can be any class or structure type or even a Visual Basic elementary type such as `Integer`.</span></span>  <span data-ttu-id="0f0e4-126">`objectExpression`이 개체 이외의 모든 항목을 생성하는 경우 멤버 또는 호출 메서드의 값을 읽을 수만 있으며, `With...End With` 문에서 사용된 구조체의 멤버에 값을 할당하도록 시도하는 경우 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="0f0e4-126">If `objectExpression` results in anything other than an object, you can only read the values of its members or invoke methods, and you get an error if you try to assign values to members of a structure used in a `With...End With` statement.</span></span>  <span data-ttu-id="0f0e4-127">이는 구조체를 반환하고 `GetAPoint().x = 1`과 같은 함수 결과의 멤버에 즉시 액세스하여 값을 할당한 메서드를 호출한 경우 발생하는 오류와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="0f0e4-127">This is the same error you would get if you invoked a method that returned a structure and immediately accessed and assigned a value to a member of the function’s result, such as `GetAPoint().x = 1`.</span></span>  <span data-ttu-id="0f0e4-128">두 경우 모두 구조체가 호출 스택에만 존재하고 이러한 상황의 수정된 구조체 멤버가 프로그램의 다른 코드가 변경을 관찰할 수 있는 위치에 쓸 수 있는 방법이 없는 문제가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="0f0e4-128">The problem in both cases is that the structure exists only on the call stack, and there is no way a modified structure member in these situations can write to  a location such that any other code in the program can observe the change.</span></span>

<span data-ttu-id="0f0e4-129">`objectExpression`은 블록에 삽입될 때 한번 평가됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f0e4-129">The `objectExpression` is evaluated once, upon entry into the block.</span></span> <span data-ttu-id="0f0e4-130">`objectExpression` 블록 내에서 `With`을 다시 할당할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0f0e4-130">You can't reassign the `objectExpression` from within the `With` block.</span></span>

<span data-ttu-id="0f0e4-131">`With` 블록 내에서 지정된 개체의 메서드와 속성을 한정하지 않고도 해당 메서드와 속성에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f0e4-131">Within a `With` block, you can access the methods and properties of only the specified object without qualifying them.</span></span> <span data-ttu-id="0f0e4-132">다른 개체의 메서드와 속성을 사용할 수 있지만 메서드와 속성을 해당 개체 이름으로 한정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f0e4-132">You can use methods and properties of other objects, but you must qualify them with their object names.</span></span>

<span data-ttu-id="0f0e4-133">하나의 `With...End With` 문을 배치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f0e4-133">You can place one `With...End With` statement within another.</span></span> <span data-ttu-id="0f0e4-134">참조 중인 개체가 컨텍스트에서 명확하지 않은 경우 중첩 `With...End With` 문이 혼동을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f0e4-134">Nested `With...End With` statements may be confusing if the objects that are being referred to aren't clear from context.</span></span> <span data-ttu-id="0f0e4-135">개체가 내부 `With` 블록 내에서 참조되면 외부 `With` 블록에 있는 개체에 대한 정규화된 참조를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f0e4-135">You must provide a fully qualified reference to an object that's in an outer `With` block when the object is referenced from within an inner `With` block.</span></span>

<span data-ttu-id="0f0e4-136">블록 외부에서 `With` 문 블록으로 분기할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0f0e4-136">You can't branch into a `With` statement block from outside the block.</span></span>

<span data-ttu-id="0f0e4-137">블록에 루프가 없으면 문이 한 번만 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f0e4-137">Unless the block contains a loop, the statements run only once.</span></span> <span data-ttu-id="0f0e4-138">다른 종류의 제어 구조를 중첩할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f0e4-138">You can nest different kinds of control structures.</span></span> <span data-ttu-id="0f0e4-139">자세한 내용은 [중첩 컨트롤 구조](../../programming-guide/language-features/control-flow/nested-control-structures.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0f0e4-139">For more information, see [Nested Control Structures](../../programming-guide/language-features/control-flow/nested-control-structures.md).</span></span>

> [!NOTE]
> <span data-ttu-id="0f0e4-140">개체 이니셜라이저에서도 `With` 키워드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f0e4-140">You can use the `With` keyword in object initializers also.</span></span> <span data-ttu-id="0f0e4-141">자세한 내용 및 예제는 [개체 이니셜라이저: 명명 된 형식과 익명 형식](../../programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md) 및 [익명 형식](../../programming-guide/language-features/objects-and-classes/anonymous-types.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0f0e4-141">For more information and examples, see [Object Initializers: Named and Anonymous Types](../../programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md) and [Anonymous Types](../../programming-guide/language-features/objects-and-classes/anonymous-types.md).</span></span>
>
> <span data-ttu-id="0f0e4-142">인스턴스화한 개체의 필드 또는 속성을 초기화하기 위해서만 `With` 블록을 사용하는 경우 대신 개체 이니셜라이저를 사용할 것을 고려하십시오.</span><span class="sxs-lookup"><span data-stu-id="0f0e4-142">If you're using a `With` block only to initialize the properties or fields of an object that you've just instantiated, consider using an object initializer instead.</span></span>

## <a name="example"></a><span data-ttu-id="0f0e4-143">예제</span><span class="sxs-lookup"><span data-stu-id="0f0e4-143">Example</span></span>

<span data-ttu-id="0f0e4-144">다음 예제에서는 각 `With` 블록이 단일 개체에 대해 일련의 문을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0f0e4-144">In the following example, each `With` block executes a series of statements on a single object.</span></span>

[!code-vb[VbVbalrWithStatement#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrwithstatement/vb/mainwindow.xaml.vb#2)]

## <a name="example"></a><span data-ttu-id="0f0e4-145">예제</span><span class="sxs-lookup"><span data-stu-id="0f0e4-145">Example</span></span>

<span data-ttu-id="0f0e4-146">다음 예제에서는 `With…End With` 문을 중첩시킵니다.</span><span class="sxs-lookup"><span data-stu-id="0f0e4-146">The following example nests `With…End With` statements.</span></span> <span data-ttu-id="0f0e4-147">중첩된 `With` 문 내에서 구문은 내부 개체를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="0f0e4-147">Within the nested `With` statement, the syntax refers to the inner object.</span></span>

[!code-vb[VbVbalrWithStatement#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrwithstatement/vb/mainwindow.xaml.vb#1)]

## <a name="see-also"></a><span data-ttu-id="0f0e4-148">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0f0e4-148">See also</span></span>

- <xref:System.Collections.Generic.List%601>
- [<span data-ttu-id="0f0e4-149">중첩 제어 구조체</span><span class="sxs-lookup"><span data-stu-id="0f0e4-149">Nested Control Structures</span></span>](../../programming-guide/language-features/control-flow/nested-control-structures.md)
- [<span data-ttu-id="0f0e4-150">개체 이니셜라이저: 명명된 형식 및 무명 형식</span><span class="sxs-lookup"><span data-stu-id="0f0e4-150">Object Initializers: Named and Anonymous Types</span></span>](../../programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [<span data-ttu-id="0f0e4-151">익명 형식</span><span class="sxs-lookup"><span data-stu-id="0f0e4-151">Anonymous Types</span></span>](../../programming-guide/language-features/objects-and-classes/anonymous-types.md)
