---
title: bool 키워드 - C# 참조
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- bool_CSharpKeyword
- bool
helpviewer_keywords:
- bool keyword [C#]
ms.assetid: 551cfe35-2632-4343-af49-33ad12da08e2
ms.openlocfilehash: 880e8c0b733afbf5c09f543e06a5a4a858d2b456
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2019
ms.locfileid: "72771856"
---
# <a name="bool-c-reference"></a><span data-ttu-id="d47da-102">bool(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="d47da-102">bool (C# Reference)</span></span>

<span data-ttu-id="d47da-103">`bool` 키워드는 <xref:System.Boolean?displayProperty=nameWithType>의 별칭입니다.</span><span class="sxs-lookup"><span data-stu-id="d47da-103">The `bool` keyword is an alias of <xref:System.Boolean?displayProperty=nameWithType>.</span></span> <span data-ttu-id="d47da-104">부울 값 [true](true-literal.md) 및 [false](false-literal.md)를 저장할 변수를 선언하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d47da-104">It is used to declare variables to store the Boolean values: [true](true-literal.md) and [false](false-literal.md).</span></span>

> [!NOTE]
> <span data-ttu-id="d47da-105">예를 들어 값이 세 개인 논리를 지원해야 하는 경우(예: 값이 세 개인 부울 형식을 지원하는 데이터베이스에서 작업하는 경우) `bool?` 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d47da-105">Use the `bool?` type, if you need to support the three-valued logic, for example, when you work with databases that support a three-valued Boolean type.</span></span> <span data-ttu-id="d47da-106">`bool?` 피연산자의 경우 미리 정의된 `&` 및 `|` 연산자는 값이 세 개인 논리를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="d47da-106">For the `bool?` operands, the predefined `&` and `|` operators support the three-valued logic.</span></span> <span data-ttu-id="d47da-107">자세한 내용은 [부울 논리 연산자](../operators/boolean-logical-operators.md) 문서의 [Nullable 부울 논리 연산자](../operators/boolean-logical-operators.md#nullable-boolean-logical-operators) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d47da-107">For more information, see the [Nullable Boolean logical operators](../operators/boolean-logical-operators.md#nullable-boolean-logical-operators) section of the [Boolean logical operators](../operators/boolean-logical-operators.md) article.</span></span>

## <a name="literals"></a><span data-ttu-id="d47da-108">리터럴</span><span class="sxs-lookup"><span data-stu-id="d47da-108">Literals</span></span>

<span data-ttu-id="d47da-109">`bool` 변수에 부울 값을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d47da-109">You can assign a Boolean value to a `bool` variable.</span></span> <span data-ttu-id="d47da-110">`bool`로 계산되는 식을 `bool` 변수에 할당할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d47da-110">You can also assign an expression that evaluates to `bool` to a `bool` variable.</span></span>

[!code-csharp[csrefKeywordsTypes#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#1)]

<span data-ttu-id="d47da-111">`bool` 변수의 기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="d47da-111">The default value of a `bool` variable is `false`.</span></span> <span data-ttu-id="d47da-112">`bool?` 변수의 기본값은 `null`입니다.</span><span class="sxs-lookup"><span data-stu-id="d47da-112">The default value of a `bool?` variable is `null`.</span></span>

## <a name="conversions"></a><span data-ttu-id="d47da-113">변환</span><span class="sxs-lookup"><span data-stu-id="d47da-113">Conversions</span></span>

<span data-ttu-id="d47da-114">C++에서 `bool` 형식의 값은 `int` 형식의 값으로 변환될 수 있습니다. 즉, `false`는 0과 같고 `true`는 0이 아닌 값과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d47da-114">In C++, a value of type `bool` can be converted to a value of type `int`; in other words, `false` is equivalent to zero and `true` is equivalent to nonzero values.</span></span> <span data-ttu-id="d47da-115">C#에는 `bool` 형식과 다른 형식 간의 변환이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d47da-115">In C#, there is no conversion between the `bool` type and other types.</span></span> <span data-ttu-id="d47da-116">예를 들어 다음 `if` 문은 C#에서 유효하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d47da-116">For example, the following `if` statement is invalid in C#:</span></span>

[!code-csharp[csrefKeywordsTypes#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#2)]

<span data-ttu-id="d47da-117">`int` 형식의 변수를 테스트하려면 다음과 같이 0과 같은 값에 변수를 명시적으로 비교해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d47da-117">To test a variable of the type `int`, you have to explicitly compare it to a value, such as zero, as follows:</span></span>

[!code-csharp[csrefKeywordsTypes#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#3)]

## <a name="example"></a><span data-ttu-id="d47da-118">예</span><span class="sxs-lookup"><span data-stu-id="d47da-118">Example</span></span>

<span data-ttu-id="d47da-119">이 예제에서는 키보드에서 문자를 입력하면 프로그램에서 입력 문자가 문자인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d47da-119">In this example, you enter a character from the keyboard and the program checks if the input character is a letter.</span></span> <span data-ttu-id="d47da-120">문자인 경우 소문자 또는 대문자인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d47da-120">If it is a letter, it checks if it is lowercase or uppercase.</span></span> <span data-ttu-id="d47da-121">이러한 검사는 <xref:System.Char.IsLetter%2A> 및 <xref:System.Char.IsLower%2A>를 사용하여 수행되며, 둘 다 `bool` 형식을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="d47da-121">These checks are performed with the <xref:System.Char.IsLetter%2A>, and <xref:System.Char.IsLower%2A>, both of which return the `bool` type:</span></span>

[!code-csharp[csrefKeywordsTypes#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#4)]

## <a name="c-language-specification"></a><span data-ttu-id="d47da-122">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="d47da-122">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="d47da-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d47da-123">See also</span></span>

- [<span data-ttu-id="d47da-124">C# 참조</span><span class="sxs-lookup"><span data-stu-id="d47da-124">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="d47da-125">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="d47da-125">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="d47da-126">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="d47da-126">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="d47da-127">정수 형식</span><span class="sxs-lookup"><span data-stu-id="d47da-127">Integral types</span></span>](../builtin-types/integral-numeric-types.md)
- [<span data-ttu-id="d47da-128">기본 제공 형식 표</span><span class="sxs-lookup"><span data-stu-id="d47da-128">Built-In Types Table</span></span>](./built-in-types-table.md)
