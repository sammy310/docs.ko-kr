---
title: 익명 함수 - C# 프로그래밍 가이드
description: 익명 함수에 대해 알아봅니다. 람다 식 또는 무명 메서드를 사용하여 익명 함수를 만들 수 있습니다.
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [C#], as anonymous functions
- anonymous functions [C#]
- anonymous methods [C#]
ms.assetid: 6ce3f04d-0c71-4728-9127-634c7e9a8365
ms.openlocfilehash: 1fde7d535054f09d55018a010468776622ebfba7
ms.sourcegitcommit: 7476c20d2f911a834a00b8a7f5e8926bae6804d9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/11/2020
ms.locfileid: "88063265"
---
# <a name="anonymous-functions-c-programming-guide"></a><span data-ttu-id="8c785-104">익명 함수(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="8c785-104">Anonymous functions (C# Programming Guide)</span></span>

<span data-ttu-id="8c785-105">익명 함수는 대리자 형식이 예상되는 곳에서 항상 사용할 수 있는 “인라인” 문 또는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="8c785-105">An anonymous function is an "inline" statement or expression that can be used wherever a delegate type is expected.</span></span> <span data-ttu-id="8c785-106">이를 사용하여 명명된 대리자를 초기화하거나 명명된 대리자 형식 대신 이를 메서드 매개 변수로 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c785-106">You can use it to initialize a named delegate or pass it instead of a named delegate type as a method parameter.</span></span>

<span data-ttu-id="8c785-107">[람다 식](../../language-reference/operators/lambda-expressions.md) 또는 [무명 메서드](../../language-reference/operators/delegate-operator.md)를 사용하여 익명 함수를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c785-107">You can use a [lambda expression](../../language-reference/operators/lambda-expressions.md) or an [anonymous method](../../language-reference/operators/delegate-operator.md) to create an anonymous function.</span></span> <span data-ttu-id="8c785-108">인라인 코드를 작성하는 더 간결하고 이해하기 쉬운 방법을 제공하는 람다 식을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="8c785-108">We recommend using lambda expressions as they provide more concise and expressive way to write inline code.</span></span> <span data-ttu-id="8c785-109">무명 메서드와 달리 일부 형식의 람다 식은 식 트리 형식으로 변환될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c785-109">Unlike anonymous methods, some types of lambda expressions can be converted to the expression tree types.</span></span>

## <a name="the-evolution-of-delegates-in-c"></a><span data-ttu-id="8c785-110">C\#에서 대리자의 발전</span><span class="sxs-lookup"><span data-stu-id="8c785-110">The Evolution of Delegates in C\#</span></span>

 <span data-ttu-id="8c785-111">C# 1.0에서는 코드의 다른 위치에 정의된 메서드를 사용하여 명시적으로 초기화하는 방식으로 대리자의 인스턴스를 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="8c785-111">In C# 1.0, you created an instance of a delegate by explicitly initializing it with a method that was defined elsewhere in the code.</span></span> <span data-ttu-id="8c785-112">C# 2.0에서는 대리자 호출에서 실행될 수 있는 이름 없는 인라인 문 블록을 작성하는 방법으로 무명 메서드의 개념을 소개했습니다.</span><span class="sxs-lookup"><span data-stu-id="8c785-112">C# 2.0 introduced the concept of anonymous methods as a way to write unnamed inline statement blocks that can be executed in a delegate invocation.</span></span> <span data-ttu-id="8c785-113">C# 3.0에서는 개념적으로 무명 메서드와 비슷하지만 더 간결하고 표현이 다양한 람다 식을 소개했습니다.</span><span class="sxs-lookup"><span data-stu-id="8c785-113">C# 3.0 introduced lambda expressions, which are similar in concept to anonymous methods but more expressive and concise.</span></span> <span data-ttu-id="8c785-114">이러한 두 기능을 함께 *익명 함수*라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c785-114">These two features are known collectively as *anonymous functions*.</span></span> <span data-ttu-id="8c785-115">일반적으로 .NET Framework 3.5 이상을 대상으로 하는 애플리케이션은 람다 식을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c785-115">In general, applications that target .NET Framework 3.5 or later should use lambda expressions.</span></span>  
  
 <span data-ttu-id="8c785-116">다음 예제에서는 C# 1.0에서 C# 3.0까지 대리자 만들기의 발전을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8c785-116">The following example demonstrates the evolution of delegate creation from C# 1.0 to C# 3.0:</span></span>  
  
 [!code-csharp[csProgGuideLINQ#65](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#65)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="8c785-117">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="8c785-117">C# language specification</span></span>

<span data-ttu-id="8c785-118">자세한 내용은 [C# 언어 사양](~/_csharplang/spec/introduction.md)의 [익명 함수 식](~/_csharplang/spec/expressions.md#anonymous-function-expressions) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8c785-118">For more information, see the [Anonymous function expressions](~/_csharplang/spec/expressions.md#anonymous-function-expressions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="8c785-119">참조</span><span class="sxs-lookup"><span data-stu-id="8c785-119">See also</span></span>

- [<span data-ttu-id="8c785-120">문, 식, 연산자</span><span class="sxs-lookup"><span data-stu-id="8c785-120">Statements, Expressions, and Operators</span></span>](./index.md)
- [<span data-ttu-id="8c785-121">람다 식</span><span class="sxs-lookup"><span data-stu-id="8c785-121">Lambda Expressions</span></span>](../../language-reference/operators/lambda-expressions.md)
- [<span data-ttu-id="8c785-122">대리자</span><span class="sxs-lookup"><span data-stu-id="8c785-122">Delegates</span></span>](../delegates/index.md)
- [<span data-ttu-id="8c785-123">식 트리(C#)</span><span class="sxs-lookup"><span data-stu-id="8c785-123">Expression Trees (C#)</span></span>](../concepts/expression-trees/index.md)
