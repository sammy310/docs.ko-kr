---
title: Dim 문
ms.date: 05/12/2018
f1_keywords:
- vb.Dim
- Dim
helpviewer_keywords:
- Public keyword [Visual Basic], in Dim statement
- Dim statement [Visual Basic]
- fixed-length strings [Visual Basic], declaring
- variables [Visual Basic], declaring
- WithEvents keyword [Visual Basic], Dim statement
- dynamic arrays [Visual Basic], Dim statement
- variables [Visual Basic], initializing
- '{} braces'
- fields [Visual Basic], as member variables
- declarations [Visual Basic], dynamic arrays
- member variables [Visual Basic]
- default values [Visual Basic]
- data types [Visual Basic], assigning
- braces {}
- As keyword [Visual Basic], in Dim statement
- arrays [Visual Basic], declaring
- New keyword [Visual Basic], Dim statement
- To keyword [Visual Basic], in Dim statement
- storage [Visual Basic], allocating
- local variables [Visual Basic]
- declaration statements [Visual Basic]
- Dim statement [Visual Basic], syntax
- variables [Visual Basic], member and local
ms.assetid: fae3eca1-f0b2-4400-994b-7aa58a848448
ms.openlocfilehash: ac66ffdba622673ef42017d147c05b2a2733dede
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343765"
---
# <a name="dim-statement-visual-basic"></a><span data-ttu-id="ee26c-102">Dim 문(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ee26c-102">Dim Statement (Visual Basic)</span></span>

<span data-ttu-id="ee26c-103">Declares and allocates storage space for one or more variables.</span><span class="sxs-lookup"><span data-stu-id="ee26c-103">Declares and allocates storage space for one or more variables.</span></span>

## <a name="syntax"></a><span data-ttu-id="ee26c-104">구문</span><span class="sxs-lookup"><span data-stu-id="ee26c-104">Syntax</span></span>

```vb
[ <attributelist> ] [ accessmodifier ] [[ Shared ] [ Shadows ] | [ Static ]] [ ReadOnly ]
Dim [ WithEvents ] variablelist
```

## <a name="parts"></a><span data-ttu-id="ee26c-105">요소</span><span class="sxs-lookup"><span data-stu-id="ee26c-105">Parts</span></span>

- `attributelist`

  <span data-ttu-id="ee26c-106">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="ee26c-106">Optional.</span></span> <span data-ttu-id="ee26c-107">See [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md).</span><span class="sxs-lookup"><span data-stu-id="ee26c-107">See [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md).</span></span>

- `accessmodifier`

  <span data-ttu-id="ee26c-108">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="ee26c-108">Optional.</span></span> <span data-ttu-id="ee26c-109">다음 중 하나일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee26c-109">Can be one of the following:</span></span>

  - [<span data-ttu-id="ee26c-110">Public</span><span class="sxs-lookup"><span data-stu-id="ee26c-110">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)

  - [<span data-ttu-id="ee26c-111">보호됨</span><span class="sxs-lookup"><span data-stu-id="ee26c-111">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)

  - [<span data-ttu-id="ee26c-112">Friend</span><span class="sxs-lookup"><span data-stu-id="ee26c-112">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)

  - [<span data-ttu-id="ee26c-113">전용</span><span class="sxs-lookup"><span data-stu-id="ee26c-113">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)

  - [<span data-ttu-id="ee26c-114">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="ee26c-114">Protected Friend</span></span>](../../language-reference/modifiers/protected-friend.md)

  - [<span data-ttu-id="ee26c-115">Private Protected</span><span class="sxs-lookup"><span data-stu-id="ee26c-115">Private Protected</span></span>](../../language-reference/modifiers/private-protected.md)

  <span data-ttu-id="ee26c-116">[Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ee26c-116">See [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>

- `Shared`

  <span data-ttu-id="ee26c-117">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="ee26c-117">Optional.</span></span> <span data-ttu-id="ee26c-118">See [Shared](../../../visual-basic/language-reference/modifiers/shared.md).</span><span class="sxs-lookup"><span data-stu-id="ee26c-118">See [Shared](../../../visual-basic/language-reference/modifiers/shared.md).</span></span>

- `Shadows`

  <span data-ttu-id="ee26c-119">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="ee26c-119">Optional.</span></span> <span data-ttu-id="ee26c-120">See [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).</span><span class="sxs-lookup"><span data-stu-id="ee26c-120">See [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).</span></span>

- `Static`

  <span data-ttu-id="ee26c-121">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="ee26c-121">Optional.</span></span> <span data-ttu-id="ee26c-122">See [Static](../../../visual-basic/language-reference/modifiers/static.md).</span><span class="sxs-lookup"><span data-stu-id="ee26c-122">See [Static](../../../visual-basic/language-reference/modifiers/static.md).</span></span>

- `ReadOnly`

  <span data-ttu-id="ee26c-123">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="ee26c-123">Optional.</span></span> <span data-ttu-id="ee26c-124">See [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="ee26c-124">See [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>

- `WithEvents`

<span data-ttu-id="ee26c-125">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="ee26c-125">Optional.</span></span> <span data-ttu-id="ee26c-126">Specifies that these are object variables that refer to instances of a class that can raise events.</span><span class="sxs-lookup"><span data-stu-id="ee26c-126">Specifies that these are object variables that refer to instances of a class that can raise events.</span></span> <span data-ttu-id="ee26c-127">See [WithEvents](../../../visual-basic/language-reference/modifiers/withevents.md).</span><span class="sxs-lookup"><span data-stu-id="ee26c-127">See [WithEvents](../../../visual-basic/language-reference/modifiers/withevents.md).</span></span>

- `variablelist`

  <span data-ttu-id="ee26c-128">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="ee26c-128">Required.</span></span> <span data-ttu-id="ee26c-129">List of variables being declared in this statement.</span><span class="sxs-lookup"><span data-stu-id="ee26c-129">List of variables being declared in this statement.</span></span>

  `variable [ , variable ... ]`

  <span data-ttu-id="ee26c-130">각 `variable`에는 다음과 같은 구문과 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee26c-130">Each `variable` has the following syntax and parts:</span></span>

  <span data-ttu-id="ee26c-131">`variablename [ ( [ boundslist ] ) ] [ As [ New ] datatype [ With`{`[ .propertyname = propinitializer [ , ... ] ] } ] ] [ = initializer ]`</span><span class="sxs-lookup"><span data-stu-id="ee26c-131">`variablename [ ( [ boundslist ] ) ] [ As [ New ] datatype [ With`{`[ .propertyname = propinitializer [ , ... ] ] } ] ] [ = initializer ]`</span></span>

  |<span data-ttu-id="ee26c-132">파트</span><span class="sxs-lookup"><span data-stu-id="ee26c-132">Part</span></span>|<span data-ttu-id="ee26c-133">설명</span><span class="sxs-lookup"><span data-stu-id="ee26c-133">Description</span></span>|
  |---|---|
  |`variablename`|<span data-ttu-id="ee26c-134">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="ee26c-134">Required.</span></span> <span data-ttu-id="ee26c-135">변수의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="ee26c-135">Name of the variable.</span></span> <span data-ttu-id="ee26c-136">[Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ee26c-136">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>|
  |`boundslist`|<span data-ttu-id="ee26c-137">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="ee26c-137">Optional.</span></span> <span data-ttu-id="ee26c-138">List of bounds of each dimension of an array variable.</span><span class="sxs-lookup"><span data-stu-id="ee26c-138">List of bounds of each dimension of an array variable.</span></span>|
  |`New`|<span data-ttu-id="ee26c-139">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="ee26c-139">Optional.</span></span> <span data-ttu-id="ee26c-140">Creates a new instance of the class when the `Dim` statement runs.</span><span class="sxs-lookup"><span data-stu-id="ee26c-140">Creates a new instance of the class when the `Dim` statement runs.</span></span>|
  |`datatype`|<span data-ttu-id="ee26c-141">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="ee26c-141">Optional.</span></span> <span data-ttu-id="ee26c-142">Data type of the variable.</span><span class="sxs-lookup"><span data-stu-id="ee26c-142">Data type of the variable.</span></span>|
  |`With`|<span data-ttu-id="ee26c-143">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="ee26c-143">Optional.</span></span> <span data-ttu-id="ee26c-144">Introduces the object initializer list.</span><span class="sxs-lookup"><span data-stu-id="ee26c-144">Introduces the object initializer list.</span></span>|
  |`propertyname`|<span data-ttu-id="ee26c-145">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="ee26c-145">Optional.</span></span> <span data-ttu-id="ee26c-146">The name of a property in the class you are making an instance of.</span><span class="sxs-lookup"><span data-stu-id="ee26c-146">The name of a property in the class you are making an instance of.</span></span>|
  |`propinitializer`|<span data-ttu-id="ee26c-147">Required after `propertyname` =.</span><span class="sxs-lookup"><span data-stu-id="ee26c-147">Required after `propertyname` =.</span></span> <span data-ttu-id="ee26c-148">The expression that is evaluated and assigned to the property name.</span><span class="sxs-lookup"><span data-stu-id="ee26c-148">The expression that is evaluated and assigned to the property name.</span></span>|
  |`initializer`|<span data-ttu-id="ee26c-149">Optional if `New` is not specified.</span><span class="sxs-lookup"><span data-stu-id="ee26c-149">Optional if `New` is not specified.</span></span> <span data-ttu-id="ee26c-150">Expression that is evaluated and assigned to the variable when it is created.</span><span class="sxs-lookup"><span data-stu-id="ee26c-150">Expression that is evaluated and assigned to the variable when it is created.</span></span>|

## <a name="remarks"></a><span data-ttu-id="ee26c-151">주의</span><span class="sxs-lookup"><span data-stu-id="ee26c-151">Remarks</span></span>

<span data-ttu-id="ee26c-152">The Visual Basic compiler uses the `Dim` statement to determine the variable's data type and other information, such as what code can access the variable.</span><span class="sxs-lookup"><span data-stu-id="ee26c-152">The Visual Basic compiler uses the `Dim` statement to determine the variable's data type and other information, such as what code can access the variable.</span></span> <span data-ttu-id="ee26c-153">The following example declares a variable to hold an `Integer` value.</span><span class="sxs-lookup"><span data-stu-id="ee26c-153">The following example declares a variable to hold an `Integer` value.</span></span>

```vb
Dim numberOfStudents As Integer
```

<span data-ttu-id="ee26c-154">You can specify any data type or the name of an enumeration, structure, class, or interface.</span><span class="sxs-lookup"><span data-stu-id="ee26c-154">You can specify any data type or the name of an enumeration, structure, class, or interface.</span></span>

```vb
Dim finished As Boolean
Dim monitorBox As System.Windows.Forms.Form
```

<span data-ttu-id="ee26c-155">For a reference type, you use the `New` keyword to create a new instance of the class or structure that is specified by the data type.</span><span class="sxs-lookup"><span data-stu-id="ee26c-155">For a reference type, you use the `New` keyword to create a new instance of the class or structure that is specified by the data type.</span></span> <span data-ttu-id="ee26c-156">If you use `New`, you do not use an initializer expression.</span><span class="sxs-lookup"><span data-stu-id="ee26c-156">If you use `New`, you do not use an initializer expression.</span></span> <span data-ttu-id="ee26c-157">Instead, you supply arguments, if they are required, to the constructor of the class from which you are creating the variable.</span><span class="sxs-lookup"><span data-stu-id="ee26c-157">Instead, you supply arguments, if they are required, to the constructor of the class from which you are creating the variable.</span></span>

```vb
Dim bottomLabel As New System.Windows.Forms.Label
```

<span data-ttu-id="ee26c-158">You can declare a variable in a procedure, block, class, structure, or module.</span><span class="sxs-lookup"><span data-stu-id="ee26c-158">You can declare a variable in a procedure, block, class, structure, or module.</span></span> <span data-ttu-id="ee26c-159">You cannot declare a variable in a source file, namespace, or interface.</span><span class="sxs-lookup"><span data-stu-id="ee26c-159">You cannot declare a variable in a source file, namespace, or interface.</span></span> <span data-ttu-id="ee26c-160">자세한 내용은 [선언 컨텍스트 및 기본 액세스 수준](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ee26c-160">For more information, see [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span></span>

<span data-ttu-id="ee26c-161">A variable that is declared at module level, outside any procedure, is a *member variable* or *field*.</span><span class="sxs-lookup"><span data-stu-id="ee26c-161">A variable that is declared at module level, outside any procedure, is a *member variable* or *field*.</span></span> <span data-ttu-id="ee26c-162">Member variables are in scope throughout their class, structure, or module.</span><span class="sxs-lookup"><span data-stu-id="ee26c-162">Member variables are in scope throughout their class, structure, or module.</span></span> <span data-ttu-id="ee26c-163">A variable that is declared at procedure level is a *local variable*.</span><span class="sxs-lookup"><span data-stu-id="ee26c-163">A variable that is declared at procedure level is a *local variable*.</span></span> <span data-ttu-id="ee26c-164">Local variables are in scope only within their procedure or block.</span><span class="sxs-lookup"><span data-stu-id="ee26c-164">Local variables are in scope only within their procedure or block.</span></span>

<span data-ttu-id="ee26c-165">The following access modifiers are used to declare variables outside a procedure: `Public`, `Protected`, `Friend`, `Protected Friend`, and `Private`.</span><span class="sxs-lookup"><span data-stu-id="ee26c-165">The following access modifiers are used to declare variables outside a procedure: `Public`, `Protected`, `Friend`, `Protected Friend`, and `Private`.</span></span> <span data-ttu-id="ee26c-166">For more information, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="ee26c-166">For more information, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>

<span data-ttu-id="ee26c-167">The `Dim` keyword is optional and usually omitted if you specify any of the following modifiers: `Public`, `Protected`, `Friend`, `Protected Friend`, `Private`, `Shared`, `Shadows`, `Static`, `ReadOnly`, or `WithEvents`.</span><span class="sxs-lookup"><span data-stu-id="ee26c-167">The `Dim` keyword is optional and usually omitted if you specify any of the following modifiers: `Public`, `Protected`, `Friend`, `Protected Friend`, `Private`, `Shared`, `Shadows`, `Static`, `ReadOnly`, or `WithEvents`.</span></span>

```vb
Public maximumAllowed As Double
Protected Friend currentUserName As String
Private salary As Decimal
Static runningTotal As Integer
```

<span data-ttu-id="ee26c-168">If `Option Explicit` is on (the default), the compiler requires a declaration for every variable you use.</span><span class="sxs-lookup"><span data-stu-id="ee26c-168">If `Option Explicit` is on (the default), the compiler requires a declaration for every variable you use.</span></span> <span data-ttu-id="ee26c-169">For more information, see [Option Explicit Statement](../../../visual-basic/language-reference/statements/option-explicit-statement.md).</span><span class="sxs-lookup"><span data-stu-id="ee26c-169">For more information, see [Option Explicit Statement](../../../visual-basic/language-reference/statements/option-explicit-statement.md).</span></span>

## <a name="specifying-an-initial-value"></a><span data-ttu-id="ee26c-170">Specifying an Initial Value</span><span class="sxs-lookup"><span data-stu-id="ee26c-170">Specifying an Initial Value</span></span>

<span data-ttu-id="ee26c-171">You can assign a value to a variable when it is created.</span><span class="sxs-lookup"><span data-stu-id="ee26c-171">You can assign a value to a variable when it is created.</span></span> <span data-ttu-id="ee26c-172">For a value type, you use an *initializer* to supply an expression to be assigned to the variable.</span><span class="sxs-lookup"><span data-stu-id="ee26c-172">For a value type, you use an *initializer* to supply an expression to be assigned to the variable.</span></span> <span data-ttu-id="ee26c-173">The expression must evaluate to a constant that can be calculated at compile time.</span><span class="sxs-lookup"><span data-stu-id="ee26c-173">The expression must evaluate to a constant that can be calculated at compile time.</span></span>

```vb
Dim quantity As Integer = 10
Dim message As String = "Just started"
```

<span data-ttu-id="ee26c-174">If an initializer is specified and a data type is not specified in an `As` clause, *type inference* is used to infer the data type from the initializer.</span><span class="sxs-lookup"><span data-stu-id="ee26c-174">If an initializer is specified and a data type is not specified in an `As` clause, *type inference* is used to infer the data type from the initializer.</span></span> <span data-ttu-id="ee26c-175">In the following example, both `num1` and `num2` are strongly typed as integers.</span><span class="sxs-lookup"><span data-stu-id="ee26c-175">In the following example, both `num1` and `num2` are strongly typed as integers.</span></span> <span data-ttu-id="ee26c-176">In the second declaration, type inference infers the type from the value 3.</span><span class="sxs-lookup"><span data-stu-id="ee26c-176">In the second declaration, type inference infers the type from the value 3.</span></span>

```vb
' Use explicit typing.
Dim num1 As Integer = 3

' Use local type inference.
Dim num2 = 3
```

<span data-ttu-id="ee26c-177">Type inference applies at the procedure level.</span><span class="sxs-lookup"><span data-stu-id="ee26c-177">Type inference applies at the procedure level.</span></span> <span data-ttu-id="ee26c-178">It does not apply outside a procedure in a class, structure, module, or interface.</span><span class="sxs-lookup"><span data-stu-id="ee26c-178">It does not apply outside a procedure in a class, structure, module, or interface.</span></span> <span data-ttu-id="ee26c-179">For more information about type inference, see [Option Infer Statement](../../../visual-basic/language-reference/statements/option-infer-statement.md) and [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span><span class="sxs-lookup"><span data-stu-id="ee26c-179">For more information about type inference, see [Option Infer Statement](../../../visual-basic/language-reference/statements/option-infer-statement.md) and [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span></span>

<span data-ttu-id="ee26c-180">For information about what happens when a data type or initializer is not specified, see [Default Data Types and Values](../../../visual-basic/language-reference/statements/dim-statement.md#default) later in this topic.</span><span class="sxs-lookup"><span data-stu-id="ee26c-180">For information about what happens when a data type or initializer is not specified, see [Default Data Types and Values](../../../visual-basic/language-reference/statements/dim-statement.md#default) later in this topic.</span></span>

<span data-ttu-id="ee26c-181">You can use an *object initializer* to declare instances of named and anonymous types.</span><span class="sxs-lookup"><span data-stu-id="ee26c-181">You can use an *object initializer* to declare instances of named and anonymous types.</span></span> <span data-ttu-id="ee26c-182">The following code creates an instance of a `Student` class and uses an object initializer to initialize properties.</span><span class="sxs-lookup"><span data-stu-id="ee26c-182">The following code creates an instance of a `Student` class and uses an object initializer to initialize properties.</span></span>

```vb
Dim student1 As New Student With {.First = "Michael",
                                  .Last = "Tucker"}
```

<span data-ttu-id="ee26c-183">For more information about object initializers, see [How to: Declare an Object by Using an Object Initializer](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md), [Object Initializers: Named and Anonymous Types](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md), and [Anonymous Types](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="ee26c-183">For more information about object initializers, see [How to: Declare an Object by Using an Object Initializer](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md), [Object Initializers: Named and Anonymous Types](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md), and [Anonymous Types](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span></span>

## <a name="declaring-multiple-variables"></a><span data-ttu-id="ee26c-184">Declaring Multiple Variables</span><span class="sxs-lookup"><span data-stu-id="ee26c-184">Declaring Multiple Variables</span></span>

<span data-ttu-id="ee26c-185">You can declare several variables in one declaration statement, specifying the variable name for each one, and following each array name with parentheses.</span><span class="sxs-lookup"><span data-stu-id="ee26c-185">You can declare several variables in one declaration statement, specifying the variable name for each one, and following each array name with parentheses.</span></span> <span data-ttu-id="ee26c-186">여러 변수는 쉼표로 구분됩니다.</span><span class="sxs-lookup"><span data-stu-id="ee26c-186">Multiple variables are separated by commas.</span></span>

```vb
Dim lastTime, nextTime, allTimes() As Date
```

<span data-ttu-id="ee26c-187">If you declare more than one variable with one `As` clause, you cannot supply an initializer for that group of variables.</span><span class="sxs-lookup"><span data-stu-id="ee26c-187">If you declare more than one variable with one `As` clause, you cannot supply an initializer for that group of variables.</span></span>

<span data-ttu-id="ee26c-188">You can specify different data types for different variables by using a separate `As` clause for each variable you declare.</span><span class="sxs-lookup"><span data-stu-id="ee26c-188">You can specify different data types for different variables by using a separate `As` clause for each variable you declare.</span></span> <span data-ttu-id="ee26c-189">Each variable takes the data type specified in the first `As` clause encountered after its `variablename` part.</span><span class="sxs-lookup"><span data-stu-id="ee26c-189">Each variable takes the data type specified in the first `As` clause encountered after its `variablename` part.</span></span>

```vb
Dim a, b, c As Single, x, y As Double, i As Integer
' a, b, and c are all Single; x and y are both Double
```

## <a name="arrays"></a><span data-ttu-id="ee26c-190">배열</span><span class="sxs-lookup"><span data-stu-id="ee26c-190">Arrays</span></span>

<span data-ttu-id="ee26c-191">You can declare a variable to hold an *array*, which can hold multiple values.</span><span class="sxs-lookup"><span data-stu-id="ee26c-191">You can declare a variable to hold an *array*, which can hold multiple values.</span></span> <span data-ttu-id="ee26c-192">To specify that a variable holds an array, follow its `variablename` immediately with parentheses.</span><span class="sxs-lookup"><span data-stu-id="ee26c-192">To specify that a variable holds an array, follow its `variablename` immediately with parentheses.</span></span> <span data-ttu-id="ee26c-193">배열에 대한 자세한 내용은 [배열](../../../visual-basic/programming-guide/language-features/arrays/index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ee26c-193">For more information about arrays, see [Arrays](../../../visual-basic/programming-guide/language-features/arrays/index.md).</span></span>

<span data-ttu-id="ee26c-194">You can specify the lower and upper bound of each dimension of an array.</span><span class="sxs-lookup"><span data-stu-id="ee26c-194">You can specify the lower and upper bound of each dimension of an array.</span></span> <span data-ttu-id="ee26c-195">To do this, include a `boundslist` inside the parentheses.</span><span class="sxs-lookup"><span data-stu-id="ee26c-195">To do this, include a `boundslist` inside the parentheses.</span></span> <span data-ttu-id="ee26c-196">For each dimension, the `boundslist` specifies the upper bound and optionally the lower bound.</span><span class="sxs-lookup"><span data-stu-id="ee26c-196">For each dimension, the `boundslist` specifies the upper bound and optionally the lower bound.</span></span> <span data-ttu-id="ee26c-197">The lower bound is always zero, whether you specify it or not.</span><span class="sxs-lookup"><span data-stu-id="ee26c-197">The lower bound is always zero, whether you specify it or not.</span></span> <span data-ttu-id="ee26c-198">Each index can vary from zero through its upper bound value.</span><span class="sxs-lookup"><span data-stu-id="ee26c-198">Each index can vary from zero through its upper bound value.</span></span>

<span data-ttu-id="ee26c-199">The following two statements are equivalent.</span><span class="sxs-lookup"><span data-stu-id="ee26c-199">The following two statements are equivalent.</span></span> <span data-ttu-id="ee26c-200">Each statement declares an array of 21 `Integer` elements.</span><span class="sxs-lookup"><span data-stu-id="ee26c-200">Each statement declares an array of 21 `Integer` elements.</span></span> <span data-ttu-id="ee26c-201">When you access the array, the index can vary from 0 through 20.</span><span class="sxs-lookup"><span data-stu-id="ee26c-201">When you access the array, the index can vary from 0 through 20.</span></span>

```vb
Dim totals(20) As Integer
Dim totals(0 To 20) As Integer
```

<span data-ttu-id="ee26c-202">The following statement declares a two-dimensional array of type `Double`.</span><span class="sxs-lookup"><span data-stu-id="ee26c-202">The following statement declares a two-dimensional array of type `Double`.</span></span> <span data-ttu-id="ee26c-203">The array has 4 rows (3 + 1) of 6 columns (5 + 1) each.</span><span class="sxs-lookup"><span data-stu-id="ee26c-203">The array has 4 rows (3 + 1) of 6 columns (5 + 1) each.</span></span> <span data-ttu-id="ee26c-204">Note that an upper bound represents the highest possible value for the index, not the length of the dimension.</span><span class="sxs-lookup"><span data-stu-id="ee26c-204">Note that an upper bound represents the highest possible value for the index, not the length of the dimension.</span></span> <span data-ttu-id="ee26c-205">The length of the dimension is the upper bound plus one.</span><span class="sxs-lookup"><span data-stu-id="ee26c-205">The length of the dimension is the upper bound plus one.</span></span>

```vb
Dim matrix2(3, 5) As Double
```

<span data-ttu-id="ee26c-206">An array can have from 1 to 32 dimensions.</span><span class="sxs-lookup"><span data-stu-id="ee26c-206">An array can have from 1 to 32 dimensions.</span></span>

<span data-ttu-id="ee26c-207">You can leave all the bounds blank in an array declaration.</span><span class="sxs-lookup"><span data-stu-id="ee26c-207">You can leave all the bounds blank in an array declaration.</span></span> <span data-ttu-id="ee26c-208">If you do this, the array has the number of dimensions you specify, but it is uninitialized.</span><span class="sxs-lookup"><span data-stu-id="ee26c-208">If you do this, the array has the number of dimensions you specify, but it is uninitialized.</span></span> <span data-ttu-id="ee26c-209">It has a value of `Nothing` until you initialize at least some of its elements.</span><span class="sxs-lookup"><span data-stu-id="ee26c-209">It has a value of `Nothing` until you initialize at least some of its elements.</span></span> <span data-ttu-id="ee26c-210">The `Dim` statement must specify bounds either for all dimensions or for no dimensions.</span><span class="sxs-lookup"><span data-stu-id="ee26c-210">The `Dim` statement must specify bounds either for all dimensions or for no dimensions.</span></span>

```vb
' Declare an array with blank array bounds.
Dim messages() As String
' Initialize the array.
ReDim messages(4)
```

<span data-ttu-id="ee26c-211">If the array has more than one dimension, you must include commas between the parentheses to indicate the number of dimensions.</span><span class="sxs-lookup"><span data-stu-id="ee26c-211">If the array has more than one dimension, you must include commas between the parentheses to indicate the number of dimensions.</span></span>

```vb
Dim oneDimension(), twoDimensions(,), threeDimensions(,,) As Byte
```

<span data-ttu-id="ee26c-212">You can declare a *zero-length array* by declaring one of the array's dimensions to be -1.</span><span class="sxs-lookup"><span data-stu-id="ee26c-212">You can declare a *zero-length array* by declaring one of the array's dimensions to be -1.</span></span> <span data-ttu-id="ee26c-213">A variable that holds a zero-length array does not have the value `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="ee26c-213">A variable that holds a zero-length array does not have the value `Nothing`.</span></span> <span data-ttu-id="ee26c-214">Zero-length arrays are required by certain common language runtime functions.</span><span class="sxs-lookup"><span data-stu-id="ee26c-214">Zero-length arrays are required by certain common language runtime functions.</span></span> <span data-ttu-id="ee26c-215">If you try to access such an array, a runtime exception occurs.</span><span class="sxs-lookup"><span data-stu-id="ee26c-215">If you try to access such an array, a runtime exception occurs.</span></span> <span data-ttu-id="ee26c-216">자세한 내용은 [배열](../../../visual-basic/programming-guide/language-features/arrays/index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ee26c-216">For more information, see [Arrays](../../../visual-basic/programming-guide/language-features/arrays/index.md).</span></span>

<span data-ttu-id="ee26c-217">You can initialize the values of an array by using an array literal.</span><span class="sxs-lookup"><span data-stu-id="ee26c-217">You can initialize the values of an array by using an array literal.</span></span> <span data-ttu-id="ee26c-218">To do this, surround the initialization values with braces (`{}`).</span><span class="sxs-lookup"><span data-stu-id="ee26c-218">To do this, surround the initialization values with braces (`{}`).</span></span>

```vb
Dim longArray() As Long = {0, 1, 2, 3}
```

<span data-ttu-id="ee26c-219">For multidimensional arrays, the initialization for each separate dimension is enclosed in braces in the outer dimension.</span><span class="sxs-lookup"><span data-stu-id="ee26c-219">For multidimensional arrays, the initialization for each separate dimension is enclosed in braces in the outer dimension.</span></span> <span data-ttu-id="ee26c-220">The elements are specified in row-major order.</span><span class="sxs-lookup"><span data-stu-id="ee26c-220">The elements are specified in row-major order.</span></span>

```vb
Dim twoDimensions(,) As Integer = {{0, 1, 2}, {10, 11, 12}}
```

<span data-ttu-id="ee26c-221">For more information about array literals, see [Arrays](../../../visual-basic/programming-guide/language-features/arrays/index.md).</span><span class="sxs-lookup"><span data-stu-id="ee26c-221">For more information about array literals, see [Arrays](../../../visual-basic/programming-guide/language-features/arrays/index.md).</span></span>

## <a name="default"></a> <span data-ttu-id="ee26c-222">Default Data Types and Values</span><span class="sxs-lookup"><span data-stu-id="ee26c-222">Default Data Types and Values</span></span>

<span data-ttu-id="ee26c-223">다음 테이블에는 `Dim` 문에서 데이터 형식과 이니셜라이저를 지정하는 다양한 조합의 결과에 대한 설명이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee26c-223">The following table describes the results of various combinations of specifying the data type and initializer in a `Dim` statement.</span></span>

|<span data-ttu-id="ee26c-224">데이터 형식 지정 여부</span><span class="sxs-lookup"><span data-stu-id="ee26c-224">Data type specified?</span></span>|<span data-ttu-id="ee26c-225">이니셜라이저 지정 여부</span><span class="sxs-lookup"><span data-stu-id="ee26c-225">Initializer specified?</span></span>|<span data-ttu-id="ee26c-226">예제</span><span class="sxs-lookup"><span data-stu-id="ee26c-226">Example</span></span>|<span data-ttu-id="ee26c-227">결과</span><span class="sxs-lookup"><span data-stu-id="ee26c-227">Result</span></span>|
|---|---|---|---|
|<span data-ttu-id="ee26c-228">아니요</span><span class="sxs-lookup"><span data-stu-id="ee26c-228">No</span></span>|<span data-ttu-id="ee26c-229">아니요</span><span class="sxs-lookup"><span data-stu-id="ee26c-229">No</span></span>|`Dim qty`|<span data-ttu-id="ee26c-230">If [Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md) is off (the default), the variable is set to `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="ee26c-230">If [Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md) is off (the default), the variable is set to `Nothing`.</span></span><br /><br /> <span data-ttu-id="ee26c-231">`Option Strict`가 on이면 컴파일 시간 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="ee26c-231">If `Option Strict` is on, a compile-time error occurs.</span></span>|
|<span data-ttu-id="ee26c-232">아니요</span><span class="sxs-lookup"><span data-stu-id="ee26c-232">No</span></span>|<span data-ttu-id="ee26c-233">예</span><span class="sxs-lookup"><span data-stu-id="ee26c-233">Yes</span></span>|`Dim qty = 5`|<span data-ttu-id="ee26c-234">If [Option Infer](../../../visual-basic/language-reference/statements/option-infer-statement.md) is on (the default), the variable takes the data type of the initializer.</span><span class="sxs-lookup"><span data-stu-id="ee26c-234">If [Option Infer](../../../visual-basic/language-reference/statements/option-infer-statement.md) is on (the default), the variable takes the data type of the initializer.</span></span> <span data-ttu-id="ee26c-235">See [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span><span class="sxs-lookup"><span data-stu-id="ee26c-235">See [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span></span><br /><br /> <span data-ttu-id="ee26c-236">`Option Infer`가 off이고 `Option Strict`고 off이면 변수가 `Object`의 데이터 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ee26c-236">If `Option Infer` is off and `Option Strict` is off, the variable takes the data type of `Object`.</span></span><br /><br /> <span data-ttu-id="ee26c-237">`Option Infer`가 off이고 `Option Strict`는 on이면 컴파일 시간 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="ee26c-237">If `Option Infer` is off and `Option Strict` is on, a compile-time error occurs.</span></span>|
|<span data-ttu-id="ee26c-238">예</span><span class="sxs-lookup"><span data-stu-id="ee26c-238">Yes</span></span>|<span data-ttu-id="ee26c-239">아니요</span><span class="sxs-lookup"><span data-stu-id="ee26c-239">No</span></span>|`Dim qty As Integer`|<span data-ttu-id="ee26c-240">변수는 데이터 형식의 기본값으로 초기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="ee26c-240">The variable is initialized to the default value for the data type.</span></span> <span data-ttu-id="ee26c-241">See the table later in this section.</span><span class="sxs-lookup"><span data-stu-id="ee26c-241">See the table later in this section.</span></span>|
|<span data-ttu-id="ee26c-242">예</span><span class="sxs-lookup"><span data-stu-id="ee26c-242">Yes</span></span>|<span data-ttu-id="ee26c-243">예</span><span class="sxs-lookup"><span data-stu-id="ee26c-243">Yes</span></span>|`Dim qty  As Integer = 5`|<span data-ttu-id="ee26c-244">이니셜라이저의 데이터 형식을 지정한 데이터 형식으로 변환할 수 없으면 컴파일 시간 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="ee26c-244">If the data type of the initializer is not convertible to the specified data type, a compile-time error occurs.</span></span>|

<span data-ttu-id="ee26c-245">If you specify a data type but do not specify an initializer, Visual Basic initializes the variable to the default value for its data type.</span><span class="sxs-lookup"><span data-stu-id="ee26c-245">If you specify a data type but do not specify an initializer, Visual Basic initializes the variable to the default value for its data type.</span></span> <span data-ttu-id="ee26c-246">The following table shows the default initialization values.</span><span class="sxs-lookup"><span data-stu-id="ee26c-246">The following table shows the default initialization values.</span></span>

|<span data-ttu-id="ee26c-247">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="ee26c-247">Data type</span></span>|<span data-ttu-id="ee26c-248">기본값</span><span class="sxs-lookup"><span data-stu-id="ee26c-248">Default value</span></span>|
|---|---|
|<span data-ttu-id="ee26c-249">All numeric types (including `Byte` and `SByte`)</span><span class="sxs-lookup"><span data-stu-id="ee26c-249">All numeric types (including `Byte` and `SByte`)</span></span>|<span data-ttu-id="ee26c-250">0</span><span class="sxs-lookup"><span data-stu-id="ee26c-250">0</span></span>|
|`Char`|<span data-ttu-id="ee26c-251">Binary 0</span><span class="sxs-lookup"><span data-stu-id="ee26c-251">Binary 0</span></span>|
|<span data-ttu-id="ee26c-252">All reference types (including `Object`, `String`, and all arrays)</span><span class="sxs-lookup"><span data-stu-id="ee26c-252">All reference types (including `Object`, `String`, and all arrays)</span></span>|`Nothing`|
|`Boolean`|`False`|
|`Date`|<span data-ttu-id="ee26c-253">12:00 AM of January 1 of the year 1 (01/01/0001 12:00:00 AM)</span><span class="sxs-lookup"><span data-stu-id="ee26c-253">12:00 AM of January 1 of the year 1 (01/01/0001 12:00:00 AM)</span></span>|

<span data-ttu-id="ee26c-254">Each element of a structure is initialized as if it were a separate variable.</span><span class="sxs-lookup"><span data-stu-id="ee26c-254">Each element of a structure is initialized as if it were a separate variable.</span></span> <span data-ttu-id="ee26c-255">If you declare the length of an array but do not initialize its elements, each element is initialized as if it were a separate variable.</span><span class="sxs-lookup"><span data-stu-id="ee26c-255">If you declare the length of an array but do not initialize its elements, each element is initialized as if it were a separate variable.</span></span>

## <a name="static-local-variable-lifetime"></a><span data-ttu-id="ee26c-256">Static Local Variable Lifetime</span><span class="sxs-lookup"><span data-stu-id="ee26c-256">Static Local Variable Lifetime</span></span>

<span data-ttu-id="ee26c-257">A `Static` local variable has a longer lifetime than that of the procedure in which it is declared.</span><span class="sxs-lookup"><span data-stu-id="ee26c-257">A `Static` local variable has a longer lifetime than that of the procedure in which it is declared.</span></span> <span data-ttu-id="ee26c-258">The boundaries of the variable's lifetime depend on where the procedure is declared and whether it is `Shared`.</span><span class="sxs-lookup"><span data-stu-id="ee26c-258">The boundaries of the variable's lifetime depend on where the procedure is declared and whether it is `Shared`.</span></span>

|<span data-ttu-id="ee26c-259">Procedure declaration</span><span class="sxs-lookup"><span data-stu-id="ee26c-259">Procedure declaration</span></span>|<span data-ttu-id="ee26c-260">Variable initialized</span><span class="sxs-lookup"><span data-stu-id="ee26c-260">Variable initialized</span></span>|<span data-ttu-id="ee26c-261">Variable stops existing</span><span class="sxs-lookup"><span data-stu-id="ee26c-261">Variable stops existing</span></span>|
|---|---|---|
|<span data-ttu-id="ee26c-262">In a module</span><span class="sxs-lookup"><span data-stu-id="ee26c-262">In a module</span></span>|<span data-ttu-id="ee26c-263">The first time the procedure is called</span><span class="sxs-lookup"><span data-stu-id="ee26c-263">The first time the procedure is called</span></span>|<span data-ttu-id="ee26c-264">When your program stops execution</span><span class="sxs-lookup"><span data-stu-id="ee26c-264">When your program stops execution</span></span>|
|<span data-ttu-id="ee26c-265">In a class or structure, procedure is `Shared`</span><span class="sxs-lookup"><span data-stu-id="ee26c-265">In a class or structure, procedure is `Shared`</span></span>|<span data-ttu-id="ee26c-266">The first time the procedure is called either on a specific instance or on the class or structure itself</span><span class="sxs-lookup"><span data-stu-id="ee26c-266">The first time the procedure is called either on a specific instance or on the class or structure itself</span></span>|<span data-ttu-id="ee26c-267">When your program stops execution</span><span class="sxs-lookup"><span data-stu-id="ee26c-267">When your program stops execution</span></span>|
|<span data-ttu-id="ee26c-268">In a class or structure, procedure isn't `Shared`</span><span class="sxs-lookup"><span data-stu-id="ee26c-268">In a class or structure, procedure isn't `Shared`</span></span>|<span data-ttu-id="ee26c-269">The first time the procedure is called on a specific instance</span><span class="sxs-lookup"><span data-stu-id="ee26c-269">The first time the procedure is called on a specific instance</span></span>|<span data-ttu-id="ee26c-270">When the instance is released for garbage collection (GC)</span><span class="sxs-lookup"><span data-stu-id="ee26c-270">When the instance is released for garbage collection (GC)</span></span>|

## <a name="attributes-and-modifiers"></a><span data-ttu-id="ee26c-271">Attributes and Modifiers</span><span class="sxs-lookup"><span data-stu-id="ee26c-271">Attributes and Modifiers</span></span>

<span data-ttu-id="ee26c-272">You can apply attributes only to member variables, not to local variables.</span><span class="sxs-lookup"><span data-stu-id="ee26c-272">You can apply attributes only to member variables, not to local variables.</span></span> <span data-ttu-id="ee26c-273">An attribute contributes information to the assembly's metadata, which is not meaningful for temporary storage such as local variables.</span><span class="sxs-lookup"><span data-stu-id="ee26c-273">An attribute contributes information to the assembly's metadata, which is not meaningful for temporary storage such as local variables.</span></span>

<span data-ttu-id="ee26c-274">At module level, you cannot use the `Static` modifier to declare member variables.</span><span class="sxs-lookup"><span data-stu-id="ee26c-274">At module level, you cannot use the `Static` modifier to declare member variables.</span></span> <span data-ttu-id="ee26c-275">At procedure level, you cannot use `Shared`, `Shadows`, `ReadOnly`, `WithEvents`, or any access modifiers to declare local variables.</span><span class="sxs-lookup"><span data-stu-id="ee26c-275">At procedure level, you cannot use `Shared`, `Shadows`, `ReadOnly`, `WithEvents`, or any access modifiers to declare local variables.</span></span>

<span data-ttu-id="ee26c-276">You can specify what code can access a variable by supplying an `accessmodifier`.</span><span class="sxs-lookup"><span data-stu-id="ee26c-276">You can specify what code can access a variable by supplying an `accessmodifier`.</span></span> <span data-ttu-id="ee26c-277">Class and module member variables (outside any procedure) default to private access, and structure member variables default to public access.</span><span class="sxs-lookup"><span data-stu-id="ee26c-277">Class and module member variables (outside any procedure) default to private access, and structure member variables default to public access.</span></span> <span data-ttu-id="ee26c-278">You can adjust their access levels with the access modifiers.</span><span class="sxs-lookup"><span data-stu-id="ee26c-278">You can adjust their access levels with the access modifiers.</span></span> <span data-ttu-id="ee26c-279">You cannot use access modifiers on local variables (inside a procedure).</span><span class="sxs-lookup"><span data-stu-id="ee26c-279">You cannot use access modifiers on local variables (inside a procedure).</span></span>

<span data-ttu-id="ee26c-280">You can specify `WithEvents` only on member variables, not on local variables inside a procedure.</span><span class="sxs-lookup"><span data-stu-id="ee26c-280">You can specify `WithEvents` only on member variables, not on local variables inside a procedure.</span></span> <span data-ttu-id="ee26c-281">If you specify `WithEvents`, the data type of the variable must be a specific class type, not `Object`.</span><span class="sxs-lookup"><span data-stu-id="ee26c-281">If you specify `WithEvents`, the data type of the variable must be a specific class type, not `Object`.</span></span> <span data-ttu-id="ee26c-282">You cannot declare an array with `WithEvents`.</span><span class="sxs-lookup"><span data-stu-id="ee26c-282">You cannot declare an array with `WithEvents`.</span></span> <span data-ttu-id="ee26c-283">For more information about events, see [Events](../../../visual-basic/programming-guide/language-features/events/index.md).</span><span class="sxs-lookup"><span data-stu-id="ee26c-283">For more information about events, see [Events](../../../visual-basic/programming-guide/language-features/events/index.md).</span></span>

> [!NOTE]
> <span data-ttu-id="ee26c-284">Code outside a class, structure, or module must qualify a member variable's name with the name of that class, structure, or module.</span><span class="sxs-lookup"><span data-stu-id="ee26c-284">Code outside a class, structure, or module must qualify a member variable's name with the name of that class, structure, or module.</span></span> <span data-ttu-id="ee26c-285">Code outside a procedure or block cannot refer to any local variables within that procedure or block.</span><span class="sxs-lookup"><span data-stu-id="ee26c-285">Code outside a procedure or block cannot refer to any local variables within that procedure or block.</span></span>

## <a name="releasing-managed-resources"></a><span data-ttu-id="ee26c-286">Releasing Managed Resources</span><span class="sxs-lookup"><span data-stu-id="ee26c-286">Releasing Managed Resources</span></span>

<span data-ttu-id="ee26c-287">The .NET Framework garbage collector disposes of managed resources without any extra coding on your part.</span><span class="sxs-lookup"><span data-stu-id="ee26c-287">The .NET Framework garbage collector disposes of managed resources without any extra coding on your part.</span></span> <span data-ttu-id="ee26c-288">However, you can force the disposal of a managed resource instead of waiting for the garbage collector.</span><span class="sxs-lookup"><span data-stu-id="ee26c-288">However, you can force the disposal of a managed resource instead of waiting for the garbage collector.</span></span>

<span data-ttu-id="ee26c-289">If a class holds onto a particularly valuable and scarce resource (such as a database connection or file handle), you might not want to wait until the next garbage collection to clean up a class instance that's no longer in use.</span><span class="sxs-lookup"><span data-stu-id="ee26c-289">If a class holds onto a particularly valuable and scarce resource (such as a database connection or file handle), you might not want to wait until the next garbage collection to clean up a class instance that's no longer in use.</span></span> <span data-ttu-id="ee26c-290">A class may implement the <xref:System.IDisposable> interface to provide a way to release resources before a garbage collection.</span><span class="sxs-lookup"><span data-stu-id="ee26c-290">A class may implement the <xref:System.IDisposable> interface to provide a way to release resources before a garbage collection.</span></span> <span data-ttu-id="ee26c-291">A class that implements that interface exposes a `Dispose` method that can be called to force valuable resources to be released immediately.</span><span class="sxs-lookup"><span data-stu-id="ee26c-291">A class that implements that interface exposes a `Dispose` method that can be called to force valuable resources to be released immediately.</span></span>

<span data-ttu-id="ee26c-292">The `Using` statement automates the process of acquiring a resource, executing a set of statements, and then disposing of the resource.</span><span class="sxs-lookup"><span data-stu-id="ee26c-292">The `Using` statement automates the process of acquiring a resource, executing a set of statements, and then disposing of the resource.</span></span> <span data-ttu-id="ee26c-293">However, the resource must implement the <xref:System.IDisposable> interface.</span><span class="sxs-lookup"><span data-stu-id="ee26c-293">However, the resource must implement the <xref:System.IDisposable> interface.</span></span> <span data-ttu-id="ee26c-294">자세한 내용은 [using 문](../../../visual-basic/language-reference/statements/using-statement.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ee26c-294">For more information, see [Using Statement](../../../visual-basic/language-reference/statements/using-statement.md).</span></span>

## <a name="example"></a><span data-ttu-id="ee26c-295">예제</span><span class="sxs-lookup"><span data-stu-id="ee26c-295">Example</span></span>

<span data-ttu-id="ee26c-296">The following example declares variables by using the `Dim` statement with various options.</span><span class="sxs-lookup"><span data-stu-id="ee26c-296">The following example declares variables by using the `Dim` statement with various options.</span></span>

[!code-vb[VbVbalrStatements#141](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class11.vb#141)]

## <a name="example"></a><span data-ttu-id="ee26c-297">예제</span><span class="sxs-lookup"><span data-stu-id="ee26c-297">Example</span></span>

<span data-ttu-id="ee26c-298">The following example lists the prime numbers between 1 and 30.</span><span class="sxs-lookup"><span data-stu-id="ee26c-298">The following example lists the prime numbers between 1 and 30.</span></span> <span data-ttu-id="ee26c-299">The scope of local variables is described in code comments.</span><span class="sxs-lookup"><span data-stu-id="ee26c-299">The scope of local variables is described in code comments.</span></span>

[!code-vb[VbVbalrStatements#142](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class11.vb#142)]

## <a name="example"></a><span data-ttu-id="ee26c-300">예제</span><span class="sxs-lookup"><span data-stu-id="ee26c-300">Example</span></span>

<span data-ttu-id="ee26c-301">In the following example, the `speedValue` variable is declared at the class level.</span><span class="sxs-lookup"><span data-stu-id="ee26c-301">In the following example, the `speedValue` variable is declared at the class level.</span></span> <span data-ttu-id="ee26c-302">The `Private` keyword is used to declare the variable.</span><span class="sxs-lookup"><span data-stu-id="ee26c-302">The `Private` keyword is used to declare the variable.</span></span> <span data-ttu-id="ee26c-303">The variable can be accessed by any procedure in the `Car` class.</span><span class="sxs-lookup"><span data-stu-id="ee26c-303">The variable can be accessed by any procedure in the `Car` class.</span></span>

[!code-vb[VbVbalrStatements#144](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class11.vb#144)]

[!code-vb[VbVbalrStatements#145](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class11.vb#145)]

## <a name="see-also"></a><span data-ttu-id="ee26c-304">참조</span><span class="sxs-lookup"><span data-stu-id="ee26c-304">See also</span></span>

- [<span data-ttu-id="ee26c-305">Const 문</span><span class="sxs-lookup"><span data-stu-id="ee26c-305">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)
- [<span data-ttu-id="ee26c-306">ReDim 문</span><span class="sxs-lookup"><span data-stu-id="ee26c-306">ReDim Statement</span></span>](../../../visual-basic/language-reference/statements/redim-statement.md)
- [<span data-ttu-id="ee26c-307">Option Explicit 문</span><span class="sxs-lookup"><span data-stu-id="ee26c-307">Option Explicit Statement</span></span>](../../../visual-basic/language-reference/statements/option-explicit-statement.md)
- [<span data-ttu-id="ee26c-308">Option Infer 문</span><span class="sxs-lookup"><span data-stu-id="ee26c-308">Option Infer Statement</span></span>](../../../visual-basic/language-reference/statements/option-infer-statement.md)
- [<span data-ttu-id="ee26c-309">Option Strict 문</span><span class="sxs-lookup"><span data-stu-id="ee26c-309">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [<span data-ttu-id="ee26c-310">프로젝트 디자이너, 컴파일 페이지(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ee26c-310">Compile Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)
- [<span data-ttu-id="ee26c-311">변수 선언</span><span class="sxs-lookup"><span data-stu-id="ee26c-311">Variable Declaration</span></span>](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [<span data-ttu-id="ee26c-312">배열</span><span class="sxs-lookup"><span data-stu-id="ee26c-312">Arrays</span></span>](../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [<span data-ttu-id="ee26c-313">개체 이니셜라이저: 명명된 형식과 익명 형식</span><span class="sxs-lookup"><span data-stu-id="ee26c-313">Object Initializers: Named and Anonymous Types</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [<span data-ttu-id="ee26c-314">익명 형식</span><span class="sxs-lookup"><span data-stu-id="ee26c-314">Anonymous Types</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
- [<span data-ttu-id="ee26c-315">개체 이니셜라이저: 명명된 형식과 익명 형식</span><span class="sxs-lookup"><span data-stu-id="ee26c-315">Object Initializers: Named and Anonymous Types</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [<span data-ttu-id="ee26c-316">방법: 개체 이니셜라이저를 사용하여 개체 선언</span><span class="sxs-lookup"><span data-stu-id="ee26c-316">How to: Declare an Object by Using an Object Initializer</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md)
- [<span data-ttu-id="ee26c-317">지역 형식 유추</span><span class="sxs-lookup"><span data-stu-id="ee26c-317">Local Type Inference</span></span>](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
