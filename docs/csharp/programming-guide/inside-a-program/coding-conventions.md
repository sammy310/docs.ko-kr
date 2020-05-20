---
title: C# 코딩 규칙 - C# 프로그래밍 가이드
ms.date: 07/20/2015
helpviewer_keywords:
- coding conventions, C#
- Visual C#, coding conventions
- C# language, coding conventions
ms.assetid: f4f60de9-d49b-4fb6-bab1-20e19ea24710
ms.openlocfilehash: 77b173a420f26834855e0bdca3c8d04406ac65d4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "79398378"
---
# <a name="c-coding-conventions-c-programming-guide"></a><span data-ttu-id="7a29e-102">C# 코딩 규칙(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="7a29e-102">C# Coding Conventions (C# Programming Guide)</span></span>

<span data-ttu-id="7a29e-103">코딩 규칙은 다음과 같은 용도로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7a29e-103">Coding conventions serve the following purposes:</span></span>  
  
- <span data-ttu-id="7a29e-104">코드를 확인하는 사용자들이 레이아웃이 아닌 내용에 집중할 수 있도록 일관성 있게 표시되는 코드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7a29e-104">They create a consistent look to the code, so that readers can focus on content, not layout.</span></span>  
  
- <span data-ttu-id="7a29e-105">코드를 확인하는 사용자들이 이전 경험을 토대로 한 가정을 통해 코드를 보다 빠르게 이해할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a29e-105">They enable readers to understand the code more quickly by making assumptions based on previous experience.</span></span>  
  
- <span data-ttu-id="7a29e-106">코드를 보다 쉽게 복사, 변경 및 유지 관리할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a29e-106">They facilitate copying, changing, and maintaining the code.</span></span>  
  
- <span data-ttu-id="7a29e-107">C# 모범 사례를 제시합니다.</span><span class="sxs-lookup"><span data-stu-id="7a29e-107">They demonstrate C# best practices.</span></span>  

<span data-ttu-id="7a29e-108">이 문서의 지침은 Microsoft에서 샘플과 설명서를 개발하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7a29e-108">The guidelines in this article are used by Microsoft to develop samples and documentation.</span></span>  
  
## <a name="naming-conventions"></a><span data-ttu-id="7a29e-109">명명 규칙</span><span class="sxs-lookup"><span data-stu-id="7a29e-109">Naming Conventions</span></span>  
  
- <span data-ttu-id="7a29e-110">[using 지시문](../../language-reference/keywords/using-directive.md)이 포함되지 않는 간단한 예제에서 네임스페이스 한정자를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7a29e-110">In short examples that do not include [using directives](../../language-reference/keywords/using-directive.md), use namespace qualifications.</span></span> <span data-ttu-id="7a29e-111">프로젝트에서 네임스페이스를 기본적으로 가져오는 경우에는 해당 네임스페이스의 이름을 정규화하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7a29e-111">If you know that a namespace is imported by default in a project, you do not have to fully qualify the names from that namespace.</span></span> <span data-ttu-id="7a29e-112">정규화된 이름은 한 줄에 표시하기가 너무 길면 다음 예제에 나와 있는 것처럼 점(.)으로 분할할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a29e-112">Qualified names can be broken after a dot (.) if they are too long for a single line, as shown in the following example.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#1](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#1)]  
  
- <span data-ttu-id="7a29e-113">다른 지침에 맞도록 조정하기 위해 Visual Studio 디자이너 도구를 사용하여 만든 개체 이름을 변경할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7a29e-113">You do not have to change the names of objects that were created by using the Visual Studio designer tools to make them fit other guidelines.</span></span>  
  
## <a name="layout-conventions"></a><span data-ttu-id="7a29e-114">레이아웃 규칙</span><span class="sxs-lookup"><span data-stu-id="7a29e-114">Layout Conventions</span></span>  

<span data-ttu-id="7a29e-115">효율적인 레이아웃에서는 서식을 사용하여 코드 구조를 강조하고 코드를 보다 쉽게 읽을 수 있도록 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="7a29e-115">Good layout uses formatting to emphasize the structure of your code and to make the code easier to read.</span></span> <span data-ttu-id="7a29e-116">Microsoft 예제 및 샘플은 다음 규칙을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="7a29e-116">Microsoft examples and samples conform to the following conventions:</span></span>  
  
- <span data-ttu-id="7a29e-117">기본 코드 편집기 설정(스마트 들여쓰기, 4자 들여쓰기, 탭을 공백으로 저장)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7a29e-117">Use the default Code Editor settings (smart indenting, four-character indents, tabs saved as spaces).</span></span> <span data-ttu-id="7a29e-118">자세한 내용은 [옵션, 텍스트 편집기, C#, 서식](/visualstudio/ide/reference/options-text-editor-csharp-formatting)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7a29e-118">For more information, see [Options, Text Editor, C#, Formatting](/visualstudio/ide/reference/options-text-editor-csharp-formatting).</span></span>  
  
- <span data-ttu-id="7a29e-119">문을 한 줄에 하나씩만 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="7a29e-119">Write only one statement per line.</span></span>  
  
- <span data-ttu-id="7a29e-120">선언을 한 줄에 하나씩만 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="7a29e-120">Write only one declaration per line.</span></span>  
  
- <span data-ttu-id="7a29e-121">연속 줄이 자동으로 들여쓰기되지 않으면 탭 정지 하나(공백 4개)만큼 들여씁니다.</span><span class="sxs-lookup"><span data-stu-id="7a29e-121">If continuation lines are not indented automatically, indent them one tab stop (four spaces).</span></span>  
  
- <span data-ttu-id="7a29e-122">메서드 정의와 속성 정의 간에는 빈 줄을 하나 이상 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7a29e-122">Add at least one blank line between method definitions and property definitions.</span></span>  
  
- <span data-ttu-id="7a29e-123">다음 코드에 나와 있는 것처럼 괄호를 사용하여 식의 절을 명확하게 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="7a29e-123">Use parentheses to make clauses in an expression apparent, as shown in the following code.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#2](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#2)]  
  
## <a name="commenting-conventions"></a><span data-ttu-id="7a29e-124">주석 규칙</span><span class="sxs-lookup"><span data-stu-id="7a29e-124">Commenting Conventions</span></span>  
  
- <span data-ttu-id="7a29e-125">코드 줄의 끝이 아닌 별도의 줄에 주석을 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="7a29e-125">Place the comment on a separate line, not at the end of a line of code.</span></span>  
  
- <span data-ttu-id="7a29e-126">주석 텍스트는 대문자로 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="7a29e-126">Begin comment text with an uppercase letter.</span></span>  
  
- <span data-ttu-id="7a29e-127">주석 텍스트 끝에는 마침표를 붙입니다.</span><span class="sxs-lookup"><span data-stu-id="7a29e-127">End comment text with a period.</span></span>  
  
- <span data-ttu-id="7a29e-128">다음 코드에 나와 있는 것처럼 주석 구분 기호(//)와 주석 텍스트 사이에 공백을 하나 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="7a29e-128">Insert one space between the comment delimiter (//) and the comment text, as shown in the following example.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#3](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#3)]  
  
- <span data-ttu-id="7a29e-129">서식이 지정된 별표 블록으로 주석을 묶지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7a29e-129">Do not create formatted blocks of asterisks around comments.</span></span>  
  
## <a name="language-guidelines"></a><span data-ttu-id="7a29e-130">언어 지침</span><span class="sxs-lookup"><span data-stu-id="7a29e-130">Language Guidelines</span></span>  

<span data-ttu-id="7a29e-131">다음 섹션에서는 C# 팀이 코드 예제와 샘플을 준비할 때 따르는 방식에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7a29e-131">The following sections describe practices that the C# team follows to prepare code examples and samples.</span></span>  
  
### <a name="string-data-type"></a><span data-ttu-id="7a29e-132">문자열 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="7a29e-132">String Data Type</span></span>  
  
- <span data-ttu-id="7a29e-133">다음 코드에 나와 있는 것처럼 [문자열 보간](../../language-reference/tokens/interpolated.md)을 사용하여 짧은 문자열을 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="7a29e-133">Use [string interpolation](../../language-reference/tokens/interpolated.md) to concatenate short strings, as shown in the following code.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#6](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#6)]  
  
- <span data-ttu-id="7a29e-134">특히 많은 양의 텍스트를 사용할 때 문자열을 루프에 추가하려면 <xref:System.Text.StringBuilder> 개체를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7a29e-134">To append strings in loops, especially when you are working with large amounts of text, use a <xref:System.Text.StringBuilder> object.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#7](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#7)]  
  
### <a name="implicitly-typed-local-variables"></a><span data-ttu-id="7a29e-135">암시적으로 형식화한 지역 변수</span><span class="sxs-lookup"><span data-stu-id="7a29e-135">Implicitly Typed Local Variables</span></span>  
  
- <span data-ttu-id="7a29e-136">할당 오른쪽에서 변수 형식이 명확하거나 정확한 형식이 중요하지 않으면 지역 변수에 대해 [암시적 형식](../classes-and-structs/implicitly-typed-local-variables.md)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7a29e-136">Use [implicit typing](../classes-and-structs/implicitly-typed-local-variables.md) for local variables when the type of the variable is obvious from the right side of the assignment, or when the precise type is not important.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#8](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#8)]  
  
- <span data-ttu-id="7a29e-137">할당 오른쪽에서 변수 형식이 명확하지 않으면 [var](../../language-reference/keywords/var.md)를 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7a29e-137">Do not use [var](../../language-reference/keywords/var.md) when the type is not apparent from the right side of the assignment.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#9](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#9)]  
  
- <span data-ttu-id="7a29e-138">변수 이름을 사용하여 변수 형식을 지정하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7a29e-138">Do not rely on the variable name to specify the type of the variable.</span></span> <span data-ttu-id="7a29e-139">이렇게 하면 형식이 올바르게 지정되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a29e-139">It might not be correct.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#10](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#10)]  
  
- <span data-ttu-id="7a29e-140">[dynamic](../../language-reference/builtin-types/reference-types.md) 대신 `var`를 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7a29e-140">Avoid the use of `var` in place of [dynamic](../../language-reference/builtin-types/reference-types.md).</span></span>  
  
- <span data-ttu-id="7a29e-141">[for](../../language-reference/keywords/for.md) 루프의 루프 변수 형식을 결정하려면 암시적 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7a29e-141">Use implicit typing to determine the type of the loop variable in [for](../../language-reference/keywords/for.md) loops.</span></span>  
  
     <span data-ttu-id="7a29e-142">다음 예제에서는 `for` 문에서 암시적 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7a29e-142">The following example uses implicit typing in a `for` statement.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#7](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#7)]  

- <span data-ttu-id="7a29e-143">[foreach](../../language-reference/keywords/foreach-in.md) 루프의 루프 변수 형식을 결정하기 위해 암시적 형식을 사용하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="7a29e-143">Do not use implicit typing to determine the type of the loop variable in [foreach](../../language-reference/keywords/foreach-in.md) loops.</span></span>

     <span data-ttu-id="7a29e-144">다음 예제에서는 `foreach` 문에서 명시적 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7a29e-144">The following example uses explicit typing in a `foreach` statement.</span></span>

     [!code-csharp[csProgGuideCodingConventions#12](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#12)]

     > [!NOTE]
     > <span data-ttu-id="7a29e-145">반복 가능한 컬렉션의 요소 형식을 실수로 변경하지 않도록 주의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a29e-145">Be careful not to accidentally change a type of an element of the iterable collection.</span></span> <span data-ttu-id="7a29e-146">예를 들어 `foreach` 문에서 <xref:System.Linq.IQueryable?displayProperty=nameWithType>을 <xref:System.Collections.IEnumerable?displayProperty=nameWithType>으로 전환하기 쉬운데 그러면 쿼리 실행이 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="7a29e-146">For example, it is easy to switch from <xref:System.Linq.IQueryable?displayProperty=nameWithType> to <xref:System.Collections.IEnumerable?displayProperty=nameWithType> in a `foreach` statement, which changes the execution of a query.</span></span>

### <a name="unsigned-data-type"></a><span data-ttu-id="7a29e-147">부호 없는 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="7a29e-147">Unsigned Data Type</span></span>  
  
<span data-ttu-id="7a29e-148">일반적으로는 부호 없는 형식 대신 `int`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7a29e-148">In general, use `int` rather than unsigned types.</span></span> <span data-ttu-id="7a29e-149">`int`는 C# 전체에서 일반적으로 사용되며, `int`를 사용하는 경우 다른 라이브러리와 보다 쉽게 상호 작용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a29e-149">The use of `int` is common throughout C#, and it is easier to interact with other libraries when you use `int`.</span></span>  
  
### <a name="arrays"></a><span data-ttu-id="7a29e-150">배열</span><span class="sxs-lookup"><span data-stu-id="7a29e-150">Arrays</span></span>  
  
<span data-ttu-id="7a29e-151">선언 줄에서 배열을 초기화할 때는 간결한 구문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7a29e-151">Use the concise syntax when you initialize arrays on the declaration line.</span></span>  
  
[!code-csharp[csProgGuideCodingConventions#13](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#13)]  
  
### <a name="delegates"></a><span data-ttu-id="7a29e-152">대리자</span><span class="sxs-lookup"><span data-stu-id="7a29e-152">Delegates</span></span>  
  
<span data-ttu-id="7a29e-153">대리자 형식의 인스턴스를 만들려면 간결한 구문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7a29e-153">Use the concise syntax to create instances of a delegate type.</span></span>  
  
[!code-csharp[csProgGuideCodingConventions#14](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#14)]  
  
[!code-csharp[csProgGuideCodingConventions#15](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#15)]  
  
### <a name="try-catch-and-using-statements-in-exception-handling"></a><span data-ttu-id="7a29e-154">예외 처리의 try-catch 및 using 문</span><span class="sxs-lookup"><span data-stu-id="7a29e-154">try-catch and using Statements in Exception Handling</span></span>  
  
- <span data-ttu-id="7a29e-155">대부분의 예외 처리에서는 [try-catch](../../language-reference/keywords/try-catch.md) 문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7a29e-155">Use a [try-catch](../../language-reference/keywords/try-catch.md) statement for most exception handling.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#16](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#16)]  
  
- <span data-ttu-id="7a29e-156">C# [using 문](../../language-reference/keywords/using-statement.md)을 사용하면 코드를 간소화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a29e-156">Simplify your code by using the C# [using statement](../../language-reference/keywords/using-statement.md).</span></span> <span data-ttu-id="7a29e-157">`finally` 블록의 코드가 <xref:System.IDisposable.Dispose%2A> 메서드 호출뿐인 [try-finally](../../language-reference/keywords/try-finally.md) 문이 있는 경우에는 `using` 문을 대신 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7a29e-157">If you have a [try-finally](../../language-reference/keywords/try-finally.md) statement in which the only code in the `finally` block is a call to the <xref:System.IDisposable.Dispose%2A> method, use a `using` statement instead.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#17](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#17)]  
  
### <a name="-and-124124-operators"></a><span data-ttu-id="7a29e-158">&& 및 &#124;&#124; 연산자</span><span class="sxs-lookup"><span data-stu-id="7a29e-158">&& and &#124;&#124; Operators</span></span>  
  
<span data-ttu-id="7a29e-159">예외를 방지하고 불필요한 비교를 건너뛰어 성능을 개선하려면 비교를 수행할 때 다음 예제에 나와 있는 것처럼 [&](../../language-reference/operators/boolean-logical-operators.md#logical-and-operator-) 대신 [&&](../../language-reference/operators/boolean-logical-operators.md#conditional-logical-and-operator-)를 사용하고 [&#124;](../../language-reference/operators/boolean-logical-operators.md#logical-or-operator-) 대신 [&#124;&#124;](../../language-reference/operators/boolean-logical-operators.md#conditional-logical-or-operator-)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7a29e-159">To avoid exceptions and increase performance by skipping unnecessary comparisons, use [&&](../../language-reference/operators/boolean-logical-operators.md#conditional-logical-and-operator-) instead of [&](../../language-reference/operators/boolean-logical-operators.md#logical-and-operator-) and [&#124;&#124;](../../language-reference/operators/boolean-logical-operators.md#conditional-logical-or-operator-) instead of [&#124;](../../language-reference/operators/boolean-logical-operators.md#logical-or-operator-) when you perform comparisons, as shown in the following example.</span></span>  
  
[!code-csharp[csProgGuideCodingConventions#18](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#18)]  
  
### <a name="new-operator"></a><span data-ttu-id="7a29e-160">New 연산자</span><span class="sxs-lookup"><span data-stu-id="7a29e-160">New Operator</span></span>  
  
- <span data-ttu-id="7a29e-161">다음 선언에 나와 있는 것처럼 암시적 형식이 포함된 간결한 형태의 개체 인스턴스화를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7a29e-161">Use the concise form of object instantiation, with implicit typing, as shown in the following declaration.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#19](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#19)]  
  
     <span data-ttu-id="7a29e-162">위의 줄은 다음 선언과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="7a29e-162">The previous line is equivalent to the following declaration.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#20](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#20)]  
  
- <span data-ttu-id="7a29e-163">개체를 간편하게 만들려면 개체 이니셜라이저를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7a29e-163">Use object initializers to simplify object creation.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#21](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#21)]  
  
### <a name="event-handling"></a><span data-ttu-id="7a29e-164">이벤트 처리</span><span class="sxs-lookup"><span data-stu-id="7a29e-164">Event Handling</span></span>  
  
<span data-ttu-id="7a29e-165">나중에 제거할 필요가 없는 이벤트 처리기를 정의하는 경우 람다 식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7a29e-165">If you are defining an event handler that you do not need to remove later, use a lambda expression.</span></span>  
  
[!code-csharp[csProgGuideCodingConventions#22](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#22)]  
  
[!code-csharp[csProgGuideCodingConventions#23](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#23)]  
  
### <a name="static-members"></a><span data-ttu-id="7a29e-166">정적 멤버</span><span class="sxs-lookup"><span data-stu-id="7a29e-166">Static Members</span></span>  
  
<span data-ttu-id="7a29e-167">*ClassName.StaticMember*와 같이 클래스 이름을 사용하여 [static](../../language-reference/keywords/static.md) 멤버를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="7a29e-167">Call [static](../../language-reference/keywords/static.md) members by using the class name: *ClassName.StaticMember*.</span></span> <span data-ttu-id="7a29e-168">이렇게 하면 정적 액세스가 명확하게 표시되므로 코드를 보다 쉽게 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a29e-168">This practice makes code more readable by making static access clear.</span></span>  <span data-ttu-id="7a29e-169">파생 클래스 이름을 사용하여 기본 클래스에 정의된 정적 멤버를 정규화해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7a29e-169">Do not qualify a static member defined in a base class with the name of a derived class.</span></span>  <span data-ttu-id="7a29e-170">이 코드는 컴파일되기는 하지만 가독성이 떨어지며 나중에 파생 클래스와 이름이 같은 정적 멤버를 추가하면 코드가 손상될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a29e-170">While that code compiles, the code readability is misleading, and the code may break in the future if you add a static member with the same name to the derived class.</span></span>  
  
### <a name="linq-queries"></a><span data-ttu-id="7a29e-171">LINQ 쿼리</span><span class="sxs-lookup"><span data-stu-id="7a29e-171">LINQ Queries</span></span>  
  
- <span data-ttu-id="7a29e-172">쿼리 변수에 의미 있는 이름을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7a29e-172">Use meaningful names for query variables.</span></span> <span data-ttu-id="7a29e-173">다음 예제에서는 Seattle 거주 고객에 대해 `seattleCustomers`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7a29e-173">The following example uses `seattleCustomers` for customers who are located in Seattle.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#25](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#25)]  
  
- <span data-ttu-id="7a29e-174">별칭을 사용하여 익명 형식의 속성 이름 대/소문자를 올바르게 표시합니다(파스칼식 대/소문자 사용).</span><span class="sxs-lookup"><span data-stu-id="7a29e-174">Use aliases to make sure that property names of anonymous types are correctly capitalized, using Pascal casing.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#26](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#26)]  
  
- <span data-ttu-id="7a29e-175">결과의 속성 이름이 모호하면 속성 이름을 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="7a29e-175">Rename properties when the property names in the result would be ambiguous.</span></span> <span data-ttu-id="7a29e-176">예를 들어 쿼리에서 고객 이름과 배포자 ID를 반환하는 경우 결과에서 이러한 정보를 `Name` 및 `ID`로 유지하는 대신 `Name`은 고객의 이름이고 `ID`는 배포자의 ID임을 명확하게 나타내도록 이름을 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="7a29e-176">For example, if your query returns a customer name and a distributor ID, instead of leaving them as `Name` and `ID` in the result, rename them to clarify that `Name` is the name of a customer, and `ID` is the ID of a distributor.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#27](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#27)]  
  
- <span data-ttu-id="7a29e-177">쿼리 변수 및 범위 변수의 선언에서 암시적 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7a29e-177">Use implicit typing in the declaration of query variables and range variables.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#25](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#25)]  
  
- <span data-ttu-id="7a29e-178">위의 예제에 나와 있는 것처럼 [from](../../language-reference/keywords/from-clause.md) 절 아래의 쿼리 절을 정렬합니다.</span><span class="sxs-lookup"><span data-stu-id="7a29e-178">Align query clauses under the [from](../../language-reference/keywords/from-clause.md) clause, as shown in the previous examples.</span></span>  
  
- <span data-ttu-id="7a29e-179">뒷부분의 쿼리 절이 필터링을 통해 범위가 좁아진 데이터 집합에 대해 작동하도록 다른 쿼리 절 앞에 [where](../../language-reference/keywords/where-clause.md) 절을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7a29e-179">Use [where](../../language-reference/keywords/where-clause.md) clauses before other query clauses to ensure that later query clauses operate on the reduced, filtered set of data.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#29](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#29)]  
  
- <span data-ttu-id="7a29e-180">내부 컬렉션에 액세스하려면 [join](../../language-reference/keywords/join-clause.md) 절 대신 여러 `from` 절을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7a29e-180">Use multiple `from` clauses instead of a [join](../../language-reference/keywords/join-clause.md) clause to access inner collections.</span></span> <span data-ttu-id="7a29e-181">예를 들어 `Student` 개체 컬렉션이 각각 테스트 점수 컬렉션을 포함하는 경우</span><span class="sxs-lookup"><span data-stu-id="7a29e-181">For example, a collection of `Student` objects might each contain a collection of test scores.</span></span> <span data-ttu-id="7a29e-182">다음 쿼리를 실행하면 90점보다 높은 각 점수와 해당 점수를 받은 학생의 성이 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="7a29e-182">When the following query is executed, it returns each score that is over 90, along with the last name of the student who received the score.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#30](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#30)]  
  
## <a name="security"></a><span data-ttu-id="7a29e-183">보안</span><span class="sxs-lookup"><span data-stu-id="7a29e-183">Security</span></span>  

<span data-ttu-id="7a29e-184">[보안 코딩 지침](../../../standard/security/secure-coding-guidelines.md)의 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="7a29e-184">Follow the guidelines in [Secure Coding Guidelines](../../../standard/security/secure-coding-guidelines.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a29e-185">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7a29e-185">See also</span></span>

- [<span data-ttu-id="7a29e-186">Visual Basic 코딩 규칙</span><span class="sxs-lookup"><span data-stu-id="7a29e-186">Visual Basic Coding Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/coding-conventions.md)
- [<span data-ttu-id="7a29e-187">보안 코딩 지침</span><span class="sxs-lookup"><span data-stu-id="7a29e-187">Secure Coding Guidelines</span></span>](../../../standard/security/secure-coding-guidelines.md)
