---
title: 익명 함수 - C# 프로그래밍 가이드
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [C#], as anonymous functions
- anonymous functions [C#]
- anonymous methods [C#]
ms.assetid: 6ce3f04d-0c71-4728-9127-634c7e9a8365
ms.openlocfilehash: cfb0190ee263e65e8130a8925f76357a382eafa3
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712002"
---
# <a name="anonymous-functions-c-programming-guide"></a><span data-ttu-id="5c165-102">익명 함수(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="5c165-102">Anonymous functions (C# Programming Guide)</span></span>

<span data-ttu-id="5c165-103">익명 함수는 대리자 형식이 예상되는 곳에서 항상 사용할 수 있는 “인라인” 문 또는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="5c165-103">An anonymous function is an "inline" statement or expression that can be used wherever a delegate type is expected.</span></span> <span data-ttu-id="5c165-104">이를 사용하여 명명된 대리자를 초기화하거나 명명된 대리자 형식 대신 이를 메서드 매개 변수로 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c165-104">You can use it to initialize a named delegate or pass it instead of a named delegate type as a method parameter.</span></span>

<span data-ttu-id="5c165-105">[람다 식](lambda-expressions.md) 또는 [무명 메서드](../../language-reference/operators/delegate-operator.md)를 사용하여 익명 함수를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c165-105">You can use a [lambda expression](lambda-expressions.md) or an [anonymous method](../../language-reference/operators/delegate-operator.md) to create an anonymous function.</span></span> <span data-ttu-id="5c165-106">인라인 코드를 작성하는 더 간결하고 이해하기 쉬운 방법을 제공하는 람다 식을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5c165-106">We recommend using lambda expressions as they provide more concise and expressive way to write inline code.</span></span> <span data-ttu-id="5c165-107">무명 메서드와 달리 일부 형식의 람다 식은 식 트리 형식으로 변환될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c165-107">Unlike anonymous methods, some types of lambda expressions can be converted to the expression tree types.</span></span>

## <a name="the-evolution-of-delegates-in-c"></a><span data-ttu-id="5c165-108">C\#에서 대리자의 발전</span><span class="sxs-lookup"><span data-stu-id="5c165-108">The Evolution of Delegates in C\#</span></span>

 <span data-ttu-id="5c165-109">C# 1.0에서는 코드의 다른 위치에 정의된 메서드를 사용하여 명시적으로 초기화하는 방식으로 대리자의 인스턴스를 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="5c165-109">In C# 1.0, you created an instance of a delegate by explicitly initializing it with a method that was defined elsewhere in the code.</span></span> <span data-ttu-id="5c165-110">C# 2.0에서는 대리자 호출에서 실행될 수 있는 이름 없는 인라인 문 블록을 작성하는 방법으로 무명 메서드의 개념을 소개했습니다.</span><span class="sxs-lookup"><span data-stu-id="5c165-110">C# 2.0 introduced the concept of anonymous methods as a way to write unnamed inline statement blocks that can be executed in a delegate invocation.</span></span> <span data-ttu-id="5c165-111">C# 3.0에서는 개념적으로 무명 메서드와 비슷하지만 더 간결하고 표현이 다양한 람다 식을 소개했습니다.</span><span class="sxs-lookup"><span data-stu-id="5c165-111">C# 3.0 introduced lambda expressions, which are similar in concept to anonymous methods but more expressive and concise.</span></span> <span data-ttu-id="5c165-112">이러한 두 기능을 함께 *익명 함수*라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c165-112">These two features are known collectively as *anonymous functions*.</span></span> <span data-ttu-id="5c165-113">일반적으로 .NET Framework의 버전 3.5 이상을 대상으로 하는 애플리케이션은 람다 식을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c165-113">In general, applications that target version 3.5 and later of the .NET Framework should use lambda expressions.</span></span>  
  
 <span data-ttu-id="5c165-114">다음 예제에서는 C# 1.0에서 C# 3.0까지 대리자 만들기의 발전을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5c165-114">The following example demonstrates the evolution of delegate creation from C# 1.0 to C# 3.0:</span></span>  
  
 [!code-csharp[csProgGuideLINQ#65](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#65)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="5c165-115">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="5c165-115">C# language specification</span></span>

<span data-ttu-id="5c165-116">자세한 내용은 [C# 언어 사양](~/_csharplang/spec/introduction.md)의 [익명 함수 식](~/_csharplang/spec/expressions.md#anonymous-function-expressions) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5c165-116">For more information, see the [Anonymous function expressions](~/_csharplang/spec/expressions.md#anonymous-function-expressions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5c165-117">참조</span><span class="sxs-lookup"><span data-stu-id="5c165-117">See also</span></span>

- [<span data-ttu-id="5c165-118">문, 식, 연산자</span><span class="sxs-lookup"><span data-stu-id="5c165-118">Statements, Expressions, and Operators</span></span>](./index.md)
- [<span data-ttu-id="5c165-119">람다 식</span><span class="sxs-lookup"><span data-stu-id="5c165-119">Lambda Expressions</span></span>](./lambda-expressions.md)
- [<span data-ttu-id="5c165-120">대리자</span><span class="sxs-lookup"><span data-stu-id="5c165-120">Delegates</span></span>](../delegates/index.md)
- [<span data-ttu-id="5c165-121">식 트리(C#)</span><span class="sxs-lookup"><span data-stu-id="5c165-121">Expression Trees (C#)</span></span>](../concepts/expression-trees/index.md)
