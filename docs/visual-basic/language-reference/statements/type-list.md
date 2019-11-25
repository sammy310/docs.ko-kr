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
# <a name="type-list-visual-basic"></a><span data-ttu-id="83b76-102">형식 목록(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="83b76-102">Type List (Visual Basic)</span></span>

<span data-ttu-id="83b76-103">Specifies the *type parameters* for a *generic* programming element.</span><span class="sxs-lookup"><span data-stu-id="83b76-103">Specifies the *type parameters* for a *generic* programming element.</span></span> <span data-ttu-id="83b76-104">Multiple parameters are separated by commas.</span><span class="sxs-lookup"><span data-stu-id="83b76-104">Multiple parameters are separated by commas.</span></span> <span data-ttu-id="83b76-105">Following is the syntax for one type parameter.</span><span class="sxs-lookup"><span data-stu-id="83b76-105">Following is the syntax for one type parameter.</span></span>

## <a name="syntax"></a><span data-ttu-id="83b76-106">구문</span><span class="sxs-lookup"><span data-stu-id="83b76-106">Syntax</span></span>

```vb
[genericmodifier] typename [ As constraintlist ]
```

## <a name="parts"></a><span data-ttu-id="83b76-107">요소</span><span class="sxs-lookup"><span data-stu-id="83b76-107">Parts</span></span>

|<span data-ttu-id="83b76-108">용어</span><span class="sxs-lookup"><span data-stu-id="83b76-108">Term</span></span>|<span data-ttu-id="83b76-109">정의</span><span class="sxs-lookup"><span data-stu-id="83b76-109">Definition</span></span>|
|---|---|
|`genericmodifier`|<span data-ttu-id="83b76-110">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="83b76-110">Optional.</span></span> <span data-ttu-id="83b76-111">Can be used only in generic interfaces and delegates.</span><span class="sxs-lookup"><span data-stu-id="83b76-111">Can be used only in generic interfaces and delegates.</span></span> <span data-ttu-id="83b76-112">You can declare a type covariant by using the [Out](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md) keyword or contravariant by using the [In](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md) keyword.</span><span class="sxs-lookup"><span data-stu-id="83b76-112">You can declare a type covariant by using the [Out](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md) keyword or contravariant by using the [In](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md) keyword.</span></span> <span data-ttu-id="83b76-113">[공변성(Covariance) 및 반공변성(Contravariance)](../../programming-guide/concepts/covariance-contravariance/index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="83b76-113">See [Covariance and Contravariance](../../programming-guide/concepts/covariance-contravariance/index.md).</span></span>|
|`typename`|<span data-ttu-id="83b76-114">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="83b76-114">Required.</span></span> <span data-ttu-id="83b76-115">Name of the type parameter.</span><span class="sxs-lookup"><span data-stu-id="83b76-115">Name of the type parameter.</span></span> <span data-ttu-id="83b76-116">This is a placeholder, to be replaced by a defined type supplied by the corresponding type argument.</span><span class="sxs-lookup"><span data-stu-id="83b76-116">This is a placeholder, to be replaced by a defined type supplied by the corresponding type argument.</span></span>|
|`constraintlist`|<span data-ttu-id="83b76-117">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="83b76-117">Optional.</span></span> <span data-ttu-id="83b76-118">List of requirements that constrain the data type that can be supplied for `typename`.</span><span class="sxs-lookup"><span data-stu-id="83b76-118">List of requirements that constrain the data type that can be supplied for `typename`.</span></span> <span data-ttu-id="83b76-119">If you have multiple constraints, enclose them in curly braces (`{ }`) and separate them with commas.</span><span class="sxs-lookup"><span data-stu-id="83b76-119">If you have multiple constraints, enclose them in curly braces (`{ }`) and separate them with commas.</span></span> <span data-ttu-id="83b76-120">You must introduce the constraint list with the [As](../../../visual-basic/language-reference/statements/as-clause.md) keyword.</span><span class="sxs-lookup"><span data-stu-id="83b76-120">You must introduce the constraint list with the [As](../../../visual-basic/language-reference/statements/as-clause.md) keyword.</span></span> <span data-ttu-id="83b76-121">You use `As` only once, at the beginning of the list.</span><span class="sxs-lookup"><span data-stu-id="83b76-121">You use `As` only once, at the beginning of the list.</span></span>|

## <a name="remarks"></a><span data-ttu-id="83b76-122">주의</span><span class="sxs-lookup"><span data-stu-id="83b76-122">Remarks</span></span>

<span data-ttu-id="83b76-123">Every generic programming element must take at least one type parameter.</span><span class="sxs-lookup"><span data-stu-id="83b76-123">Every generic programming element must take at least one type parameter.</span></span> <span data-ttu-id="83b76-124">A type parameter is a placeholder for a specific type (a *constructed element*) that client code specifies when it creates an instance of the generic type.</span><span class="sxs-lookup"><span data-stu-id="83b76-124">A type parameter is a placeholder for a specific type (a *constructed element*) that client code specifies when it creates an instance of the generic type.</span></span> <span data-ttu-id="83b76-125">You can define a generic class, structure, interface, procedure, or delegate.</span><span class="sxs-lookup"><span data-stu-id="83b76-125">You can define a generic class, structure, interface, procedure, or delegate.</span></span>

<span data-ttu-id="83b76-126">For more information on when to define a generic type, see [Generic Types in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md).</span><span class="sxs-lookup"><span data-stu-id="83b76-126">For more information on when to define a generic type, see [Generic Types in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md).</span></span> <span data-ttu-id="83b76-127">For more information on type parameter names, see [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="83b76-127">For more information on type parameter names, see [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>

## <a name="rules"></a><span data-ttu-id="83b76-128">규칙</span><span class="sxs-lookup"><span data-stu-id="83b76-128">Rules</span></span>

- <span data-ttu-id="83b76-129">**Parentheses.**</span><span class="sxs-lookup"><span data-stu-id="83b76-129">**Parentheses.**</span></span> <span data-ttu-id="83b76-130">If you supply a type parameter list, you must enclose it in parentheses, and you must introduce the list with the [Of](../../../visual-basic/language-reference/statements/of-clause.md) keyword.</span><span class="sxs-lookup"><span data-stu-id="83b76-130">If you supply a type parameter list, you must enclose it in parentheses, and you must introduce the list with the [Of](../../../visual-basic/language-reference/statements/of-clause.md) keyword.</span></span> <span data-ttu-id="83b76-131">You use `Of` only once, at the beginning of the list.</span><span class="sxs-lookup"><span data-stu-id="83b76-131">You use `Of` only once, at the beginning of the list.</span></span>

- <span data-ttu-id="83b76-132">**Constraints.**</span><span class="sxs-lookup"><span data-stu-id="83b76-132">**Constraints.**</span></span> <span data-ttu-id="83b76-133">A list of *constraints* on a type parameter can include the following items in any combination:</span><span class="sxs-lookup"><span data-stu-id="83b76-133">A list of *constraints* on a type parameter can include the following items in any combination:</span></span>

  - <span data-ttu-id="83b76-134">Any number of interfaces.</span><span class="sxs-lookup"><span data-stu-id="83b76-134">Any number of interfaces.</span></span> <span data-ttu-id="83b76-135">The supplied type must implement every interface in this list.</span><span class="sxs-lookup"><span data-stu-id="83b76-135">The supplied type must implement every interface in this list.</span></span>

  - <span data-ttu-id="83b76-136">At most one class.</span><span class="sxs-lookup"><span data-stu-id="83b76-136">At most one class.</span></span> <span data-ttu-id="83b76-137">The supplied type must inherit from that class.</span><span class="sxs-lookup"><span data-stu-id="83b76-137">The supplied type must inherit from that class.</span></span>

  - <span data-ttu-id="83b76-138">`New` 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="83b76-138">The `New` keyword.</span></span> <span data-ttu-id="83b76-139">The supplied type must expose a parameterless constructor that your generic type can access.</span><span class="sxs-lookup"><span data-stu-id="83b76-139">The supplied type must expose a parameterless constructor that your generic type can access.</span></span> <span data-ttu-id="83b76-140">This is useful if you constrain a type parameter by one or more interfaces.</span><span class="sxs-lookup"><span data-stu-id="83b76-140">This is useful if you constrain a type parameter by one or more interfaces.</span></span> <span data-ttu-id="83b76-141">A type that implements interfaces does not necessarily expose a constructor, and depending on the access level of a constructor, the code within the generic type might not be able to access it.</span><span class="sxs-lookup"><span data-stu-id="83b76-141">A type that implements interfaces does not necessarily expose a constructor, and depending on the access level of a constructor, the code within the generic type might not be able to access it.</span></span>

  - <span data-ttu-id="83b76-142">Either the `Class` keyword or the `Structure` keyword.</span><span class="sxs-lookup"><span data-stu-id="83b76-142">Either the `Class` keyword or the `Structure` keyword.</span></span> <span data-ttu-id="83b76-143">The `Class` keyword constrains a generic type parameter to require that any type argument passed to it be a reference type, for example a string, array, or delegate, or an object created from a class.</span><span class="sxs-lookup"><span data-stu-id="83b76-143">The `Class` keyword constrains a generic type parameter to require that any type argument passed to it be a reference type, for example a string, array, or delegate, or an object created from a class.</span></span> <span data-ttu-id="83b76-144">The `Structure` keyword constrains a generic type parameter to require that any type argument passed to it be a value type, for example a structure, enumeration, or elementary data type.</span><span class="sxs-lookup"><span data-stu-id="83b76-144">The `Structure` keyword constrains a generic type parameter to require that any type argument passed to it be a value type, for example a structure, enumeration, or elementary data type.</span></span> <span data-ttu-id="83b76-145">You cannot include both `Class` and `Structure` in the same `constraintlist`.</span><span class="sxs-lookup"><span data-stu-id="83b76-145">You cannot include both `Class` and `Structure` in the same `constraintlist`.</span></span>

  <span data-ttu-id="83b76-146">The supplied type must satisfy every requirement you include in `constraintlist`.</span><span class="sxs-lookup"><span data-stu-id="83b76-146">The supplied type must satisfy every requirement you include in `constraintlist`.</span></span>

  <span data-ttu-id="83b76-147">Constraints on each type parameter are independent of constraints on other type parameters.</span><span class="sxs-lookup"><span data-stu-id="83b76-147">Constraints on each type parameter are independent of constraints on other type parameters.</span></span>

## <a name="behavior"></a><span data-ttu-id="83b76-148">동작</span><span class="sxs-lookup"><span data-stu-id="83b76-148">Behavior</span></span>

- <span data-ttu-id="83b76-149">**Compile-Time Substitution.**</span><span class="sxs-lookup"><span data-stu-id="83b76-149">**Compile-Time Substitution.**</span></span> <span data-ttu-id="83b76-150">When you create a constructed type from a generic programming element, you supply a defined type for each type parameter.</span><span class="sxs-lookup"><span data-stu-id="83b76-150">When you create a constructed type from a generic programming element, you supply a defined type for each type parameter.</span></span> <span data-ttu-id="83b76-151">The Visual Basic compiler substitutes that supplied type for every occurrence of `typename` within the generic element.</span><span class="sxs-lookup"><span data-stu-id="83b76-151">The Visual Basic compiler substitutes that supplied type for every occurrence of `typename` within the generic element.</span></span>

- <span data-ttu-id="83b76-152">**Absence of Constraints.**</span><span class="sxs-lookup"><span data-stu-id="83b76-152">**Absence of Constraints.**</span></span> <span data-ttu-id="83b76-153">If you do not specify any constraints on a type parameter, your code is limited to the operations and members supported by the [Object Data Type](../../../visual-basic/language-reference/data-types/object-data-type.md) for that type parameter.</span><span class="sxs-lookup"><span data-stu-id="83b76-153">If you do not specify any constraints on a type parameter, your code is limited to the operations and members supported by the [Object Data Type](../../../visual-basic/language-reference/data-types/object-data-type.md) for that type parameter.</span></span>

## <a name="example"></a><span data-ttu-id="83b76-154">예제</span><span class="sxs-lookup"><span data-stu-id="83b76-154">Example</span></span>

<span data-ttu-id="83b76-155">The following example shows a skeleton definition of a generic dictionary class, including a skeleton function to add a new entry to the dictionary.</span><span class="sxs-lookup"><span data-stu-id="83b76-155">The following example shows a skeleton definition of a generic dictionary class, including a skeleton function to add a new entry to the dictionary.</span></span>

[!code-vb[VbVbalrStatements#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#3)]

## <a name="example"></a><span data-ttu-id="83b76-156">예제</span><span class="sxs-lookup"><span data-stu-id="83b76-156">Example</span></span>

<span data-ttu-id="83b76-157">Because `dictionary` is generic, the code that uses it can create a variety of objects from it, each having the same functionality but acting on a different data type.</span><span class="sxs-lookup"><span data-stu-id="83b76-157">Because `dictionary` is generic, the code that uses it can create a variety of objects from it, each having the same functionality but acting on a different data type.</span></span> <span data-ttu-id="83b76-158">The following example shows a line of code that creates a `dictionary` object with `String` entries and `Integer` keys.</span><span class="sxs-lookup"><span data-stu-id="83b76-158">The following example shows a line of code that creates a `dictionary` object with `String` entries and `Integer` keys.</span></span>

[!code-vb[VbVbalrStatements#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#4)]

## <a name="example"></a><span data-ttu-id="83b76-159">예제</span><span class="sxs-lookup"><span data-stu-id="83b76-159">Example</span></span>

<span data-ttu-id="83b76-160">The following example shows the equivalent skeleton definition generated by the preceding example.</span><span class="sxs-lookup"><span data-stu-id="83b76-160">The following example shows the equivalent skeleton definition generated by the preceding example.</span></span>

[!code-vb[VbVbalrStatements#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#5)]

## <a name="see-also"></a><span data-ttu-id="83b76-161">참조</span><span class="sxs-lookup"><span data-stu-id="83b76-161">See also</span></span>

- [<span data-ttu-id="83b76-162">Of</span><span class="sxs-lookup"><span data-stu-id="83b76-162">Of</span></span>](../../../visual-basic/language-reference/statements/of-clause.md)
- [<span data-ttu-id="83b76-163">New 연산자</span><span class="sxs-lookup"><span data-stu-id="83b76-163">New Operator</span></span>](../../../visual-basic/language-reference/operators/new-operator.md)
- [<span data-ttu-id="83b76-164">Access levels in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="83b76-164">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="83b76-165">Object 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="83b76-165">Object Data Type</span></span>](../../../visual-basic/language-reference/data-types/object-data-type.md)
- [<span data-ttu-id="83b76-166">Function 문</span><span class="sxs-lookup"><span data-stu-id="83b76-166">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="83b76-167">Structure 문</span><span class="sxs-lookup"><span data-stu-id="83b76-167">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)
- [<span data-ttu-id="83b76-168">Sub 문</span><span class="sxs-lookup"><span data-stu-id="83b76-168">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="83b76-169">방법: 제네릭 클래스 사용</span><span class="sxs-lookup"><span data-stu-id="83b76-169">How to: Use a Generic Class</span></span>](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)
- [<span data-ttu-id="83b76-170">공 분산 및 반공 분산</span><span class="sxs-lookup"><span data-stu-id="83b76-170">Covariance and Contravariance</span></span>](../../programming-guide/concepts/covariance-contravariance/index.md)
- [<span data-ttu-id="83b76-171">In</span><span class="sxs-lookup"><span data-stu-id="83b76-171">In</span></span>](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)
- [<span data-ttu-id="83b76-172">Out</span><span class="sxs-lookup"><span data-stu-id="83b76-172">Out</span></span>](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)
