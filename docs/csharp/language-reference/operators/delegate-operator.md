---
description: delegate 연산자 - C# 참조
title: delegate 연산자 - C# 참조
ms.date: 09/25/2020
helpviewer_keywords:
- delegate [C#]
- anonymous method [C#]
ms.openlocfilehash: db2bf673db12e4a10741a26112820726a4b8aaee
ms.sourcegitcommit: c04535ad05e374fb269fcfc6509217755fbc0d54
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/25/2020
ms.locfileid: "91247659"
---
# <a name="delegate-operator-c-reference"></a><span data-ttu-id="f62d2-103">delegate 연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="f62d2-103">delegate operator (C# reference)</span></span>

<span data-ttu-id="f62d2-104">`delegate` 연산자는 대리자 형식으로 변환될 수 있는 무명 메서드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f62d2-104">The `delegate` operator creates an anonymous method that can be converted to a delegate type:</span></span>

[!code-csharp-interactive[anonymous method](snippets/shared/DelegateOperator.cs#AnonymousMethod)]

> [!NOTE]
> <span data-ttu-id="f62d2-105">C# 3으로 시작하는 람다 식은 익명 함수를 만드는 더 간결하고 이해하기 쉬운 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f62d2-105">Beginning with C# 3, lambda expressions provide a more concise and expressive way to create an anonymous function.</span></span> <span data-ttu-id="f62d2-106">[=> 연산자](lambda-operator.md)를 사용하여 람다 식을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="f62d2-106">Use the [=> operator](lambda-operator.md) to construct a lambda expression:</span></span>
>
> [!code-csharp-interactive[lambda expression](snippets/shared/DelegateOperator.cs#Lambda)]
>
> <span data-ttu-id="f62d2-107">람다 식의 기능(예: 외부 변수 캡처)에 대한 자세한 내용은 [람다 식](lambda-expressions.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f62d2-107">For more information about features of lambda expressions, for example, capturing outer variables, see [Lambda expressions](lambda-expressions.md).</span></span>

<span data-ttu-id="f62d2-108">`delegate` 연산자를 사용하는 경우 매개 변수 목록을 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f62d2-108">When you use the `delegate` operator, you might omit the parameter list.</span></span> <span data-ttu-id="f62d2-109">이렇게 하면 다음 예제와 같이 매개 변수 목록을 사용하여 생성된 무명 메서드를 대리자 형식으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f62d2-109">If you do that, the created anonymous method can be converted to a delegate type with any list of  parameters, as the following example shows:</span></span>

[!code-csharp-interactive[no parameter list](snippets/shared/DelegateOperator.cs#WithoutParameterList)]

<span data-ttu-id="f62d2-110">이 기능은 람다 식에서 지원되지 않는 무명 메서드의 유일한 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="f62d2-110">That's the only functionality of anonymous methods that is not supported by lambda expressions.</span></span> <span data-ttu-id="f62d2-111">다른 모든 경우 인라인 코드를 작성하는 데 람다 식이 선호됩니다.</span><span class="sxs-lookup"><span data-stu-id="f62d2-111">In all other cases, a lambda expression is a preferred way to write inline code.</span></span>

<span data-ttu-id="f62d2-112">C# 9.0부터 [무시 항목](../../discards.md)을 사용하여 무명 메서드에서 사용하지 않는 입력 매개 변수를 두 개 이상 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f62d2-112">Beginning with C# 9.0, you can use [discards](../../discards.md) to specify two or more input parameters of an anonymous method that aren't used by the method:</span></span>

:::code language="csharp" source="snippets/shared/DelegateOperator.cs" id="SnippetDiscards" :::

<span data-ttu-id="f62d2-113">이전 버전과의 호환성을 위해, 단일 매개 변수만 `_`로 명명된 경우 `_`가 무명 메서드 내에서 해당 매개 변수의 이름으로 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="f62d2-113">For backwards compatibility, if only a single parameter is named `_`, `_` is treated as the name of that parameter within an anonymous method.</span></span>

<span data-ttu-id="f62d2-114">또한 C# 9.0부터 무명 메서드 선언에 `static` 한정자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f62d2-114">Also beginning with C# 9.0, you can use the `static` modifier at the declaration of an anonymous method:</span></span>

:::code language="csharp" source="snippets/shared/DelegateOperator.cs" id="SnippetStatic" :::

<span data-ttu-id="f62d2-115">정적 무명 메서드는 바깥쪽 범위에서 지역 변수 또는 인스턴스 상태를 캡처할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f62d2-115">A static anonymous method can't capture local variables or instance state from enclosing scopes.</span></span>

<span data-ttu-id="f62d2-116">`delegate` 키워드를 사용하여 [대리자 형식](../builtin-types/reference-types.md#the-delegate-type)을 선언할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f62d2-116">You also use the `delegate` keyword to declare a [delegate type](../builtin-types/reference-types.md#the-delegate-type).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="f62d2-117">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="f62d2-117">C# language specification</span></span>

<span data-ttu-id="f62d2-118">자세한 내용은 [C# 언어 사양](~/_csharplang/spec/introduction.md)의 [익명 함수 식](~/_csharplang/spec/expressions.md#anonymous-function-expressions) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f62d2-118">For more information, see the [Anonymous function expressions](~/_csharplang/spec/expressions.md#anonymous-function-expressions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f62d2-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f62d2-119">See also</span></span>

- [<span data-ttu-id="f62d2-120">C# 참조</span><span class="sxs-lookup"><span data-stu-id="f62d2-120">C# reference</span></span>](../index.md)
- [<span data-ttu-id="f62d2-121">C# 연산자 및 식</span><span class="sxs-lookup"><span data-stu-id="f62d2-121">C# operators and expressions</span></span>](index.md)
- [<span data-ttu-id="f62d2-122">=> 연산자</span><span class="sxs-lookup"><span data-stu-id="f62d2-122">=> operator</span></span>](lambda-operator.md)
