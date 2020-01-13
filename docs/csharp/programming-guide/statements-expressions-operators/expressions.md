---
title: 식 - C# 프로그래밍 가이드
ms.date: 05/11/2017
helpviewer_keywords:
- expressions [C#]
- C# language, expressions
ms.assetid: c7d8feb0-0e58-4f94-8bf6-4d070550a832
ms.openlocfilehash: 4bbee8f15c2591e8b172df9a6759449d48697804
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2020
ms.locfileid: "75699095"
---
# <a name="expressions-c-programming-guide"></a><span data-ttu-id="7d3c2-102">식(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="7d3c2-102">Expressions (C# Programming Guide)</span></span>

<span data-ttu-id="7d3c2-103">‘식’은 단일 값, 개체, 메서드 또는 네임스페이스로 평가될 수 있는 하나 이상의 피연산자 및 0개 이상의 [연산자](../../language-reference/operators/index.md) 시퀀스입니다. </span><span class="sxs-lookup"><span data-stu-id="7d3c2-103">An *expression* is a sequence of one or more operands and zero or more [operators](../../language-reference/operators/index.md) that can be evaluated to a single value, object, method, or namespace.</span></span> <span data-ttu-id="7d3c2-104">식은 리터럴 값, 메서드 호출, 연산자 및 피연산자, *단순 이름* 등으로 구성될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d3c2-104">Expressions can consist of a literal value, a method invocation, an operator and its operands, or a *simple name*.</span></span> <span data-ttu-id="7d3c2-105">단순한 이름이란 변수, 형식 멤버, 메서드 매개 변수, 네임스페이스 또는 형식의 이름일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d3c2-105">Simple names can be the name of a variable, type member, method parameter, namespace or type.</span></span>  
  
 <span data-ttu-id="7d3c2-106">식은 다른 식을 매개 변수로 사용하는 연산자 또는 다른 메서드 호출을 매개 변수로 가지는 메서드 호출을 사용할 수 있으므로 간단한 식부터 복잡한 식까지 다양할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d3c2-106">Expressions can use operators that in turn use other expressions as parameters, or method calls whose parameters are in turn other method calls, so expressions can range from simple to very complex.</span></span> <span data-ttu-id="7d3c2-107">다음은 식의 두 가지 예입니다.</span><span class="sxs-lookup"><span data-stu-id="7d3c2-107">Following are two examples of expressions:</span></span>  
  
```csharp  
((x < 10) && ( x > 5)) || ((x > 20) && (x < 25));

System.Convert.ToInt32("35");  
```  
  
## <a name="expression-values"></a><span data-ttu-id="7d3c2-108">식 값</span><span class="sxs-lookup"><span data-stu-id="7d3c2-108">Expression values</span></span>

 <span data-ttu-id="7d3c2-109">식이 사용되는 대부분의 컨텍스트(예: 문 또는 메서드 매개 변수)에서 식은 특정 값으로 평가되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d3c2-109">In most of the contexts in which expressions are used, for example in statements or method parameters, the expression is expected to evaluate to some value.</span></span> <span data-ttu-id="7d3c2-110">x와 y가 정수이면 `x + y` 식은 숫자 값으로 평가됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d3c2-110">If x and y are integers, the expression `x + y` evaluates to a numeric value.</span></span> <span data-ttu-id="7d3c2-111">`new MyClass()` 식은 `MyClass` 클래스의 새 인스턴스에 대한 참조로 평가됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d3c2-111">The expression `new MyClass()` evaluates to a reference to a new instance of a `MyClass` class.</span></span> <span data-ttu-id="7d3c2-112">`myClass.ToString()` 식은 메서드의 반환 형식인 문자열로 평가됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d3c2-112">The expression `myClass.ToString()` evaluates to a string because that is the return type of the method.</span></span> <span data-ttu-id="7d3c2-113">그러나 네임스페이스 이름은 식으로 분류되지만 값으로 평가되지 않으므로 식의 최종 결과가 될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7d3c2-113">However, although a namespace name is classified as an expression, it does not evaluate to a value and therefore can never be the final result of any expression.</span></span> <span data-ttu-id="7d3c2-114">네임스페이스 이름을 메서드 매개 변수에 전달할 수 없거나, 새 식에 사용하거나 변수에 할당할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7d3c2-114">You cannot pass a namespace name to a method parameter, or use it in a new expression, or assign it to a variable.</span></span> <span data-ttu-id="7d3c2-115">더 큰 식의 하위 식으로만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d3c2-115">You can only use it as a sub-expression in a larger expression.</span></span> <span data-ttu-id="7d3c2-116">형식(<xref:System.Type?displayProperty=nameWithType> 개체와 다름), 메서드 그룹 이름(특정 메서드와 다름), 이벤트 [add](../../language-reference/keywords/add.md) 및 [remove](../../language-reference/keywords/remove.md) 접근자의 경우도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="7d3c2-116">The same is true for types (as distinct from <xref:System.Type?displayProperty=nameWithType> objects), method group names (as distinct from specific methods), and event [add](../../language-reference/keywords/add.md) and [remove](../../language-reference/keywords/remove.md) accessors.</span></span>  
  
 <span data-ttu-id="7d3c2-117">모든 값에는 연결된 형식이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d3c2-117">Every value has an associated type.</span></span> <span data-ttu-id="7d3c2-118">예를 들어 x와 y가 둘 다 `int` 형식의 변수이면 `x + y` 식의 값도 `int`로 형식화됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d3c2-118">For example, if x and y are both variables of type `int`, the value of the expression `x + y` is also typed as `int`.</span></span> <span data-ttu-id="7d3c2-119">다른 형식의 변수에 값이 할당된 경우 또는 x와 y가 서로 다른 형식인 경우 형식 변환 규칙이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d3c2-119">If the value is assigned to a variable of a different type, or if x and y are different types, the rules of type conversion are applied.</span></span> <span data-ttu-id="7d3c2-120">이러한 변환이 작동하는 방식에 대한 자세한 내용은 [캐스팅 및 형식 변환](../types/casting-and-type-conversions.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7d3c2-120">For more information about how such conversions work, see [Casting and Type Conversions](../types/casting-and-type-conversions.md).</span></span>  
  
## <a name="overflows"></a><span data-ttu-id="7d3c2-121">오버플로</span><span class="sxs-lookup"><span data-stu-id="7d3c2-121">Overflows</span></span>

 <span data-ttu-id="7d3c2-122">값이 값 형식의 최대값보다 클 경우 숫자 식에서 오버플로가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d3c2-122">Numeric expressions may cause overflows if the value is larger than the maximum value of the value's type.</span></span> <span data-ttu-id="7d3c2-123">자세한 내용은 [기본 제공 숫자 변환](../../language-reference/builtin-types/numeric-conversions.md) 문서의 [명시적 숫자 변환](../../language-reference/builtin-types/numeric-conversions.md#explicit-numeric-conversions) 섹션과 [Checked 및 Unchecked](../../language-reference/keywords/checked-and-unchecked.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7d3c2-123">For more information, see [Checked and Unchecked](../../language-reference/keywords/checked-and-unchecked.md) and the [Explicit numeric conversions](../../language-reference/builtin-types/numeric-conversions.md#explicit-numeric-conversions) section of the [Built-in numeric conversions](../../language-reference/builtin-types/numeric-conversions.md) article.</span></span>
  
## <a name="operator-precedence-and-associativity"></a><span data-ttu-id="7d3c2-124">연산자 우선 순위 및 결합성</span><span class="sxs-lookup"><span data-stu-id="7d3c2-124">Operator precedence and associativity</span></span>

 <span data-ttu-id="7d3c2-125">식이 평가되는 방식은 결합성 및 연산자 우선 순위 규칙에 의해 제어됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d3c2-125">The manner in which an expression is evaluated is governed by the rules of associativity and operator precedence.</span></span> <span data-ttu-id="7d3c2-126">자세한 내용은 [연산자](../../language-reference/operators/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7d3c2-126">For more information, see [Operators](../../language-reference/operators/index.md).</span></span>  
  
 <span data-ttu-id="7d3c2-127">할당 식 및 메서드 호출을 제외한 대부분의 식은 문에 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d3c2-127">Most expressions, except assignment expressions and method invocation expressions, must be embedded in a statement.</span></span> <span data-ttu-id="7d3c2-128">자세한 내용은 [문](./statements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7d3c2-128">For more information, see [Statements](./statements.md).</span></span>  
  
## <a name="literals-and-simple-names"></a><span data-ttu-id="7d3c2-129">리터럴 및 단순 이름</span><span class="sxs-lookup"><span data-stu-id="7d3c2-129">Literals and simple names</span></span>

 <span data-ttu-id="7d3c2-130">가장 간단한 두 가지 형식의 식은 리터럴과 단순 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="7d3c2-130">The two simplest types of expressions are literals and simple names.</span></span> <span data-ttu-id="7d3c2-131">리터럴은 이름이 없는 상수 값입니다.</span><span class="sxs-lookup"><span data-stu-id="7d3c2-131">A literal is a constant value that has no name.</span></span> <span data-ttu-id="7d3c2-132">예를 들어 다음 코드 예제에서 `5` 및 `"Hello World"`는 둘 다 리터럴 값입니다.</span><span class="sxs-lookup"><span data-stu-id="7d3c2-132">For example, in the following code example, both `5` and `"Hello World"` are literal values:</span></span>  
  
 [!code-csharp[csProgGuideStatements#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#2)]  
  
 <span data-ttu-id="7d3c2-133">리터럴에 대한 자세한 내용은 [형식](/dotnet/csharp/language-reference/keywords)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7d3c2-133">For more information on literals, see [Types](/dotnet/csharp/language-reference/keywords).</span></span>  
  
 <span data-ttu-id="7d3c2-134">앞의 예제에서 `i` 및 `s`는 둘 다 지역 변수를 식별하는 단순 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="7d3c2-134">In the preceding example, both `i` and `s` are simple names that identify local variables.</span></span> <span data-ttu-id="7d3c2-135">이러한 변수가 식에 사용되는 경우 변수 이름은 현재 메모리의 변수 위치에 저장된 값으로 평가됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d3c2-135">When those variables are used in an expression, the variable name evaluates to the value that is currently stored in the variable's location in memory.</span></span> <span data-ttu-id="7d3c2-136">이는 다음 예제에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d3c2-136">This is shown in the following example:</span></span>  
  
 [!code-csharp[csProgGuideStatements#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#3)]

## <a name="invocation-expressions"></a><span data-ttu-id="7d3c2-137">호출 식</span><span class="sxs-lookup"><span data-stu-id="7d3c2-137">Invocation expressions</span></span>

 <span data-ttu-id="7d3c2-138">다음 코드 예제에서 `DoWork` 호출은 호출 식입니다.</span><span class="sxs-lookup"><span data-stu-id="7d3c2-138">In the following code example, the call to `DoWork` is an invocation expression.</span></span>  
  
```csharp
DoWork();  
```  
  
 <span data-ttu-id="7d3c2-139">메서드 호출 시 이름(앞의 예제 참조) 또는 다른 식의 결과와 뒤에 나오는 괄호 및 메서드 매개 변수인 메서드 이름이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="7d3c2-139">A method invocation requires the name of the method, either as a name as in the previous example, or as the result of another expression, followed by parenthesis and any method parameters.</span></span> <span data-ttu-id="7d3c2-140">자세한 내용은 [메서드](../classes-and-structs/methods.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7d3c2-140">For more information, see [Methods](../classes-and-structs/methods.md).</span></span> <span data-ttu-id="7d3c2-141">대리자 호출은 괄호 안에 대리자 이름 및 메서드 매개 변수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7d3c2-141">A delegate invocation uses the name of a delegate and method parameters in parenthesis.</span></span> <span data-ttu-id="7d3c2-142">자세한 내용은 [대리자](../delegates/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7d3c2-142">For more information, see [Delegates](../delegates/index.md).</span></span> <span data-ttu-id="7d3c2-143">메서드가 값을 반환하는 경우 메서드 호출 및 대리자 호출은 메서드의 반환 값으로 평가됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d3c2-143">Method invocations and delegate invocations evaluate to the return value of the method, if the method returns a value.</span></span> <span data-ttu-id="7d3c2-144">void를 반환하는 메서드를 식에 값 대신 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7d3c2-144">Methods that return void cannot be used in place of a value in an expression.</span></span>  

## <a name="query-expressions"></a><span data-ttu-id="7d3c2-145">쿼리 식</span><span class="sxs-lookup"><span data-stu-id="7d3c2-145">Query expressions</span></span>

 <span data-ttu-id="7d3c2-146">쿼리 식에는 일반적인 식과 동일한 규칙이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d3c2-146">The same rules for expressions in general apply to query expressions.</span></span> <span data-ttu-id="7d3c2-147">자세한 내용은 [LINQ](../../linq/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7d3c2-147">For more information, see [LINQ](../../linq/index.md).</span></span>  
  
## <a name="lambda-expressions"></a><span data-ttu-id="7d3c2-148">람다 식</span><span class="sxs-lookup"><span data-stu-id="7d3c2-148">Lambda expressions</span></span>

 <span data-ttu-id="7d3c2-149">람다 식은 이름이 없지만 입력 매개 변수와 여러 개의 문을 사용할 수 있는 "인라인 메서드"를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7d3c2-149">Lambda expressions represent "inline methods" that have no name but can have input parameters and multiple statements.</span></span> <span data-ttu-id="7d3c2-150">메서드에 인수를 전달하기 위해 LINQ에서 광범위하게 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d3c2-150">They are used extensively in LINQ to pass arguments to methods.</span></span> <span data-ttu-id="7d3c2-151">람다 식은 사용되는 컨텍스트에 따라 대리자 또는 식 트리로 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d3c2-151">Lambda expressions are compiled to either delegates or expression trees depending on the context in which they are used.</span></span> <span data-ttu-id="7d3c2-152">자세한 내용은 [람다 식](lambda-expressions.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7d3c2-152">For more information, see [Lambda Expressions](lambda-expressions.md).</span></span>  
  
## <a name="expression-trees"></a><span data-ttu-id="7d3c2-153">식 트리</span><span class="sxs-lookup"><span data-stu-id="7d3c2-153">Expression trees</span></span>

<span data-ttu-id="7d3c2-154">식 트리를 사용하면 식을 데이터 구조로 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d3c2-154">Expression trees enable expressions to be represented as data structures.</span></span> <span data-ttu-id="7d3c2-155">쿼리 식을 SQL 데이터베이스 등의 다른 일부 컨텍스트에서 의미 있는 코드로 변환하기 위해 LINQ 공급자에서 광범위하게 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d3c2-155">They are used extensively by LINQ providers to translate query expressions into code that is meaningful in some other context, such as a SQL database.</span></span> <span data-ttu-id="7d3c2-156">자세한 내용은 [식 트리(C#)](../concepts/expression-trees/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7d3c2-156">For more information, see [Expression Trees (C#)](../concepts/expression-trees/index.md).</span></span>
  
## <a name="expression-body-definitions"></a><span data-ttu-id="7d3c2-157">식 본문 정의</span><span class="sxs-lookup"><span data-stu-id="7d3c2-157">Expression body definitions</span></span>

<span data-ttu-id="7d3c2-158">C#에서는 메서드, 생성자, 종료자, 속성 및 인덱서에 대한 간단한 식 본문 정의를 제공할 수 있도록 하는 *식 본문 멤버*를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="7d3c2-158">C# supports *expression-bodied members*, which allow you to supply a concise expression body definition for methods, constructors, finalizers, properties, and indexers.</span></span> <span data-ttu-id="7d3c2-159">자세한 내용은 [식 본문 멤버](expression-bodied-members.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7d3c2-159">For more information, see [Expression-bodied members](expression-bodied-members.md).</span></span>

## <a name="remarks"></a><span data-ttu-id="7d3c2-160">설명</span><span class="sxs-lookup"><span data-stu-id="7d3c2-160">Remarks</span></span>

 <span data-ttu-id="7d3c2-161">식에서 변수, 개체 속성 또는 개체 인덱서 액세스를 식별할 때마다 해당 항목의 값이 식의 값으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d3c2-161">Whenever a variable, object property, or object indexer access is identified from an expression, the value of that item is used as the value of the expression.</span></span> <span data-ttu-id="7d3c2-162">식이 궁극적으로 필수 형식으로 평가되기만 하면 C#에서 값 또는 개체가 필요한 어디에든 식을 배치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d3c2-162">An expression can be placed anywhere in C# where a value or object is required, as long as the expression ultimately evaluates to the required type.</span></span>  

## <a name="c-language-specification"></a><span data-ttu-id="7d3c2-163">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="7d3c2-163">C# language specification</span></span>

<span data-ttu-id="7d3c2-164">자세한 내용은 [C# 언어 사양](~/_csharplang/spec/introduction.md)의 [식](~/_csharplang/spec/expressions.md) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7d3c2-164">For more information, see the [Expressions](~/_csharplang/spec/expressions.md) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="7d3c2-165">참조</span><span class="sxs-lookup"><span data-stu-id="7d3c2-165">See also</span></span>

- [<span data-ttu-id="7d3c2-166">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="7d3c2-166">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="7d3c2-167">연산자</span><span class="sxs-lookup"><span data-stu-id="7d3c2-167">Operators</span></span>](../../language-reference/operators/index.md)
- [<span data-ttu-id="7d3c2-168">메서드</span><span class="sxs-lookup"><span data-stu-id="7d3c2-168">Methods</span></span>](../classes-and-structs/methods.md)
- [<span data-ttu-id="7d3c2-169">대리자</span><span class="sxs-lookup"><span data-stu-id="7d3c2-169">Delegates</span></span>](../delegates/index.md)
- [<span data-ttu-id="7d3c2-170">유형</span><span class="sxs-lookup"><span data-stu-id="7d3c2-170">Types</span></span>](../types/index.md)
- [<span data-ttu-id="7d3c2-171">LINQ</span><span class="sxs-lookup"><span data-stu-id="7d3c2-171">LINQ</span></span>](../../linq/index.md)
