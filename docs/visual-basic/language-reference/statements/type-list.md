---
title: Type List
ms.date: 07/20/2015
f1_keywords:
- StructureConstraint
- vb.StructureConstraint
- ClassConstraint
- vb.ClassConstraint
helpviewer_keywords:
- class constraint
- constraints, Visual Basic generic types
- generic parameters
- generics [Visual Basic], constraints
- generics [Visual Basic], type list
- structure constraint
- constraints, in type parameters
- generics [Visual Basic], generic types
- parameters [Visual Basic], type
- constraints, Structure keyword
- type parameters [Visual Basic], constraints
- types [Visual Basic], generic
- parameters [Visual Basic], generic
- generics [Visual Basic], type parameters
- type parameters
- constraints, Class keyword
ms.assetid: 56db947a-2ae8-40f2-a70a-960764e9d0db
ms.openlocfilehash: 3f2aaa65293ed2bcc6c8eeb4bd77e49907d93425
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352771"
---
# <a name="type-list-visual-basic"></a><span data-ttu-id="721ad-102">형식 목록(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="721ad-102">Type List (Visual Basic)</span></span>

<span data-ttu-id="721ad-103">*제네릭* 프로그래밍 요소에 대 한 *형식 매개 변수* 를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="721ad-103">Specifies the *type parameters* for a *generic* programming element.</span></span> <span data-ttu-id="721ad-104">여러 매개 변수는 쉼표로 구분 됩니다.</span><span class="sxs-lookup"><span data-stu-id="721ad-104">Multiple parameters are separated by commas.</span></span> <span data-ttu-id="721ad-105">다음은 하나의 형식 매개 변수에 대 한 구문입니다.</span><span class="sxs-lookup"><span data-stu-id="721ad-105">Following is the syntax for one type parameter.</span></span>

## <a name="syntax"></a><span data-ttu-id="721ad-106">구문</span><span class="sxs-lookup"><span data-stu-id="721ad-106">Syntax</span></span>

```vb
[genericmodifier] typename [ As constraintlist ]
```

## <a name="parts"></a><span data-ttu-id="721ad-107">요소</span><span class="sxs-lookup"><span data-stu-id="721ad-107">Parts</span></span>

|<span data-ttu-id="721ad-108">용어</span><span class="sxs-lookup"><span data-stu-id="721ad-108">Term</span></span>|<span data-ttu-id="721ad-109">정의</span><span class="sxs-lookup"><span data-stu-id="721ad-109">Definition</span></span>|
|---|---|
|`genericmodifier`|<span data-ttu-id="721ad-110">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="721ad-110">Optional.</span></span> <span data-ttu-id="721ad-111">제네릭 인터페이스 및 대리자 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="721ad-111">Can be used only in generic interfaces and delegates.</span></span> <span data-ttu-id="721ad-112">In 키워드를 사용 하 여 [Out](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md) 키워드나 반공 변을 사용 하 여 형식을 공변 [(](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md) covariant)으로 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="721ad-112">You can declare a type covariant by using the [Out](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md) keyword or contravariant by using the [In](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md) keyword.</span></span> <span data-ttu-id="721ad-113">[공변성(Covariance) 및 반공변성(Contravariance)](../../programming-guide/concepts/covariance-contravariance/index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="721ad-113">See [Covariance and Contravariance](../../programming-guide/concepts/covariance-contravariance/index.md).</span></span>|
|`typename`|<span data-ttu-id="721ad-114">필수입니다.</span><span class="sxs-lookup"><span data-stu-id="721ad-114">Required.</span></span> <span data-ttu-id="721ad-115">형식 매개 변수의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="721ad-115">Name of the type parameter.</span></span> <span data-ttu-id="721ad-116">해당 형식 인수가 제공 하는 정의 된 형식으로 대체 될 자리 표시자입니다.</span><span class="sxs-lookup"><span data-stu-id="721ad-116">This is a placeholder, to be replaced by a defined type supplied by the corresponding type argument.</span></span>|
|`constraintlist`|<span data-ttu-id="721ad-117">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="721ad-117">Optional.</span></span> <span data-ttu-id="721ad-118">`typename`에 대해 제공할 수 있는 데이터 형식을 제한 하는 요구 사항 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="721ad-118">List of requirements that constrain the data type that can be supplied for `typename`.</span></span> <span data-ttu-id="721ad-119">여러 제약 조건이 있는 경우 중괄호 (`{ }`)로 묶고 쉼표로 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="721ad-119">If you have multiple constraints, enclose them in curly braces (`{ }`) and separate them with commas.</span></span> <span data-ttu-id="721ad-120">제약 조건 목록에 [As](../../../visual-basic/language-reference/statements/as-clause.md) 키워드를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="721ad-120">You must introduce the constraint list with the [As](../../../visual-basic/language-reference/statements/as-clause.md) keyword.</span></span> <span data-ttu-id="721ad-121">목록의 시작 부분에 `As` 한 번만 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="721ad-121">You use `As` only once, at the beginning of the list.</span></span>|

## <a name="remarks"></a><span data-ttu-id="721ad-122">주의</span><span class="sxs-lookup"><span data-stu-id="721ad-122">Remarks</span></span>

<span data-ttu-id="721ad-123">모든 제네릭 프로그래밍 요소는 하나 이상의 형식 매개 변수를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="721ad-123">Every generic programming element must take at least one type parameter.</span></span> <span data-ttu-id="721ad-124">형식 매개 변수는 클라이언트 코드에서 제네릭 형식의 인스턴스를 만들 때 지정 하는 특정 형식 ( *생성 된 요소*)에 대 한 자리 표시자입니다.</span><span class="sxs-lookup"><span data-stu-id="721ad-124">A type parameter is a placeholder for a specific type (a *constructed element*) that client code specifies when it creates an instance of the generic type.</span></span> <span data-ttu-id="721ad-125">제네릭 클래스, 구조체, 인터페이스, 프로시저 또는 대리자를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="721ad-125">You can define a generic class, structure, interface, procedure, or delegate.</span></span>

<span data-ttu-id="721ad-126">제네릭 형식을 정의 하는 경우에 대 한 자세한 내용은 [Visual Basic의 제네릭 형식](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="721ad-126">For more information on when to define a generic type, see [Generic Types in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md).</span></span> <span data-ttu-id="721ad-127">형식 매개 변수 이름에 대 한 자세한 내용은 [선언 된 요소 이름](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="721ad-127">For more information on type parameter names, see [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>

## <a name="rules"></a><span data-ttu-id="721ad-128">규칙</span><span class="sxs-lookup"><span data-stu-id="721ad-128">Rules</span></span>

- <span data-ttu-id="721ad-129">**괄호.**</span><span class="sxs-lookup"><span data-stu-id="721ad-129">**Parentheses.**</span></span> <span data-ttu-id="721ad-130">형식 매개 변수 목록을 제공 하는 경우 괄호로 묶어야 합니다 .이 목록에는 [Of](../../../visual-basic/language-reference/statements/of-clause.md) 키워드를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="721ad-130">If you supply a type parameter list, you must enclose it in parentheses, and you must introduce the list with the [Of](../../../visual-basic/language-reference/statements/of-clause.md) keyword.</span></span> <span data-ttu-id="721ad-131">목록의 시작 부분에 `Of` 한 번만 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="721ad-131">You use `Of` only once, at the beginning of the list.</span></span>

- <span data-ttu-id="721ad-132">**적용.**</span><span class="sxs-lookup"><span data-stu-id="721ad-132">**Constraints.**</span></span> <span data-ttu-id="721ad-133">형식 매개 변수에 대 한 *제약 조건* 목록에는 다음과 같은 항목이 조합 되어 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="721ad-133">A list of *constraints* on a type parameter can include the following items in any combination:</span></span>

  - <span data-ttu-id="721ad-134">인터페이스 수 제한 없음</span><span class="sxs-lookup"><span data-stu-id="721ad-134">Any number of interfaces.</span></span> <span data-ttu-id="721ad-135">제공 된 형식은이 목록의 모든 인터페이스를 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="721ad-135">The supplied type must implement every interface in this list.</span></span>

  - <span data-ttu-id="721ad-136">최대 하나의 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="721ad-136">At most one class.</span></span> <span data-ttu-id="721ad-137">제공 된 형식은 해당 클래스에서 상속 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="721ad-137">The supplied type must inherit from that class.</span></span>

  - <span data-ttu-id="721ad-138">`New` 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="721ad-138">The `New` keyword.</span></span> <span data-ttu-id="721ad-139">제공 된 형식은 제네릭 형식에서 액세스할 수 있는 매개 변수가 없는 생성자를 노출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="721ad-139">The supplied type must expose a parameterless constructor that your generic type can access.</span></span> <span data-ttu-id="721ad-140">이는 하나 이상의 인터페이스로 형식 매개 변수를 제한 하는 경우에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="721ad-140">This is useful if you constrain a type parameter by one or more interfaces.</span></span> <span data-ttu-id="721ad-141">인터페이스를 구현 하는 형식이 반드시 생성자를 노출 하는 것은 아니며, 생성자의 액세스 수준에 따라 제네릭 형식 내의 코드에서 액세스 하지 못할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="721ad-141">A type that implements interfaces does not necessarily expose a constructor, and depending on the access level of a constructor, the code within the generic type might not be able to access it.</span></span>

  - <span data-ttu-id="721ad-142">`Class` 키워드 또는 `Structure` 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="721ad-142">Either the `Class` keyword or the `Structure` keyword.</span></span> <span data-ttu-id="721ad-143">`Class` 키워드는 제네릭 형식 매개 변수에 전달 된 형식 인수가 문자열, 배열 또는 대리자와 같은 참조 형식 이거나 클래스에서 만든 개체를 참조 형식으로 제한 하도록 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="721ad-143">The `Class` keyword constrains a generic type parameter to require that any type argument passed to it be a reference type, for example a string, array, or delegate, or an object created from a class.</span></span> <span data-ttu-id="721ad-144">`Structure` 키워드는 제네릭 형식 매개 변수에 전달 된 형식 인수가 구조체, 열거형 또는 기본 데이터 형식 등의 값 형식이 되도록 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="721ad-144">The `Structure` keyword constrains a generic type parameter to require that any type argument passed to it be a value type, for example a structure, enumeration, or elementary data type.</span></span> <span data-ttu-id="721ad-145">동일한 `constraintlist`에 `Class`와 `Structure`를 모두 포함할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="721ad-145">You cannot include both `Class` and `Structure` in the same `constraintlist`.</span></span>

  <span data-ttu-id="721ad-146">제공 된 형식은 `constraintlist`에 포함 하는 모든 요구 사항을 충족 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="721ad-146">The supplied type must satisfy every requirement you include in `constraintlist`.</span></span>

  <span data-ttu-id="721ad-147">각 형식 매개 변수에 대 한 제약 조건은 다른 형식 매개 변수에 대 한 제약 조건과는 독립적입니다.</span><span class="sxs-lookup"><span data-stu-id="721ad-147">Constraints on each type parameter are independent of constraints on other type parameters.</span></span>

## <a name="behavior"></a><span data-ttu-id="721ad-148">동작</span><span class="sxs-lookup"><span data-stu-id="721ad-148">Behavior</span></span>

- <span data-ttu-id="721ad-149">**컴파일 시간 대체입니다.**</span><span class="sxs-lookup"><span data-stu-id="721ad-149">**Compile-Time Substitution.**</span></span> <span data-ttu-id="721ad-150">제네릭 프로그래밍 요소에서 생성 된 형식을 만들 때 각 형식 매개 변수에 대해 정의 된 형식을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="721ad-150">When you create a constructed type from a generic programming element, you supply a defined type for each type parameter.</span></span> <span data-ttu-id="721ad-151">Visual Basic 컴파일러는 제네릭 요소 내에서 `typename` 발생 하는 모든 항목에 대해 제공 된 형식을 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="721ad-151">The Visual Basic compiler substitutes that supplied type for every occurrence of `typename` within the generic element.</span></span>

- <span data-ttu-id="721ad-152">**제약 조건이 없습니다.**</span><span class="sxs-lookup"><span data-stu-id="721ad-152">**Absence of Constraints.**</span></span> <span data-ttu-id="721ad-153">형식 매개 변수에 대 한 제약 조건을 지정 하지 않으면 해당 형식 매개 변수에 대 한 [개체 데이터 형식](../../../visual-basic/language-reference/data-types/object-data-type.md) 에서 지 원하는 작업 및 멤버로 코드가 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="721ad-153">If you do not specify any constraints on a type parameter, your code is limited to the operations and members supported by the [Object Data Type](../../../visual-basic/language-reference/data-types/object-data-type.md) for that type parameter.</span></span>

## <a name="example"></a><span data-ttu-id="721ad-154">예제</span><span class="sxs-lookup"><span data-stu-id="721ad-154">Example</span></span>

<span data-ttu-id="721ad-155">다음 예제에서는 사전에 새 항목을 추가 하는 기본 함수를 포함 하 여 제네릭 사전 클래스의 기본 정의를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="721ad-155">The following example shows a skeleton definition of a generic dictionary class, including a skeleton function to add a new entry to the dictionary.</span></span>

[!code-vb[VbVbalrStatements#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#3)]

## <a name="example"></a><span data-ttu-id="721ad-156">예제</span><span class="sxs-lookup"><span data-stu-id="721ad-156">Example</span></span>

<span data-ttu-id="721ad-157">`dictionary`은 일반적 이므로이를 사용 하는 코드는 동일한 기능을 갖지만 다른 데이터 형식에서 작동 하는 다양 한 개체를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="721ad-157">Because `dictionary` is generic, the code that uses it can create a variety of objects from it, each having the same functionality but acting on a different data type.</span></span> <span data-ttu-id="721ad-158">다음 예제에서는 `String` 항목과 `Integer` 키를 사용 하 여 `dictionary` 개체를 만드는 코드 줄을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="721ad-158">The following example shows a line of code that creates a `dictionary` object with `String` entries and `Integer` keys.</span></span>

[!code-vb[VbVbalrStatements#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#4)]

## <a name="example"></a><span data-ttu-id="721ad-159">예제</span><span class="sxs-lookup"><span data-stu-id="721ad-159">Example</span></span>

<span data-ttu-id="721ad-160">다음 예제에서는 앞의 예제에서 생성 된 해당 하는 기본 정의를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="721ad-160">The following example shows the equivalent skeleton definition generated by the preceding example.</span></span>

[!code-vb[VbVbalrStatements#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#5)]

## <a name="see-also"></a><span data-ttu-id="721ad-161">참고 항목</span><span class="sxs-lookup"><span data-stu-id="721ad-161">See also</span></span>

- [<span data-ttu-id="721ad-162">Of</span><span class="sxs-lookup"><span data-stu-id="721ad-162">Of</span></span>](../../../visual-basic/language-reference/statements/of-clause.md)
- [<span data-ttu-id="721ad-163">New 연산자</span><span class="sxs-lookup"><span data-stu-id="721ad-163">New Operator</span></span>](../../../visual-basic/language-reference/operators/new-operator.md)
- [<span data-ttu-id="721ad-164">Visual Basic의 액세스 수준</span><span class="sxs-lookup"><span data-stu-id="721ad-164">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="721ad-165">Object 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="721ad-165">Object Data Type</span></span>](../../../visual-basic/language-reference/data-types/object-data-type.md)
- [<span data-ttu-id="721ad-166">Function 문</span><span class="sxs-lookup"><span data-stu-id="721ad-166">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="721ad-167">Structure 문</span><span class="sxs-lookup"><span data-stu-id="721ad-167">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)
- [<span data-ttu-id="721ad-168">Sub 문</span><span class="sxs-lookup"><span data-stu-id="721ad-168">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="721ad-169">방법: 제네릭 클래스 사용</span><span class="sxs-lookup"><span data-stu-id="721ad-169">How to: Use a Generic Class</span></span>](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)
- [<span data-ttu-id="721ad-170">공 분산 및 반공 분산</span><span class="sxs-lookup"><span data-stu-id="721ad-170">Covariance and Contravariance</span></span>](../../programming-guide/concepts/covariance-contravariance/index.md)
- [<span data-ttu-id="721ad-171">In</span><span class="sxs-lookup"><span data-stu-id="721ad-171">In</span></span>](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)
- [<span data-ttu-id="721ad-172">Out</span><span class="sxs-lookup"><span data-stu-id="721ad-172">Out</span></span>](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)
