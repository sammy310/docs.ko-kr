---
title: nameof 식 - C# 참조
ms.date: 04/23/2020
f1_keywords:
- nameof_CSharpKeyword
- nameof
helpviewer_keywords:
- nameof expression [C#]
ms.assetid: 33601bf3-cc2c-4496-846d-f9679bccf2a7
ms.openlocfilehash: b00c5f6f97d27290fb3773dcbb422bf9fb4c425b
ms.sourcegitcommit: ef50c99928183a0bba75e07b9f22895cd4c480f8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2020
ms.locfileid: "87916783"
---
# <a name="nameof-expression-c-reference"></a><span data-ttu-id="4da14-102">nameof 식(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="4da14-102">nameof expression (C# reference)</span></span>

<span data-ttu-id="4da14-103">`nameof` 식은 변수, 형식 또는 멤버의 이름을 문자열 상수로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="4da14-103">A `nameof` expression produces the name of a variable, type, or member as the string constant:</span></span>

[!code-csharp-interactive[nameof expression](snippets/shared/NameOfOperator.cs#Examples)]

<span data-ttu-id="4da14-104">이전 예제와 같이 형식 및 네임스페이스의 경우 생성되는 이름은 일반적으로 [정규화된](~/_csharplang/spec/basic-concepts.md#fully-qualified-names) 이름이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="4da14-104">As the preceding example shows, in the case of a type and a namespace, the produced name is usually not [fully qualified](~/_csharplang/spec/basic-concepts.md#fully-qualified-names).</span></span>

<span data-ttu-id="4da14-105">[verbatim 식별자](../tokens/verbatim.md)의 경우 다음 예제와 같이 `@` 문자는 이름의 일부가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="4da14-105">In the case of [verbatim identifiers](../tokens/verbatim.md), the `@` character is not the part of a name, as the following example shows:</span></span>

[!code-csharp-interactive[nameof verbatim](snippets/shared/NameOfOperator.cs#Verbatim)]

<span data-ttu-id="4da14-106">`nameof` 식은 컴파일 시간에 계산되며 런타임에는 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4da14-106">A `nameof` expression is evaluated at compile time and has no effect at run time.</span></span>

<span data-ttu-id="4da14-107">`nameof` 식을 사용하여 인수 검사 코드를 더 쉽게 유지 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4da14-107">You can use a `nameof` expression to make the argument-checking code more maintainable:</span></span>

[!code-csharp[nameof and argument check](snippets/shared/NameOfOperator.cs#ExceptionMessage)]

<span data-ttu-id="4da14-108">`nameof` 식은 C# 6 이상에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4da14-108">A `nameof` expression is available in C# 6 and later.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="4da14-109">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="4da14-109">C# language specification</span></span>

<span data-ttu-id="4da14-110">자세한 내용은 [C# 언어 사양](~/_csharplang/spec/introduction.md)의 [Nameof 식](~/_csharplang/spec/expressions.md#nameof-expressions) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4da14-110">For more information, see the [Nameof expressions](~/_csharplang/spec/expressions.md#nameof-expressions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="4da14-111">참조</span><span class="sxs-lookup"><span data-stu-id="4da14-111">See also</span></span>

- [<span data-ttu-id="4da14-112">C# 참조</span><span class="sxs-lookup"><span data-stu-id="4da14-112">C# reference</span></span>](../index.md)
- [<span data-ttu-id="4da14-113">C# 연산자 및 식</span><span class="sxs-lookup"><span data-stu-id="4da14-113">C# operators and expressions</span></span>](index.md)
