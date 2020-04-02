---
title: nameof 식 - C# 참조
ms.date: 07/12/2019
f1_keywords:
- nameof_CSharpKeyword
- nameof
helpviewer_keywords:
- nameof expression [C#]
ms.assetid: 33601bf3-cc2c-4496-846d-f9679bccf2a7
ms.openlocfilehash: 5a68161be7bb03122d2a63ccef4365c5853862b2
ms.sourcegitcommit: 2514f4e3655081dcfe1b22470c0c28500f952c42
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/18/2020
ms.locfileid: "79507141"
---
# <a name="nameof-expression-c-reference"></a><span data-ttu-id="ae595-102">nameof 식(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="ae595-102">nameof expression (C# reference)</span></span>

<span data-ttu-id="ae595-103">`nameof` 식은 변수, 형식 또는 멤버의 이름을 문자열 상수로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ae595-103">A `nameof` expression produces the name of a variable, type, or member as the string constant:</span></span>

[!code-csharp-interactive[nameof expression](snippets/NameOfOperator.cs#Examples)]

<span data-ttu-id="ae595-104">이전 예제와 같이 형식 및 네임스페이스의 경우 생성되는 이름은 일반적으로 [정규화된](~/_csharplang/spec/basic-concepts.md#fully-qualified-names) 이름이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="ae595-104">As the preceding example shows, in the case of a type and a namespace, the produced name is usually not [fully qualified](~/_csharplang/spec/basic-concepts.md#fully-qualified-names).</span></span>

<span data-ttu-id="ae595-105">`nameof` 식은 컴파일 시간에 계산되며 런타임에는 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ae595-105">A `nameof` expression is evaluated at compile time and has no effect at run time.</span></span>

<span data-ttu-id="ae595-106">`nameof` 식을 사용하여 인수 검사 코드를 더 쉽게 유지 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae595-106">You can use a `nameof` expression to make the argument-checking code more maintainable:</span></span>

[!code-csharp[nameof and argument check](snippets/NameOfOperator.cs#ExceptionMessage)]

<span data-ttu-id="ae595-107">`nameof` 식은 C# 6 이상에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae595-107">A `nameof` expression is available in C# 6 and later.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="ae595-108">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="ae595-108">C# language specification</span></span>

<span data-ttu-id="ae595-109">자세한 내용은 [C# 언어 사양](~/_csharplang/spec/introduction.md)의 [Nameof 식](~/_csharplang/spec/expressions.md#nameof-expressions) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ae595-109">For more information, see the [Nameof expressions](~/_csharplang/spec/expressions.md#nameof-expressions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="ae595-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ae595-110">See also</span></span>

- [<span data-ttu-id="ae595-111">C# 참조</span><span class="sxs-lookup"><span data-stu-id="ae595-111">C# reference</span></span>](../index.md)
- [<span data-ttu-id="ae595-112">C# 연산자</span><span class="sxs-lookup"><span data-stu-id="ae595-112">C# operators</span></span>](index.md)
