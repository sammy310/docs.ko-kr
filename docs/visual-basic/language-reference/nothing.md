---
title: Nothing 키워드
ms.date: 07/20/2015
f1_keywords:
- Nothing
- vb.Nothing
helpviewer_keywords:
- Nothing keyword [Visual Basic]
- Nothing keyword [Visual Basic], syntax
ms.assetid: 06176e2d-bbf7-4a37-afaa-a86ad21ee99f
ms.openlocfilehash: 3bd4681341a33cc8db4ecbc2b284be243db56549
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344169"
---
# <a name="nothing-keyword-visual-basic"></a><span data-ttu-id="08477-102">Nothing 키워드 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="08477-102">Nothing keyword (Visual Basic)</span></span>

<span data-ttu-id="08477-103">모든 데이터 형식의 기본값을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="08477-103">Represents the default value of any data type.</span></span> <span data-ttu-id="08477-104">참조 형식의 경우 기본값은 `null` 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="08477-104">For reference types, the default value is the `null` reference.</span></span> <span data-ttu-id="08477-105">값 형식의 경우 기본값은 값 형식이 null을 허용 하는지 여부에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="08477-105">For value types, the default value depends on whether the value type is nullable.</span></span>

> [!NOTE]
> <span data-ttu-id="08477-106">Nullable이 아닌 값 형식의 경우의 `Nothing` Visual Basic의 `null` 다릅니다 C#.</span><span class="sxs-lookup"><span data-stu-id="08477-106">For non-nullable value types, `Nothing` in Visual Basic differs from `null` in C#.</span></span> <span data-ttu-id="08477-107">Visual Basic nullable이 아닌 값 형식의 변수를 `Nothing`로 설정 하면 변수가 선언 된 형식에 대 한 기본값으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="08477-107">In Visual Basic, if you set a variable of a non-nullable value type to `Nothing`, the variable is set to the default value for its declared type.</span></span> <span data-ttu-id="08477-108">에서 C#nullable이 아닌 값 형식의 변수를 `null`에 할당 하면 컴파일 타임 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="08477-108">In C#, if you assign a variable of a non-nullable value type to `null`, a compile-time error occurs.</span></span>

## <a name="remarks"></a><span data-ttu-id="08477-109">주의</span><span class="sxs-lookup"><span data-stu-id="08477-109">Remarks</span></span>

<span data-ttu-id="08477-110">데이터 형식의 기본값을 나타내는 `Nothing`입니다.</span><span class="sxs-lookup"><span data-stu-id="08477-110">`Nothing` represents the default value of a data type.</span></span> <span data-ttu-id="08477-111">기본값은 변수가 값 형식 인지 참조 형식 인지에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="08477-111">The default value depends on whether the variable is of a value type or of a reference type.</span></span>

<span data-ttu-id="08477-112">*값 형식의* 변수에는 해당 값이 직접 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="08477-112">A variable of a *value type* directly contains its value.</span></span> <span data-ttu-id="08477-113">값 형식에는 모든 숫자 데이터 형식, `Boolean`, `Char`, `Date`, 모든 구조 및 모든 열거형이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="08477-113">Value types include all numeric data types, `Boolean`, `Char`, `Date`, all structures, and all enumerations.</span></span> <span data-ttu-id="08477-114">*참조 형식의* 변수는 메모리에 있는 개체의 인스턴스에 대 한 참조를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="08477-114">A variable of a *reference type* stores a reference to an instance of the object in memory.</span></span> <span data-ttu-id="08477-115">참조 형식에는 클래스, 배열, 대리자 및 문자열이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="08477-115">Reference types include classes, arrays, delegates, and strings.</span></span> <span data-ttu-id="08477-116">자세한 내용은 [Value Types and Reference Types](../programming-guide/language-features/data-types/value-types-and-reference-types.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="08477-116">For more information, see [Value Types and Reference Types](../programming-guide/language-features/data-types/value-types-and-reference-types.md).</span></span>

<span data-ttu-id="08477-117">변수가 값 형식이 면 변수의 `Nothing` 동작은 변수가 nullable 데이터 형식 인지에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="08477-117">If a variable is of a value type, the behavior of `Nothing` depends on whether the variable is of a nullable data type.</span></span> <span data-ttu-id="08477-118">Nullable 값 형식을 나타내려면 형식 이름에 `?` 한정자를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="08477-118">To represent a nullable value type, add a `?` modifier to the type name.</span></span> <span data-ttu-id="08477-119">Nullable 변수에 `Nothing`를 할당 하면 값이 `null`로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="08477-119">Assigning `Nothing` to a nullable variable sets the value to `null`.</span></span> <span data-ttu-id="08477-120">자세한 내용 및 예제는 [Nullable 값 형식](../programming-guide/language-features/data-types/nullable-value-types.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="08477-120">For more information and examples, see [Nullable Value Types](../programming-guide/language-features/data-types/nullable-value-types.md).</span></span>

<span data-ttu-id="08477-121">변수가 null을 허용 하지 않는 값 형식인 경우 `Nothing`를 할당 하면 선언 된 형식에 대 한 기본값으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="08477-121">If a variable is of a value type that is not nullable, assigning `Nothing` to it sets it to the default value for its declared type.</span></span> <span data-ttu-id="08477-122">해당 형식에 변수 멤버가 포함 되어 있으면 모두 기본값으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="08477-122">If that type contains variable members, they are all set to their default values.</span></span> <span data-ttu-id="08477-123">다음 예제에서는 스칼라 형식에 대해이를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="08477-123">The following example illustrates this for scalar types.</span></span>

[!code-vb[VbVbalrKeywords#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class2.vb#7)]

<span data-ttu-id="08477-124">변수가 참조 형식이 면 변수에 `Nothing`를 할당 하면 변수의 형식에 대 한 `null` 참조로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="08477-124">If a variable is of a reference type, assigning `Nothing` to the variable sets it to a `null` reference of the variable's type.</span></span> <span data-ttu-id="08477-125">`null` 참조로 설정 된 변수가 개체와 연결 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="08477-125">A variable that is set to a `null` reference is not associated with any object.</span></span> <span data-ttu-id="08477-126">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="08477-126">The following example demonstrates this:</span></span>

[!code-vb[VbVbalrKeywords#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/class3.vb#8)]

<span data-ttu-id="08477-127">참조 (또는 nullable 값 형식) 변수가 `null`되는지 여부를 확인할 때 `= Nothing` 또는 `<> Nothing`를 사용 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="08477-127">When checking whether a reference (or nullable value type) variable is `null`, do not use `= Nothing` or `<> Nothing`.</span></span> <span data-ttu-id="08477-128">항상 `Is Nothing` 또는 `IsNot Nothing`를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="08477-128">Always use `Is Nothing` or `IsNot Nothing`.</span></span>

<span data-ttu-id="08477-129">Visual Basic 문자열의 경우 빈 문자열은 `Nothing`와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="08477-129">For strings in Visual Basic, the empty string equals `Nothing`.</span></span> <span data-ttu-id="08477-130">따라서 `"" = Nothing` true입니다.</span><span class="sxs-lookup"><span data-stu-id="08477-130">Therefore, `"" = Nothing` is true.</span></span>

<span data-ttu-id="08477-131">다음 예에서는 `Is` 및 `IsNot` 연산자를 사용 하는 비교를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="08477-131">The following example shows comparisons that use the `Is` and `IsNot` operators:</span></span>

[!code-vb[VbVbalrKeywords#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class4.vb#9)]

<span data-ttu-id="08477-132">`As` 절을 사용 하지 않고 변수를 선언 하 고 `Nothing`로 설정 하는 경우 변수에는 `Object`형식이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08477-132">If you declare a variable without using an `As` clause and set it to `Nothing`, the variable has a type of `Object`.</span></span> <span data-ttu-id="08477-133">이에 대 한 예는 `Dim something = Nothing`합니다.</span><span class="sxs-lookup"><span data-stu-id="08477-133">An example of this is `Dim something = Nothing`.</span></span> <span data-ttu-id="08477-134">이 경우 `Option Strict`가 on이 고 `Option Infer` 꺼져 있는 경우 컴파일 시간 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="08477-134">A compile-time error occurs in this case when `Option Strict` is on and `Option Infer` is off.</span></span>

<span data-ttu-id="08477-135">개체 변수에 `Nothing` 할당 하면 더 이상 개체 인스턴스를 참조 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="08477-135">When you assign `Nothing` to an object variable, it no longer refers to any object instance.</span></span> <span data-ttu-id="08477-136">변수가 이전에 인스턴스를 참조 한 경우 `Nothing`로 설정 해도 인스턴스 자체는 종료 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="08477-136">If the variable had previously referred to an instance, setting it to `Nothing` does not terminate the instance itself.</span></span> <span data-ttu-id="08477-137">인스턴스가 종료 되 고 해당 인스턴스와 연결 된 메모리 및 시스템 리소스가 해제 된 후에만 GC (가비지 수집기)에서 활성 참조가 남아 있지 않음을 감지한 후에만 해제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="08477-137">The instance is terminated, and the memory and system resources associated with it are released, only after the garbage collector (GC) detects that there are no active references remaining.</span></span>

<span data-ttu-id="08477-138">`Nothing`은 초기화 되지 않은 variant 또는 존재 하지 않는 데이터베이스 열을 나타내는 <xref:System.DBNull> 개체와 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="08477-138">`Nothing` differs from the <xref:System.DBNull> object, which represents an uninitialized variant or a nonexistent database column.</span></span>

## <a name="see-also"></a><span data-ttu-id="08477-139">참고 항목</span><span class="sxs-lookup"><span data-stu-id="08477-139">See also</span></span>

- [<span data-ttu-id="08477-140">Dim 문</span><span class="sxs-lookup"><span data-stu-id="08477-140">Dim Statement</span></span>](./statements/dim-statement.md)
- [<span data-ttu-id="08477-141">개체 수명: 개체가 만들어지고 제거되는 방법</span><span class="sxs-lookup"><span data-stu-id="08477-141">Object Lifetime: How Objects Are Created and Destroyed</span></span>](../programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
- [<span data-ttu-id="08477-142">Visual Basic 수명</span><span class="sxs-lookup"><span data-stu-id="08477-142">Lifetime in Visual Basic</span></span>](../programming-guide/language-features/declared-elements/lifetime.md)
- [<span data-ttu-id="08477-143">Is 연산자</span><span class="sxs-lookup"><span data-stu-id="08477-143">Is Operator</span></span>](./operators/is-operator.md)
- [<span data-ttu-id="08477-144">IsNot 연산자</span><span class="sxs-lookup"><span data-stu-id="08477-144">IsNot Operator</span></span>](./operators/isnot-operator.md)
- [<span data-ttu-id="08477-145">Nullable 값 형식</span><span class="sxs-lookup"><span data-stu-id="08477-145">Nullable Value Types</span></span>](../programming-guide/language-features/data-types/nullable-value-types.md)
