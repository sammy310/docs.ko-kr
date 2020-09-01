---
description: delegate 연산자 - C# 참조
title: delegate 연산자 - C# 참조
ms.date: 07/18/2019
helpviewer_keywords:
- delegate [C#]
- anonymous method [C#]
ms.openlocfilehash: 1dfaaf40c0f5a19534adef3be7e3c917bc95c4a8
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/30/2020
ms.locfileid: "89122253"
---
# <a name="delegate-operator-c-reference"></a><span data-ttu-id="2abfb-103">delegate 연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="2abfb-103">delegate operator (C# reference)</span></span>

<span data-ttu-id="2abfb-104">`delegate` 연산자는 대리자 형식으로 변환될 수 있는 무명 메서드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2abfb-104">The `delegate` operator creates an anonymous method that can be converted to a delegate type:</span></span>

[!code-csharp-interactive[anonymous method](snippets/shared/DelegateOperator.cs#AnonymousMethod)]

> [!NOTE]
> <span data-ttu-id="2abfb-105">C# 3으로 시작하는 람다 식은 익명 함수를 만드는 더 간결하고 이해하기 쉬운 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2abfb-105">Beginning with C# 3, lambda expressions provide a more concise and expressive way to create an anonymous function.</span></span> <span data-ttu-id="2abfb-106">[=> 연산자](lambda-operator.md)를 사용하여 람다 식을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="2abfb-106">Use the [=> operator](lambda-operator.md) to construct a lambda expression:</span></span>
>
> [!code-csharp-interactive[lambda expression](snippets/shared/DelegateOperator.cs#Lambda)]
>
> <span data-ttu-id="2abfb-107">람다 식의 기능(예: 외부 변수 캡처)에 대한 자세한 내용은 [람다 식](lambda-expressions.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2abfb-107">For more information about features of lambda expressions, for example, capturing outer variables, see [Lambda expressions](lambda-expressions.md).</span></span>

<span data-ttu-id="2abfb-108">`delegate` 연산자를 사용하는 경우 매개 변수 목록을 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2abfb-108">When you use the `delegate` operator, you might omit the parameter list.</span></span> <span data-ttu-id="2abfb-109">이렇게 하면 다음 예제와 같이 매개 변수 목록을 사용하여 생성된 무명 메서드를 대리자 형식으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2abfb-109">If you do that, the created anonymous method can be converted to a delegate type with any list of  parameters, as the following example shows:</span></span>

[!code-csharp-interactive[no parameter list](snippets/shared/DelegateOperator.cs#WithoutParameterList)]

<span data-ttu-id="2abfb-110">이 기능은 람다 식에서 지원되지 않는 무명 메서드의 유일한 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="2abfb-110">That's the only functionality of anonymous methods that is not supported by lambda expressions.</span></span> <span data-ttu-id="2abfb-111">다른 모든 경우 인라인 코드를 작성하는 데 람다 식이 선호됩니다.</span><span class="sxs-lookup"><span data-stu-id="2abfb-111">In all other cases, a lambda expression is a preferred way to write inline code.</span></span>

<span data-ttu-id="2abfb-112">`delegate` 키워드를 사용하여 [대리자 형식](../builtin-types/reference-types.md#the-delegate-type)을 선언할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2abfb-112">You also use the `delegate` keyword to declare a [delegate type](../builtin-types/reference-types.md#the-delegate-type).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="2abfb-113">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="2abfb-113">C# language specification</span></span>

<span data-ttu-id="2abfb-114">자세한 내용은 [C# 언어 사양](~/_csharplang/spec/introduction.md)의 [익명 함수 식](~/_csharplang/spec/expressions.md#anonymous-function-expressions) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2abfb-114">For more information, see the [Anonymous function expressions](~/_csharplang/spec/expressions.md#anonymous-function-expressions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="2abfb-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2abfb-115">See also</span></span>

- [<span data-ttu-id="2abfb-116">C# 참조</span><span class="sxs-lookup"><span data-stu-id="2abfb-116">C# reference</span></span>](../index.md)
- [<span data-ttu-id="2abfb-117">C# 연산자 및 식</span><span class="sxs-lookup"><span data-stu-id="2abfb-117">C# operators and expressions</span></span>](index.md)
- [<span data-ttu-id="2abfb-118">=> 연산자</span><span class="sxs-lookup"><span data-stu-id="2abfb-118">=> operator</span></span>](lambda-operator.md)
