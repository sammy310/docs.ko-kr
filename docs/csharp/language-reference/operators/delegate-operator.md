---
title: delegate 연산자 - C# 참조
ms.date: 07/18/2019
helpviewer_keywords:
- delegate [C#]
- anonymous method [C#]
ms.openlocfilehash: 1dd27fe5fdfdc1bc8a63e1298da00d252e800a72
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "78847341"
---
# <a name="delegate-operator-c-reference"></a><span data-ttu-id="5801b-102">delegate 연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="5801b-102">delegate operator (C# reference)</span></span>

<span data-ttu-id="5801b-103">`delegate` 연산자는 대리자 형식으로 변환될 수 있는 무명 메서드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5801b-103">The `delegate` operator creates an anonymous method that can be converted to a delegate type:</span></span>

[!code-csharp-interactive[anonymous method](snippets/DelegateOperator.cs#AnonymousMethod)]

> [!NOTE]
> <span data-ttu-id="5801b-104">C# 3으로 시작하는 람다 식은 익명 함수를 만드는 더 간결하고 이해하기 쉬운 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5801b-104">Beginning with C# 3, lambda expressions provide a more concise and expressive way to create an anonymous function.</span></span> <span data-ttu-id="5801b-105">[=> 연산자](lambda-operator.md)를 사용하여 람다 식을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="5801b-105">Use the [=> operator](lambda-operator.md) to construct a lambda expression:</span></span>
>
> [!code-csharp-interactive[lambda expression](snippets/DelegateOperator.cs#Lambda)]
>
> <span data-ttu-id="5801b-106">람다 식의 기능(예: 외부 변수 캡처)에 대한 자세한 내용은 [람다 식](../../programming-guide/statements-expressions-operators/lambda-expressions.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5801b-106">For more information about features of lambda expressions, for example, capturing outer variables, see [Lambda expressions](../../programming-guide/statements-expressions-operators/lambda-expressions.md).</span></span>

<span data-ttu-id="5801b-107">`delegate` 연산자를 사용하는 경우 매개 변수 목록을 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5801b-107">When you use the `delegate` operator, you might omit the parameter list.</span></span> <span data-ttu-id="5801b-108">이렇게 하면 다음 예제와 같이 매개 변수 목록을 사용하여 생성된 무명 메서드를 대리자 형식으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5801b-108">If you do that, the created anonymous method can be converted to a delegate type with any list of  parameters, as the following example shows:</span></span>

[!code-csharp-interactive[no parameter list](snippets/DelegateOperator.cs#WithoutParameterList)]

<span data-ttu-id="5801b-109">이 기능은 람다 식에서 지원되지 않는 무명 메서드의 유일한 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="5801b-109">That's the only functionality of anonymous methods that is not supported by lambda expressions.</span></span> <span data-ttu-id="5801b-110">다른 모든 경우 인라인 코드를 작성하는 데 람다 식이 선호됩니다.</span><span class="sxs-lookup"><span data-stu-id="5801b-110">In all other cases, a lambda expression is a preferred way to write inline code.</span></span>

<span data-ttu-id="5801b-111">`delegate` 키워드를 사용하여 [대리자 형식](../builtin-types/reference-types.md#the-delegate-type)을 선언할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5801b-111">You also use the `delegate` keyword to declare a [delegate type](../builtin-types/reference-types.md#the-delegate-type).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="5801b-112">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="5801b-112">C# language specification</span></span>

<span data-ttu-id="5801b-113">자세한 내용은 [C# 언어 사양](~/_csharplang/spec/introduction.md)의 [익명 함수 식](~/_csharplang/spec/expressions.md#anonymous-function-expressions) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5801b-113">For more information, see the [Anonymous function expressions](~/_csharplang/spec/expressions.md#anonymous-function-expressions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="5801b-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5801b-114">See also</span></span>

- [<span data-ttu-id="5801b-115">C# 참조</span><span class="sxs-lookup"><span data-stu-id="5801b-115">C# reference</span></span>](../index.md)
- [<span data-ttu-id="5801b-116">C# 연산자</span><span class="sxs-lookup"><span data-stu-id="5801b-116">C# operators</span></span>](index.md)
- [<span data-ttu-id="5801b-117">=> 연산자</span><span class="sxs-lookup"><span data-stu-id="5801b-117">=> operator</span></span>](lambda-operator.md)
